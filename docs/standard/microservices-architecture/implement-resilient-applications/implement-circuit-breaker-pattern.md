---
title: 实现断路器模式
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 实现断路器模式，作为对 Http 重试的补充系统
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 07/03/2018
ms.openlocfilehash: 8cd3564e5240ec5a8783edb336957549be27ea6a
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45647192"
---
# <a name="implement-the-circuit-breaker-pattern"></a><span data-ttu-id="fef25-103">实现断路器模式</span><span class="sxs-lookup"><span data-stu-id="fef25-103">Implement the Circuit Breaker pattern</span></span>

<span data-ttu-id="fef25-104">如前文所述，需要处理某类故障，处理这类故障时，所需的时间并不固定，尝试连接远程服务或资源时就可能会发生这类故障。</span><span class="sxs-lookup"><span data-stu-id="fef25-104">As noted earlier, you should handle faults that might take a variable amount of time to recover from, as might happen when you try to connect to a remote service or resource.</span></span> <span data-ttu-id="fef25-105">处理这类故障可以提高应用程序的稳定性和复原能力。</span><span class="sxs-lookup"><span data-stu-id="fef25-105">Handling this type of fault can improve the stability and resiliency of an application.</span></span>

<span data-ttu-id="fef25-106">在分布式环境中，对远程资源和服务的调用可能由于暂时性故障而失败，例如网络连接速度较慢和超时或资源响应缓慢或暂时不可用。</span><span class="sxs-lookup"><span data-stu-id="fef25-106">In a distributed environment, calls to remote resources and services can fail due to transient faults, such as slow network connections and timeouts, or if resources are responding slowly or are temporarily unavailable.</span></span> <span data-ttu-id="fef25-107">这些故障通常在一段时间之后会自动消失，应配备可靠强大的云应用程序，使用“重试模式”等策略来解决这些故障。</span><span class="sxs-lookup"><span data-stu-id="fef25-107">These faults typically correct themselves after a short time, and a robust cloud application should be prepared to handle them by using a strategy like the "Retry pattern".</span></span> 

<span data-ttu-id="fef25-108">但也可能存在这种情况，由于意外事件引发故障，需要更长的时间来解决故障。</span><span class="sxs-lookup"><span data-stu-id="fef25-108">However, there can also be situations where faults are due to unanticipated events that might take much longer to fix.</span></span> <span data-ttu-id="fef25-109">这些故障轻则导致部分连接中断，重则导致服务完全瘫痪。</span><span class="sxs-lookup"><span data-stu-id="fef25-109">These faults can range in severity from a partial loss of connectivity to the complete failure of a service.</span></span> <span data-ttu-id="fef25-110">在这些情况下，应用程序持续重试一个操作可能毫无意义，因为操作不可能成功。</span><span class="sxs-lookup"><span data-stu-id="fef25-110">In these situations, it might be pointless for an application to continually retry an operation that is unlikely to succeed.</span></span> 

<span data-ttu-id="fef25-111">相反，应对应用程序进行编码，使其接受已失败的操作，并相应解决故障。</span><span class="sxs-lookup"><span data-stu-id="fef25-111">Instead, the application should be coded to accept that the operation has failed and handle the failure accordingly.</span></span>

<span data-ttu-id="fef25-112">如果不恰当地使用 Http 重试，可能会在自己的软件中产生拒绝服务 ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) 攻击。</span><span class="sxs-lookup"><span data-stu-id="fef25-112">Using Http retries carelessly could result in creating a Denial of Service ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) attack within your own software.</span></span> <span data-ttu-id="fef25-113">由于微服务出现故障或执行缓慢，多个客户端可能会反复重试失败的请求。</span><span class="sxs-lookup"><span data-stu-id="fef25-113">As a microservice fails or performs slowly, multiple clients might repeatedly retry failed requests.</span></span> <span data-ttu-id="fef25-114">这会产生极高的风险，导致针对失败的服务的流量成倍增加。</span><span class="sxs-lookup"><span data-stu-id="fef25-114">That creates a dangerous risk of exponentially increasing traffic targeted at the failing service.</span></span>

