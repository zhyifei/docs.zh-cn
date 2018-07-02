---
title: 实现断路器模式
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 实现断路器模式
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/12/2017
ms.openlocfilehash: 2c89992c4c60ca7f1085050e6fed4922ecd4d8cc
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106119"
---
# <a name="implementing-the-circuit-breaker-pattern"></a><span data-ttu-id="4ac6f-103">实现断路器模式</span><span class="sxs-lookup"><span data-stu-id="4ac6f-103">Implementing the Circuit Breaker pattern</span></span>

<span data-ttu-id="4ac6f-104">如前文所述，需要处理某类故障，处理这类故障时，所需的时间并不固定，尝试连接远程服务或资源时就可能会发生这类故障。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-104">As noted earlier, you should handle faults that might take a variable amount of time to recover from, as might happen when you try to connect to a remote service or resource.</span></span> <span data-ttu-id="4ac6f-105">处理这类故障可以提高应用程序的稳定性和复原能力。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-105">Handling this type of fault can improve the stability and resiliency of an application.</span></span>

<span data-ttu-id="4ac6f-106">在分布式环境中，对远程资源和服务的调用可能由于暂时性故障而失败，例如网络连接速度较慢和超时或资源连接缓慢或暂时不可用。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-106">In a distributed environment, calls to remote resources and services can fail due to transient faults, such as slow network connections and timeouts, or if resources are being slow or are temporarily unavailable.</span></span> <span data-ttu-id="4ac6f-107">这些故障通常在一段时间之后会自动消失，应配备可靠强大的云应用程序，使用“重试”模式等策略来解决这些故障。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-107">These faults typically correct themselves after a short time, and a robust cloud application should be prepared to handle them by using a strategy like the Retry pattern.</span></span>

<span data-ttu-id="4ac6f-108">但也可能存在这种情况，由于意外事件引发故障，需要更长的时间来解决故障。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-108">However, there can also be situations where faults are due to unanticipated events that might take much longer to fix.</span></span> <span data-ttu-id="4ac6f-109">这些故障轻则导致部分连接中断，重则导致服务完全瘫痪。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-109">These faults can range in severity from a partial loss of connectivity to the complete failure of a service.</span></span> <span data-ttu-id="4ac6f-110">在这些情况下，应用程序持续重试一个操作可能毫无意义，因为操作不可能成功。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-110">In these situations, it might be pointless for an application to continually retry an operation that is unlikely to succeed.</span></span> <span data-ttu-id="4ac6f-111">相反，应对应用程序进行编码，使其接受已失败的操作，并相应解决故障。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-111">Instead, the application should be coded to accept that the operation has failed and handle the failure accordingly.</span></span>

<span data-ttu-id="4ac6f-112">断路器模式与重试模式的目的和用途不同。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-112">The Circuit Breaker pattern has a different purpose than the Retry pattern.</span></span> <span data-ttu-id="4ac6f-113">重试模式让应用程序能够重试一个操作，并预期操作最终会成功。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-113">The Retry pattern enables an application to retry an operation in the expectation that the operation will eventually succeed.</span></span> <span data-ttu-id="4ac6f-114">断路器模式阻止应用程序执行很可能会失败的操作。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-114">The Circuit Breaker pattern prevents an application from performing an operation that is likely to fail.</span></span> <span data-ttu-id="4ac6f-115">应用程序可将这两种模式结合起来，方法是使用重试模式，通过断路器来调用操作。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-115">An application can combine these two patterns by using the Retry pattern to invoke an operation through a circuit breaker.</span></span> <span data-ttu-id="4ac6f-116">但重试逻辑应能敏锐觉察断路器返回的任何异常，并在断路器指示故障并非暂时性故障时放弃重试尝试。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-116">However, the retry logic should be sensitive to any exceptions returned by the circuit breaker, and it should abandon retry attempts if the circuit breaker indicates that a fault is not transient.</span></span>

## <a name="implementing-a-circuit-breaker-pattern-with-polly"></a><span data-ttu-id="4ac6f-117">使用 Polly 实现断路器模式</span><span class="sxs-lookup"><span data-stu-id="4ac6f-117">Implementing a Circuit Breaker pattern with Polly</span></span>

