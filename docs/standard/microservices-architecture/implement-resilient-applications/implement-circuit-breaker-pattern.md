---
title: "实现断路器模式"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |实现断路器模式"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 2a629e25a7565aaba156f68cf06d9a24b6c2b8b0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-the-circuit-breaker-pattern"></a><span data-ttu-id="5d502-104">实现断路器模式</span><span class="sxs-lookup"><span data-stu-id="5d502-104">Implementing the Circuit Breaker pattern</span></span>

<span data-ttu-id="5d502-105">如前文所述，你应处理可能需要变量大量时间才能恢复，当你尝试连接到远程服务或资源可能会发生的错误。</span><span class="sxs-lookup"><span data-stu-id="5d502-105">As noted earlier, you should handle faults that might take a variable amount of time to recover from, as might happen when you try to connect to a remote service or resource.</span></span> <span data-ttu-id="5d502-106">处理这种类型的错误可以提高稳定性和复原能力的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5d502-106">Handling this type of fault can improve the stability and resiliency of an application.</span></span>

<span data-ttu-id="5d502-107">在分布式环境中，对远程资源和服务的调用可能失败由于暂时性故障，例如慢速网络连接和超时，或如果资源正在缓慢或暂时不可用。</span><span class="sxs-lookup"><span data-stu-id="5d502-107">In a distributed environment, calls to remote resources and services can fail due to transient faults, such as slow network connections and timeouts, or if resources are being slow or are temporarily unavailable.</span></span> <span data-ttu-id="5d502-108">这些故障通常一段时间之后, 更正本身和可靠的云应用程序应准备好处理它们通过使用类似的重试模式的策略。</span><span class="sxs-lookup"><span data-stu-id="5d502-108">These faults typically correct themselves after a short time, and a robust cloud application should be prepared to handle them by using a strategy like the Retry pattern.</span></span>

<span data-ttu-id="5d502-109">但是，也可以存在的情况下错误由于可能需要较长时间才能解决的意外事件。</span><span class="sxs-lookup"><span data-stu-id="5d502-109">However, there can also be situations where faults are due to unanticipated events that might take much longer to fix.</span></span> <span data-ttu-id="5d502-110">从部分连接断开到服务的完整失败的严重性范围可以是这些错误。</span><span class="sxs-lookup"><span data-stu-id="5d502-110">These faults can range in severity from a partial loss of connectivity to the complete failure of a service.</span></span> <span data-ttu-id="5d502-111">在这些情况下，它可能是应用程序，以不断重试不太可能成功操作毫无意义。</span><span class="sxs-lookup"><span data-stu-id="5d502-111">In these situations, it might be pointless for an application to continually retry an operation that is unlikely to succeed.</span></span> <span data-ttu-id="5d502-112">相反，应用程序应编码为接受的操作已失败并相应地处理错误。</span><span class="sxs-lookup"><span data-stu-id="5d502-112">Instead, the application should be coded to accept that the operation has failed and handle the failure accordingly.</span></span>

<span data-ttu-id="5d502-113">断路器模式具有与重试模式不同的用途。</span><span class="sxs-lookup"><span data-stu-id="5d502-113">The Circuit Breaker pattern has a different purpose than the Retry pattern.</span></span> <span data-ttu-id="5d502-114">应用程序，以重试该操作将最终成功的假定条件下在操作可以重试模式。</span><span class="sxs-lookup"><span data-stu-id="5d502-114">The Retry pattern enables an application to retry an operation in the expectation that the operation will eventually succeed.</span></span> <span data-ttu-id="5d502-115">断路器模式防止应用程序执行的操作，则可能会失败。</span><span class="sxs-lookup"><span data-stu-id="5d502-115">The Circuit Breaker pattern prevents an application from performing an operation that is likely to fail.</span></span> <span data-ttu-id="5d502-116">应用程序可以通过使用重试模式来调用通过断路器操作来组合这些两种模式。</span><span class="sxs-lookup"><span data-stu-id="5d502-116">An application can combine these two patterns by using the Retry pattern to invoke an operation through a circuit breaker.</span></span> <span data-ttu-id="5d502-117">但是，重试逻辑应能觉察到返回的断路器中，任何异常，并且如果故障不是暂时性的断路器指示它应放弃重试尝试。</span><span class="sxs-lookup"><span data-stu-id="5d502-117">However, the retry logic should be sensitive to any exceptions returned by the circuit breaker, and it should abandon retry attempts if the circuit breaker indicates that a fault is not transient.</span></span>