<span data-ttu-id="fef25-115">因此，需要某种防御屏障，以便在不断尝试无意义时停止过多的请求。</span><span class="sxs-lookup"><span data-stu-id="fef25-115">Therefore, you need some kind of defense barrier so that excessive requests stop when it is not worth keeping trying.</span></span> <span data-ttu-id="fef25-116">此防御屏障正是断路器。</span><span class="sxs-lookup"><span data-stu-id="fef25-116">That defense barrier is precisely the circuit breaker.</span></span>

<span data-ttu-id="fef25-117">断路器模式与“重试模式”的目的和用途不同。</span><span class="sxs-lookup"><span data-stu-id="fef25-117">The Circuit Breaker pattern has a different purpose than the "Retry pattern".</span></span> <span data-ttu-id="fef25-118">“重试模式”让应用程序能够重试某项操作，并预期该操作最终会成功。</span><span class="sxs-lookup"><span data-stu-id="fef25-118">The "Retry pattern" enables an application to retry an operation in the expectation that the operation will eventually succeed.</span></span> <span data-ttu-id="fef25-119">断路器模式阻止应用程序执行很可能会失败的操作。</span><span class="sxs-lookup"><span data-stu-id="fef25-119">The Circuit Breaker pattern prevents an application from performing an operation that is likely to fail.</span></span> <span data-ttu-id="fef25-120">应用程序可以合并这两种模式。</span><span class="sxs-lookup"><span data-stu-id="fef25-120">An application can combine these two patterns.</span></span> <span data-ttu-id="fef25-121">但重试逻辑应能敏锐觉察断路器返回的任何异常，并在断路器指示故障并非暂时性故障时放弃重试尝试。</span><span class="sxs-lookup"><span data-stu-id="fef25-121">However, the retry logic should be sensitive to any exception returned by the circuit breaker, and it should abandon retry attempts if the circuit breaker indicates that a fault is not transient.</span></span>

## <a name="implement-circuit-breaker-pattern-with-httpclientfactory-and-polly"></a><span data-ttu-id="fef25-122">使用 HttpClientFactory 和 Polly 实现断路器模式</span><span class="sxs-lookup"><span data-stu-id="fef25-122">Implement Circuit Breaker pattern with HttpClientFactory and Polly</span></span>

<span data-ttu-id="fef25-123">在实现重试操作时，建议的方法为断路器使用 Polly 这种经过验证的 .NET 库以及它与 HttpClientFactory 的本机集成。</span><span class="sxs-lookup"><span data-stu-id="fef25-123">As when implementing retries, the recommended approach for circuit breakers is to take advantage of proven .NET libraries like Polly and its native integration with HttpClientFactory.</span></span>

<span data-ttu-id="fef25-124">在使用 HttpClientFactory 时，将断路器策略添加到 HttpClientFactory 传出中间件管道就像将单个增量代码片段添加到已有代码一样简单。</span><span class="sxs-lookup"><span data-stu-id="fef25-124">Adding a circuit breaker policy into your HttpClientFactory outgoing middleware pipeline is as simple as adding a single incremental piece of code to what you already have when using HttpClientFactory.</span></span>

<span data-ttu-id="fef25-125">此处在用于 HTTP 调用重试的代码中添加的唯一内容是用于将断路器策略添加到策略列表的代码（如以下增量代码所示，该代码是 ConfigureServices() 方法的一部分）。</span><span class="sxs-lookup"><span data-stu-id="fef25-125">The only addition here to the code used for HTTP call retries is the code where you add the Circuit Breaker policy to the list of policies to use, as shown in the following incremental code, part of the ConfigureServices() method.</span></span>

```csharp
//ConfigureServices()  - Startup.cs
services.AddHttpClient<IBasketService, BasketService>()
        .SetHandlerLifetime(TimeSpan.FromMinutes(5))  //Set lifetime to 5 minutes
        .AddPolicyHandler(GetRetryPolicy())
        .AddPolicyHandler(GetCircuitBreakerPolicy());
```

<span data-ttu-id="fef25-126">`AddPolicyHandler()` 方法将策略添加至将要使用的 HttpClient 对象。</span><span class="sxs-lookup"><span data-stu-id="fef25-126">The `AddPolicyHandler()`method is what adds policies to the HttpClient objects you will use.</span></span> <span data-ttu-id="fef25-127">在这种情况下，它会为断路器添加 Polly 策略。</span><span class="sxs-lookup"><span data-stu-id="fef25-127">In this case, it is adding a Polly policy for a circuit breaker.</span></span>

