---
title: 创建 gRPC 客户端库-WCF 开发人员 gRPC
description: 针对 gRPC services 的共享客户端库/包的讨论。
ms.date: 09/02/2019
ms.openlocfilehash: 2135fe8b24a2311a31cb2bed191d290b1112bc66
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967877"
---
# <a name="create-grpc-client-libraries"></a>创建 gRPC 客户端库

不需要为 gRPC 应用程序分发客户端库。 你可以在组织中创建 `.proto` 文件的共享库，并且其他团队可以使用这些文件在其自己的项目中生成客户端代码。 但是，如果你有一个专用 NuGet 存储库，而其他许多团队正在使用 .NET Core，则在你的服务项目中创建并发布客户端 NuGet 包可能是共享和升级服务的好方法。

分发客户端库的一个优点是，您可以使用有用的 "方便性" 方法和属性来增强生成的 gRPC 和 Protobuf 类。 在客户端代码中，与在服务器中一样，所有类都声明为 `partial`，因此你可以在不编辑生成的代码的情况下扩展它们。 这意味着可以轻松地将构造函数、方法、计算属性等添加到基本类型。

> [!CAUTION]
> **不**应使用自定义代码来提供基本功能，因为这意味着使用共享库将功能限制为 .net 团队，而不是使用其他语言或平台（如 Python 或 Java）的团队。

在不同团队频繁使用不同编程语言和框架的多平台环境中，或者 API 可从外部访问的位置，只需共享 `.proto` 文件，开发人员便可生成自己的客户端，这是确保尽可能多的团队可以访问 gRPC 服务的最佳方式。

## <a name="useful-extensions"></a>有用的扩展

.NET 中有两个用于处理对象流的常用接口： <xref:System.Collections.Generic.IEnumerable%601> 和 <xref:System.IObservable%601>。 从 .NET Core 3.0 和C# 8.0 开始，有一个 <xref:System.Collections.Generic.IAsyncEnumerable%601> 接口，用于以异步方式处理流，以及使用接口 `await foreach` 语法。 本部分提供可重用的代码，用于将这些接口应用到 gRPC 流。

使用 .NET Core gRPC 客户端库，`IAsyncStreamReader<T>` 创建 `IAsyncEnumerable<T>``ReadAllAsync` 扩展方法。 对于使用反应性编程的开发人员，创建 `IObservable<T>` 的等效扩展方法可能如下所示。

### <a name="iobservable"></a>IObservable

`IObservable<T>` 接口是 `IEnumerable<T>`的反向 "。 反应方法不会从流中提取项，而是允许流将项推送到订阅服务器。 这非常类似于 gRPC 流，可轻松地在 `IAsyncStreamReader<T>`周围环绕 `IObservable<T>`。

此代码的长度超过了 `IAsyncEnumerable<T>` 代码， C#因为没有内置的可观察量支持，因此必须手动创建实现类。 但它是一个泛型类，因此单个实现可跨所有类型工作。

```csharp
using System;
using System.Diagnostics;
using System.Threading;
using System.Threading.Tasks;

namespace Grpc.Core
{
    public class GrpcStreamObservable<T> : IObservable<T>
    {
        private readonly IAsyncStreamReader<T> _reader;
        private readonly CancellationToken _token;
        private int _used;

        public Observable(IAsyncStreamReader<T> reader, CancellationToken token = default)
        {
            _reader = reader;
            _token = token;
            _used = 0;
        }

        public IDisposable Subscribe(IObserver<T> observer) =>
            Interlocked.Exchange(ref _used, 1) == 0
                ? new GrpcStreamSubscription(_reader, observer, _token)
                : throw new InvalidOperationException("Subscribe can only be called once.");

    }
}
```

> [!IMPORTANT]
> 此可观察实现仅允许调用一次 `Subscribe` 方法，因为尝试从流中读取多个订阅服务器会导致混乱。 在可观察量中有一些运算符（如 `Replay`）可实现缓冲和可重复的共享，这可与此实现一起[使用。](https://www.nuget.org/packages/System.Reactive.Linq)

`GrpcStreamSubscription` 类处理 `IAsyncStreamReader`的枚举。

```csharp
public class GrpcStreamSubscription : IDisposable
{
    private readonly Task _task;
    private readonly CancellationTokenSource _tokenSource;
    private bool _completed;

    public Subscription(IAsyncStreamReader<T> reader, IObserver<T> observer, CancellationToken token)
    {
        Debug.Assert(reader != null);
        Debug.Assert(observer != null);
        _tokenSource = new CancellationTokenSource();
        token.Register(_tokenSource.Cancel);
        _task = Run(reader, observer, _tokenSource.Token);
    }

    private async Task Run(IAsyncStreamReader<T> reader, IObserver<T> observer, CancellationToken token)
    {
        while (!token.IsCancellationRequested)
        {
            try
            {
                if (!await reader.MoveNext(token)) break;
            }
            catch (RpcException e) when (e.StatusCode == Grpc.Core.StatusCode.NotFound)
            {
                break;
            }
            catch (OperationCanceledException)
            {
                break;
            }
            catch (Exception e)
            {
                observer.OnError(e);
                _completed = true;
                return;
            }

            observer.OnNext(reader.Current);
        }

        _completed = true;
        observer.OnCompleted();
    }

    public void Dispose()
    {
        if (!_completed && !_tokenSource.IsCancellationRequested)
        {
            _tokenSource.Cancel();
        }

        _tokenSource.Dispose();
        _task.Dispose();
    }

}
```

现在只需要一个简单的扩展方法，用于从流读取器创建可观察的。

```csharp
using System;
using System.Diagnostics;
using System.Threading;
using System.Threading.Tasks;

namespace Grpc.Core
{
    public static class AsyncStreamReaderObservableExtensions
    {
        public static IObservable<T> AsObservable<T>(this IAsyncStreamReader<T> reader) =>
            new GrpcStreamObservable<T>(reader);
    }
}
```

## <a name="summary"></a>摘要

`IAsyncEnumerable` 和 `IObservable` 模型都是非常受支持的，并通过记录良好的方式处理 .NET 中的异步数据流。 gRPC 流可以很好地映射到这两个范例，提供与新式 .NET Core 框架和反应/异步编程风格的紧密集成。

>[!div class="step-by-step"]
>[上一页](streaming-versus-repeated.md)
>[下一页](security.md)
