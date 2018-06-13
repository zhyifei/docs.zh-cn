---
title: 实现断路器模式
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 实现断路器模式
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/12/2017
ms.openlocfilehash: dea94d8eda3341cca5e3aaf6b3c8369c27381135
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33578009"
---
# <a name="implementing-the-circuit-breaker-pattern"></a>实现断路器模式

如前文所述，需要处理某类故障，处理这类故障时，所需的时间并不固定，尝试连接远程服务或资源时就可能会发生这类故障。 处理这类故障可以提高应用程序的稳定性和复原能力。

在分布式环境中，对远程资源和服务的调用可能由于暂时性故障而失败，例如网络连接速度较慢和超时或资源连接缓慢或暂时不可用。 这些故障通常在一段时间之后会自动消失，应配备可靠强大的云应用程序，使用“重试”模式等策略来解决这些故障。

但也可能存在这种情况，由于意外事件引发故障，需要更长的时间来解决故障。 这些故障轻则导致部分连接中断，重则导致服务完全瘫痪。 在这些情况下，应用程序持续重试一个操作可能毫无意义，因为操作不可能成功。 相反，应对应用程序进行编码，使其接受已失败的操作，并相应解决故障。

断路器模式与重试模式的目的和用途不同。 重试模式让应用程序能够重试一个操作，并预期操作最终会成功。 断路器模式阻止应用程序执行很可能会失败的操作。 应用程序可将这两种模式结合起来，方法是使用重试模式，通过断路器来调用操作。 但重试逻辑应能敏锐觉察断路器返回的任何异常，并在断路器指示故障并非暂时性故障时放弃重试尝试。

## <a name="implementing-a-circuit-breaker-pattern-with-polly"></a>使用 Polly 实现断路器模式

实现重试操作时，建议的方法为断路器使用 Polly 这种经过验证的 .NET 库。

eShopOnContainers 应用程序实现 HTTP 重试时，使用 Polly 断路器策略。 事实上，应用程序对 ResilientHttpClient 实用程序类同时应用两种策略。 每当将 ResilientHttpClient 类型的对象用于 HTTP 请求（来自 eShopOnContainers）时，会同时应用两种策略，但也可以添加其他策略。

此处在用于 HTTP 调用重试的代码中添加的唯一内容是用于将断路器策略添加到策略列表的代码，如以下代码的结尾处所示：

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

此代码将一个策略添加到 HTTP 包装器。 该策略定义一个断路器，当代码检测到指定数目的连续异常（连续的一系列异常）时，该断路器会断开，这里的指定数目即为传入 exceptionsAllowedBeforeBreaking 参数的数目（在此情况下为 5）。 线路断开时，HTTP 请求不起作用，但会引发异常。

如果一个特定资源可能出问题，且该资源部署在不同于执行 HTTP 调用的客户端应用程序或服务的环境中，则还应使用断路器将请求重定向到回退基础结构。 这样一来，如果数据中心发生故障，但该故障只影响后端微服务，而不影响客户端应用程序，则客户端应用程序可以重定向到回退服务。 Polly 正在规划新策略，用于自动实现此[故障转移策略](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy)方案。

当然，所有这些功能均适用于从 .NET 代码内部管理故障转移的情况，与由 Azure 自动管理的情况相反（位置透明化）。

## <a name="using-the-resilienthttpclient-utility-class-from-eshoponcontainers"></a>从 eShopOnContainers 使用 ResilientHttpClient 实用程序类

使用 ResilientHttpClient 实用程序类的方式与使用 .NET HttpClient 类的方式相似。 在以下源自 eShopOnContainers MVC web 应用程序（供 OrderController 使用的 OrderingService 代理类）的示例中，通过构造函数的 httpClient 参数注入 ResilientHttpClient 对象。 然后使用该对象执行 HTTP 请求。

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

每当使用 \_apiClient 成员对象时，它会在内部配合使用包装类和 Polly 策略—重试策略、断路器策略和任何其他想从 Polly 策略集合中应用的策略。

## <a name="testing-retries-in-eshoponcontainers"></a>在 eShopOnContainers 中测试重试

每当在 Docker 主机中启动 eShopOnContainers 解决方案时，它需要启动多个容器。 启动和初始化某些容器时会比较慢，如 SQL Server 容器。 尤其是首次在 Docker 中部署 eShopOnContainers 应用程序时，因为它需要设置映像和数据库。 某些容器的启动速度比其他容器慢，这可能导致其余服务一开始会引发 HTTP 异常，即使在 docker-compose 级别设置容器之间的依赖关系也会如此，如前面部分中所述。 容器之间的那些 docker-compose 依赖关系只存在于进程级别。 可能容器的入口点进程已启动，但 SQL Server 可能还不能响应查询。 这是一连串错误导致的结果，应用程序在尝试使用该特定容器时可能引发异常。

