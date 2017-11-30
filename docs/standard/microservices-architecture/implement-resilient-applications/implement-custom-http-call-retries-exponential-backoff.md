---
title: "实现自定义 HTTP 调用的重试使用指数退让"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |实现自定义 HTTP 调用的重试使用指数退让"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 4449e5d7e0ca3c81aead26fac653de3ba2187a92
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-custom-http-call-retries-with-exponential-backoff"></a><span data-ttu-id="68fff-104">实现自定义 HTTP 调用的重试使用指数退让</span><span class="sxs-lookup"><span data-stu-id="68fff-104">Implementing custom HTTP call retries with exponential backoff</span></span>

<span data-ttu-id="68fff-105">若要创建弹性微服务，你需要以处理可能的 HTTP 故障方案。</span><span class="sxs-lookup"><span data-stu-id="68fff-105">In order to create resilient microservices, you need to handle possible HTTP failure scenarios.</span></span> <span data-ttu-id="68fff-106">出于这个目的，你可以使用指数退让创建您自己的重试次数的实现。</span><span class="sxs-lookup"><span data-stu-id="68fff-106">For that purpose, you could create your own implementation of retries with exponential backoff.</span></span>

<span data-ttu-id="68fff-107">除了处理临时资源不可用，使用指数退让策略还需要考虑云提供商可能会限制的资源，以防止使用重载的可用性。</span><span class="sxs-lookup"><span data-stu-id="68fff-107">In addition to handling temporal resource unavailability, the exponential backoff also needs to take into account that the cloud provider might throttle availability of resources to prevent usage overload.</span></span> <span data-ttu-id="68fff-108">例如，非常快速地创建过多的连接请求可能被视作拒绝服务 ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) 云提供商的攻击。</span><span class="sxs-lookup"><span data-stu-id="68fff-108">For example, creating too many connection requests very quickly might be viewed as a Denial of Service ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) attack by the cloud provider.</span></span> <span data-ttu-id="68fff-109">因此，你需要提供一种机制来扩展后的连接请求时遇到的容量阈值。</span><span class="sxs-lookup"><span data-stu-id="68fff-109">As a result, you need to provide a mechanism to scale back connection requests when a capacity threshold has been encountered.</span></span>

<span data-ttu-id="68fff-110">作为初始探索，可以实现你自己的代码作为以指数回退的实用程序类[RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260)，加上类似于下面的代码 (这也是可在上找到[GitHub 存储库](https://gist.github.com/CESARDELATORRE/d80c6423a1aebaffaf387469f5194f5b)).</span><span class="sxs-lookup"><span data-stu-id="68fff-110">As an initial exploration, you could implement your own code with a utility class for exponential backoff as in [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260), plus code like the following (which is also available on a [GitHub repo](https://gist.github.com/CESARDELATORRE/d80c6423a1aebaffaf387469f5194f5b)).</span></span>

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

<span data-ttu-id="68fff-111">在客户端 C 中使用此代码\#应用程序 (另一个 Web API 客户端微服务、 ASP.NET MVC 应用程序或甚至 C\# Xamarin 应用程序) 非常简单。</span><span class="sxs-lookup"><span data-stu-id="68fff-111">Using this code in a client C\# application (another Web API client microservice, an ASP.NET MVC application, or even a C\# Xamarin application) is straightforward.</span></span> <span data-ttu-id="68fff-112">下面的示例演示如何操作，请使用 HttpClient 类。</span><span class="sxs-lookup"><span data-stu-id="68fff-112">The following example shows how, using the HttpClient class.</span></span>

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

<span data-ttu-id="68fff-113">但是，此代码适合仅作为概念证明。</span><span class="sxs-lookup"><span data-stu-id="68fff-113">However, this code is suitable only as a proof of concept.</span></span> <span data-ttu-id="68fff-114">下一主题说明如何使用更复杂和经验证的库。</span><span class="sxs-lookup"><span data-stu-id="68fff-114">The next topic explains how to use more sophisticated and proven libraries.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="68fff-115">[以前](implement-resilient-entity-framework-core-sql-connections.md) [下一步] (implement-http-call-retries-exponential-backoff-polly.md)</span><span class="sxs-lookup"><span data-stu-id="68fff-115">[Previous] (implement-resilient-entity-framework-core-sql-connections.md) [Next] (implement-http-call-retries-exponential-backoff-polly.md)</span></span>
