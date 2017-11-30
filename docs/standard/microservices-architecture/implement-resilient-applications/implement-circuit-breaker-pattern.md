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
# <a name="implementing-the-circuit-breaker-pattern"></a>实现断路器模式

如前文所述，你应处理可能需要变量大量时间才能恢复，当你尝试连接到远程服务或资源可能会发生的错误。 处理这种类型的错误可以提高稳定性和复原能力的应用程序。

在分布式环境中，对远程资源和服务的调用可能失败由于暂时性故障，例如慢速网络连接和超时，或如果资源正在缓慢或暂时不可用。 这些故障通常一段时间之后, 更正本身和可靠的云应用程序应准备好处理它们通过使用类似的重试模式的策略。

但是，也可以存在的情况下错误由于可能需要较长时间才能解决的意外事件。 从部分连接断开到服务的完整失败的严重性范围可以是这些错误。 在这些情况下，它可能是应用程序，以不断重试不太可能成功操作毫无意义。 相反，应用程序应编码为接受的操作已失败并相应地处理错误。

断路器模式具有与重试模式不同的用途。 应用程序，以重试该操作将最终成功的假定条件下在操作可以重试模式。 断路器模式防止应用程序执行的操作，则可能会失败。 应用程序可以通过使用重试模式来调用通过断路器操作来组合这些两种模式。 但是，重试逻辑应能觉察到返回的断路器中，任何异常，并且如果故障不是暂时性的断路器指示它应放弃重试尝试。

## <a name="implementing-a-circuit-breaker-pattern-with-polly"></a>使用 Polly 和实施断路器模式

作为在实现重试时，断路器的建议的方法是利用 Polly 类似的经过验证.NET 库。

实现 HTTP 重试时，eShopOnContainers 应用程序使用 Polly 断路器策略。 事实上，应用程序将这两个策略应用到 ResilientHttpClient 实用程序类。 每当 ResilientHttpClient 类型的对象使用的 HTTP 请求 （来自 eShopOnContainers) 时，您将在应用这两个这些策略，但您无法太添加其他策略。

唯一新增此处的内容所使用的 HTTP 调用重试代码是其中断路器策略向添加的策略，若要使用，列表末尾的以下代码所示的代码：

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

代码将策略添加到 HTTP 包装器。 策略定义断路器将打开代码检测到指定的数目的连续异常 （在一行中的异常） 时，为传入 exceptionsAllowedBeforeBreaking 参数 (在此情况下为 5)。 打开线路时，HTTP 请求不起作用，但在引发异常。

此外应该使用断路器将请求重定向到一个回退的基础结构，如果你可能必须部署在不同环境比客户端应用程序的特定资源或正在执行 HTTP 调用的服务中的问题。 这样一来，如果在会影响你后端微服务但不是在客户端应用程序，数据中心中断客户端应用程序可以重定向到备用服务。 Polly 正在计划新的策略来自动化这[故障转移策略](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy)方案。

当然，所有这些功能适用于管理中的.NET 代码，而不是让它自动为你管理的 azure，具有位置透明度从故障转移的情况。

## <a name="using-the-resilienthttpclient-utility-class-from-eshoponcontainers"></a>使用从 eShopOnContainers ResilientHttpClient 实用程序类

类似于你如何使用.NET HttpClient 类的方式使用 ResilientHttpClient 实用程序类。 在以下示例从 eShopOnContainers MVC web 应用程序 （由 OrderController OrderingService 代理类） 中，通过 httpClient 参数的构造函数注入 ResilientHttpClient 对象。 然后，该对象用于执行 HTTP 请求。

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

每当\_apiClient 成员对象时，它在内部使用 Polly policiesؙ 使用包装类-重试策略，断路器策略中，你可能想要从 Polly 策略集合应用的任何其他策略。

## <a name="testing-retries-in-eshoponcontainers"></a>在 eShopOnContainers 中测试重试

每当在 Docker 主机中启动 eShopOnContainers 解决方案，它需要启动多个容器。 某些容器是启动并初始化，如 SQL Server 容器要稍慢一些。 这是尤其如此首次部署 eShopOnContainers 应用程序置于 Docker，因为它需要设置图像和数据库。 某些容器启动速度比其他人可能会导致最初引发 HTTP 异常的服务的其余部分，即使设置在容器之间的依赖关系要慢事实 docker compose 级别，，如前面部分中所述。 那些 docker-撰写容器之间的依赖关系是否在进程级别。 容器的入口点进程可能会启动，但 SQL Server 可能不是准备好进行查询。 将会导致错误，级联和应用程序尝试使用该特定容器时将引发异常。