在应用程序部署到云时，也可能在启动时看到这种类型的错误。 在这种情况下，业务流程协调程序可能会将容器从一个节点或 VM 移动到另一个（即启动新实例），以平衡群集节点中的容器数。

eShopOnContainers 解决此问题的方法是使用前文所述的重试模式。 这也是为什么启动解决方案时可能会收到如下所示的日志跟踪或警告：

> “**已使用 Polly 的 RetryPolicy 实现重试 1**，引发原因：System.Net.Http.HttpRequestException：发送请求时出错。 ---&gt; System.Net.Http.CurlException：无法连接到服务器\\n 位置：System.Net.Http.CurlHandler.ThrowIfCURLEError(CURLcode error)\\n 位置：\[...\]。

## <a name="testing-the-circuit-breaker-in-eshoponcontainers"></a>在 eShopOnContainers 中测试断路器

有几种方法可以打开线路，并使用 eShopOnContainers 进行测试。

一种方法是在断路器策略中将允许的重试次数减少为 1 次，并将整个解决方案重新部署到 Docker。 如果设为一次重试，部署过程中 HTTP 请求失败的可能性就会很大，断路器会打开，然后收到错误。

另一种方法是使用 `Basket` 微服务中实现的自定义中间件。 启用此中间件后，它会捕获所有 HTTP 请求并返回状态代码 500。 可以通过向失败 URI 发出 GET 请求来启用此中间件，如下所示：

-   GET /failing

此请求返回中间件的当前状态。 如果启用了中间件，则请求返回状态代码 500。 如果禁用了中间件，则无响应。

-   GET /failing?enable

此请求启用中间件。

-   GET /failing?disable

此请求禁用中间件。

例如，应用程序运行后，可立即通过在任何浏览器中使用以下 URI 发出请求，来启用中间件。 请注意，订单微服务使用端口 5103。

http://localhost:5103/failing?enable

然后可以使用 URI [http://localhost:5103/failing](http://localhost:5103/failing) 检查状态，如图 10-4 中所示。

![](./media/image4.png)

**图 10-4**。 正在检查“失败”的 ASP.NET 中间件的状态 – 在此例中为禁用状态。 

在这种情况下，每当调用市场篮微服务时，微服务就会使用状态代码 500 进行响应。

中间件开始运行后，便可尝试从 MVC web 应用程序下订单。 由于请求失败，线路将打开。

在下面的示例中，可以看到 MVC web 应用程序在用于下订单的逻辑中具有一个捕获块。 如果代码捕获了一个开路异常，会向用户显示一条友好消息，请用户等待。

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

下面是摘要。 重试策略尝试数次发出 HTTP 请求，并获取 HTTP 错误。 当尝试次数达到断路器策略设置的最大次数时（此例中为 5），应用程序会引发 BrokenCircuitException。 结果是一条友好消息，如图 10-5 中所示。

![](./media/image5.png)

**图 10-5**。 断路器向 UI 返回一个错误

可以实现其他逻辑来指定何时打开线路。 或如果有一个回退数据中心或冗余的后端系统，可尝试对另一个后端微服务发出 HTTP 请求。

最后，针对 CircuitBreakerPolicy 的另一种可能操作是使用隔离（强制打开线路并保持为打开状态）和重置（再次关闭路线）。 可使用这些操作构建一个实用程序 HTTP 终结点，用于在策略上直接调用隔离和重置。 还可以在生产中以合适的安全程度使用这种 HTTP 终结点，用于临时隔离下游系统，比如在想要升级系统的时候。 或可手动打开线路，以保护疑似发生故障的下游系统。

## <a name="adding-a-jitter-strategy-to-the-retry-policy"></a>将抖动策略添加到重试策略

在高并发率、高可伸缩性和高争用的情况下，常规重试策略可能会对系统产生影响。 在部分运行中断的情况下，有可能会有许多客户端同时发出相似的重试操作，从而形成操作高峰，为克服这种情况，一个好办法是向重试算法或策略中添加抖动策略。 由于增加了指数退避的随机性，这可能会改进端到端系统的整体性能。 这样在出现问题时可以分散峰值。 使用 Polly 时，用于实现抖动的代码类似下面的示例：

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

-   **连接复原** (Entity Framework Core)[*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)

-   **Polly**（.NET 的恢复和暂时性故障处理库）[*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)

-   **断路器模式**
    [*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)

-   **Marc Brooker。抖动：随机性使操作变得更好**https://brooker.co.za/blog/2015/03/21/backoff.html


>[!div class="step-by-step"]
[上一项] (implement-http-call-retries-exponential-backoff-polly.md) [下一项] (monitor-app-health.md)