## <a name="implementing-a-circuit-breaker-pattern-with-polly"></a><span data-ttu-id="5d502-118">使用 Polly 和实施断路器模式</span><span class="sxs-lookup"><span data-stu-id="5d502-118">Implementing a Circuit Breaker pattern with Polly</span></span>

<span data-ttu-id="5d502-119">作为在实现重试时，断路器的建议的方法是利用 Polly 类似的经过验证.NET 库。</span><span class="sxs-lookup"><span data-stu-id="5d502-119">As when implementing retries, the recommended approach for circuit breakers is to take advantage of proven .NET libraries like Polly.</span></span>

<span data-ttu-id="5d502-120">实现 HTTP 重试时，eShopOnContainers 应用程序使用 Polly 断路器策略。</span><span class="sxs-lookup"><span data-stu-id="5d502-120">The eShopOnContainers application uses the Polly Circuit Breaker policy when implementing HTTP retries.</span></span> <span data-ttu-id="5d502-121">事实上，应用程序将这两个策略应用到 ResilientHttpClient 实用程序类。</span><span class="sxs-lookup"><span data-stu-id="5d502-121">In fact, the application applies both policies to the ResilientHttpClient utility class.</span></span> <span data-ttu-id="5d502-122">每当 ResilientHttpClient 类型的对象使用的 HTTP 请求 （来自 eShopOnContainers) 时，您将在应用这两个这些策略，但您无法太添加其他策略。</span><span class="sxs-lookup"><span data-stu-id="5d502-122">Whenever you use an object of type ResilientHttpClient for HTTP requests (from eShopOnContainers), you will be applying both those policies, but you could add additional policies, too.</span></span>

<span data-ttu-id="5d502-123">唯一新增此处的内容所使用的 HTTP 调用重试代码是其中断路器策略向添加的策略，若要使用，列表末尾的以下代码所示的代码：</span><span class="sxs-lookup"><span data-stu-id="5d502-123">The only addition here to the code used for HTTP call retries is the code where you add the Circuit Breaker policy to the list of policies to use, as shown at the end of the following code:</span></span>

```csharp
public ResilientHttpClient CreateResilientHttpClient()
    => new ResilientHttpClient(CreatePolicies(), _logger);

private Policy[] CreatePolicies()
    => new Policy[]
    {
        Policy.Handle<HttpRequestException>()
            .WaitAndRetryAsync(
            // number of retries
            6,
            // exponential backofff
            retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)),
            // on retry
            (exception, timeSpan, retryCount, context) =>
            {
                var msg = $"Retry {retryCount} implemented with Polly RetryPolicy " +
                    $"of {context.PolicyKey} " +
                    $"at {context.ExecutionKey}, " +
                    $"due to: {exception}.";
                _logger.LogWarning(msg);
                _logger.LogDebug(msg);
            }),
            Policy.Handle<HttpRequestException>()
                .CircuitBreakerAsync(
                    // number of exceptions before breaking circuit
                    5,
                    // time circuit opened before retry
                    TimeSpan.FromMinutes(1),
                    (exception, duration) =>
                    {
                        // on circuit opened
                        _logger.LogTrace("Circuit breaker opened");
                    },
                    () =>
                    {
                        // on circuit closed
                        _logger.LogTrace("Circuit breaker reset");
                    })
    };
}
```

