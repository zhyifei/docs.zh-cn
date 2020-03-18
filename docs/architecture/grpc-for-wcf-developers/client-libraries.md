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
# <a name="create-grpc-client-libraries"></a><span data-ttu-id="06939-103">创建 gRPC 客户端库</span><span class="sxs-lookup"><span data-stu-id="06939-103">Create gRPC client libraries</span></span>

<span data-ttu-id="06939-104">不需要为 gRPC 应用程序分发客户端库。</span><span class="sxs-lookup"><span data-stu-id="06939-104">It isn't necessary to distribute client libraries for a gRPC application.</span></span> <span data-ttu-id="06939-105">您可以在组织内创建文件共享`.proto`库，其他团队可以使用这些文件在他们自己的项目中生成客户端代码。</span><span class="sxs-lookup"><span data-stu-id="06939-105">You can create a shared library of `.proto` files within your organization, and other teams can use those files to generate client code in their own projects.</span></span> <span data-ttu-id="06939-106">但是，如果您有一个私有的 NuGet 存储库，并且许多其他团队正在使用 .NET Core，则可以创建和发布客户端 NuGet 包，作为服务项目的一部分。</span><span class="sxs-lookup"><span data-stu-id="06939-106">But if you have a private NuGet repository and many other teams are using .NET Core, you can create and publish client NuGet packages as part of your service project.</span></span> <span data-ttu-id="06939-107">这是分享和推广服务的好方法。</span><span class="sxs-lookup"><span data-stu-id="06939-107">This can be a good way of sharing and promoting your service.</span></span>

<span data-ttu-id="06939-108">分发客户端库的一个优点是，您可以使用有用的"方便"方法和属性增强生成的 gRPC 和 Protobuf 类。</span><span class="sxs-lookup"><span data-stu-id="06939-108">One advantage of distributing a client library is that you can enhance the generated gRPC and Protobuf classes with helpful "convenience" methods and properties.</span></span> <span data-ttu-id="06939-109">在客户端代码中，如在服务器中，所有类都声明为`partial`，因此您可以扩展它们，而无需编辑生成的代码。</span><span class="sxs-lookup"><span data-stu-id="06939-109">In the client code, as in the server, all the classes are declared as `partial`, so you can extend them without editing the generated code.</span></span> <span data-ttu-id="06939-110">这意味着可以轻松地将构造函数、方法和计算属性添加到基本类型。</span><span class="sxs-lookup"><span data-stu-id="06939-110">This means it's easy to add constructors, methods, and calculated properties to the basic types.</span></span>

> [!CAUTION]
> <span data-ttu-id="06939-111">不应使用自定义代码来提供基本功能。</span><span class="sxs-lookup"><span data-stu-id="06939-111">You shouldn't use custom code to provide essential functionality.</span></span> <span data-ttu-id="06939-112">您不希望将该基本功能限制为使用共享库的 .NET 团队，而不是将其提供给使用其他语言或平台（如 Python 或 Java）的团队。</span><span class="sxs-lookup"><span data-stu-id="06939-112">You don't want to restrict that essential functionality to .NET teams that use the shared library, and not provide it to teams that use other languages or platforms, such as Python or Java.</span></span>

<span data-ttu-id="06939-113">确保尽可能多的团队可以访问您的 gRPC 服务。</span><span class="sxs-lookup"><span data-stu-id="06939-113">Ensure that as many teams as possible can access your gRPC service.</span></span> <span data-ttu-id="06939-114">最好的方法是共享`.proto`文件，以便开发人员可以生成自己的客户端。</span><span class="sxs-lookup"><span data-stu-id="06939-114">The best way to do this is to share `.proto` files so developers can generate their own clients.</span></span> <span data-ttu-id="06939-115">在多平台环境中尤其如此，其中不同的团队经常使用不同的编程语言和框架，或者 API 是外部可访问的。</span><span class="sxs-lookup"><span data-stu-id="06939-115">This is particularly true in a multi-platform environment, where different teams frequently use different programming languages and frameworks, or where your API is externally accessible.</span></span>

## <a name="useful-extensions"></a><span data-ttu-id="06939-116">有用的扩展</span><span class="sxs-lookup"><span data-stu-id="06939-116">Useful extensions</span></span>

<span data-ttu-id="06939-117">.NET 中有两个常用接口用于处理对象流：<xref:System.Collections.Generic.IEnumerable%601>和<xref:System.IObservable%601>。</span><span class="sxs-lookup"><span data-stu-id="06939-117">There are two commonly used interfaces in .NET for dealing with streams of objects: <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IObservable%601>.</span></span> <span data-ttu-id="06939-118">从 .NET Core 3.0 和 C# 8.0<xref:System.Collections.Generic.IAsyncEnumerable%601>开始，有一个用于异步处理`await foreach`流的接口，以及一个用于使用该接口的语法。</span><span class="sxs-lookup"><span data-stu-id="06939-118">Starting with .NET Core 3.0 and C# 8.0, there's an <xref:System.Collections.Generic.IAsyncEnumerable%601> interface for processing streams asynchronously, and an `await foreach` syntax for using the interface.</span></span> <span data-ttu-id="06939-119">本节介绍将这些接口应用于 gRPC 流的可重用代码。</span><span class="sxs-lookup"><span data-stu-id="06939-119">This section presents reusable code for applying these interfaces to gRPC streams.</span></span>

