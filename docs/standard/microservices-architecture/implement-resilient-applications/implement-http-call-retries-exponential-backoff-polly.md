---
title: "使用 Polly 和实施 HTTP 调用重试使用指数退让"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |使用 Polly 和实施 HTTP 调用重试使用指数退让"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 1ed48142546403ea710f4c132e038521232c20ed
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-http-call-retries-with-exponential-backoff-with-polly"></a>使用 Polly 和实施 HTTP 调用重试使用指数退让

指数回退重试的建议的方法是以利用更高级的.NET 库等开放源代码[Polly](https://github.com/App-vNext/Polly)库。

Polly 是一个.NET 库，提供了恢复能力和暂时性故障处理功能。 通过应用 Polly 如重试、 断路器、 Bulkhead 隔离、 超时，和回退的策略，可以轻松地实现这些功能。 Polly 面向.NET 4.x 和.NET 标准版本 1.0 （它支持.NET 核心）。

Polly 的重试策略是实现 HTTP 重试时，在 eShopOnContainers 中使用的方法。 你可以实现接口，以便你可以将注入标准 HttpClient 功能或 HttpClient 使用 Polly，具体取决于你想要使用何种重试策略配置的弹性版本。

下面的示例演示 eShopOnContainers 中实现的接口。

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

如果你不想要使用弹性的机制，作为开发或测试更简单的方法时，你可以使用标准的实现。 下面的代码演示标准 HttpClient 实现允许请求与身份验证令牌，作为可选的情况。

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

有趣的实现是代码另一个类似的类，但它使用 Polly 以实现你想要使用的弹性机制 — 在以下示例中，重试使用指数退让。

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

使用 Polly，你定义的重试策略所具有的重试次数、 指数退让配置和要执行时出现 HTTP 异常，如日志记录错误的操作数。 在这种情况下，配置策略，因此它将尝试在 IoC 容器中注册的类型时指定的次数。 由于指数退让配置中，只要代码检测到 HttpRequest 异常，重试发送 Http 请求后等待一段时间，具体取决于配置策略的方式将以指数增长。

重要的方法是 HttpInvoker，它是什么发出整个此实用程序类的 HTTP 请求。 方法内部执行的 HTTP 请求\_policyWrapper.ExecuteAsync，将考虑在内的重试策略。

在 eShopOnContainers 你指定 Polly 策略注册在 IoC 容器，如从以下代码所示的类型时[MVC web 应用程序在 startup.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Web/WebMVC/Startup.cs)类。

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

请注意，以便服务有效地使用 TCP 连接 IHttpClient 对象实例化为为临时的而不是单一实例映射和[套接字的问题](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/)不会发生。

但是，有关复原重要的一点是，你将在 CreateResilientHttpClient 方法中，Polly WaitAndRetryAsync 策略 ResilientHttpClientFactory 中的应用下面的代码中所示：

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
[以前](implement-custom-http-call-retries-exponential-backoff.md) [下一步] (实现的线路的断路器-pattern.md)