<span data-ttu-id="5d502-124">代码将策略添加到 HTTP 包装器。</span><span class="sxs-lookup"><span data-stu-id="5d502-124">The code adds a policy to the HTTP wrapper.</span></span> <span data-ttu-id="5d502-125">策略定义断路器将打开代码检测到指定的数目的连续异常 （在一行中的异常） 时，为传入 exceptionsAllowedBeforeBreaking 参数 (在此情况下为 5)。</span><span class="sxs-lookup"><span data-stu-id="5d502-125">That policy defines a circuit breaker that opens when the code detects the specified number of consecutive exceptions (exceptions in a row), as passed in the exceptionsAllowedBeforeBreaking parameter (5 in this case).</span></span> <span data-ttu-id="5d502-126">打开线路时，HTTP 请求不起作用，但在引发异常。</span><span class="sxs-lookup"><span data-stu-id="5d502-126">When the circuit is open, HTTP requests do not work, but an exception is raised.</span></span>

<span data-ttu-id="5d502-127">此外应该使用断路器将请求重定向到一个回退的基础结构，如果你可能必须部署在不同环境比客户端应用程序的特定资源或正在执行 HTTP 调用的服务中的问题。</span><span class="sxs-lookup"><span data-stu-id="5d502-127">Circuit breakers should also be used to redirect requests to a fallback infrastructure if you might have issues in a particular resource that is deployed in a different environment than the client application or service that is performing the HTTP call.</span></span> <span data-ttu-id="5d502-128">这样一来，如果在会影响你后端微服务但不是在客户端应用程序，数据中心中断客户端应用程序可以重定向到备用服务。</span><span class="sxs-lookup"><span data-stu-id="5d502-128">That way, if there is an outage in the datacenter that impacts only your backend microservices but not your client applications, the client applications can redirect to the fallback services.</span></span> <span data-ttu-id="5d502-129">Polly 正在计划新的策略来自动化这[故障转移策略](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy)方案。</span><span class="sxs-lookup"><span data-stu-id="5d502-129">Polly is planning a new policy to automate this [failover policy](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) scenario.</span></span>

<span data-ttu-id="5d502-130">当然，所有这些功能适用于管理中的.NET 代码，而不是让它自动为你管理的 azure，具有位置透明度从故障转移的情况。</span><span class="sxs-lookup"><span data-stu-id="5d502-130">Of course, all those features are for cases where you are managing the failover from within the .NET code, as opposed to having it managed automatically for you by Azure, with location transparency.</span></span>

## <a name="using-the-resilienthttpclient-utility-class-from-eshoponcontainers"></a><span data-ttu-id="5d502-131">使用从 eShopOnContainers ResilientHttpClient 实用程序类</span><span class="sxs-lookup"><span data-stu-id="5d502-131">Using the ResilientHttpClient utility class from eShopOnContainers</span></span>

<span data-ttu-id="5d502-132">类似于你如何使用.NET HttpClient 类的方式使用 ResilientHttpClient 实用程序类。</span><span class="sxs-lookup"><span data-stu-id="5d502-132">You use the ResilientHttpClient utility class in a way similar to how you use the .NET HttpClient class.</span></span> <span data-ttu-id="5d502-133">在以下示例从 eShopOnContainers MVC web 应用程序 （由 OrderController OrderingService 代理类） 中，通过 httpClient 参数的构造函数注入 ResilientHttpClient 对象。</span><span class="sxs-lookup"><span data-stu-id="5d502-133">In the following example from the eShopOnContainers MVC web application (the OrderingService agent class used by OrderController), the ResilientHttpClient object is injected through the httpClient parameter of the constructor.</span></span> <span data-ttu-id="5d502-134">然后，该对象用于执行 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="5d502-134">Then the object is used to perform HTTP requests.</span></span>

