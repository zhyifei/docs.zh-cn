---
title: 使用 HttpClientFactory 实现复原 HTTP 请求
description: 了解如何使用自 .NET Core 2.1 起可用的 HttpClientFactory 来创建 `HttpClient` 实例，使其更轻松地在应用程序中使用。
ms.date: 08/08/2019
ms.openlocfilehash: 6c862171ee6b5eda6f95694878bfa43518a9bdfa
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71039977"
---
# <a name="use-httpclientfactory-to-implement-resilient-http-requests"></a><span data-ttu-id="2feab-103">使用 HttpClientFactory 实现复原 HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="2feab-103">Use HttpClientFactory to implement resilient HTTP requests</span></span>

<span data-ttu-id="2feab-104">自 .NET Core 2.1 起可用的 `HttpClientFactory` 是一个“固执的”工厂，用于创建在应用程序中使用的 <xref:System.Net.Http.HttpClient> 实例。</span><span class="sxs-lookup"><span data-stu-id="2feab-104">`HttpClientFactory` is an opinionated factory, available since .NET Core 2.1, for creating <xref:System.Net.Http.HttpClient> instances to be used in your applications.</span></span>

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a><span data-ttu-id="2feab-105">.NET Core 中提供的原始 HttpClient 类的相关问题</span><span class="sxs-lookup"><span data-stu-id="2feab-105">Issues with the original HttpClient class available in .NET Core</span></span>

<span data-ttu-id="2feab-106">常见的原始 <xref:System.Net.Http.HttpClient> 类非常易于使用，但在某些情况下，许多开发人员却并未正确使用该类。</span><span class="sxs-lookup"><span data-stu-id="2feab-106">The original and well-known <xref:System.Net.Http.HttpClient> class can be easily used, but in some cases, it isn't being properly used by many developers.</span></span>

<span data-ttu-id="2feab-107">第一个问题，当此类可释放时，将其用于 `using` 语句并不是最佳选择，因为即使释放 `HttpClient` 对象，基础套接字也不会立即释放，并可能导致严重问题：“套接字耗尽”。</span><span class="sxs-lookup"><span data-stu-id="2feab-107">As a first issue, while this class is disposable, using it with the `using` statement is not the best choice because even when you dispose `HttpClient` object, the underlying socket is not immediately released and can cause a serious issue named ‘sockets exhaustion’.</span></span> <span data-ttu-id="2feab-108">有关此问题的详细信息，请参阅[你正在以错误方式使用 HttpClient，这将导致软件受损](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/)博客文章。</span><span class="sxs-lookup"><span data-stu-id="2feab-108">For more information about this issue, see [You're using HttpClient wrong and it's destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) blog post.</span></span>

<span data-ttu-id="2feab-109">因此，`HttpClient` 应进行一次实例化并在应用程序的生命周期中重复使用。</span><span class="sxs-lookup"><span data-stu-id="2feab-109">Therefore, `HttpClient` is intended to be instantiated once and reused throughout the life of an application.</span></span> <span data-ttu-id="2feab-110">在负载较重的情况下，实例化每个请求的 `HttpClient` 类将耗尽可用的套接字数。</span><span class="sxs-lookup"><span data-stu-id="2feab-110">Instantiating an `HttpClient` class for every request will exhaust the number of sockets available under heavy loads.</span></span> <span data-ttu-id="2feab-111">该问题会导致 `SocketException` 错误。</span><span class="sxs-lookup"><span data-stu-id="2feab-111">That issue will result in `SocketException` errors.</span></span> <span data-ttu-id="2feab-112">要解决此问题，可能的方法是将 `HttpClient` 对象创建为单一对象或静态对象，请参阅[关于 HttpClient 用法的 Microsoft 文章](../../../csharp/tutorials/console-webapiclient.md)中的说明。</span><span class="sxs-lookup"><span data-stu-id="2feab-112">Possible approaches to solve that problem are based on the creation of the `HttpClient` object as singleton or static, as explained in this [Microsoft article on HttpClient usage](../../../csharp/tutorials/console-webapiclient.md).</span></span>