<span data-ttu-id="4ac6f-118">实现重试操作时，建议的方法为断路器使用 Polly 这种经过验证的 .NET 库。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-118">As when implementing retries, the recommended approach for circuit breakers is to take advantage of proven .NET libraries like Polly.</span></span>

<span data-ttu-id="4ac6f-119">eShopOnContainers 应用程序实现 HTTP 重试时，使用 Polly 断路器策略。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-119">The eShopOnContainers application uses the Polly Circuit Breaker policy when implementing HTTP retries.</span></span> <span data-ttu-id="4ac6f-120">事实上，应用程序对 ResilientHttpClient 实用程序类同时应用两种策略。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-120">In fact, the application applies both policies to the ResilientHttpClient utility class.</span></span> <span data-ttu-id="4ac6f-121">每当将 ResilientHttpClient 类型的对象用于 HTTP 请求（来自 eShopOnContainers）时，会同时应用两种策略，但也可以添加其他策略。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-121">Whenever you use an object of type ResilientHttpClient for HTTP requests (from eShopOnContainers), you will be applying both those policies, but you could add additional policies, too.</span></span>

<span data-ttu-id="4ac6f-122">此处在用于 HTTP 调用重试的代码中添加的唯一内容是用于将断路器策略添加到策略列表的代码，如以下代码的结尾处所示：</span><span class="sxs-lookup"><span data-stu-id="4ac6f-122">The only addition here to the code used for HTTP call retries is the code where you add the Circuit Breaker policy to the list of policies to use, as shown at the end of the following code:</span></span>

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

<span data-ttu-id="4ac6f-123">此代码将一个策略添加到 HTTP 包装器。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-123">The code adds a policy to the HTTP wrapper.</span></span> <span data-ttu-id="4ac6f-124">该策略定义一个断路器，当代码检测到指定数目的连续异常（连续的一系列异常）时，该断路器会断开，这里的指定数目即为传入 exceptionsAllowedBeforeBreaking 参数的数目（在此情况下为 5）。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-124">That policy defines a circuit breaker that opens when the code detects the specified number of consecutive exceptions (exceptions in a row), as passed in the exceptionsAllowedBeforeBreaking parameter (5 in this case).</span></span> <span data-ttu-id="4ac6f-125">线路断开时，HTTP 请求不起作用，但会引发异常。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-125">When the circuit is open, HTTP requests do not work, but an exception is raised.</span></span>

<span data-ttu-id="4ac6f-126">如果一个特定资源可能出问题，且该资源部署在不同于执行 HTTP 调用的客户端应用程序或服务的环境中，则还应使用断路器将请求重定向到回退基础结构。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-126">Circuit breakers should also be used to redirect requests to a fallback infrastructure if you might have issues in a particular resource that is deployed in a different environment than the client application or service that is performing the HTTP call.</span></span> <span data-ttu-id="4ac6f-127">这样一来，如果数据中心发生故障，但该故障只影响后端微服务，而不影响客户端应用程序，则客户端应用程序可以重定向到回退服务。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-127">That way, if there is an outage in the datacenter that impacts only your backend microservices but not your client applications, the client applications can redirect to the fallback services.</span></span> <span data-ttu-id="4ac6f-128">Polly 正在规划新策略，用于自动实现此[故障转移策略](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy)方案。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-128">Polly is planning a new policy to automate this [failover policy](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) scenario.</span></span>

<span data-ttu-id="4ac6f-129">当然，所有这些功能均适用于从 .NET 代码内部管理故障转移的情况，与由 Azure 自动管理的情况相反（位置透明化）。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-129">Of course, all those features are for cases where you are managing the failover from within the .NET code, as opposed to having it managed automatically for you by Azure, with location transparency.</span></span>

## <a name="using-the-resilienthttpclient-utility-class-from-eshoponcontainers"></a><span data-ttu-id="4ac6f-130">从 eShopOnContainers 使用 ResilientHttpClient 实用程序类</span><span class="sxs-lookup"><span data-stu-id="4ac6f-130">Using the ResilientHttpClient utility class from eShopOnContainers</span></span>