```csharp
public class OrderingService : IOrderingService
{
    private IHttpClient _apiClient;
    private readonly string _remoteServiceBaseUrl;
    private readonly IOptionsSnapshot<AppSettings> _settings;
    private readonly IHttpContextAccessor _httpContextAccesor;

    public OrderingService(IOptionsSnapshot<AppSettings> settings,
        IHttpContextAccessor httpContextAccesor,
        IHttpClient httpClient)
    {
        _remoteServiceBaseUrl = $"{settings.Value.OrderingUrl}/api/v1/orders";
        _settings = settings;
        _httpContextAccesor = httpContextAccesor;
        _apiClient = httpClient;
    }

    async public Task<List<Order>> GetMyOrders(ApplicationUser user)
    {
        var context = _httpContextAccesor.HttpContext;
        var token = await context.Authentication.GetTokenAsync("access_token");
        _apiClient.Inst.DefaultRequestHeaders.Authorization = new
            System.Net.Http.Headers.AuthenticationHeaderValue("Bearer", token);
        var ordersUrl = _remoteServiceBaseUrl;
        var dataString = await _apiClient.GetStringAsync(ordersUrl);
        var response = JsonConvert.DeserializeObject<List<Order>>(dataString);
        return response;
    }

    // Other methods ...
    async public Task CreateOrder(Order order)
    {
        var context = _httpContextAccesor.HttpContext;
        var token = await context.Authentication.GetTokenAsync("access_token");
        _apiClient.Inst.DefaultRequestHeaders.Authorization = new
            System.Net.Http.Headers.AuthenticationHeaderValue("Bearer", token);
        _apiClient.Inst.DefaultRequestHeaders.Add("x-requestid",
            order.RequestId.ToString());
        var ordersUrl = $"{_remoteServiceBaseUrl}/new";
        order.CardTypeId = 1;
        order.CardExpirationApiFormat();
        SetFakeIdToProducts(order);
        var response = await _apiClient.PostAsync(ordersUrl, order);
        response.EnsureSuccessStatusCode();
    }
}
```

<span data-ttu-id="5d502-135">每当\_apiClient 成员对象时，它在内部使用 Polly policiesؙ 使用包装类-重试策略，断路器策略中，你可能想要从 Polly 策略集合应用的任何其他策略。</span><span class="sxs-lookup"><span data-stu-id="5d502-135">Whenever the \_apiClient member object is used, it internally uses the wrapper class with Polly policiesؙ—the Retry policy, the Circuit Breaker policy, and any other policy that you might want to apply from the Polly policies collection.</span></span>

## <a name="testing-retries-in-eshoponcontainers"></a><span data-ttu-id="5d502-136">在 eShopOnContainers 中测试重试</span><span class="sxs-lookup"><span data-stu-id="5d502-136">Testing retries in eShopOnContainers</span></span>

<span data-ttu-id="5d502-137">每当在 Docker 主机中启动 eShopOnContainers 解决方案，它需要启动多个容器。</span><span class="sxs-lookup"><span data-stu-id="5d502-137">Whenever you start the eShopOnContainers solution in a Docker host, it needs to start multiple containers.</span></span> <span data-ttu-id="5d502-138">某些容器是启动并初始化，如 SQL Server 容器要稍慢一些。</span><span class="sxs-lookup"><span data-stu-id="5d502-138">Some of the containers are slower to start and initialize, like the SQL Server container.</span></span> <span data-ttu-id="5d502-139">这是尤其如此首次部署 eShopOnContainers 应用程序置于 Docker，因为它需要设置图像和数据库。</span><span class="sxs-lookup"><span data-stu-id="5d502-139">This is especially true the first time you deploy the eShopOnContainers application into Docker, because it needs to set up the images and the database.</span></span> <span data-ttu-id="5d502-140">某些容器启动速度比其他人可能会导致最初引发 HTTP 异常的服务的其余部分，即使设置在容器之间的依赖关系要慢事实 docker compose 级别，，如前面部分中所述。</span><span class="sxs-lookup"><span data-stu-id="5d502-140">The fact that some containers start slower than others can cause the rest of the services to initially throw HTTP exceptions, even if you set dependencies between containers at the docker-compose level, as explained in previous sections.</span></span> <span data-ttu-id="5d502-141">那些 docker-撰写容器之间的依赖关系是否在进程级别。</span><span class="sxs-lookup"><span data-stu-id="5d502-141">Those docker-compose dependencies between containers are just at the process level.</span></span> <span data-ttu-id="5d502-142">容器的入口点进程可能会启动，但 SQL Server 可能不是准备好进行查询。</span><span class="sxs-lookup"><span data-stu-id="5d502-142">The container’s entry point process might be started, but SQL Server might not be ready for queries.</span></span> <span data-ttu-id="5d502-143">将会导致错误，级联和应用程序尝试使用该特定容器时将引发异常。</span><span class="sxs-lookup"><span data-stu-id="5d502-143">The result can be a cascade of errors, and the application can get an exception when trying to consume that particular container.</span></span>

