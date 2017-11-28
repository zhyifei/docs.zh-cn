---
title: "如何：自定义基于时间的缓存策略"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time-based cache policies
- customizing time-based cache policies
- cache [.NET Framework], time-based policies
ms.assetid: 8d84f936-2376-4356-9264-03162e0f9279
caps.latest.revision: "15"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 58fa5c71bc459b65d35f9a59bdddccab9a0f5e56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-customize-a-time-based-cache-policy"></a><span data-ttu-id="12588-102">如何：自定义基于时间的缓存策略</span><span class="sxs-lookup"><span data-stu-id="12588-102">How to: Customize a Time-Based Cache Policy</span></span>
<span data-ttu-id="12588-103">创建基于时间的缓存策略时，可以通过为最长使用时间、最低新鲜度、最长过期时间或缓存同步日期指定值，以自定义缓存行为。</span><span class="sxs-lookup"><span data-stu-id="12588-103">When creating a time-based cache policy, you can customize caching behavior by specifying values for maximum age, minimum freshness, maximum staleness, or cache synchronization date.</span></span> <span data-ttu-id="12588-104"><xref:System.Net.Cache.HttpRequestCachePolicy> 对象提供几个构造函数，可用于指定这些值的有效组合。</span><span class="sxs-lookup"><span data-stu-id="12588-104">The <xref:System.Net.Cache.HttpRequestCachePolicy> object provides several constructors that allow you to specify valid combinations of these values.</span></span>  
  
### <a name="to-create-a-time-based-cache-policy-that-uses-a-cache-synchronization-date"></a><span data-ttu-id="12588-105">创建使用缓存同步日期的基于时间的缓存策略</span><span class="sxs-lookup"><span data-stu-id="12588-105">To create a time-based cache policy that uses a cache synchronization date</span></span>  
  
-   <span data-ttu-id="12588-106">通过将 <xref:System.DateTime> 对象传递给 <xref:System.Net.Cache.HttpRequestCachePolicy> 构造函数，可创建使用缓存同步日期的基于时间的缓存策略。</span><span class="sxs-lookup"><span data-stu-id="12588-106">Create a time-based cache policy that uses a cache synchronization date by passing a <xref:System.DateTime> object to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor.</span></span>  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateLastSyncPolicy(DateTime when)  
    {  
        HttpRequestCachePolicy policy =   
            new HttpRequestCachePolicy(when);  
        Console.WriteLine("When: {0}", when);  
        Console.WriteLine(policy.ToString());  
        return policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Function CreateLastSyncPolicy([when] As DateTime) As HttpRequestCachePolicy  
        Dim policy As New HttpRequestCachePolicy([when])  
        Console.WriteLine("When: {0}", [when])  
        Console.WriteLine(policy.ToString())  
        Return policy  
    End Function  
    ```  
  
 <span data-ttu-id="12588-107">此输出类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="12588-107">The output is similar to the following:</span></span>  
  
```  
When: 1/14/2004 8:07:30 AM  
Level:Default CacheSyncDate:1/14/2004 8:07:30 AM  
```  
  
### <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness"></a><span data-ttu-id="12588-108">创建基于最低新鲜度的基于时间的缓存策略</span><span class="sxs-lookup"><span data-stu-id="12588-108">To create a time-based cache policy that is based on minimum freshness</span></span>  
  
-   <span data-ttu-id="12588-109">通过将 <xref:System.Net.Cache.HttpCacheAgeControl.MinFresh> 指定为 `cacheAgeControl` 参数值，并且将 <xref:System.TimeSpan> 对象传递给 <xref:System.Net.Cache.HttpRequestCachePolicy> 构造函数，可创建基于最低新鲜度的基于时间的缓存策略。</span><span class="sxs-lookup"><span data-stu-id="12588-109">Create a time-based cache policy that is based on minimum freshness by specifying <xref:System.Net.Cache.HttpCacheAgeControl.MinFresh> as the `cacheAgeControl` parameter value and passing a <xref:System.TimeSpan> object to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor.</span></span>  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateMinFreshPolicy(TimeSpan span)  
    {  
        HttpRequestCachePolicy policy =   
            new HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span);  
        Console.WriteLine(policy.ToString());  
        return policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Function CreateMinFreshPolicy(span As TimeSpan) As HttpRequestCachePolicy  
        Dim policy As New HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span)  
        Console.WriteLine(policy.ToString())  
        Return policy  
    End Function  
    ```  
  
 <span data-ttu-id="12588-110">对于以下调用：</span><span class="sxs-lookup"><span data-stu-id="12588-110">For the following invocation:</span></span>  
  
```  
CreateMinFreshPolicy(new TimeSpan(1,0,0));  
```  
  
```  
Level:Default MinFresh:3600  
```  
  
### <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness-and-maximum-age"></a><span data-ttu-id="12588-111">创建基于最低新鲜度和最长使用时间的基于时间的缓存策略</span><span class="sxs-lookup"><span data-stu-id="12588-111">To create a time-based cache policy that is based on minimum freshness and maximum age</span></span>  
  
-   <span data-ttu-id="12588-112">通过将 <xref:System.Net.Cache.HttpCacheAgeControl.MaxAgeAndMinFresh> 指定为 `cacheAgeControl` 参数值，并且将两个 <xref:System.TimeSpan> 对象（一个用于指定资源的最长使用时间，另一个用于指定缓存中返回对象的最低新鲜度）传递到 <xref:System.Net.Cache.HttpRequestCachePolicy> 构造函数，可创建基于最低新鲜度和最长使用时间的一个基于时间的缓存策略。</span><span class="sxs-lookup"><span data-stu-id="12588-112">Create a time-based cache policy that is based on minimum freshness and maximum age by specifying <xref:System.Net.Cache.HttpCacheAgeControl.MaxAgeAndMinFresh> as the `cacheAgeControl` parameter value and passing two <xref:System.TimeSpan> objects to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor, one to specify the maximum age for resources and a second to specify the minimum freshness permitted for an object returned from the cache.</span></span>  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateFreshAndAgePolicy(TimeSpan freshMinimum, TimeSpan ageMaximum)  
    {  
        HttpRequestCachePolicy policy =   
        new HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum);  
        Console.WriteLine(policy.ToString());  
        return policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Function CreateFreshAndAgePolicy(freshMinimum As TimeSpan, ageMaximum As TimeSpan) As HttpRequestCachePolicy  
        Dim policy As New HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum)  
        Console.WriteLine(policy.ToString())  
        Return policy  
    End Function  
    ```  
  
 <span data-ttu-id="12588-113">对于以下调用：</span><span class="sxs-lookup"><span data-stu-id="12588-113">For the following invocation:</span></span>  
  
```  
CreateFreshAndAgePolicy(new TimeSpan(5,0,0), new TimeSpan(10,0,0));  
```  
  
```  
Level:Default MaxAge:36000 MinFresh:18000  
```  
  
## <a name="see-also"></a><span data-ttu-id="12588-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12588-114">See Also</span></span>  
 [<span data-ttu-id="12588-115">网络应用程序的缓存管理</span><span class="sxs-lookup"><span data-stu-id="12588-115">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [<span data-ttu-id="12588-116">缓存策略</span><span class="sxs-lookup"><span data-stu-id="12588-116">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)  
 [<span data-ttu-id="12588-117">基于位置的缓存策略</span><span class="sxs-lookup"><span data-stu-id="12588-117">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [<span data-ttu-id="12588-118">基于时间的缓存策略</span><span class="sxs-lookup"><span data-stu-id="12588-118">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 [<span data-ttu-id="12588-119">\<requestCaching> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="12588-119">\<requestCaching> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