<span data-ttu-id="4ac6f-131">使用 ResilientHttpClient 实用程序类的方式与使用 .NET HttpClient 类的方式相似。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-131">You use the ResilientHttpClient utility class in a way similar to how you use the .NET HttpClient class.</span></span> <span data-ttu-id="4ac6f-132">在以下源自 eShopOnContainers MVC web 应用程序（供 OrderController 使用的 OrderingService 代理类）的示例中，通过构造函数的 httpClient 参数注入 ResilientHttpClient 对象。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-132">In the following example from the eShopOnContainers MVC web application (the OrderingService agent class used by OrderController), the ResilientHttpClient object is injected through the httpClient parameter of the constructor.</span></span> <span data-ttu-id="4ac6f-133">然后使用该对象执行 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-133">Then the object is used to perform HTTP requests.</span></span>

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

<span data-ttu-id="4ac6f-134">每当使用 \_apiClient 成员对象时，它会在内部配合使用包装类和 Polly 策略—重试策略、断路器策略和任何其他想从 Polly 策略集合中应用的策略。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-134">Whenever the \_apiClient member object is used, it internally uses the wrapper class with Polly policiesؙ—the Retry policy, the Circuit Breaker policy, and any other policy that you might want to apply from the Polly policies collection.</span></span>

## <a name="testing-retries-in-eshoponcontainers"></a><span data-ttu-id="4ac6f-135">在 eShopOnContainers 中测试重试</span><span class="sxs-lookup"><span data-stu-id="4ac6f-135">Testing retries in eShopOnContainers</span></span>

<span data-ttu-id="4ac6f-136">每当在 Docker 主机中启动 eShopOnContainers 解决方案时，它需要启动多个容器。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-136">Whenever you start the eShopOnContainers solution in a Docker host, it needs to start multiple containers.</span></span> <span data-ttu-id="4ac6f-137">启动和初始化某些容器时会比较慢，如 SQL Server 容器。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-137">Some of the containers are slower to start and initialize, like the SQL Server container.</span></span> <span data-ttu-id="4ac6f-138">尤其是首次在 Docker 中部署 eShopOnContainers 应用程序时，因为它需要设置映像和数据库。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-138">This is especially true the first time you deploy the eShopOnContainers application into Docker, because it needs to set up the images and the database.</span></span> <span data-ttu-id="4ac6f-139">某些容器的启动速度比其他容器慢，这可能导致其余服务一开始会引发 HTTP 异常，即使在 docker-compose 级别设置容器之间的依赖关系也会如此，如前面部分中所述。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-139">The fact that some containers start slower than others can cause the rest of the services to initially throw HTTP exceptions, even if you set dependencies between containers at the docker-compose level, as explained in previous sections.</span></span> <span data-ttu-id="4ac6f-140">容器之间的那些 docker-compose 依赖关系只存在于进程级别。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-140">Those docker-compose dependencies between containers are just at the process level.</span></span> <span data-ttu-id="4ac6f-141">可能容器的入口点进程已启动，但 SQL Server 可能还不能响应查询。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-141">The container’s entry point process might be started, but SQL Server might not be ready for queries.</span></span> <span data-ttu-id="4ac6f-142">这是一连串错误导致的结果，应用程序在尝试使用该特定容器时可能引发异常。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-142">The result can be a cascade of errors, and the application can get an exception when trying to consume that particular container.</span></span>

<span data-ttu-id="4ac6f-143">在应用程序部署到云时，也可能在启动时看到这种类型的错误。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-143">You might also see this type of error on startup when the application is deploying to the cloud.</span></span> <span data-ttu-id="4ac6f-144">在这种情况下，业务流程协调程序可能会将容器从一个节点或 VM 移动到另一个（即启动新实例），以平衡群集节点中的容器数。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-144">In that case, orchestrators might be moving containers from one node or VM to another (that is, starting new instances) when balancing the number of containers across the cluster’s nodes.</span></span>

<span data-ttu-id="4ac6f-145">eShopOnContainers 解决此问题的方法是使用前文所述的重试模式。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-145">The way eShopOnContainers solves this issue is by using the Retry pattern we illustrated earlier.</span></span> <span data-ttu-id="4ac6f-146">这也是为什么启动解决方案时可能会收到如下所示的日志跟踪或警告：</span><span class="sxs-lookup"><span data-stu-id="4ac6f-146">It is also why, when starting the solution, you might get log traces or warnings like the following:</span></span>