<span data-ttu-id="06939-120">使用 .NET Core gRPC 客户端库时，有`ReadAllAsync`一种扩展`IAsyncStreamReader<T>`方法用于创建`IAsyncEnumerable<T>`接口。</span><span class="sxs-lookup"><span data-stu-id="06939-120">With the .NET Core gRPC client libraries, there's a `ReadAllAsync` extension method for `IAsyncStreamReader<T>` that creates an `IAsyncEnumerable<T>` interface.</span></span> <span data-ttu-id="06939-121">对于使用反应式编程的开发人员，创建接口的`IObservable<T>`等效扩展方法可能类似于下一节中的示例。</span><span class="sxs-lookup"><span data-stu-id="06939-121">For developers using reactive programming, an equivalent extension method to create an `IObservable<T>` interface might look like the example in the following section.</span></span>

### <a name="iobservable"></a><span data-ttu-id="06939-122">可观察</span><span class="sxs-lookup"><span data-stu-id="06939-122">IObservable</span></span>

<span data-ttu-id="06939-123">接口`IObservable<T>`是 中的"反应"反对。 `IEnumerable<T>`</span><span class="sxs-lookup"><span data-stu-id="06939-123">The `IObservable<T>` interface is the "reactive" inverse of `IEnumerable<T>`.</span></span> <span data-ttu-id="06939-124">被动方法允许流将项目推送到订阅服务器，而不是从流中提取项目。</span><span class="sxs-lookup"><span data-stu-id="06939-124">Rather than pulling items from a stream, the reactive approach lets the stream push items to a subscriber.</span></span> <span data-ttu-id="06939-125">这与 gRPC 流非常相似，并且很容易围绕`IObservable<T>``IAsyncStreamReader<T>`接口包装接口。</span><span class="sxs-lookup"><span data-stu-id="06939-125">This is very similar to gRPC streams, and it's easy to wrap an `IObservable<T>` interface around an `IAsyncStreamReader<T>` interface.</span></span>

<span data-ttu-id="06939-126">此代码比`IAsyncEnumerable<T>`代码长，因为 C# 没有内置支持使用可观察器。</span><span class="sxs-lookup"><span data-stu-id="06939-126">This code is longer than the `IAsyncEnumerable<T>` code, because C# doesn't have built-in support for working with observables.</span></span> <span data-ttu-id="06939-127">您必须手动创建实现类。</span><span class="sxs-lookup"><span data-stu-id="06939-127">You have to create the implementation class manually.</span></span> <span data-ttu-id="06939-128">但它是一个泛型类，因此单个实现适用于所有类型。</span><span class="sxs-lookup"><span data-stu-id="06939-128">It's a generic class, though, so a single implementation works across all types.</span></span>

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
> <span data-ttu-id="06939-129">此可观察的实现只允许`Subscribe`调用一次该方法，因为有多个订阅者尝试从流中读取将导致混乱。</span><span class="sxs-lookup"><span data-stu-id="06939-129">This observable implementation allows the `Subscribe` method to be called only once, because having multiple subscribers trying to read from the stream would result in chaos.</span></span> <span data-ttu-id="06939-130">有运算符，如`Replay` [System.Reactive.Linq，](https://www.nuget.org/packages/System.Reactive.Linq)它们支持可观察的缓冲和可重复共享，这些可与此实现一起使用。</span><span class="sxs-lookup"><span data-stu-id="06939-130">There are operators, such as `Replay` in the [System.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq), that enable buffering and repeatable sharing of observables, which can be used with this implementation.</span></span>

<span data-ttu-id="06939-131">类`GrpcStreamSubscription`处理 的`IAsyncStreamReader`枚举：</span><span class="sxs-lookup"><span data-stu-id="06939-131">The `GrpcStreamSubscription` class handles the enumeration of the `IAsyncStreamReader`:</span></span>

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

<span data-ttu-id="06939-132">现在只需要一个简单的扩展方法，从流读取器创建可观察的。</span><span class="sxs-lookup"><span data-stu-id="06939-132">All that is required now is a simple extension method to create the observable from the stream reader.</span></span>

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

## <a name="summary"></a><span data-ttu-id="06939-133">总结</span><span class="sxs-lookup"><span data-stu-id="06939-133">Summary</span></span>

<span data-ttu-id="06939-134">和`IAsyncEnumerable``IObservable`模型都是支持良好且记录良好的处理 .NET 中异步数据流的方法。</span><span class="sxs-lookup"><span data-stu-id="06939-134">The `IAsyncEnumerable` and `IObservable` models are both well-supported and well-documented ways of dealing with asynchronous streams of data in .NET.</span></span> <span data-ttu-id="06939-135">gRPC 流很好地映射到这两种范例，提供与 .NET Core 以及被动和异步编程样式的紧密集成。</span><span class="sxs-lookup"><span data-stu-id="06939-135">gRPC streams map well to both paradigms, offering close integration with .NET Core, and reactive and asynchronous programming styles.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="06939-136">[上一个](streaming-versus-repeated.md)
>[下一个](security.md)</span><span class="sxs-lookup"><span data-stu-id="06939-136">[Previous](streaming-versus-repeated.md)
[Next](security.md)</span></span>
