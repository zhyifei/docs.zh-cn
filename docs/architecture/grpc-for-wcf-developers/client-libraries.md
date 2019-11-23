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
# <a name="create-grpc-client-libraries"></a><span data-ttu-id="aa88a-103">创建 gRPC 客户端库</span><span class="sxs-lookup"><span data-stu-id="aa88a-103">Create gRPC client libraries</span></span>

<span data-ttu-id="aa88a-104">不需要为 gRPC 应用程序分发客户端库。</span><span class="sxs-lookup"><span data-stu-id="aa88a-104">It isn't necessary to distribute client libraries for a gRPC application.</span></span> <span data-ttu-id="aa88a-105">你可以在组织中创建 `.proto` 文件的共享库，并且其他团队可以使用这些文件在其自己的项目中生成客户端代码。</span><span class="sxs-lookup"><span data-stu-id="aa88a-105">You can create a shared library of `.proto` files within your organization, and other teams can use those files to generate client code in their own projects.</span></span> <span data-ttu-id="aa88a-106">但是，如果你有一个专用 NuGet 存储库，而其他许多团队正在使用 .NET Core，则在你的服务项目中创建并发布客户端 NuGet 包可能是共享和升级服务的好方法。</span><span class="sxs-lookup"><span data-stu-id="aa88a-106">But if you have a private NuGet repository and many other teams are using .NET Core, creating and publishing client NuGet packages as part of your service project may be a good way of sharing and promoting your service.</span></span>

<span data-ttu-id="aa88a-107">分发客户端库的一个优点是，您可以使用有用的 "方便性" 方法和属性来增强生成的 gRPC 和 Protobuf 类。</span><span class="sxs-lookup"><span data-stu-id="aa88a-107">One advantage of distributing a client library is that you can enhance the generated gRPC and Protobuf classes with helpful "convenience" methods and properties.</span></span> <span data-ttu-id="aa88a-108">在客户端代码中，与在服务器中一样，所有类都声明为 `partial`，因此你可以在不编辑生成的代码的情况下扩展它们。</span><span class="sxs-lookup"><span data-stu-id="aa88a-108">In the client code, as in the server, all the classes are declared as `partial` so you can extend them without editing the generated code.</span></span> <span data-ttu-id="aa88a-109">这意味着可以轻松地将构造函数、方法、计算属性等添加到基本类型。</span><span class="sxs-lookup"><span data-stu-id="aa88a-109">This means it's easy to add constructors, methods, calculated properties, and more to the basic types.</span></span>

> [!CAUTION]
> <span data-ttu-id="aa88a-110">**不**应使用自定义代码来提供基本功能，因为这意味着使用共享库将功能限制为 .net 团队，而不是使用其他语言或平台（如 Python 或 Java）的团队。</span><span class="sxs-lookup"><span data-stu-id="aa88a-110">You should **not** use custom code to provide essential functionality, as this would mean that functionality would be restricted to .NET teams using the shared library, and not to teams using other languages or platforms such as Python or Java.</span></span>

<span data-ttu-id="aa88a-111">在不同团队频繁使用不同编程语言和框架的多平台环境中，或者 API 可从外部访问的位置，只需共享 `.proto` 文件，开发人员便可生成自己的客户端，这是确保尽可能多的团队可以访问 gRPC 服务的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="aa88a-111">In a multi-platform environment where different teams frequently use different programming languages and frameworks, or where your API is externally accessible, simply sharing `.proto` files so developers can generate their own clients is the best way to ensure as many teams as possible can access your gRPC service.</span></span>

## <a name="useful-extensions"></a><span data-ttu-id="aa88a-112">有用的扩展</span><span class="sxs-lookup"><span data-stu-id="aa88a-112">Useful extensions</span></span>

<span data-ttu-id="aa88a-113">.NET 中有两个用于处理对象流的常用接口： <xref:System.Collections.Generic.IEnumerable%601> 和 <xref:System.IObservable%601>。</span><span class="sxs-lookup"><span data-stu-id="aa88a-113">There are two commonly used interfaces in .NET for dealing with streams of objects: <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IObservable%601>.</span></span> <span data-ttu-id="aa88a-114">从 .NET Core 3.0 和C# 8.0 开始，有一个 <xref:System.Collections.Generic.IAsyncEnumerable%601> 接口，用于以异步方式处理流，以及使用接口 `await foreach` 语法。</span><span class="sxs-lookup"><span data-stu-id="aa88a-114">Starting with .NET Core 3.0 and C# 8.0, there's an <xref:System.Collections.Generic.IAsyncEnumerable%601> interface for processing streams asynchronously, and an `await foreach` syntax for using the interface.</span></span> <span data-ttu-id="aa88a-115">本部分提供可重用的代码，用于将这些接口应用到 gRPC 流。</span><span class="sxs-lookup"><span data-stu-id="aa88a-115">This section presents reusable code for applying these interfaces to gRPC streams.</span></span>

