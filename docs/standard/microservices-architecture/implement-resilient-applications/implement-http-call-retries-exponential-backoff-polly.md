---
title: "使用 Polly 实现使用指数退避算法的 HTTP 调用重试"
description: "适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 使用 Polly 实现使用指数退避算法的 HTTP 调用重试"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 122f617874188d3bffe689d6b3cf7d7249c59c3b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="implementing-http-call-retries-with-exponential-backoff-with-polly"></a>使用 Polly 实现使用指数退避算法的 HTTP 调用重试

建议的使用指数退避算法的重试方法是利用更高级的 .NET 库，如开放源 [Polly](https://github.com/App-vNext/Polly) 库。

Polly 是一个 .NET 库，提供恢复能力和瞬态故障处理功能。 通过应用 Polly 策略（如重试、断路器、舱壁隔离、超时和回退）可以轻松地实现这些功能。 Polly 面向 .NET 4.x 和 .NET Standard 版本 1.0 （支持 .NET Core）。

Polly 中的重试策略是实现 HTTP 重试时在 eShopOnContainers 中使用的方法。 可以实现接口以便可以使用 Polly 注入标准 HttpClient 功能或弹性版本的 HttpClient，具体取决于想要使用的重试策略配置。

下面的示例演示在 eShopOnContainers 中实现的接口。

```csharp
public interface IHttpClient
{
    Task<string> GetStringAsync(string uri, string authorizationToken = null,
        string authorizationMethod = "Bearer");
        Task<HttpResponseMessage> PostAsync<T>(string uri, T item,
        string authorizationToken = null, string requestId = null,
        string authorizationMethod = "Bearer");

    Task<HttpResponseMessage> DeleteAsync(string uri,
        string authorizationToken = null, string requestId = null,
        string authorizationMethod = "Bearer");

    // Other methods ...
}
```

如果不想使用弹性机制，可以使用标准实现，就像在开发或测试更简单的方法时一样。 下面的代码演示标准 HttpClient 实现，允许将带有身份验证令牌的请求作为可选情况。

```csharp
public class StandardHttpClient : IHttpClient
{
    private HttpClient _client;
    private ILogger<StandardHttpClient> _logger;

    public StandardHttpClient(ILogger<StandardHttpClient> logger)
    {
        _client = new HttpClient();
        _logger = logger;
    }

    public async Task<string> GetStringAsync(string uri,
        string authorizationToken = null,
        string authorizationMethod = "Bearer")
    {
        var requestMessage = new HttpRequestMessage(HttpMethod.Get, uri);
        if (authorizationToken != null)
        {
            requestMessage.Headers.Authorization =
                new AuthenticationHeaderValue(authorizationMethod, authorizationToken);
        }
        var response = await _client.SendAsync(requestMessage);
        return await response.Content.ReadAsStringAsync();
    }

    public async Task<HttpResponseMessage> PostAsync<T>(string uri, T item,
        string authorizationToken = null, string requestId = null,
        string authorizationMethod = "Bearer")
    {
        // Rest of the code and other Http methods ...
```

有趣的实现是编写另一个类似的类，但是使用 Polly 来实现想要使用的弹性机制，在下面的示例中，使用指数退避算法重试。

```csharp
public class ResilientHttpClient : IHttpClient
{
    private HttpClient _client;
    private PolicyWrap _policyWrapper;
    private ILogger<ResilientHttpClient> _logger;

    public ResilientHttpClient(Policy[] policies,
        ILogger<ResilientHttpClient> logger)
    {
        _client = new HttpClient();
        _logger = logger;
        // Add Policies to be applied
        _policyWrapper = Policy.WrapAsync(policies);
    }

    private Task<T> HttpInvoker<T>(Func<Task<T>> action)
    {
        // Executes the action applying all
        // the policies defined in the wrapper
        return _policyWrapper.ExecuteAsync(() => action());
    }

    public Task<string> GetStringAsync(string uri,
        string authorizationToken = null,
        string authorizationMethod = "Bearer")
    {
        return HttpInvoker(async () =>
        {
            var requestMessage = new HttpRequestMessage(HttpMethod.Get, uri);
            // The Token's related code eliminated for clarity in code snippet
            var response = await _client.SendAsync(requestMessage);
            return await response.Content.ReadAsStringAsync();
        });
    }
    // Other Http methods executed through HttpInvoker so it applies Polly policies
    // ...
}
```

使用 Polly 定义一个重试策略，其中包含重试次数、指数退避算法配置以及在出现 HTTP 异常时要采取的操作，例如记录错误。 此时将配置策略，以便尝试在 IoC 容器中注册类型时指定的次数。 由于指数退避算法配置，每当代码检测到 HttpRequest 异常时，它都会在等待了一段时间之后重试发送 Http 请求，这一时间会随策略的配置方式呈指数增长。

重要的方法是 HttpInvoker，它使 HTTP 在整个此实用类发出请求。 该方法使用 \_policyWrapper.ExecuteAsync 在内部执行 HTTP 请求并考虑到重试策略。

在 eShopOnContainers 中，在 IoC 容器注册类型时指定 Polly 策略，如 [MVC Web 应用在 startup.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Web/WebMVC/Startup.cs) 类中的以下代码所示。

```csharp
// Startup.cs class
if (Configuration.GetValue<string>("UseResilientHttp") == bool.TrueString)
{
    services.AddTransient<IResilientHttpClientFactory,
        ResilientHttpClientFactory>();
    services.AddSingleton<IHttpClient,
        ResilientHttpClient>(sp =>
            sp.GetService<IResilientHttpClientFactory>().
            CreateResilientHttpClient());
}
else
{
    services.AddSingleton<IHttpClient, StandardHttpClient>();
}
```

请注意，IHttpClient 对象被实例化为单例，而不是临时的，这样服务就可以有效地使用 TCP 连接，并且不会发生[套接字问题](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/)。

但是关于复原的重要一点是在 CreateResilientHttpClient 方法中的 ResilientHttpClientFactory 中应用 Polly WaitAndRetryAsync 策略，如以下代码所示：

```csharp
public ResilientHttpClient CreateResilientHttpClient()
    => new ResilientHttpClient(CreatePolicies(), _logger);

// Other code
private Policy[] CreatePolicies()
    => new Policy[]
    {
        Policy.Handle<HttpRequestException>()
            .WaitAndRetryAsync(
        // number of retries
        6,
        // exponential backoff
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)),
        // on retry
        (exception, timeSpan, retryCount, context) =>
        {
            var msg = $"Retry {retryCount} implemented with Pollys RetryPolicy " +
            $"of {context.PolicyKey} " +
            $"at {context.ExecutionKey}, " +
            $"due to: {exception}.";
            _logger.LogWarning(msg);
            _logger.LogDebug(msg);
        }),
    }
```


>[!div class="step-by-step"]
[上一篇] (implement-custom-http-call-retries-exponential-backoff.md) [下一篇] (implement-circuit-breaker-pattern.md)
