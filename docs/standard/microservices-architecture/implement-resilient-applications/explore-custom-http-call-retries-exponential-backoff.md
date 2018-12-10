---
title: 了解如何使用指数退避算法实现自定义 HTTP 调用重试
description: 了解如何使用指数退避算法从头实现 HTTP 调用重试，以处理可能的 HTTP 故障情况。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/08/2018
ms.openlocfilehash: b7aaad9199bb275f45fd088a6207d707e8e5751c
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145093"
---
# <a name="explore-custom-http-call-retries-with-exponential-backoff"></a><span data-ttu-id="9edbf-103">了解如何使用指数退避算法实现自定义 HTTP 调用重试</span><span class="sxs-lookup"><span data-stu-id="9edbf-103">Explore custom HTTP call retries with exponential backoff</span></span>

<span data-ttu-id="9edbf-104">若要创建复原微服务，需要处理可能的 HTTP 故障情况。</span><span class="sxs-lookup"><span data-stu-id="9edbf-104">To create resilient microservices, you need to handle possible HTTP failure scenarios.</span></span> <span data-ttu-id="9edbf-105">处理此类故障的一种方法是，使用指数退避算法创建自己的重试实现（但不建议这样做）。</span><span class="sxs-lookup"><span data-stu-id="9edbf-105">One way of handling those failures, although not recommended, is to create your own implementation of retries with exponential backoff.</span></span>

<span data-ttu-id="9edbf-106">**重要说明：** 本部分说明如何创建自定义代码以实现 HTTP 调用重试。</span><span class="sxs-lookup"><span data-stu-id="9edbf-106">**Important note:** This section shows you how you could create your own custom code to implement HTTP call retries.</span></span> <span data-ttu-id="9edbf-107">但是不建议自己完成此过程，而是使用更加强大、可靠且更加简单的机制，如具有 Polly 的 `HttpClientFactory`（自 .NET Core 2.1 起可用）。</span><span class="sxs-lookup"><span data-stu-id="9edbf-107">However, it is not recommended to do it by your own but to use more powerful and reliable while simpler to use mechanisms, such as `HttpClientFactory` with Polly, available since .NET Core 2.1.</span></span> <span data-ttu-id="9edbf-108">后续部分将介绍建议采用的方法。</span><span class="sxs-lookup"><span data-stu-id="9edbf-108">Those recommended approaches are explained in the next sections.</span></span> 

<span data-ttu-id="9edbf-109">作为初始探索，可以使用针对指数退避算法（如 [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260) 中所述）的实用工具类和如下所示的代码（[GitHub 存储库](https://gist.github.com/CESARDELATORRE/d80c6423a1aebaffaf387469f5194f5b)上也提供这种代码）来实现自己的代码。</span><span class="sxs-lookup"><span data-stu-id="9edbf-109">As an initial exploration, you could implement your own code with a utility class for exponential backoff as in [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260), plus code like the following (which is also available at this [GitHub repo](https://gist.github.com/CESARDELATORRE/d80c6423a1aebaffaf387469f5194f5b)).</span></span>

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

<span data-ttu-id="9edbf-110">在客户端 C\# 应用程序（另一个 Web API 客户端微服务、ASP.NET MVC 应用程序，甚至 C\# Xamarin 应用程序）中使用此代码非常简单。</span><span class="sxs-lookup"><span data-stu-id="9edbf-110">Using this code in a client C\# application (another Web API client microservice, an ASP.NET MVC application, or even a C\# Xamarin application) is straightforward.</span></span> <span data-ttu-id="9edbf-111">下面的示例使用 HttpClient 类演示操作方法。</span><span class="sxs-lookup"><span data-stu-id="9edbf-111">The following example shows how, using the HttpClient class.</span></span>

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

<span data-ttu-id="9edbf-112">请记住，此代码仅适合用作概念证明。</span><span class="sxs-lookup"><span data-stu-id="9edbf-112">Remember that this code is suitable only as a proof of concept.</span></span> <span data-ttu-id="9edbf-113">以下部分介绍如何通过使用 HttpClientFactory 来应用更高级但却更简单的方法。</span><span class="sxs-lookup"><span data-stu-id="9edbf-113">The next sections explain how to use more sophisticated approaches while simpler, by using HttpClientFactory.</span></span>
<span data-ttu-id="9edbf-114">自 .NET Core 2.1 起可使用 HttpClientFactory，并提供 Polly 等经验证的复原库。</span><span class="sxs-lookup"><span data-stu-id="9edbf-114">HttpClientFactory is available since .NET Core 2.1, with proven resiliency libraries like Polly.</span></span> 

>[!div class="step-by-step"]
><span data-ttu-id="9edbf-115">[上一页](implement-resilient-entity-framework-core-sql-connections.md)
>[下一页](use-httpclientfactory-to-implement-resilient-http-requests.md)</span><span class="sxs-lookup"><span data-stu-id="9edbf-115">[Previous](implement-resilient-entity-framework-core-sql-connections.md)
[Next](use-httpclientfactory-to-implement-resilient-http-requests.md)</span></span>