应用程序部署到云时，你还可能在启动时看到这种类型的错误。 在这种情况下，orchestrators 可能来移动容器从一个节点或 VM 之间 （即，启动新实例） 时平衡群集的节点的容器数。

EShopOnContainers 可以解决此问题的方法是使用我们本文前面所述的重试模式。 它是原因，当从开始解决方案，你可能会收到日志跟踪或警告如下所示：

> "**使用 Polly 的 RetryPolicy 实现重试 1**，因为： System.Net.Http.HttpRequestException： 发送的请求时出错。 ---&gt;System.Net.Http.CurlException： 无法连接到服务器\\System.Net.Http.CurlHandler.ThrowIfCURLEError （CURLcode 错误） 在 n\\在 n \[...\].

## <a name="testing-the-circuit-breaker-in-eshoponcontainers"></a>在 eShopOnContainers 中测试断路器

有几种方法可以打开线路，还可以使用 eShopOnContainers 对它进行测试。

一个选项用于降低允许为 1 断路器策略中的重试次数和探究 Docker 重新部署整个解决方案。 与单个重试，存在很可能会在部署过程的 HTTP 请求将失败，断路器将打开，以及可能会出错。

另一种方法是使用自定义在排序的微服务中实现的中间件。 启用此中间件后，它将捕获所有 HTTP 请求并返回状态代码 500。 可以通过向失败发出 GET 请求来启用该中间件 URI，如下所示：

-   获取/出现故障

此请求返回的中间件的当前状态。 如果启用了该中间件，则请求将返回状态代码 500。 如果禁用了该中间件，则无响应。

-   获取/失败？ 启用

此请求使该中间件。

-   获取/失败？ 禁用

此请求禁用该中间件。

例如，应用程序运行后，你可以通过发出请求的任何浏览器中使用以下 URI 启用该中间件。 请注意，排序微服务使用端口 5102。

http://localhost:5102 / 失败？ 启用

然后，可以选中状态使用 URI [http://localhost:5102 / 失败](http://localhost:5100/failing)，如图 10-4 中所示。

![](./media/image4.png)

**图 10-4**。 模拟与 ASP.NET 中间件失败

此时，排序的微服务进行响应，并返回状态代码 500 每当你调用调用该录制。

该中间件运行后，你可以尝试进行 MVC web 应用程序从订单。 由于请求失败，将打开线路。

在下面的示例中，你可以看到 MVC web 应用程序具有 catch 块中，在下订单的逻辑。 如果代码将捕获打开线路异常，它显示的用户友好条消息，告知等待。

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

下面是摘要。 重试策略尝试数次以进行 HTTP 请求和获取 HTTP 错误。 当尝试次数达到断路器策略 （在此情况下，5） 设置的最大数字时，该应用程序会引发 BrokenCircuitException。 结果是友好消息，图 10-5 中所示。

![](./media/image5.png)

**图 10-5**。 断路器返回到 UI 的错误

你可以实现其他逻辑来确定何时打开线路。 或者，如果没有回退数据中心或冗余的后端系统，你可以尝试针对不同的后端微服务的 HTTP 请求。

最后，为 CircuitBreakerPolicy 的另一种可能是使用隔离 （该强制打开，并使保持打开的线路） 和重置 （这会再次关闭）。 这些无法用于生成的策略中将调用隔离和重置直接的实用程序 HTTP 终结点。 这样的 HTTP 终结点可能还用于，适当保护，暂时隔离下游系统，如你想要将其升级的生产环境中。 或它无法跳闸线路后，手动以保护您怀疑出错的下游系统。

## <a name="adding-a-jitter-strategy-to-the-retry-policy"></a>将抖动策略添加到重试策略

常规的重试策略可能会影响你的系统中的高并发性和可伸缩性，但在高争用的情况。 若要解决的类似来自发生部分服务中断的多个客户端的重试次数的峰值，好的变通方法是将抖动策略添加到重试算法/策略。 通过将随机性添加到使用指数退让策略，这可以提高端到端系统的整体性能。 此分布峰值时出现问题。 当你使用 Polly 时，代码以实现抖动无法类似下面的示例：

```csharp
Random jitterer = new Random();
Policy.Handle<HttpResponseException>() // etc
    .WaitAndRetry(5, // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))
            + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

## <a name="additional-resources"></a>其他资源

-   **重试模式**
    [*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)

-   **连接复原**（实体框架核） [ *https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)

-   **Polly** （.NET 恢复能力和暂时性故障处理库） [ *https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)

-   **断路器模式**
    [*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)

-   **Marc Brooker。抖动： 使得操作更好地与随机性**https://brooker.co.za/blog/2015/03/21/backoff.html


>[!div class="step-by-step"]
[以前](implement-http-call-retries-exponential-backoff-polly.md) [下一步] (监视器应用 health.md)