<span data-ttu-id="5d502-144">应用程序部署到云时，你还可能在启动时看到这种类型的错误。</span><span class="sxs-lookup"><span data-stu-id="5d502-144">You might also see this type of error on startup when the application is deploying to the cloud.</span></span> <span data-ttu-id="5d502-145">在这种情况下，orchestrators 可能来移动容器从一个节点或 VM 之间 （即，启动新实例） 时平衡群集的节点的容器数。</span><span class="sxs-lookup"><span data-stu-id="5d502-145">In that case, orchestrators might be moving containers from one node or VM to another (that is, starting new instances) when balancing the number of containers across the cluster’s nodes.</span></span>

<span data-ttu-id="5d502-146">EShopOnContainers 可以解决此问题的方法是使用我们本文前面所述的重试模式。</span><span class="sxs-lookup"><span data-stu-id="5d502-146">The way eShopOnContainers solves this issue is by using the Retry pattern we illustrated earlier.</span></span> <span data-ttu-id="5d502-147">它是原因，当从开始解决方案，你可能会收到日志跟踪或警告如下所示：</span><span class="sxs-lookup"><span data-stu-id="5d502-147">It is also why, when starting the solution, you might get log traces or warnings like the following:</span></span>

> <span data-ttu-id="5d502-148">"**使用 Polly 的 RetryPolicy 实现重试 1**，因为： System.Net.Http.HttpRequestException： 发送的请求时出错。</span><span class="sxs-lookup"><span data-stu-id="5d502-148">"**Retry 1 implemented with Polly's RetryPolicy**, due to: System.Net.Http.HttpRequestException: An error occurred while sending the request.</span></span><span data-ttu-id="5d502-149"> ---&gt;System.Net.Http.CurlException： 无法连接到服务器\\System.Net.Http.CurlHandler.ThrowIfCURLEError （CURLcode 错误） 在 n\\在 n \[...\].</span><span class="sxs-lookup"><span data-stu-id="5d502-149"> ---&gt; System.Net.Http.CurlException: Couldn't connect to server\\n at System.Net.Http.CurlHandler.ThrowIfCURLEError(CURLcode error)\\n at \[...\].</span></span>

## <a name="testing-the-circuit-breaker-in-eshoponcontainers"></a><span data-ttu-id="5d502-150">在 eShopOnContainers 中测试断路器</span><span class="sxs-lookup"><span data-stu-id="5d502-150">Testing the circuit breaker in eShopOnContainers</span></span>

<span data-ttu-id="5d502-151">有几种方法可以打开线路，还可以使用 eShopOnContainers 对它进行测试。</span><span class="sxs-lookup"><span data-stu-id="5d502-151">There are a few ways you can open the circuit and test it with eShopOnContainers.</span></span>

<span data-ttu-id="5d502-152">一个选项用于降低允许为 1 断路器策略中的重试次数和探究 Docker 重新部署整个解决方案。</span><span class="sxs-lookup"><span data-stu-id="5d502-152">One option is to lower the allowed number of retries to 1 in the circuit breaker policy and redeploy the whole solution into Docker.</span></span> <span data-ttu-id="5d502-153">与单个重试，存在很可能会在部署过程的 HTTP 请求将失败，断路器将打开，以及可能会出错。</span><span class="sxs-lookup"><span data-stu-id="5d502-153">With a single retry, there is a good chance that an HTTP request will fail during deployment, the circuit breaker will open, and you get an error.</span></span>

