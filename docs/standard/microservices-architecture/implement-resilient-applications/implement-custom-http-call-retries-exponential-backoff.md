---
title: 实现使用指数退避算法的自定义 HTTP 调用重试
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 实现使用指数退避算法的自定义 HTTP 调用重试
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 10751bb74ed648839fabec67ff7a71e458fb2a44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33574941"
---
# <a name="implementing-custom-http-call-retries-with-exponential-backoff"></a>实现使用指数退避算法的自定义 HTTP 调用重试

若要创建弹性微服务，需要处理可能的 HTTP 故障方案。 出于该目的，可以使用指数退避算法创建自己的重试实现。

除了处理时态资源不可用，指数退避算法还需要考虑云提供商可能会限制资源的可用性，以防止使用情况重载。 例如，非常快速地创建过多的连接请求可能被云提供商视为拒绝服务 ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) 攻击。 因此，当遇到容量阈值时，需要提供一种机制来减少连接请求。

作为初始探索，可以使用针对指数退避算法（如 [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260)中所述）的实用工具类和如下所示的代码（[GitHub 存储库](https://gist.github.com/CESARDELATORRE/d80c6423a1aebaffaf387469f5194f5b)上也有这种代码）来实现自己的代码。

```csharp
public sealed class RetryWithExponentialBackoff
{
    private readonly int maxRetries, delayMilliseconds, maxDelayMilliseconds;

    public RetryWithExponentialBackoff(int maxRetries = 50,
        int delayMilliseconds = 200,
        int maxDelayMilliseconds = 2000)
    {
        this.maxRetries = maxRetries;
        this.delayMilliseconds = delayMilliseconds;
        this.maxDelayMilliseconds = maxDelayMilliseconds;
    }

    public async Task RunAsync(Func<Task> func)
    {
        ExponentialBackoff backoff = new ExponentialBackoff(this.maxRetries,
            this.delayMilliseconds,
            this.maxDelayMilliseconds);
        retry:
        try
        {
            await func();
        }
        catch (Exception ex) when (ex is TimeoutException ||
            ex is System.Net.Http.HttpRequestException)
        {
            Debug.WriteLine("Exception raised is: " +
                ex.GetType().ToString() +
                " –Message: " + ex.Message +
                " -- Inner Message: " +
                ex.InnerException.Message);
            await backoff.Delay();
            goto retry;
        }
    }
}

public struct ExponentialBackoff
{
    private readonly int m_maxRetries, m_delayMilliseconds, m_maxDelayMilliseconds;
    private int m_retries, m_pow;

    public ExponentialBackoff(int maxRetries, int delayMilliseconds,
        int maxDelayMilliseconds)
    {
        m_maxRetries = maxRetries;
        m_delayMilliseconds = delayMilliseconds;
        m_maxDelayMilliseconds = maxDelayMilliseconds;
        m_retries = 0;
        m_pow = 1;
    }

    public Task Delay()
    {
        if (m_retries == m_maxRetries)
        {
            throw new TimeoutException("Max retry attempts exceeded.");
        }
        ++m_retries;
        if (m_retries < 31)
        {
            m_pow = m_pow << 1; // m_pow = Pow(2, m_retries - 1)
        }
        int delay = Math.Min(m_delayMilliseconds * (m_pow - 1) / 2,
            m_maxDelayMilliseconds);
        return Task.Delay(delay);
    }
}
```

在客户端 C\# 应用程序（另一个 Web API 客户端微服务、ASP.NET MVC 应用程序，甚至 C\# Xamarin 应用程序）中使用此代码非常简单。 下面的示例使用 HttpClient 类演示操作方法。

```csharp
public async Task<Catalog> GetCatalogItems(int page,int take, int? brand, int? type)
{
    _apiClient = new HttpClient();
    var itemsQs = $"items?pageIndex={page}&pageSize={take}";
    var filterQs = "";
    var catalogUrl = $"{_remoteServiceBaseUrl}items{filterQs}?pageIndex={page}&pageSize={take}";
    var dataString = "";
    //
    // Using HttpClient with Retry and Exponential Backoff
    //
    var retry = new RetryWithExponentialBackoff();
    await retry.RunAsync(async () =>
    {
        // work with HttpClient call
        dataString = await _apiClient.GetStringAsync(catalogUrl);
    });
    return JsonConvert.DeserializeObject<Catalog>(dataString);
}
```

但是，此代码仅适合用作概念证明。 下一主题将说明如何使用更复杂和行之有效的库。


>[!div class="step-by-step"]
[上一篇] (implement-resilient-entity-framework-core-sql-connections.md) [下一篇] (implement-http-call-retries-exponential-backoff-polly.md)