<span data-ttu-id="aa88a-116">使用 .NET Core gRPC 客户端库，`IAsyncStreamReader<T>` 创建 `IAsyncEnumerable<T>``ReadAllAsync` 扩展方法。</span><span class="sxs-lookup"><span data-stu-id="aa88a-116">With the .NET Core gRPC client libraries, there's a `ReadAllAsync` extension method for `IAsyncStreamReader<T>` that creates an `IAsyncEnumerable<T>`.</span></span> <span data-ttu-id="aa88a-117">对于使用反应性编程的开发人员，创建 `IObservable<T>` 的等效扩展方法可能如下所示。</span><span class="sxs-lookup"><span data-stu-id="aa88a-117">For developers using reactive programming, an equivalent extension method to create an `IObservable<T>` might look like this.</span></span>

### <a name="iobservable"></a><span data-ttu-id="aa88a-118">IObservable</span><span class="sxs-lookup"><span data-stu-id="aa88a-118">IObservable</span></span>

<span data-ttu-id="aa88a-119">`IObservable<T>` 接口是 `IEnumerable<T>`的反向 "。</span><span class="sxs-lookup"><span data-stu-id="aa88a-119">The `IObservable<T>` interface is the "reactive" inverse of `IEnumerable<T>`.</span></span> <span data-ttu-id="aa88a-120">反应方法不会从流中提取项，而是允许流将项推送到订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="aa88a-120">Rather than pulling items from a stream, the reactive approach lets the stream push items to a subscriber.</span></span> <span data-ttu-id="aa88a-121">这非常类似于 gRPC 流，可轻松地在 `IAsyncStreamReader<T>`周围环绕 `IObservable<T>`。</span><span class="sxs-lookup"><span data-stu-id="aa88a-121">This is very similar to gRPC streams, and it's easy to wrap an `IObservable<T>` around an `IAsyncStreamReader<T>`.</span></span>

<span data-ttu-id="aa88a-122">此代码的长度超过了 `IAsyncEnumerable<T>` 代码， C#因为没有内置的可观察量支持，因此必须手动创建实现类。</span><span class="sxs-lookup"><span data-stu-id="aa88a-122">This code is longer than the `IAsyncEnumerable<T>` code because C# doesn't have built-in support for working with observables, so the implementation class has to be created manually.</span></span> <span data-ttu-id="aa88a-123">但它是一个泛型类，因此单个实现可跨所有类型工作。</span><span class="sxs-lookup"><span data-stu-id="aa88a-123">It's a generic class, though, so a single implementation will work across all types.</span></span>

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
> <span data-ttu-id="aa88a-124">此可观察实现仅允许调用一次 `Subscribe` 方法，因为尝试从流中读取多个订阅服务器会导致混乱。</span><span class="sxs-lookup"><span data-stu-id="aa88a-124">This observable implementation only allows the `Subscribe` method to be called once, as having multiple subscribers trying to read from the stream would result in chaos.</span></span> <span data-ttu-id="aa88a-125">在可观察量中有一些运算符（如 `Replay`）可实现缓冲和可重复的共享，这可与此实现一起[使用。](https://www.nuget.org/packages/System.Reactive.Linq)</span><span class="sxs-lookup"><span data-stu-id="aa88a-125">There are operators such as `Replay` in the [System.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq) that enable buffering and repeatable sharing of observables, which can be used with this implementation.</span></span>

<span data-ttu-id="aa88a-126">`GrpcStreamSubscription` 类处理 `IAsyncStreamReader`的枚举。</span><span class="sxs-lookup"><span data-stu-id="aa88a-126">The `GrpcStreamSubscription` class handles the enumeration of the `IAsyncStreamReader`.</span></span>

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

<span data-ttu-id="aa88a-127">现在只需要一个简单的扩展方法，用于从流读取器创建可观察的。</span><span class="sxs-lookup"><span data-stu-id="aa88a-127">All that is required now is a simple extension method to create the observable from the stream reader.</span></span>

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

## <a name="summary"></a><span data-ttu-id="aa88a-128">摘要</span><span class="sxs-lookup"><span data-stu-id="aa88a-128">Summary</span></span>

<span data-ttu-id="aa88a-129">`IAsyncEnumerable` 和 `IObservable` 模型都是非常受支持的，并通过记录良好的方式处理 .NET 中的异步数据流。</span><span class="sxs-lookup"><span data-stu-id="aa88a-129">The `IAsyncEnumerable` and `IObservable` models are both well-supported and well-documented ways of dealing with asynchronous streams of data in .NET.</span></span> <span data-ttu-id="aa88a-130">gRPC 流可以很好地映射到这两个范例，提供与新式 .NET Core 框架和反应/异步编程风格的紧密集成。</span><span class="sxs-lookup"><span data-stu-id="aa88a-130">gRPC streams map well to both paradigms, offering close integration with the modern .NET Core framework and reactive/asynchronous programming styles.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="aa88a-131">[上一页](streaming-versus-repeated.md)
>[下一页](security.md)</span><span class="sxs-lookup"><span data-stu-id="aa88a-131">[Previous](streaming-versus-repeated.md)
[Next](security.md)</span></span>