<span data-ttu-id="5d502-154">另一种方法是使用自定义在排序的微服务中实现的中间件。</span><span class="sxs-lookup"><span data-stu-id="5d502-154">Another option is to use custom middleware that is implemented in the ordering microservice.</span></span> <span data-ttu-id="5d502-155">启用此中间件后，它将捕获所有 HTTP 请求并返回状态代码 500。</span><span class="sxs-lookup"><span data-stu-id="5d502-155">When this middleware is enabled, it catches all HTTP requests and returns status code 500.</span></span> <span data-ttu-id="5d502-156">可以通过向失败发出 GET 请求来启用该中间件 URI，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5d502-156">You can enable the middleware by making a GET request to the failing URI, like the following:</span></span>

-   <span data-ttu-id="5d502-157">获取/出现故障</span><span class="sxs-lookup"><span data-stu-id="5d502-157">GET /failing</span></span>

<span data-ttu-id="5d502-158">此请求返回的中间件的当前状态。</span><span class="sxs-lookup"><span data-stu-id="5d502-158">This request returns the current state of the middleware.</span></span> <span data-ttu-id="5d502-159">如果启用了该中间件，则请求将返回状态代码 500。</span><span class="sxs-lookup"><span data-stu-id="5d502-159">If the middleware is enabled, the request return status code 500.</span></span> <span data-ttu-id="5d502-160">如果禁用了该中间件，则无响应。</span><span class="sxs-lookup"><span data-stu-id="5d502-160">If the middleware is disabled, there is no response.</span></span>

-   <span data-ttu-id="5d502-161">获取/失败？ 启用</span><span class="sxs-lookup"><span data-stu-id="5d502-161">GET /failing?enable</span></span>

<span data-ttu-id="5d502-162">此请求使该中间件。</span><span class="sxs-lookup"><span data-stu-id="5d502-162">This request enables the middleware.</span></span>

-   <span data-ttu-id="5d502-163">获取/失败？ 禁用</span><span class="sxs-lookup"><span data-stu-id="5d502-163">GET /failing?disable</span></span>

<span data-ttu-id="5d502-164">此请求禁用该中间件。</span><span class="sxs-lookup"><span data-stu-id="5d502-164">This request disables the middleware.</span></span>

<span data-ttu-id="5d502-165">例如，应用程序运行后，你可以通过发出请求的任何浏览器中使用以下 URI 启用该中间件。</span><span class="sxs-lookup"><span data-stu-id="5d502-165">For instance, once the application is running, you can enable the middleware by making a request using the following URI in any browser.</span></span> <span data-ttu-id="5d502-166">请注意，排序微服务使用端口 5102。</span><span class="sxs-lookup"><span data-stu-id="5d502-166">Note that the ordering microservice uses port 5102.</span></span>

<span data-ttu-id="5d502-167">http://localhost:5102 / 失败？ 启用</span><span class="sxs-lookup"><span data-stu-id="5d502-167">http://localhost:5102/failing?enable</span></span>