<span data-ttu-id="2feab-113">但将 `HttpClient` 对象用作单一对象或静态对象时还有一个问题。</span><span class="sxs-lookup"><span data-stu-id="2feab-113">But there’s a second issue with `HttpClient` that you can have when you use it as singleton or static object.</span></span> <span data-ttu-id="2feab-114">在这种情况下，单一实例或静态 `HttpClient` 不考虑 DNS 更改，请参阅 dotnet/corefx GitHub 存储库中的此[问题](https://github.com/dotnet/corefx/issues/11224)中的说明。</span><span class="sxs-lookup"><span data-stu-id="2feab-114">In this case, a singleton or static `HttpClient` doesn't respect DNS changes, as explained in this [issue](https://github.com/dotnet/corefx/issues/11224) at the dotnet/corefx GitHub repository.</span></span> 

<span data-ttu-id="2feab-115">为解决上述问题并使 `HttpClient` 实例管理更轻松，.NET Core 2.1 引入了新的 `HttpClientFactory`，后者可与 Polly 集成来实现弹性 HTTP 调用。</span><span class="sxs-lookup"><span data-stu-id="2feab-115">To address those mentioned issues and make the management of `HttpClient` instances easier, .NET Core 2.1 introduced a new `HttpClientFactory` that can also be used to implement resilient HTTP calls by integrating Polly with it.</span></span>

<span data-ttu-id="2feab-116">[Polly](http://www.thepollyproject.org/) 是瞬态故障处理库，它可以通过流畅且线程安全的方式使用一些预定义的策略，帮助开发人员为其应用程序增加弹性。</span><span class="sxs-lookup"><span data-stu-id="2feab-116">[Polly](http://www.thepollyproject.org/) is transient-fault-handling library that helps developers add resiliency to their applications, by using some pre-defined policies in a fluent and thread-safe manner.</span></span>

## <a name="what-is-httpclientfactory"></a><span data-ttu-id="2feab-117">什么是 HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="2feab-117">What is HttpClientFactory</span></span>

<span data-ttu-id="2feab-118">`HttpClientFactory` 用于：</span><span class="sxs-lookup"><span data-stu-id="2feab-118">`HttpClientFactory` is designed to:</span></span>

- <span data-ttu-id="2feab-119">提供一个中心位置，用于命名和配置逻辑 `HttpClient` 对象。</span><span class="sxs-lookup"><span data-stu-id="2feab-119">Provide a central location for naming and configuring logical `HttpClient` objects.</span></span> <span data-ttu-id="2feab-120">例如，可以配置预配置的客户端（服务代理）以访问特定微服务。</span><span class="sxs-lookup"><span data-stu-id="2feab-120">For example, you may configure a client (Service Agent) that's pre-configured to access a specific microservice.</span></span>
- <span data-ttu-id="2feab-121">通过后列方式整理出站中间件的概念：在 `HttpClient` 中委托处理程序并实现基于 Polly 的中间件以利用 Polly 的复原策略。</span><span class="sxs-lookup"><span data-stu-id="2feab-121">Codify the concept of outgoing middleware via delegating handlers in `HttpClient` and implementing Polly-based middleware to take advantage of Polly’s policies for resiliency.</span></span>
- <span data-ttu-id="2feab-122">`HttpClient` 已经具有委托处理程序的概念，这些委托处理程序可以链接在一起，处理出站 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="2feab-122">`HttpClient` already has the concept of delegating handlers that could be linked together for outgoing HTTP requests.</span></span> <span data-ttu-id="2feab-123">将 HTTP 客户端注册到工厂后，可使用一个 Polly 处理程序将 Polly 策略用于重试、断路器等。</span><span class="sxs-lookup"><span data-stu-id="2feab-123">You register HTTP clients into the factory and you can use a Polly handler to use Polly policies for Retry, CircuitBreakers, and so on.</span></span>
- <span data-ttu-id="2feab-124">管理 `HttpClientMessageHandlers` 的生存期，避免在自行管理 `HttpClient` 生存期时出现上述问题。</span><span class="sxs-lookup"><span data-stu-id="2feab-124">Manage the lifetime of `HttpClientMessageHandlers` to avoid the mentioned problems/issues that can occur when managing `HttpClient` lifetimes yourself.</span></span>

## <a name="multiple-ways-to-use-httpclientfactory"></a><span data-ttu-id="2feab-125">HttpClientFactory 的多种用法</span><span class="sxs-lookup"><span data-stu-id="2feab-125">Multiple ways to use HttpClientFactory</span></span>

<span data-ttu-id="2feab-126">可以通过多种方法在应用程序中使用 `HttpClientFactory`：</span><span class="sxs-lookup"><span data-stu-id="2feab-126">There are several ways that you can use `HttpClientFactory` in your application:</span></span>

- <span data-ttu-id="2feab-127">直接使用 `HttpClientFactory`</span><span class="sxs-lookup"><span data-stu-id="2feab-127">Use `HttpClientFactory` Directly</span></span>
- <span data-ttu-id="2feab-128">使用命名客户端</span><span class="sxs-lookup"><span data-stu-id="2feab-128">Use Named Clients</span></span>
- <span data-ttu-id="2feab-129">使用类型化客户端</span><span class="sxs-lookup"><span data-stu-id="2feab-129">Use Typed Clients</span></span>
- <span data-ttu-id="2feab-130">使用生成的客户端</span><span class="sxs-lookup"><span data-stu-id="2feab-130">Use Generated Clients</span></span>

<span data-ttu-id="2feab-131">为简洁起见，本指南介绍了使用 `HttpClientFactory` 的最结构化的方法，即使用类型化客户端（服务代理模式）。</span><span class="sxs-lookup"><span data-stu-id="2feab-131">For the sake of brevity, this guidance shows the most structured way to use `HttpClientFactory`, which is to use Typed Clients (Service Agent pattern).</span></span> <span data-ttu-id="2feab-132">不过，所有选项均已记录，并且当前在此[涵盖 HttpClientFactory 用法的文章](/aspnet/core/fundamentals/http-requests#consumption-patterns)中列出。</span><span class="sxs-lookup"><span data-stu-id="2feab-132">However, all options are documented and are currently listed in this [article covering HttpClientFactory usage](/aspnet/core/fundamentals/http-requests#consumption-patterns).</span></span>

## <a name="how-to-use-typed-clients-with-httpclientfactory"></a><span data-ttu-id="2feab-133">如何结合使用类型化客户端和 HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="2feab-133">How to use Typed Clients with HttpClientFactory</span></span>

<span data-ttu-id="2feab-134">那么，什么是“类型化客户端”？</span><span class="sxs-lookup"><span data-stu-id="2feab-134">So, what's a "Typed Client"?</span></span> <span data-ttu-id="2feab-135">它只是 `DefaultHttpClientFactory` 注入时配置的 `HttpClient`。</span><span class="sxs-lookup"><span data-stu-id="2feab-135">It's just an `HttpClient` that's configured upon injection by the `DefaultHttpClientFactory`.</span></span>

<span data-ttu-id="2feab-136">下图显示了如何将类型化客户端与 `HttpClientFactory` 结合使用：</span><span class="sxs-lookup"><span data-stu-id="2feab-136">The following diagram shows how Typed Clients are used with `HttpClientFactory`:</span></span>

![ClientService（由控制器或客户端代码使用）使用由注册的 IHttpClientFactory 创建的 HttpClient。](./media/image3.5.png)

<span data-ttu-id="2feab-140">**图 8-4**。</span><span class="sxs-lookup"><span data-stu-id="2feab-140">**Figure 8-4**.</span></span> <span data-ttu-id="2feab-141">将 HttpClientFactory 与类型化客户端类结合使用。</span><span class="sxs-lookup"><span data-stu-id="2feab-141">Using HttpClientFactory with Typed Client classes.</span></span>

<span data-ttu-id="2feab-142">首先，通过安装包含 `IServiceCollection` 的 `AddHttpClient()` 扩展方法的 `Microsoft.Extensions.Http` NuGet 包，在应用程序中设置 `HttpClientFactory`。</span><span class="sxs-lookup"><span data-stu-id="2feab-142">First, setup `HttpClientFactory` in your application by installing the `Microsoft.Extensions.Http` NuGet package that includes the `AddHttpClient()` extension method for `IServiceCollection`.</span></span> <span data-ttu-id="2feab-143">此扩展方法用于注册 `DefaultHttpClientFactory`，后者用作接口 `IHttpClientFactory` 的单一实例。</span><span class="sxs-lookup"><span data-stu-id="2feab-143">This extension method registers the `DefaultHttpClientFactory` to be used as a singleton for the interface `IHttpClientFactory`.</span></span> <span data-ttu-id="2feab-144">它定义 `HttpMessageHandlerBuilder` 的临时配置。</span><span class="sxs-lookup"><span data-stu-id="2feab-144">It defines a transient configuration for the `HttpMessageHandlerBuilder`.</span></span> <span data-ttu-id="2feab-145">此消息处理程序（`HttpMessageHandler` 对象）获取自池，可供从工厂返回的 `HttpClient` 使用。</span><span class="sxs-lookup"><span data-stu-id="2feab-145">This message handler (`HttpMessageHandler` object), taken from a pool, is used by the `HttpClient` returned from the factory.</span></span>

<span data-ttu-id="2feab-146">在下一个代码中，可以看到如何使用 `AddHttpClient()` 注册需要使用 `HttpClient` 的类型化客户端（服务代理）。</span><span class="sxs-lookup"><span data-stu-id="2feab-146">In the next code, you can see how `AddHttpClient()` can be used to register Typed Clients (Service Agents) that need to use `HttpClient`.</span></span>

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services) 
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

<span data-ttu-id="2feab-147">按先前代码中所示注册客户端服务，使 `DefaultClientFactory` 为每个服务创建一个标准 `HttpClient`。</span><span class="sxs-lookup"><span data-stu-id="2feab-147">Registering the client services as shown in the previous code, makes the `DefaultClientFactory` create a standard `HttpClient` for each service.</span></span>

<span data-ttu-id="2feab-148">还可以在注册中添加特定于实例的配置（例如，配置基址），并添加一些弹性策略，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="2feab-148">You could also add instance-specific configuration in the registration to, for example, configure the base address, and add some resiliency policies, as shown in the following code:</span></span>

```csharp
services.AddHttpClient<ICatalogService, CatalogService>(client =>
{
    client.BaseAddress = new Uri(Configuration["BaseUrl"])
})
    .AddPolicyHandler(GetRetryPolicy())
    .AddPolicyHandler(GetCircuitBreakerPolicy());
```

<span data-ttu-id="2feab-149">就本示例而言，可以在下一个代码中看到以上策略之一：</span><span class="sxs-lookup"><span data-stu-id="2feab-149">Just for the example sake, you can see one of the above policies in the next code:</span></span>

```csharp
static IAsyncPolicy<HttpResponseMessage> GetRetryPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
        .WaitAndRetryAsync(6, retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)));
}
```

<span data-ttu-id="2feab-150">可以在[下一篇文章](implement-http-call-retries-exponential-backoff-polly.md)中找到有关使用 Polly 的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="2feab-150">You can find more details about using Polly in the [Next article](implement-http-call-retries-exponential-backoff-polly.md).</span></span>

### <a name="httpclient-lifetimes"></a><span data-ttu-id="2feab-151">HttpClient 生存期</span><span class="sxs-lookup"><span data-stu-id="2feab-151">HttpClient lifetimes</span></span>

<span data-ttu-id="2feab-152">每次从 `IHttpClientFactory` 获取 `HttpClient` 对象时，都会返回一个新实例。</span><span class="sxs-lookup"><span data-stu-id="2feab-152">Each time you get an `HttpClient` object from the `IHttpClientFactory`, a new instance is returned.</span></span> <span data-ttu-id="2feab-153">但每个 `HttpClient` 使用 `IHttpClientFactory` 汇集和重用的 `HttpMessageHandler`，以减少资源消耗，只要 `HttpMessageHandler` 的生存期尚未过期。</span><span class="sxs-lookup"><span data-stu-id="2feab-153">But each `HttpClient` uses an `HttpMessageHandler` that's pooled and reused by the `IHttpClientFactory` to reduce resource consumption, as long as the `HttpMessageHandler`'s lifetime hasn't expired.</span></span>

<span data-ttu-id="2feab-154">由于每个处理程序通常都管理自己的基础 HTTP 连接，所以有必要汇集处理程序；创建的处理程序数量如果多于必需的数量，则可能导致连接延迟。</span><span class="sxs-lookup"><span data-stu-id="2feab-154">Pooling of handlers is desirable as each handler typically manages its own underlying HTTP connections; creating more handlers than necessary can result in connection delays.</span></span> <span data-ttu-id="2feab-155">部分处理程序还保持连接无期限地打开，这样可以防止处理程序对 DNS 更改作出反应。</span><span class="sxs-lookup"><span data-stu-id="2feab-155">Some handlers also keep connections open indefinitely, which can prevent the handler from reacting to DNS changes.</span></span>

<span data-ttu-id="2feab-156">池中的 `HttpMessageHandler` 对象的生存期就是池中的 `HttpMessageHandler` 实例可重用的时间长度。</span><span class="sxs-lookup"><span data-stu-id="2feab-156">The `HttpMessageHandler` objects in the pool have a lifetime that's the length of time that an `HttpMessageHandler` instance in the pool can be reused.</span></span> <span data-ttu-id="2feab-157">默认值为两分钟，但可基于每个类型化客户端重写此值。</span><span class="sxs-lookup"><span data-stu-id="2feab-157">The default value is two minutes, but it can be overridden per Typed Client.</span></span> <span data-ttu-id="2feab-158">要重写该值，请在创建客户端时在返回的 `IHttpClientBuilder` 上调用 `SetHandlerLifetime()`，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="2feab-158">To override it, call `SetHandlerLifetime()` on the `IHttpClientBuilder` that's returned when creating the client, as shown in the following code:</span></span>

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client 
services.AddHttpClient<ICatalogService, CatalogService>()
    .SetHandlerLifetime(TimeSpan.FromMinutes(5));
```

<span data-ttu-id="2feab-159">每个类型化客户端都可自行配置处理程序生存期值。</span><span class="sxs-lookup"><span data-stu-id="2feab-159">Each Typed Client can have its own configured handler lifetime value.</span></span> <span data-ttu-id="2feab-160">将生存期设置为 `InfiniteTimeSpan` 可禁用处理程序到期。</span><span class="sxs-lookup"><span data-stu-id="2feab-160">Set the lifetime to `InfiniteTimeSpan` to disable handler expiry.</span></span>

### <a name="implement-your-typed-client-classes-that-use-the-injected-and-configured-httpclient"></a><span data-ttu-id="2feab-161">实现使用注入的和配置的 HttpClient 的类型化客户端类</span><span class="sxs-lookup"><span data-stu-id="2feab-161">Implement your Typed Client classes that use the injected and configured HttpClient</span></span>

<span data-ttu-id="2feab-162">在上一步中，需要定义类型化客户端类，如示例代码中的类，“BasketService”、“CatalogService”、“OrderingService”等。类型化客户端是一个类，它接受 `HttpClient` 对象（通过其构造函数注入），并用它来调用某些远程 HTTP 服务。</span><span class="sxs-lookup"><span data-stu-id="2feab-162">As a previous step, you need to have your Typed Client classes defined, such as the classes in the sample code, like ‘BasketService’, ‘CatalogService’, ‘OrderingService’, etc. – A Typed Client is a class that accepts an `HttpClient` object (injected through its constructor) and uses it to call some remote HTTP service.</span></span> <span data-ttu-id="2feab-163">例如:</span><span class="sxs-lookup"><span data-stu-id="2feab-163">For example:</span></span>

```csharp
public class CatalogService : ICatalogService
{
    private readonly HttpClient _httpClient;
    private readonly string _remoteServiceBaseUrl;

    public CatalogService(HttpClient httpClient)
    {
        _httpClient = httpClient;
    }

    public async Task<Catalog> GetCatalogItems(int page, int take, 
                                               int? brand, int? type)
    {
        var uri = API.Catalog.GetAllCatalogItems(_remoteServiceBaseUrl, 
                                                 page, take, brand, type);

        var responseString = await _httpClient.GetStringAsync(uri);

        var catalog = JsonConvert.DeserializeObject<Catalog>(responseString);
        return catalog;
    }
}
```

<span data-ttu-id="2feab-164">类型化客户端（示例中的 CatalogService）由 DI（依赖项注入）激活，这意味着除 HttpClient 外，它还可以接受其构造函数中的任何注册服务。</span><span class="sxs-lookup"><span data-stu-id="2feab-164">The Typed Client (CatalogService in the example) is activated by DI (Dependency Injection), meaning that it can accept any registered service in its constructor, in addition to HttpClient.</span></span>

<span data-ttu-id="2feab-165">类型化客户端实际上是一个暂时对象，这意味着每次需要实例时都将创建新实例，并且它将在其每次被构造时接收一个新 `HttpClient` 实例。</span><span class="sxs-lookup"><span data-stu-id="2feab-165">A Typed Client is, effectively, a transient object, meaning that a new instance is created each time one is needed and it will receive a new `HttpClient` instance each time it's constructed.</span></span> <span data-ttu-id="2feab-166">但是，池中的 HttpMessageHandler 对象是由多个 Http 请求重复使用的对象。</span><span class="sxs-lookup"><span data-stu-id="2feab-166">However, the HttpMessageHandler objects in the pool are the objects that are reused by multiple Http requests.</span></span>

### <a name="use-your-typed-client-classes"></a><span data-ttu-id="2feab-167">使用类型化客户端类</span><span class="sxs-lookup"><span data-stu-id="2feab-167">Use your Typed Client classes</span></span>

<span data-ttu-id="2feab-168">最后，一旦实现了键入的类并在 `AddHttpClient()` 中注册了它们，就可以在每次可通过 DI 注入服务时使用它们。</span><span class="sxs-lookup"><span data-stu-id="2feab-168">Finally, once you have your typed classes implemented and have them registered with `AddHttpClient()`, you can use them wherever you can have services injected by DI.</span></span> <span data-ttu-id="2feab-169">例如，在 Razor 页面代码或 MVC Web 应用的控制器中，如 eShopOnContainers 的以下代码中：</span><span class="sxs-lookup"><span data-stu-id="2feab-169">For example, in a Razor page code or controller of an MVC web app, like in the following code from eShopOnContainers:</span></span>

```csharp
namespace Microsoft.eShopOnContainers.WebMVC.Controllers
{
    public class CatalogController : Controller
    {
        private ICatalogService _catalogSvc;

        public CatalogController(ICatalogService catalogSvc) =>
                                                           _catalogSvc = catalogSvc;

        public async Task<IActionResult> Index(int? BrandFilterApplied,
                                               int? TypesFilterApplied,
                                               int? page,
                                               [FromQuery]string errorMsg)
        {
            var itemsPage = 10;
            var catalog = await _catalogSvc.GetCatalogItems(page ?? 0,
                                                            itemsPage,
                                                            BrandFilterApplied,
                                                            TypesFilterApplied);
            //… Additional code
        }

        }
}
```

<span data-ttu-id="2feab-170">此时，所示代码仅执行常规 Http 请求，但后续部分将展示真正的“神奇”之处 - 只需向已注册的类型化客户端添加策略和委派处理程序，将由 `HttpClient` 完成的所有 HTTP 请求在执行时都将考虑帐户复原策略，例如使用指数退避算法实现的重试、断路器或用于实现额外安全功能（如使用身份验证令牌或任何其他自定义功能）的任何其他自定义委托处理程序。</span><span class="sxs-lookup"><span data-stu-id="2feab-170">Up to this point, the code shown is just performing regular Http requests, but the ‘magic’ comes in the following sections where, just by adding policies and delegating handlers to your registered Typed Clients, all the HTTP requests to be done by `HttpClient` will behave taking into account resilient policies such as retries with exponential backoff, circuit breakers, or any other custom delegating handler to implement additional security features, like using auth tokens, or any other custom feature.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2feab-171">其他资源</span><span class="sxs-lookup"><span data-stu-id="2feab-171">Additional resources</span></span>

- <span data-ttu-id="2feab-172">**在 .NET Core 中使用 HttpClientFactory** </span><span class="sxs-lookup"><span data-stu-id="2feab-172">**Using HttpClientFactory in .NET Core** </span></span>\
  [https://docs.microsoft.com/aspnet/core/fundamentals/http-requests](/aspnet/core/fundamentals/http-requests)

- <span data-ttu-id="2feab-173">**HttpClientFactory GitHub 存储库** </span><span class="sxs-lookup"><span data-stu-id="2feab-173">**HttpClientFactory GitHub repo** </span></span>\
  <https://github.com/aspnet/Extensions/tree/master/src/HttpClientFactory>

- <span data-ttu-id="2feab-174">**Polly（.NET 复原能力和暂时性故障处理库）**  </span><span class="sxs-lookup"><span data-stu-id="2feab-174">**Polly (.NET resilience and transient-fault-handling library)** </span></span>\
  <http://www.thepollyproject.org/>

>[!div class="step-by-step"]
><span data-ttu-id="2feab-175">[上一页](explore-custom-http-call-retries-exponential-backoff.md)
>[下一页](implement-http-call-retries-exponential-backoff-polly.md)</span><span class="sxs-lookup"><span data-stu-id="2feab-175">[Previous](explore-custom-http-call-retries-exponential-backoff.md)
[Next](implement-http-call-retries-exponential-backoff-polly.md)</span></span>