> <span data-ttu-id="4ac6f-147">“**已使用 Polly 的 RetryPolicy 实现重试 1**，引发原因：System.Net.Http.HttpRequestException：发送请求时出错。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-147">"**Retry 1 implemented with Polly's RetryPolicy**, due to: System.Net.Http.HttpRequestException: An error occurred while sending the request.</span></span><span data-ttu-id="4ac6f-148"> ---&gt; System.Net.Http.CurlException：无法连接到服务器\\n 位置：System.Net.Http.CurlHandler.ThrowIfCURLEError(CURLcode error)\\n 位置：\[...\]。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-148"> ---&gt; System.Net.Http.CurlException: Couldn't connect to server\\n at System.Net.Http.CurlHandler.ThrowIfCURLEError(CURLcode error)\\n at \[...\].</span></span>

## <a name="testing-the-circuit-breaker-in-eshoponcontainers"></a><span data-ttu-id="4ac6f-149">在 eShopOnContainers 中测试断路器</span><span class="sxs-lookup"><span data-stu-id="4ac6f-149">Testing the circuit breaker in eShopOnContainers</span></span>

<span data-ttu-id="4ac6f-150">有几种方法可以打开线路，并使用 eShopOnContainers 进行测试。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-150">There are a few ways you can open the circuit and test it with eShopOnContainers.</span></span>

<span data-ttu-id="4ac6f-151">一种方法是在断路器策略中将允许的重试次数减少为 1 次，并将整个解决方案重新部署到 Docker。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-151">One option is to lower the allowed number of retries to 1 in the circuit breaker policy and redeploy the whole solution into Docker.</span></span> <span data-ttu-id="4ac6f-152">如果设为一次重试，部署过程中 HTTP 请求失败的可能性就会很大，断路器会打开，然后收到错误。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-152">With a single retry, there is a good chance that an HTTP request will fail during deployment, the circuit breaker will open, and you get an error.</span></span>

<span data-ttu-id="4ac6f-153">另一种方法是使用 `Basket` 微服务中实现的自定义中间件。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-153">Another option is to use custom middleware that is implemented in the `Basket` microservice.</span></span> <span data-ttu-id="4ac6f-154">启用此中间件后，它会捕获所有 HTTP 请求并返回状态代码 500。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-154">When this middleware is enabled, it catches all HTTP requests and returns status code 500.</span></span> <span data-ttu-id="4ac6f-155">可以通过向失败 URI 发出 GET 请求来启用此中间件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4ac6f-155">You can enable the middleware by making a GET request to the failing URI, like the following:</span></span>

-   <span data-ttu-id="4ac6f-156">GET /failing</span><span class="sxs-lookup"><span data-stu-id="4ac6f-156">GET /failing</span></span>

<span data-ttu-id="4ac6f-157">此请求返回中间件的当前状态。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-157">This request returns the current state of the middleware.</span></span> <span data-ttu-id="4ac6f-158">如果启用了中间件，则请求返回状态代码 500。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-158">If the middleware is enabled, the request return status code 500.</span></span> <span data-ttu-id="4ac6f-159">如果禁用了中间件，则无响应。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-159">If the middleware is disabled, there is no response.</span></span>

-   <span data-ttu-id="4ac6f-160">GET /failing?enable</span><span class="sxs-lookup"><span data-stu-id="4ac6f-160">GET /failing?enable</span></span>

<span data-ttu-id="4ac6f-161">此请求启用中间件。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-161">This request enables the middleware.</span></span>

-   <span data-ttu-id="4ac6f-162">GET /failing?disable</span><span class="sxs-lookup"><span data-stu-id="4ac6f-162">GET /failing?disable</span></span>

<span data-ttu-id="4ac6f-163">此请求禁用中间件。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-163">This request disables the middleware.</span></span>

<span data-ttu-id="4ac6f-164">例如，应用程序运行后，可立即通过在任何浏览器中使用以下 URI 发出请求，来启用中间件。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-164">For instance, once the application is running, you can enable the middleware by making a request using the following URI in any browser.</span></span> <span data-ttu-id="4ac6f-165">请注意，订单微服务使用端口 5103。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-165">Note that the ordering microservice uses port 5103.</span></span>

http://localhost:5103/failing?enable