<span data-ttu-id="fef25-128">为了获取更为模块化的方法，会在一个名为 GetCircuitBreakerPolicy() 的单独方法中定义断路器策略，如下列代码所示。</span><span class="sxs-lookup"><span data-stu-id="fef25-128">In order to have a more modular approach, the Circuit Breaker Policy is defined in a separate method named GetCircuitBreakerPolicy(), as the following code.</span></span>

```csharp
static IAsyncPolicy<HttpResponseMessage> GetCircuitBreakerPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .CircuitBreakerAsync(5, TimeSpan.FromSeconds(30));
}
```

<span data-ttu-id="fef25-129">上述代码示例配置了断路器策略，因此，如果在重试 Http 请求时出现五个连续故障，则会中断或断开线路。</span><span class="sxs-lookup"><span data-stu-id="fef25-129">In the code example above, the circuit breaker policy is configured so it breaks or opens the circuit when there have been five consecutive faults when retrying the Http requests.</span></span> <span data-ttu-id="fef25-130">此时，电路将断开 30 秒：在此期间，断路器会立即中止呼叫，而不是拨打电话。</span><span class="sxs-lookup"><span data-stu-id="fef25-130">When that happens, the circuit will break for 30 seconds: in that period, calls will be failed immediately by the circuit-breaker rather than actually be placed.</span></span>  <span data-ttu-id="fef25-131">该策略自动将[相关异常和 HTTP 状态代码](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1#handle-transient-faults)解释为故障。</span><span class="sxs-lookup"><span data-stu-id="fef25-131">The policy automatically interprets [relevant exceptions and HTTP status codes](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1#handle-transient-faults) as faults.</span></span>  

<span data-ttu-id="fef25-132">如果一个特定资源出现问题，且该资源部署在不同于执行 HTTP 调用的客户端应用程序或服务的环境中，则还应使用断路器将请求重定向到回退基础结构。</span><span class="sxs-lookup"><span data-stu-id="fef25-132">Circuit breakers should also be used to redirect requests to a fallback infrastructure if you had issues in a particular resource that is deployed in a different environment than the client application or service that is performing the HTTP call.</span></span> <span data-ttu-id="fef25-133">这样一来，如果数据中心发生故障，但该故障只影响后端微服务，而不影响客户端应用程序，则客户端应用程序可以重定向到回退服务。</span><span class="sxs-lookup"><span data-stu-id="fef25-133">That way, if there is an outage in the datacenter that impacts only your backend microservices but not your client applications, the client applications can redirect to the fallback services.</span></span> <span data-ttu-id="fef25-134">Polly 正在规划新策略，用于自动实现此[故障转移策略](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy)方案。</span><span class="sxs-lookup"><span data-stu-id="fef25-134">Polly is planning a new policy to automate this [failover policy](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) scenario.</span></span> 

<span data-ttu-id="fef25-135">所有这些功能均适用于从 .NET 代码内部管理故障转移的情况，与由 Azure 自动管理的情况相反（位置透明化）。</span><span class="sxs-lookup"><span data-stu-id="fef25-135">All those features are for cases where you're managing the failover from within the .NET code, as opposed to having it managed automatically for you by Azure, with location transparency.</span></span> 

<span data-ttu-id="fef25-136">从使用情况角度来看，在使用 HttpClient 时，无需添加新内容，因为该代码与结合使用 HttpClientFactory 和 HttpClient 时所使用的代码相同，如之前部分所述。</span><span class="sxs-lookup"><span data-stu-id="fef25-136">From a usage point of view, when using HttpClient, there’s no need to add anything new here because the code is the same than when using HttpClient with HttpClientFactory, as shown in previous sections.</span></span> 

## <a name="testing-http-retries-and-circuit-breakers-in-eshoponcontainers"></a><span data-ttu-id="fef25-137">在 eShopOnContainers 中测试 Http 重试和断路器</span><span class="sxs-lookup"><span data-stu-id="fef25-137">Testing Http retries and circuit breakers in eShopOnContainers</span></span>

<span data-ttu-id="fef25-138">每当在 Docker 主机中启动 eShopOnContainers 解决方案时，它需要启动多个容器。</span><span class="sxs-lookup"><span data-stu-id="fef25-138">Whenever you start the eShopOnContainers solution in a Docker host, it needs to start multiple containers.</span></span> <span data-ttu-id="fef25-139">启动和初始化某些容器时会比较慢，如 SQL Server 容器。</span><span class="sxs-lookup"><span data-stu-id="fef25-139">Some of the containers are slower to start and initialize, like the SQL Server container.</span></span> <span data-ttu-id="fef25-140">尤其是首次在 Docker 中部署 eShopOnContainers 应用程序时，因为它需要设置映像和数据库。</span><span class="sxs-lookup"><span data-stu-id="fef25-140">This is especially true the first time you deploy the eShopOnContainers application into Docker, because it needs to set up the images and the database.</span></span> <span data-ttu-id="fef25-141">某些容器的启动速度比其他容器慢，这可能导致其余服务一开始会引发 HTTP 异常，即使在 docker-compose 级别设置容器之间的依赖关系也会如此，如前面部分中所述。</span><span class="sxs-lookup"><span data-stu-id="fef25-141">The fact that some containers start slower than others can cause the rest of the services to initially throw HTTP exceptions, even if you set dependencies between containers at the docker-compose level, as explained in previous sections.</span></span> <span data-ttu-id="fef25-142">容器之间的那些 docker-compose 依赖关系只存在于进程级别。</span><span class="sxs-lookup"><span data-stu-id="fef25-142">Those docker-compose dependencies between containers are just at the process level.</span></span> <span data-ttu-id="fef25-143">可能容器的入口点进程已启动，但 SQL Server 可能还不能响应查询。</span><span class="sxs-lookup"><span data-stu-id="fef25-143">The container’s entry point process might be started, but SQL Server might not be ready for queries.</span></span> <span data-ttu-id="fef25-144">这是一连串错误导致的结果，应用程序在尝试使用该特定容器时可能引发异常。</span><span class="sxs-lookup"><span data-stu-id="fef25-144">The result can be a cascade of errors, and the application can get an exception when trying to consume that particular container.</span></span> 

<span data-ttu-id="fef25-145">在应用程序部署到云时，也可能在启动时看到这种类型的错误。</span><span class="sxs-lookup"><span data-stu-id="fef25-145">You might also see this type of error on startup when the application is deploying to the cloud.</span></span> <span data-ttu-id="fef25-146">在这种情况下，业务流程协调程序可能会将容器从一个节点或 VM 移动到另一个（即启动新实例），以平衡群集节点中的容器数。</span><span class="sxs-lookup"><span data-stu-id="fef25-146">In that case, orchestrators might be moving containers from one node or VM to another (that is, starting new instances) when balancing the number of containers across the cluster’s nodes.</span></span>

<span data-ttu-id="fef25-147">在启用所有容器时，“eShopOnContainers”解决这些问题的方法是使用前文所述的重试模式。</span><span class="sxs-lookup"><span data-stu-id="fef25-147">The way 'eShopOnContainers' solves those issues when starting all the containers is by using the Retry pattern illustrated earlier.</span></span> 

### <a name="testing-the-circuit-breaker-in-eshoponcontainers"></a><span data-ttu-id="fef25-148">在 eShopOnContainers 中测试断路器</span><span class="sxs-lookup"><span data-stu-id="fef25-148">Testing the circuit breaker in eShopOnContainers</span></span>

<span data-ttu-id="fef25-149">有几种方法可以中断/打开线路，并使用 eShopOnContainers 对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="fef25-149">There are a few ways you can break/open the circuit and test it with eShopOnContainers.</span></span>

<span data-ttu-id="fef25-150">一种方法是在断路器策略中将允许的重试次数减少为 1 次，并将整个解决方案重新部署到 Docker。</span><span class="sxs-lookup"><span data-stu-id="fef25-150">One option is to lower the allowed number of retries to 1 in the circuit breaker policy and redeploy the whole solution into Docker.</span></span> <span data-ttu-id="fef25-151">如果设为一次重试，部署过程中 HTTP 请求失败的可能性就会很大，断路器会打开，然后收到错误。</span><span class="sxs-lookup"><span data-stu-id="fef25-151">With a single retry, there is a good chance that an HTTP request will fail during deployment, the circuit breaker will open, and you get an error.</span></span>

<span data-ttu-id="fef25-152">另一种方法是使用 Basket 微服务中实现的自定义中间件。</span><span class="sxs-lookup"><span data-stu-id="fef25-152">Another option is to use custom middleware that is implemented in the Basket microservice.</span></span> <span data-ttu-id="fef25-153">启用此中间件后，它会捕获所有 HTTP 请求并返回状态代码 500。</span><span class="sxs-lookup"><span data-stu-id="fef25-153">When this middleware is enabled, it catches all HTTP requests and returns status code 500.</span></span> <span data-ttu-id="fef25-154">可以通过向失败 URI 发出 GET 请求来启用此中间件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fef25-154">You can enable the middleware by making a GET request to the failing URI, like the following:</span></span>

- `GET http://localhost:5103/failing`

<span data-ttu-id="fef25-155">此请求返回中间件的当前状态。</span><span class="sxs-lookup"><span data-stu-id="fef25-155">This request returns the current state of the middleware.</span></span> <span data-ttu-id="fef25-156">如果启用了中间件，则请求返回状态代码 500。</span><span class="sxs-lookup"><span data-stu-id="fef25-156">If the middleware is enabled, the request return status code 500.</span></span> <span data-ttu-id="fef25-157">如果禁用了中间件，则无响应。</span><span class="sxs-lookup"><span data-stu-id="fef25-157">If the middleware is disabled, there is no response.</span></span> 

- `GET http://localhost:5103/failing?enable`

<span data-ttu-id="fef25-158">此请求启用中间件。</span><span class="sxs-lookup"><span data-stu-id="fef25-158">This request enables the middleware.</span></span> 

- `GET http://localhost:5103/failing?disable`

<span data-ttu-id="fef25-159">此请求禁用中间件。</span><span class="sxs-lookup"><span data-stu-id="fef25-159">This request disables the middleware.</span></span> 

<span data-ttu-id="fef25-160">例如，应用程序运行后，可立即通过在任何浏览器中使用以下 URI 发出请求，来启用中间件。</span><span class="sxs-lookup"><span data-stu-id="fef25-160">For instance, once the application is running, you can enable the middleware by making a request using the following URI in any browser.</span></span> <span data-ttu-id="fef25-161">请注意，订单微服务使用端口 5103。</span><span class="sxs-lookup"><span data-stu-id="fef25-161">Note that the ordering microservice uses port 5103.</span></span>

`http://localhost:5103/failing?enable` 

<span data-ttu-id="fef25-162">然后可以使用 URI http://localhost:5103/failing 检查状态，如图 10-4 中所示。</span><span class="sxs-lookup"><span data-stu-id="fef25-162">You can then check the status using the URI http://localhost:5103/failing, as shown in Figure 10-4.</span></span>

![](./media/image4.png)

<span data-ttu-id="fef25-163">**图 10-4**。</span><span class="sxs-lookup"><span data-stu-id="fef25-163">**Figure 10-4**.</span></span> <span data-ttu-id="fef25-164">正在检查“失败”的 ASP.NET 中间件的状态 – 在此例中为禁用状态。</span><span class="sxs-lookup"><span data-stu-id="fef25-164">Checking the state of the “Failing” ASP.NET middleware – In this case, disabled.</span></span> 

<span data-ttu-id="fef25-165">在这种情况下，每当调用市场篮微服务时，微服务就会使用状态代码 500 进行响应。</span><span class="sxs-lookup"><span data-stu-id="fef25-165">At this point, the Basket microservice responds with status code 500 whenever you call invoke it.</span></span>

<span data-ttu-id="fef25-166">中间件开始运行后，便可尝试从 MVC web 应用程序下订单。</span><span class="sxs-lookup"><span data-stu-id="fef25-166">Once the middleware is running, you can try making an order from the MVC web application.</span></span> <span data-ttu-id="fef25-167">由于请求失败，线路将打开。</span><span class="sxs-lookup"><span data-stu-id="fef25-167">Because the requests fail, the circuit will open.</span></span> 

<span data-ttu-id="fef25-168">在下面的示例中，可以看到 MVC web 应用程序在用于下订单的逻辑中具有一个捕获块。</span><span class="sxs-lookup"><span data-stu-id="fef25-168">In the following example, you can see that the MVC web application has a catch block in the logic for placing an order.</span></span>  <span data-ttu-id="fef25-169">如果代码捕获了一个开路异常，会向用户显示一条友好消息，请用户等待。</span><span class="sxs-lookup"><span data-stu-id="fef25-169">If the code catches an open-circuit exception, it shows the user a friendly message telling them to wait.</span></span>

```csharp
public class CartController : Controller
{
    //…
    public async Task<IActionResult> Index()
    {
        try
        {          
            var user = _appUserParser.Parse(HttpContext.User);
            //Http requests using the Typed Client (Service Agent)
            var vm = await _basketSvc.GetBasket(user);
            return View(vm);
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

<span data-ttu-id="fef25-170">下面是摘要。</span><span class="sxs-lookup"><span data-stu-id="fef25-170">Here’s a summary.</span></span> <span data-ttu-id="fef25-171">重试策略尝试数次发出 HTTP 请求，并获取 HTTP 错误。</span><span class="sxs-lookup"><span data-stu-id="fef25-171">The Retry policy tries several times to make the HTTP request and gets HTTP errors.</span></span> <span data-ttu-id="fef25-172">当重试次数达到断路器策略设置的最大次数时（此例中为 5），应用程序会引发 BrokenCircuitException。</span><span class="sxs-lookup"><span data-stu-id="fef25-172">When the number of retries reaches the maximum number set for the Circuit Breaker policy (in this case, 5), the application throws a BrokenCircuitException.</span></span> <span data-ttu-id="fef25-173">结果是一条友好消息，如图 10-5 中所示。</span><span class="sxs-lookup"><span data-stu-id="fef25-173">The result is a friendly message, as shown in Figure 10-5.</span></span>

![](./media/image5.png)

<span data-ttu-id="fef25-174">**图 10-5**。</span><span class="sxs-lookup"><span data-stu-id="fef25-174">**Figure 10-5**.</span></span> <span data-ttu-id="fef25-175">断路器向 UI 返回一个错误</span><span class="sxs-lookup"><span data-stu-id="fef25-175">Circuit breaker returning an error to the UI</span></span>

<span data-ttu-id="fef25-176">可以实现其他逻辑来指定何时打开/中断线路。</span><span class="sxs-lookup"><span data-stu-id="fef25-176">You can implement different logic for when to open/break the circuit.</span></span> <span data-ttu-id="fef25-177">或如果有一个回退数据中心或冗余的后端系统，可尝试对另一个后端微服务发出 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="fef25-177">Or you can try an HTTP request against a different back-end microservice if there is a fallback datacenter or redundant back-end system.</span></span> 

<span data-ttu-id="fef25-178">最后，针对 `CircuitBreakerPolicy` 的另一种可能操作是使用 `Isolate`（强制打开线路并保持为打开状态）和 `Reset`（再次关闭路线）。</span><span class="sxs-lookup"><span data-stu-id="fef25-178">Finally, another possibility for the `CircuitBreakerPolicy` is to use `Isolate` (which forces open and holds open the circuit) and `Reset` (which closes it again).</span></span> <span data-ttu-id="fef25-179">可使用这些操作构建一个实用程序 HTTP 终结点，用于在策略上直接调用隔离和重置。</span><span class="sxs-lookup"><span data-stu-id="fef25-179">These could be used to build a utility HTTP endpoint that invokes Isolate and Reset directly on the policy.</span></span>  <span data-ttu-id="fef25-180">还可以在生产中以合适的安全程度使用这种 HTTP 终结点，用于临时隔离下游系统，比如在想要升级系统的时候。</span><span class="sxs-lookup"><span data-stu-id="fef25-180">Such an HTTP endpoint could also be used, suitably secured, in production for temporarily isolating a downstream system, such as when you want to upgrade it.</span></span> <span data-ttu-id="fef25-181">或可手动打开线路，以保护疑似发生故障的下游系统。</span><span class="sxs-lookup"><span data-stu-id="fef25-181">Or it could trip the circuit manually to protect a downstream system you suspect to be faulting.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="fef25-182">其他资源</span><span class="sxs-lookup"><span data-stu-id="fef25-182">Additional resources</span></span>


-   <span data-ttu-id="fef25-183">**断路器模式**
    [*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span><span class="sxs-lookup"><span data-stu-id="fef25-183">**Circuit Breaker pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="fef25-184">[上一页](implement-http-call-retries-exponential-backoff-polly.md)
[下一页](monitor-app-health.md)</span><span class="sxs-lookup"><span data-stu-id="fef25-184">[Previous](implement-http-call-retries-exponential-backoff-polly.md)
[Next](monitor-app-health.md)</span></span>
