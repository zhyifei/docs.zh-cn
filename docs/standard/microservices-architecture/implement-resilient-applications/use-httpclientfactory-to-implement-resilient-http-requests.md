---
title: 使用 HttpClientFactory 实现复原 HTTP 请求
description: 了解如何使用自 .NET Core 2.1 起可用的 HttpClientFactory 来创建 `HttpClient` 实例，使其更轻松地在应用程序中使用。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/16/2018
ms.openlocfilehash: 6af30ae3b5111e026be6ec89d266338b88cf22b2
ms.sourcegitcommit: 542aa405b295955eb055765f33723cb8b588d0d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "54362636"
---
# <a name="use-httpclientfactory-to-implement-resilient-http-requests"></a><span data-ttu-id="2d056-103">使用 HttpClientFactory 实现复原 HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="2d056-103">Use HttpClientFactory to implement resilient HTTP requests</span></span>

<span data-ttu-id="2d056-104">自 .NET Core 2.1 起可用的 `HttpClientFactory` 是一个“固执的”工厂，用于创建在应用程序中使用的 <xref:System.Net.Http.HttpClient> 实例。</span><span class="sxs-lookup"><span data-stu-id="2d056-104">`HttpClientFactory` is an opinionated factory, available since .NET Core 2.1, for creating <xref:System.Net.Http.HttpClient> instances to be used in your applications.</span></span>

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a><span data-ttu-id="2d056-105">.NET Core 中提供的原始 HttpClient 类的相关问题</span><span class="sxs-lookup"><span data-stu-id="2d056-105">Issues with the original HttpClient class available in .NET Core</span></span>

<span data-ttu-id="2d056-106">常见的原始 [HttpClient](/dotnet/api/system.net.http.httpclient?view=netstandard-2.0) 类非常易于使用，但在某些情况下，许多开发人员却并未正确使用该类。</span><span class="sxs-lookup"><span data-stu-id="2d056-106">The original and well-known [HttpClient](/dotnet/api/system.net.http.httpclient?view=netstandard-2.0) class can be easily used, but in some cases, it isn't being properly used by many developers.</span></span> 

<span data-ttu-id="2d056-107">第一个问题，当此类可释放时，将其用于 `using` 语句并不是最佳选择，因为即使释放 `HttpClient` 对象，基础套接字也不会立即释放，并可能导致严重问题：“套接字耗尽”。</span><span class="sxs-lookup"><span data-stu-id="2d056-107">As a first issue, while this class is disposable, using it with the `using` statement is not the best choice because even when you dispose `HttpClient` object, the underlying socket is not immediately released and can cause a serious issue named ‘sockets exhaustion’.</span></span> <span data-ttu-id="2d056-108">有关此问题的详细信息，请参阅[你正在以错误方式使用 HttpClient，这将导致软件受损](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/)博客文章。</span><span class="sxs-lookup"><span data-stu-id="2d056-108">For more information about this issue, see [You're using HttpClient wrong and it's destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) blog post.</span></span>

<span data-ttu-id="2d056-109">因此，`HttpClient` 应进行一次实例化并在应用程序的生命周期中重复使用。</span><span class="sxs-lookup"><span data-stu-id="2d056-109">Therefore, `HttpClient` is intended to be instantiated once and reused throughout the life of an application.</span></span> <span data-ttu-id="2d056-110">在负载较重的情况下，实例化每个请求的 `HttpClient` 类将耗尽可用的套接字数。</span><span class="sxs-lookup"><span data-stu-id="2d056-110">Instantiating an `HttpClient` class for every request will exhaust the number of sockets available under heavy loads.</span></span> <span data-ttu-id="2d056-111">该问题会导致 `SocketException` 错误。</span><span class="sxs-lookup"><span data-stu-id="2d056-111">That issue will result in `SocketException` errors.</span></span> <span data-ttu-id="2d056-112">要解决此问题，可能的方法是将 `HttpClient` 对象创建为单一对象或静态对象，请参阅[关于 HttpClient 用法的 Microsoft 文章](/dotnet/csharp/tutorials/console-webapiclient)中的说明。</span><span class="sxs-lookup"><span data-stu-id="2d056-112">Possible approaches to solve that problem are based on the creation of the `HttpClient` object as singleton or static, as explained in this [Microsoft article on HttpClient usage](/dotnet/csharp/tutorials/console-webapiclient).</span></span> 

