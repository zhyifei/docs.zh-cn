---
title: 为 WCF 开发人员创建 gRPC 客户端库 - gRPC
description: 讨论 gRPC 服务的共享客户端库/包。
ms.date: 09/02/2019
ms.openlocfilehash: bb58cb3cda4b0cbb3a5d34129961349bcb0093e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401771"
---
# <a name="create-grpc-client-libraries"></a>创建 gRPC 客户端库

不需要为 gRPC 应用程序分发客户端库。 您可以在组织内创建文件共享`.proto`库，其他团队可以使用这些文件在他们自己的项目中生成客户端代码。 但是，如果您有一个私有的 NuGet 存储库，并且许多其他团队正在使用 .NET Core，则可以创建和发布客户端 NuGet 包，作为服务项目的一部分。 这是分享和推广服务的好方法。

分发客户端库的一个优点是，您可以使用有用的"方便"方法和属性增强生成的 gRPC 和 Protobuf 类。 在客户端代码中，如在服务器中，所有类都声明为`partial`，因此您可以扩展它们，而无需编辑生成的代码。 这意味着可以轻松地将构造函数、方法和计算属性添加到基本类型。

> [!CAUTION]
> 不应使用自定义代码来提供基本功能。 您不希望将该基本功能限制为使用共享库的 .NET 团队，而不是将其提供给使用其他语言或平台（如 Python 或 Java）的团队。

确保尽可能多的团队可以访问您的 gRPC 服务。 最好的方法是共享`.proto`文件，以便开发人员可以生成自己的客户端。 在多平台环境中尤其如此，其中不同的团队经常使用不同的编程语言和框架，或者 API 是外部可访问的。

## <a name="useful-extensions"></a>有用的扩展

.NET 中有两个常用接口用于处理对象流：<xref:System.Collections.Generic.IEnumerable%601>和<xref:System.IObservable%601>。 从 .NET Core 3.0 和 C# 8.0<xref:System.Collections.Generic.IAsyncEnumerable%601>开始，有一个用于异步处理`await foreach`流的接口，以及一个用于使用该接口的语法。 本节介绍将这些接口应用于 gRPC 流的可重用代码。

使用 .NET Core gRPC 客户端库时，有`ReadAllAsync`一种扩展`IAsyncStreamReader<T>`方法用于创建`IAsyncEnumerable<T>`接口。 对于使用反应式编程的开发人员，创建接口的`IObservable<T>`等效扩展方法可能类似于下一节中的示例。

### <a name="iobservable"></a>可观察

接口`IObservable<T>`是 中的"反应"反对。 `IEnumerable<T>` 被动方法允许流将项目推送到订阅服务器，而不是从流中提取项目。 这与 gRPC 流非常相似，并且很容易围绕`IObservable<T>``IAsyncStreamReader<T>`接口包装接口。

此代码比`IAsyncEnumerable<T>`代码长，因为 C# 没有内置支持使用可观察器。 您必须手动创建实现类。 但它是一个泛型类，因此单个实现适用于所有类型。

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
> 此可观察的实现只允许`Subscribe`调用一次该方法，因为有多个订阅者尝试从流中读取将导致混乱。 有运算符，如`Replay` [System.Reactive.Linq，](https://www.nuget.org/packages/System.Reactive.Linq)它们支持可观察的缓冲和可重复共享，这些可与此实现一起使用。

类`GrpcStreamSubscription`处理 的`IAsyncStreamReader`枚举：

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

现在只需要一个简单的扩展方法，从流读取器创建可观察的。

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

## <a name="summary"></a>总结

和`IAsyncEnumerable``IObservable`模型都是支持良好且记录良好的处理 .NET 中异步数据流的方法。 gRPC 流很好地映射到这两种范例，提供与 .NET Core 以及被动和异步编程样式的紧密集成。

>[!div class="step-by-step"]
>[上一个](streaming-versus-repeated.md)
>[下一个](security.md)