<span data-ttu-id="5d502-168">然后，可以选中状态使用 URI [http://localhost:5102 / 失败](http://localhost:5100/failing)，如图 10-4 中所示。</span><span class="sxs-lookup"><span data-stu-id="5d502-168">You can then check the status using the URI [http://localhost:5102/failing](http://localhost:5100/failing), as shown in Figure 10-4.</span></span>

![](./media/image4.png)

<span data-ttu-id="5d502-169">**图 10-4**。</span><span class="sxs-lookup"><span data-stu-id="5d502-169">**Figure 10-4**.</span></span> <span data-ttu-id="5d502-170">模拟与 ASP.NET 中间件失败</span><span class="sxs-lookup"><span data-stu-id="5d502-170">Simulating a failure with ASP.NET middleware</span></span>

<span data-ttu-id="5d502-171">此时，排序的微服务进行响应，并返回状态代码 500 每当你调用调用该录制。</span><span class="sxs-lookup"><span data-stu-id="5d502-171">At this point, the ordering microservice responds with status code 500 whenever you call invoke it.</span></span>

<span data-ttu-id="5d502-172">该中间件运行后，你可以尝试进行 MVC web 应用程序从订单。</span><span class="sxs-lookup"><span data-stu-id="5d502-172">Once the middleware is running, you can try making an order from the MVC web application.</span></span> <span data-ttu-id="5d502-173">由于请求失败，将打开线路。</span><span class="sxs-lookup"><span data-stu-id="5d502-173">Because the requests fails, the circuit will open.</span></span>

<span data-ttu-id="5d502-174">在下面的示例中，你可以看到 MVC web 应用程序具有 catch 块中，在下订单的逻辑。</span><span class="sxs-lookup"><span data-stu-id="5d502-174">In the following example, you can see that the MVC web application has a catch block in the logic for placing an order.</span></span> <span data-ttu-id="5d502-175">如果代码将捕获打开线路异常，它显示的用户友好条消息，告知等待。</span><span class="sxs-lookup"><span data-stu-id="5d502-175">If the code catches an open-circuit exception, it shows the user a friendly message telling them to wait.</span></span>

```csharp
[HttpPost]
public async Task<IActionResult> Create(Order model, string action)
{
    try
    {
        if (ModelState.IsValid)
        {
            var user = _appUserParser.Parse(HttpContext.User);
            await _orderSvc.CreateOrder(model);
            //Redirect to historic list.
            return RedirectToAction("Index");
        }
    }
    catch(BrokenCircuitException ex)
    {
        ModelState.AddModelError("Error",
            "It was not possible to create a new order, please try later on");
    }
    return View(model);
}
```

<span data-ttu-id="5d502-176">下面是摘要。</span><span class="sxs-lookup"><span data-stu-id="5d502-176">Here’s a summary.</span></span> <span data-ttu-id="5d502-177">重试策略尝试数次以进行 HTTP 请求和获取 HTTP 错误。</span><span class="sxs-lookup"><span data-stu-id="5d502-177">The Retry policy tries several times to make the HTTP request and gets HTTP errors.</span></span> <span data-ttu-id="5d502-178">当尝试次数达到断路器策略 （在此情况下，5） 设置的最大数字时，该应用程序会引发 BrokenCircuitException。</span><span class="sxs-lookup"><span data-stu-id="5d502-178">When the number of tries reaches the maximum number set for the Circuit Breaker policy (in this case, 5), the application throws a BrokenCircuitException.</span></span> <span data-ttu-id="5d502-179">结果是友好消息，图 10-5 中所示。</span><span class="sxs-lookup"><span data-stu-id="5d502-179">The result is a friendly message, as shown in Figure 10-5.</span></span>

![](./media/image5.png)

<span data-ttu-id="5d502-180">**图 10-5**。</span><span class="sxs-lookup"><span data-stu-id="5d502-180">**Figure 10-5**.</span></span> <span data-ttu-id="5d502-181">断路器返回到 UI 的错误</span><span class="sxs-lookup"><span data-stu-id="5d502-181">Circuit breaker returning an error to the UI</span></span>

<span data-ttu-id="5d502-182">你可以实现其他逻辑来确定何时打开线路。</span><span class="sxs-lookup"><span data-stu-id="5d502-182">You can implement different logic for when to open the circuit.</span></span> <span data-ttu-id="5d502-183">或者，如果没有回退数据中心或冗余的后端系统，你可以尝试针对不同的后端微服务的 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="5d502-183">Or you can try an HTTP request against a different back-end microservice if there is a fallback datacenter or redundant back-end system.</span></span>

<span data-ttu-id="5d502-184">最后，为 CircuitBreakerPolicy 的另一种可能是使用隔离 （该强制打开，并使保持打开的线路） 和重置 （这会再次关闭）。</span><span class="sxs-lookup"><span data-stu-id="5d502-184">Finally, another possibility for the CircuitBreakerPolicy is to use Isolate (which forces open and holds open the circuit) and Reset (which closes it again).</span></span> <span data-ttu-id="5d502-185">这些无法用于生成的策略中将调用隔离和重置直接的实用程序 HTTP 终结点。</span><span class="sxs-lookup"><span data-stu-id="5d502-185">These could be used to build a utility HTTP endpoint that invokes Isolate and Reset directly on the policy.</span></span> <span data-ttu-id="5d502-186">这样的 HTTP 终结点可能还用于，适当保护，暂时隔离下游系统，如你想要将其升级的生产环境中。</span><span class="sxs-lookup"><span data-stu-id="5d502-186">Such an HTTP endpoint could also be used, suitably secured, in production for temporarily isolating a downstream system, such as when you want to upgrade it.</span></span> <span data-ttu-id="5d502-187">或它无法跳闸线路后，手动以保护您怀疑出错的下游系统。</span><span class="sxs-lookup"><span data-stu-id="5d502-187">Or it could trip the circuit manually to protect a downstream system you suspect to be faulting.</span></span>

## <a name="adding-a-jitter-strategy-to-the-retry-policy"></a><span data-ttu-id="5d502-188">将抖动策略添加到重试策略</span><span class="sxs-lookup"><span data-stu-id="5d502-188">Adding a jitter strategy to the retry policy</span></span>

<span data-ttu-id="5d502-189">常规的重试策略可能会影响你的系统中的高并发性和可伸缩性，但在高争用的情况。</span><span class="sxs-lookup"><span data-stu-id="5d502-189">A regular Retry policy can impact your system in cases of high concurrency and scalability and under high contention.</span></span> <span data-ttu-id="5d502-190">若要解决的类似来自发生部分服务中断的多个客户端的重试次数的峰值，好的变通方法是将抖动策略添加到重试算法/策略。</span><span class="sxs-lookup"><span data-stu-id="5d502-190">To overcome peaks of similar retries coming from many clients in case of partial outages, a good workaround is to add a jitter strategy to the retry algorithm/policy.</span></span> <span data-ttu-id="5d502-191">通过将随机性添加到使用指数退让策略，这可以提高端到端系统的整体性能。</span><span class="sxs-lookup"><span data-stu-id="5d502-191">This can improve the overall performance of the end-to-end system by adding randomness to the exponential backoff.</span></span> <span data-ttu-id="5d502-192">此分布峰值时出现问题。</span><span class="sxs-lookup"><span data-stu-id="5d502-192">This spreads out the spikes when issues arise.</span></span> <span data-ttu-id="5d502-193">当你使用 Polly 时，代码以实现抖动无法类似下面的示例：</span><span class="sxs-lookup"><span data-stu-id="5d502-193">When you use Polly, code to implement jitter could look like the following example:</span></span>

```csharp
Random jitterer = new Random();
Policy.Handle<HttpResponseException>() // etc
    .WaitAndRetry(5, // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))
            + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

## <a name="additional-resources"></a><span data-ttu-id="5d502-194">其他资源</span><span class="sxs-lookup"><span data-stu-id="5d502-194">Additional resources</span></span>

-   <span data-ttu-id="5d502-195">**重试模式**
    [*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span><span class="sxs-lookup"><span data-stu-id="5d502-195">**Retry pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span></span>

-   <span data-ttu-id="5d502-196">**连接复原**（实体框架核） [ *https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span><span class="sxs-lookup"><span data-stu-id="5d502-196">**Connection Resiliency** (Entity Framework Core) [*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span></span>

-   <span data-ttu-id="5d502-197">**Polly** （.NET 恢复能力和暂时性故障处理库） [ *https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)</span><span class="sxs-lookup"><span data-stu-id="5d502-197">**Polly** (.NET resilience and transient-fault-handling library) [*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)</span></span>

-   <span data-ttu-id="5d502-198">**断路器模式**
    [*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span><span class="sxs-lookup"><span data-stu-id="5d502-198">**Circuit Breaker pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span></span>

-   <span data-ttu-id="5d502-199">**Marc Brooker。抖动： 使得操作更好地与随机性**https://brooker.co.za/blog/2015/03/21/backoff.html</span><span class="sxs-lookup"><span data-stu-id="5d502-199">**Marc Brooker. Jitter: Making Things Better With Randomness** https://brooker.co.za/blog/2015/03/21/backoff.html</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="5d502-200">[以前](implement-http-call-retries-exponential-backoff-polly.md) [下一步] (监视器应用 health.md)</span><span class="sxs-lookup"><span data-stu-id="5d502-200">[Previous] (implement-http-call-retries-exponential-backoff-polly.md) [Next] (monitor-app-health.md)</span></span>