<span data-ttu-id="2d056-113">但将 `HttpClient` 对象用作单一对象或静态对象时还有一个问题。</span><span class="sxs-lookup"><span data-stu-id="2d056-113">But there’s a second issue with `HttpClient` that you can have when you use it as singleton or static object.</span></span> <span data-ttu-id="2d056-114">在这种情况下，单一或静态 `HttpClient` 不考虑 DNS 更改，请参阅 [.NET Core GitHub 存储库的问题](https://github.com/dotnet/corefx/issues/11224)一文的说明。</span><span class="sxs-lookup"><span data-stu-id="2d056-114">In this case, a singleton or static `HttpClient` doesn't respect DNS changes, as explained in this [issue at the .NET Core GitHub repo](https://github.com/dotnet/corefx/issues/11224).</span></span> 

<span data-ttu-id="2d056-115">为解决上述问题并使 `HttpClient` 实例管理更轻松，.NET Core 2.1 提供新的 `HttpClientFactory`，后者可与 Polly 集成来实现复原 HTTP 调用。</span><span class="sxs-lookup"><span data-stu-id="2d056-115">To address those mentioned issues and make the management of `HttpClient` instances easier, .NET Core 2.1 offers a new `HttpClientFactory` that can also be used to implement resilient HTTP calls by integrating Polly with it.</span></span>   

## <a name="what-is-httpclientfactory"></a><span data-ttu-id="2d056-116">什么是 HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="2d056-116">What is HttpClientFactory</span></span>

<span data-ttu-id="2d056-117">`HttpClientFactory` 用于：</span><span class="sxs-lookup"><span data-stu-id="2d056-117">`HttpClientFactory` is designed to:</span></span>

- <span data-ttu-id="2d056-118">提供一个中心位置，用于命名和配置逻辑 HttpClient。</span><span class="sxs-lookup"><span data-stu-id="2d056-118">Provide a central location for naming and configuring logical HttpClients.</span></span> <span data-ttu-id="2d056-119">例如，可以配置预配置的客户端（服务代理）以访问特定微服务。</span><span class="sxs-lookup"><span data-stu-id="2d056-119">For example, you may configure a client (Service Agent) that's pre-configured to access a specific microservice.</span></span>
- <span data-ttu-id="2d056-120">通过后列方式整理出站中间件的概念：在 `HttpClient` 中委托处理程序并实现基于 Polly 的中间件以利用 Polly 的复原策略。</span><span class="sxs-lookup"><span data-stu-id="2d056-120">Codify the concept of outgoing middleware via delegating handlers in `HttpClient` and implementing Polly-based middleware to take advantage of Polly’s policies for resiliency.</span></span>
- <span data-ttu-id="2d056-121">`HttpClient` 已经具有委托处理程序的概念，这些委托处理程序可以链接在一起，处理出站 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="2d056-121">`HttpClient` already has the concept of delegating handlers that could be linked together for outgoing HTTP requests.</span></span> <span data-ttu-id="2d056-122">将 http 客户端注册到工厂后，可使用一个允许将 Polly 策略用于重试、断路器等的 Polly 处理程序。</span><span class="sxs-lookup"><span data-stu-id="2d056-122">You register http clients into the factory plus you can use a Polly handler that allows Polly policies to be used for Retry, CircuitBreakers, etc.</span></span>
- <span data-ttu-id="2d056-123">管理 HttpClientMessageHandlers 的生存期，以避免在自己管理 `HttpClient` 生存期时出现上述问题。</span><span class="sxs-lookup"><span data-stu-id="2d056-123">Manage the lifetime of HttpClientMessageHandlers to avoid the mentioned problems/issues that can occur when managing `HttpClient` lifetimes yourself.</span></span> 

## <a name="multiple-ways-to-use-httpclientfactory"></a><span data-ttu-id="2d056-124">HttpClientFactory 的多种用法</span><span class="sxs-lookup"><span data-stu-id="2d056-124">Multiple ways to use HttpClientFactory</span></span>

<span data-ttu-id="2d056-125">可以通过多种方法在应用程序中使用 `HttpClientFactory`：</span><span class="sxs-lookup"><span data-stu-id="2d056-125">There are several ways that you can use `HttpClientFactory` in your application:</span></span>

- <span data-ttu-id="2d056-126">直接使用 `HttpClientFactory`</span><span class="sxs-lookup"><span data-stu-id="2d056-126">Use `HttpClientFactory` Directly</span></span>
- <span data-ttu-id="2d056-127">使用命名客户端</span><span class="sxs-lookup"><span data-stu-id="2d056-127">Use Named Clients</span></span>
- <span data-ttu-id="2d056-128">使用类型化客户端</span><span class="sxs-lookup"><span data-stu-id="2d056-128">Use Typed Clients</span></span>
- <span data-ttu-id="2d056-129">使用生成的客户端</span><span class="sxs-lookup"><span data-stu-id="2d056-129">Use Generated Clients</span></span>

<span data-ttu-id="2d056-130">为简便起见，本指南介绍最具条理和组织性的 `HttpClientFactory` 用法，此方法就是使用类型化客户端（服务代理模式），但此[关于 HttpClientFactory 用法的文章](/aspnet/core/fundamentals/http-requests?#consumption-patterns)中当前记录并列出了全部可用的方法。</span><span class="sxs-lookup"><span data-stu-id="2d056-130">For the sake of brevity, this guidance shows the most structured way to use `HttpClientFactory` that's to use Typed Clients (Service Agent pattern), but all options are documented and are currently listed in this [article covering HttpClientFactory usage](/aspnet/core/fundamentals/http-requests?#consumption-patterns).</span></span>  

## <a name="how-to-use-typed-clients-with-httpclientfactory"></a><span data-ttu-id="2d056-131">如何结合使用类型化客户端和 HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="2d056-131">How to use Typed Clients with HttpClientFactory</span></span>

<span data-ttu-id="2d056-132">那么，什么是“类型化客户端”？</span><span class="sxs-lookup"><span data-stu-id="2d056-132">So, what's a "Typed Client"?</span></span> <span data-ttu-id="2d056-133">它只是 `DefaultHttpClientFactory` 注入时配置的 `HttpClient`。</span><span class="sxs-lookup"><span data-stu-id="2d056-133">It's just an `HttpClient` that's configured upon injection by the `DefaultHttpClientFactory`.</span></span>

<span data-ttu-id="2d056-134">下图显示了如何将类型化客户端与 `HttpClientFactory` 结合使用：</span><span class="sxs-lookup"><span data-stu-id="2d056-134">The following diagram shows how Typed Clients are used with `HttpClientFactory`:</span></span>

![ClientService（由控制器或客户端代码使用）使用由注册的 IHttpClientFactory 创建的 HttpClient。](./media/image3.5.png)

<span data-ttu-id="2d056-138">**图 8-4**。</span><span class="sxs-lookup"><span data-stu-id="2d056-138">**Figure 8-4**.</span></span> <span data-ttu-id="2d056-139">将 HttpClientFactory 与类型化客户端类结合使用。</span><span class="sxs-lookup"><span data-stu-id="2d056-139">Using HttpClientFactory with Typed Client classes.</span></span>

<span data-ttu-id="2d056-140">首先，在应用程序中设置 `HttpClientFactory`，添加对包含 `IServiceCollection` 的 `AddHttpClient()` 扩展方法的 `Microsoft.Extensions.Http` 包的引用。</span><span class="sxs-lookup"><span data-stu-id="2d056-140">First, setup `HttpClientFactory` in your application, adding a reference to the `Microsoft.Extensions.Http` package that includes the `AddHttpClient()` extension method for `IServiceCollection`.</span></span> <span data-ttu-id="2d056-141">此扩展方法用于注册 `DefaultHttpClientFactory`，后者用作接口 `IHttpClientFactory` 的单一实例。</span><span class="sxs-lookup"><span data-stu-id="2d056-141">This extension method registers the `DefaultHttpClientFactory` to be used as a singleton for the interface `IHttpClientFactory`.</span></span> <span data-ttu-id="2d056-142">它定义 `HttpMessageHandlerBuilder` 的临时配置。</span><span class="sxs-lookup"><span data-stu-id="2d056-142">It defines a transient configuration for the `HttpMessageHandlerBuilder`.</span></span> <span data-ttu-id="2d056-143">此消息处理程序（`HttpMessageHandler` 对象）获取自池，可供从工厂返回的 `HttpClient` 使用。</span><span class="sxs-lookup"><span data-stu-id="2d056-143">This message handler (`HttpMessageHandler` object), taken from a pool, is used by the `HttpClient` returned from the factory.</span></span>

<span data-ttu-id="2d056-144">在下一个代码中，可以看到如何使用 `AddHttpClient()` 注册需要使用 `HttpClient` 的类型化客户端（服务代理）。</span><span class="sxs-lookup"><span data-stu-id="2d056-144">In the next code, you can see how `AddHttpClient()` can be used to register Typed Clients (Service Agents) that need to use `HttpClient`.</span></span>

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services) 
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

<span data-ttu-id="2d056-145">正如前面代码所示，注册客户端服务将使 `DefaultClientFactory` 创建专门为每个服务配置的 `HttpClient`，我们将在下一段中对此进行解释。</span><span class="sxs-lookup"><span data-stu-id="2d056-145">Registering the client services as shown in the previous code, makes the `DefaultClientFactory` create an `HttpClient` configured specifically for each service, as we'll explain in the next paragraph.</span></span>

<span data-ttu-id="2d056-146">只需向 `AddHttpClient()` 注册客户端服务类，注入到类中的 `HttpClient` 对象将使用注册时提供的配置和策略。</span><span class="sxs-lookup"><span data-stu-id="2d056-146">Just by registering your client service class with `AddHttpClient()`, the `HttpClient` object that will be injected into your class will use the configuration and policies provided upon registration.</span></span> <span data-ttu-id="2d056-147">后续部分将介绍 Polly 重试或断路器等策略。</span><span class="sxs-lookup"><span data-stu-id="2d056-147">In the next sections, you'll see those policies like Polly’s retries or circuit-breakers.</span></span>

### <a name="httpclient-lifetimes"></a><span data-ttu-id="2d056-148">HttpClient 生存期</span><span class="sxs-lookup"><span data-stu-id="2d056-148">HttpClient lifetimes</span></span>

<span data-ttu-id="2d056-149">每次从 `IHttpClientFactory` 获取 `HttpClient` 对象时，都会返回一个新实例。</span><span class="sxs-lookup"><span data-stu-id="2d056-149">Each time you get an `HttpClient` object from the `IHttpClientFactory`, a new instance is returned.</span></span> <span data-ttu-id="2d056-150">但每个 `HttpClient` 使用 `IHttpClientFactory` 汇集和重用的 `HttpMessageHandler`，以减少资源消耗，只要 `HttpMessageHandler` 的生存期尚未过期。</span><span class="sxs-lookup"><span data-stu-id="2d056-150">But each `HttpClient` uses an `HttpMessageHandler` that's pooled and reused by the `IHttpClientFactory` to reduce resource consumption, as long as the `HttpMessageHandler`'s lifetime hasn't expired.</span></span>

<span data-ttu-id="2d056-151">由于每个处理程序通常都管理自己的基础 HTTP 连接，所以有必要汇集处理程序；创建的处理程序数量如果多于必需的数量，则可能导致连接延迟。</span><span class="sxs-lookup"><span data-stu-id="2d056-151">Pooling of handlers is desirable as each handler typically manages its own underlying HTTP connections; creating more handlers than necessary can result in connection delays.</span></span> <span data-ttu-id="2d056-152">部分处理程序还保持连接无期限地打开，这样可以防止处理程序对 DNS 更改作出反应。</span><span class="sxs-lookup"><span data-stu-id="2d056-152">Some handlers also keep connections open indefinitely, which can prevent the handler from reacting to DNS changes.</span></span>

<span data-ttu-id="2d056-153">池中的 `HttpMessageHandler` 对象的生存期就是池中的 `HttpMessageHandler` 实例可重用的时间长度。</span><span class="sxs-lookup"><span data-stu-id="2d056-153">The `HttpMessageHandler` objects in the pool have a lifetime that's the length of time that an `HttpMessageHandler` instance in the pool can be reused.</span></span> <span data-ttu-id="2d056-154">默认值为两分钟，但可基于每个类型化客户端重写此值。</span><span class="sxs-lookup"><span data-stu-id="2d056-154">The default value is two minutes, but it can be overridden per Typed Client.</span></span> <span data-ttu-id="2d056-155">要重写该值，请在创建客户端时在返回的 `IHttpClientBuilder` 上调用 `SetHandlerLifetime()`，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="2d056-155">To override it, call `SetHandlerLifetime()` on the `IHttpClientBuilder` that's returned when creating the client, as shown in the following code:</span></span>

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client 
services.AddHttpClient<ICatalogService, CatalogService>()
                 .SetHandlerLifetime(TimeSpan.FromMinutes(5));  
```

<span data-ttu-id="2d056-156">每个类型化客户端都可自行配置处理程序生存期值。</span><span class="sxs-lookup"><span data-stu-id="2d056-156">Each Typed Client can have its own configured handler lifetime value.</span></span> <span data-ttu-id="2d056-157">将生存期设置为 `InfiniteTimeSpan` 可禁用处理程序到期。</span><span class="sxs-lookup"><span data-stu-id="2d056-157">Set the lifetime to `InfiniteTimeSpan` to disable handler expiry.</span></span>

### <a name="implement-your-typed-client-classes-that-use-the-injected-and-configured-httpclient"></a><span data-ttu-id="2d056-158">实现使用注入的和配置的 HttpClient 的类型化客户端类</span><span class="sxs-lookup"><span data-stu-id="2d056-158">Implement your Typed Client classes that use the injected and configured HttpClient</span></span>

<span data-ttu-id="2d056-159">在上一步中，需要定义类型化客户端类，如示例代码中的类，“BasketService”、“CatalogService”、“OrderingService”等。类型化客户端是一个类，它接受 `HttpClient` 对象（通过其构造函数注入），并用它来调用某些远程 HTTP 服务。</span><span class="sxs-lookup"><span data-stu-id="2d056-159">As a previous step, you need to have your Typed Client classes defined, such as the classes in the sample code, like ‘BasketService’, ‘CatalogService’, ‘OrderingService’, etc. – A Typed Client is a class that accepts an `HttpClient` object (injected through its constructor) and uses it to call some remote HTTP service.</span></span> <span data-ttu-id="2d056-160">例如:</span><span class="sxs-lookup"><span data-stu-id="2d056-160">For example:</span></span>

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

<span data-ttu-id="2d056-161">类型化客户端（示例中的 CatalogService）由 DI（依赖项注入）激活，这意味着除 HttpClient 外，它还可以接受其构造函数中的任何注册服务。</span><span class="sxs-lookup"><span data-stu-id="2d056-161">The Typed Client (CatalogService in the example) is activated by DI (Dependency Injection), meaning that it can accept any registered service in its constructor, in addition to HttpClient.</span></span>

<span data-ttu-id="2d056-162">类型化客户端实际上是一个暂时对象，这意味着每次需要实例时都将创建新实例，并且它将在其每次被构造时接收一个新 `HttpClient` 实例。</span><span class="sxs-lookup"><span data-stu-id="2d056-162">A Typed Client is, effectively, a transient object, meaning that a new instance is created each time one is needed and it will receive a new `HttpClient` instance each time it's constructed.</span></span> <span data-ttu-id="2d056-163">但是，池中的 HttpMessageHandler 对象是由多个 Http 请求重复使用的对象。</span><span class="sxs-lookup"><span data-stu-id="2d056-163">However, the HttpMessageHandler objects in the pool are the objects that are reused by multiple Http requests.</span></span>

### <a name="use-your-typed-client-classes"></a><span data-ttu-id="2d056-164">使用类型化客户端类</span><span class="sxs-lookup"><span data-stu-id="2d056-164">Use your Typed Client classes</span></span>

<span data-ttu-id="2d056-165">最后，实现类型类并向 AddHttpClient() 注册这些类后，便可在允许使用 DI 注入的服务的任何位置使用，例如在任何 Razor 页面代码或 MVC Web 应用的任何控制器中，如 eShopOnContainers 中的以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="2d056-165">Finally, once you have your type classes implemented and have them registered with AddHttpClient(), you can use it anywhere you can have services injected by DI, for example in any Razor page code or any controller of an MVC web app, like in the following code from eShopOnContainers.</span></span>

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

<span data-ttu-id="2d056-166">此时，所示代码仅执行常规 Http 请求，但后续部分将展示真正的“神奇”之处 - 只需向已注册的类型化客户端添加策略和委派处理程序，将由 `HttpClient` 完成的所有 HTTP 请求在执行时都将考虑帐户复原策略，例如使用指数退避算法实现的重试、断路器或用于实现额外安全功能（如使用身份验证令牌或任何其他自定义功能）的任何其他自定义委托处理程序。</span><span class="sxs-lookup"><span data-stu-id="2d056-166">Up to this point, the code shown is just performing regular Http requests, but the ‘magic’ comes in the following sections where, just by adding policies and delegating handlers to your registered Typed Clients, all the HTTP requests to be done by `HttpClient` will behave taking into account resilient policies such as retries with exponential backoff, circuit breakers, or any other custom delegating handler to implement additional security features, like using auth tokens, or any other custom feature.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="2d056-167">其他资源</span><span class="sxs-lookup"><span data-stu-id="2d056-167">Additional resources</span></span>

- <span data-ttu-id="2d056-168">**在 .NET Core 2.1 中使用 HttpClientFactory**\\</span><span class="sxs-lookup"><span data-stu-id="2d056-168">**Using HttpClientFactory in .NET Core 2.1**\\</span></span>
  [*https://docs.microsoft.com/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1*](/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1)

- <span data-ttu-id="2d056-169">**HttpClientFactory GitHub 存储库**\\</span><span class="sxs-lookup"><span data-stu-id="2d056-169">**HttpClientFactory GitHub repo**\\</span></span>
  [*https://github.com/aspnet/HttpClientFactory*](https://github.com/aspnet/HttpClientFactory)

>[!div class="step-by-step"]
><span data-ttu-id="2d056-170">[上一页](explore-custom-http-call-retries-exponential-backoff.md)
>[下一页](implement-http-call-retries-exponential-backoff-polly.md)</span><span class="sxs-lookup"><span data-stu-id="2d056-170">[Previous](explore-custom-http-call-retries-exponential-backoff.md)
[Next](implement-http-call-retries-exponential-backoff-polly.md)</span></span>