<span data-ttu-id="4ac6f-166">然后可以使用 URI [http://localhost:5103/failing](http://localhost:5103/failing) 检查状态，如图 10-4 中所示。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-166">You can then check the status using the URI [http://localhost:5103/failing](http://localhost:5103/failing), as shown in Figure 10-4.</span></span>

![](./media/image4.png)

<span data-ttu-id="4ac6f-167">**图 10-4**。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-167">**Figure 10-4**.</span></span> <span data-ttu-id="4ac6f-168">正在检查“失败”的 ASP.NET 中间件的状态 – 在此例中为禁用状态。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-168">Checking the state of the “Failing” ASP.NET middleware – In this case, disabled.</span></span> 

<span data-ttu-id="4ac6f-169">在这种情况下，每当调用市场篮微服务时，微服务就会使用状态代码 500 进行响应。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-169">At this point, the Basket microservice responds with status code 500 whenever you call invoke it.</span></span>

<span data-ttu-id="4ac6f-170">中间件开始运行后，便可尝试从 MVC web 应用程序下订单。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-170">Once the middleware is running, you can try making an order from the MVC web application.</span></span> <span data-ttu-id="4ac6f-171">由于请求失败，线路将打开。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-171">Because the requests fails, the circuit will open.</span></span>

<span data-ttu-id="4ac6f-172">在下面的示例中，可以看到 MVC web 应用程序在用于下订单的逻辑中具有一个捕获块。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-172">In the following example, you can see that the MVC web application has a catch block in the logic for placing an order.</span></span> <span data-ttu-id="4ac6f-173">如果代码捕获了一个开路异常，会向用户显示一条友好消息，请用户等待。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-173">If the code catches an open-circuit exception, it shows the user a friendly message telling them to wait.</span></span>

```csharp
public class CartController : Controller
{
    //…
    public async Task<IActionResult> Index()
    {
        try
        {
            //… Other code
        }
        catch (BrokenCircuitException)
        {
            // Catches error when Basket.api is in circuit-opened mode                 
            HandleBrokenCircuitException();
        }
        return View();
    }       

    private void HandleBrokenCircuitException()
    {
        TempData["BasketInoperativeMsg"] = "Basket Service is inoperative, please try later on. (Business message due to Circuit-Breaker)";
    }
}
```

<span data-ttu-id="4ac6f-174">下面是摘要。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-174">Here’s a summary.</span></span> <span data-ttu-id="4ac6f-175">重试策略尝试数次发出 HTTP 请求，并获取 HTTP 错误。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-175">The Retry policy tries several times to make the HTTP request and gets HTTP errors.</span></span> <span data-ttu-id="4ac6f-176">当尝试次数达到断路器策略设置的最大次数时（此例中为 5），应用程序会引发 BrokenCircuitException。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-176">When the number of tries reaches the maximum number set for the Circuit Breaker policy (in this case, 5), the application throws a BrokenCircuitException.</span></span> <span data-ttu-id="4ac6f-177">结果是一条友好消息，如图 10-5 中所示。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-177">The result is a friendly message, as shown in Figure 10-5.</span></span>

![](./media/image5.png)

<span data-ttu-id="4ac6f-178">**图 10-5**。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-178">**Figure 10-5**.</span></span> <span data-ttu-id="4ac6f-179">断路器向 UI 返回一个错误</span><span class="sxs-lookup"><span data-stu-id="4ac6f-179">Circuit breaker returning an error to the UI</span></span>

<span data-ttu-id="4ac6f-180">可以实现其他逻辑来指定何时打开线路。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-180">You can implement different logic for when to open the circuit.</span></span> <span data-ttu-id="4ac6f-181">或如果有一个回退数据中心或冗余的后端系统，可尝试对另一个后端微服务发出 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-181">Or you can try an HTTP request against a different back-end microservice if there is a fallback datacenter or redundant back-end system.</span></span>

<span data-ttu-id="4ac6f-182">最后，针对 CircuitBreakerPolicy 的另一种可能操作是使用隔离（强制打开线路并保持为打开状态）和重置（再次关闭路线）。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-182">Finally, another possibility for the CircuitBreakerPolicy is to use Isolate (which forces open and holds open the circuit) and Reset (which closes it again).</span></span> <span data-ttu-id="4ac6f-183">可使用这些操作构建一个实用程序 HTTP 终结点，用于在策略上直接调用隔离和重置。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-183">These could be used to build a utility HTTP endpoint that invokes Isolate and Reset directly on the policy.</span></span> <span data-ttu-id="4ac6f-184">还可以在生产中以合适的安全程度使用这种 HTTP 终结点，用于临时隔离下游系统，比如在想要升级系统的时候。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-184">Such an HTTP endpoint could also be used, suitably secured, in production for temporarily isolating a downstream system, such as when you want to upgrade it.</span></span> <span data-ttu-id="4ac6f-185">或可手动打开线路，以保护疑似发生故障的下游系统。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-185">Or it could trip the circuit manually to protect a downstream system you suspect to be faulting.</span></span>

## <a name="adding-a-jitter-strategy-to-the-retry-policy"></a><span data-ttu-id="4ac6f-186">将抖动策略添加到重试策略</span><span class="sxs-lookup"><span data-stu-id="4ac6f-186">Adding a jitter strategy to the retry policy</span></span>

<span data-ttu-id="4ac6f-187">在高并发率、高可伸缩性和高争用的情况下，常规重试策略可能会对系统产生影响。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-187">A regular Retry policy can impact your system in cases of high concurrency and scalability and under high contention.</span></span> <span data-ttu-id="4ac6f-188">在部分运行中断的情况下，有可能会有许多客户端同时发出相似的重试操作，从而形成操作高峰，为克服这种情况，一个好办法是向重试算法或策略中添加抖动策略。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-188">To overcome peaks of similar retries coming from many clients in case of partial outages, a good workaround is to add a jitter strategy to the retry algorithm/policy.</span></span> <span data-ttu-id="4ac6f-189">由于增加了指数退避的随机性，这可能会改进端到端系统的整体性能。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-189">This can improve the overall performance of the end-to-end system by adding randomness to the exponential backoff.</span></span> <span data-ttu-id="4ac6f-190">这样在出现问题时可以分散峰值。</span><span class="sxs-lookup"><span data-stu-id="4ac6f-190">This spreads out the spikes when issues arise.</span></span> <span data-ttu-id="4ac6f-191">使用 Polly 时，用于实现抖动的代码类似下面的示例：</span><span class="sxs-lookup"><span data-stu-id="4ac6f-191">When you use Polly, code to implement jitter could look like the following example:</span></span>

```csharp
Random jitterer = new Random();
Policy.Handle<HttpResponseException>() // etc
    .WaitAndRetry(5, // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))
            + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

## <a name="additional-resources"></a><span data-ttu-id="4ac6f-192">其他资源</span><span class="sxs-lookup"><span data-stu-id="4ac6f-192">Additional resources</span></span>

-   <span data-ttu-id="4ac6f-193">**重试模式** 
    [*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span><span class="sxs-lookup"><span data-stu-id="4ac6f-193">**Retry pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span></span>

-   <span data-ttu-id="4ac6f-194">**连接复原** (Entity Framework Core)[*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span><span class="sxs-lookup"><span data-stu-id="4ac6f-194">**Connection Resiliency** (Entity Framework Core) [*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span></span>

-   <span data-ttu-id="4ac6f-195">**Polly**（.NET 的恢复和暂时性故障处理库）[*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)</span><span class="sxs-lookup"><span data-stu-id="4ac6f-195">**Polly** (.NET resilience and transient-fault-handling library) [*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)</span></span>

-   <span data-ttu-id="4ac6f-196">**断路器模式**
    [*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span><span class="sxs-lookup"><span data-stu-id="4ac6f-196">**Circuit Breaker pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span></span>

-   <span data-ttu-id="4ac6f-197">**Marc Brooker。抖动：随机性使操作变得更好**https://brooker.co.za/blog/2015/03/21/backoff.html</span><span class="sxs-lookup"><span data-stu-id="4ac6f-197">**Marc Brooker. Jitter: Making Things Better With Randomness** https://brooker.co.za/blog/2015/03/21/backoff.html</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="4ac6f-198">[上一页](implement-http-call-retries-exponential-backoff-polly.md)
[下一页](monitor-app-health.md)</span><span class="sxs-lookup"><span data-stu-id="4ac6f-198">[Previous](implement-http-call-retries-exponential-backoff-polly.md)
[Next](monitor-app-health.md)</span></span>
