---
title: 基于时间的缓存策略
ms.date: 03/30/2017
helpviewer_keywords:
- time-based cache policies
- cache synchronization date policy
- cache [.NET Framework], time-based policies
- freshness of cached resources
- time, cached resources
- maximum age policy
- synchronization, cache
- staleness of cached resources
- default time-based cache policy
- maximum staleness policy
- content cache policies
- expired content
- minimum freshness policy
- age of cached resources
ms.assetid: 74f0bcaf-5c95-40c1-9967-f3bbf1d2360a
ms.openlocfilehash: 4dc57ae05822a602b4647839da259ca8f469fb82
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64613836"
---
# <a name="time-based-cache-policies"></a><span data-ttu-id="ea8b3-102">基于时间的缓存策略</span><span class="sxs-lookup"><span data-stu-id="ea8b3-102">Time-Based Cache Policies</span></span>
<span data-ttu-id="ea8b3-103">基于时间的缓存策略使用检索资源的时间、随资源返回的标头和当前时间来定义缓存条目的新鲜度。</span><span class="sxs-lookup"><span data-stu-id="ea8b3-103">A time-based cache policy defines the freshness of cached entries using the time the resource was retrieved, the headers returned with the resource, and the current time.</span></span> <span data-ttu-id="ea8b3-104">设置基于时间的缓存策略时，可使用 <xref:System.Net.Cache.HttpRequestCacheLevel.Default> 基于时间的策略，也可创建自定义的基于时间的策略。</span><span class="sxs-lookup"><span data-stu-id="ea8b3-104">When setting a time-based cache policy, you can either use the <xref:System.Net.Cache.HttpRequestCacheLevel.Default> time-based policy or create a customized time-based policy.</span></span> <span data-ttu-id="ea8b3-105">当对使用超文本传输协议 (HTTP) 获得的资源使用默认的基于时间的策略时，由缓存响应中包含的标头以及 RFC 2616 第 13 和 14 节（可在 [Internet 工程任务组 (IETF)](https://www.ietf.org/) 网站上找到）中指定的行为来确定精确的缓存行为。</span><span class="sxs-lookup"><span data-stu-id="ea8b3-105">When using the default time-based policy for resources obtained using Hypertext Transfer Protocol (HTTP), the exact cache behavior is determined by the headers included in the cached response and by the behaviors specified in sections 13 and 14 of RFC 2616, available at [Internet Engineering Task Force (IETF)](https://www.ietf.org/) website.</span></span> <span data-ttu-id="ea8b3-106">如需深入了解如何为 HTTP 资源设置默认基于时间的策略的代码示例，请参阅[如何：为应用程序设置默认基于时间的缓存策略](../../../docs/framework/network-programming/how-to-set-the-default-time-based-cache-policy-for-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="ea8b3-106">For a code example that demonstrates setting the default time-based policy for HTTP resources, see [How to: Set the Default Time-Based Cache Policy for an Application](../../../docs/framework/network-programming/how-to-set-the-default-time-based-cache-policy-for-an-application.md).</span></span> <span data-ttu-id="ea8b3-107">有关演示如何创建和使用缓存策略的代码示例，请参阅[在网络应用程序中配置缓存](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="ea8b3-107">For code examples that demonstrate creating and using cache policies, see [Configuring Caching in Network Applications](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md).</span></span>  
  
## <a name="criteria-to-determine-freshness-of-cached-entries"></a><span data-ttu-id="ea8b3-108">用于确定已缓存条目新鲜度的条件</span><span class="sxs-lookup"><span data-stu-id="ea8b3-108">Criteria to Determine Freshness of Cached Entries</span></span>  
 <span data-ttu-id="ea8b3-109">要自定义基于时间的缓存策略，可指定使用以下一个或多个条件来确定已缓存条目的新鲜度：</span><span class="sxs-lookup"><span data-stu-id="ea8b3-109">To customize a time-based cache policy, you can specify that one or more of the following criteria be used to determine the freshness of cached entries:</span></span>  
  
- <span data-ttu-id="ea8b3-110">最长使用时间</span><span class="sxs-lookup"><span data-stu-id="ea8b3-110">Maximum age</span></span>  
  
- <span data-ttu-id="ea8b3-111">最长过期时间</span><span class="sxs-lookup"><span data-stu-id="ea8b3-111">Maximum staleness</span></span>  
  
- <span data-ttu-id="ea8b3-112">最低新鲜度</span><span class="sxs-lookup"><span data-stu-id="ea8b3-112">Minimum freshness</span></span>  
  
- <span data-ttu-id="ea8b3-113">缓存同步日期</span><span class="sxs-lookup"><span data-stu-id="ea8b3-113">Cache synchronization date</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea8b3-114">使用默认的基于时间的缓存策略不应与设置应用程序的默认缓存策略混淆。</span><span class="sxs-lookup"><span data-stu-id="ea8b3-114">Using the default time-based cache policy should not be confused with setting a default cache policy for your application.</span></span> <span data-ttu-id="ea8b3-115">默认的基于时间的策略是可在请求级别或应用程序级别使用的特定策略。</span><span class="sxs-lookup"><span data-stu-id="ea8b3-115">The default time-based policy is a specific policy that can be used at the request or application level.</span></span> <span data-ttu-id="ea8b3-116">应用程序的默认缓存策略是当未在请求中设置任何策略时生效的策略（基于位置或基于时间）。</span><span class="sxs-lookup"><span data-stu-id="ea8b3-116">The default cache policy for your application is a policy (location-based or time-based) that takes effect when no policy is set on a request.</span></span> <span data-ttu-id="ea8b3-117">有关为应用程序设置默认缓存策略的详细信息，请参阅 <xref:System.Net.WebRequest.DefaultCachePolicy%2A>。</span><span class="sxs-lookup"><span data-stu-id="ea8b3-117">For details on setting a default cache policy for your application, see <xref:System.Net.WebRequest.DefaultCachePolicy%2A>.</span></span>  
  
### <a name="maximum-age"></a><span data-ttu-id="ea8b3-118">最长使用时间</span><span class="sxs-lookup"><span data-stu-id="ea8b3-118">Maximum Age</span></span>  
 <span data-ttu-id="ea8b3-119">最长使用时间策略条件指定资源的缓存副本可使用的时间。</span><span class="sxs-lookup"><span data-stu-id="ea8b3-119">The maximum age policy criterion specifies the amount of time a cached copy of a resource can be used.</span></span> <span data-ttu-id="ea8b3-120">如果资源的缓存副本超过指定的时间，则必须根据服务器上的内容进行检查，重新验证该资源。</span><span class="sxs-lookup"><span data-stu-id="ea8b3-120">If the cached copy of the resource is older than the amount of time specified, the resource must be revalidated by checking it against the content on the server.</span></span> <span data-ttu-id="ea8b3-121">如果最长使用时间允许在资源过期后使用资源，则不符合此条件，除非还指定了最长过期时间值。</span><span class="sxs-lookup"><span data-stu-id="ea8b3-121">If the maximum age would allow the resource to be used after it expires, this criteria is not honored unless a maximum staleness value is also specified.</span></span>  
  
### <a name="maximum-staleness"></a><span data-ttu-id="ea8b3-122">最长过期时间</span><span class="sxs-lookup"><span data-stu-id="ea8b3-122">Maximum Staleness</span></span>  
 <span data-ttu-id="ea8b3-123">最长过期时间策略条件指定资源的缓存副本内容过期后可使用的时间。</span><span class="sxs-lookup"><span data-stu-id="ea8b3-123">The maximum staleness policy criterion specifies the length of time after content expiration that the cached copy of the resource can be used.</span></span> <span data-ttu-id="ea8b3-124">这是允许在资源过期后使用资源的唯一缓存策略条件。</span><span class="sxs-lookup"><span data-stu-id="ea8b3-124">This is the only cache policy criterion that permits resources to be used after they have expired.</span></span>  
  
### <a name="minimum-freshness"></a><span data-ttu-id="ea8b3-125">最低新鲜度</span><span class="sxs-lookup"><span data-stu-id="ea8b3-125">Minimum Freshness</span></span>  
 <span data-ttu-id="ea8b3-126">最低新鲜度策略条件指定资源的缓存副本内容过期前可使用的时间。</span><span class="sxs-lookup"><span data-stu-id="ea8b3-126">The minimum freshness policy criterion specifies the length of time before content expiration that the cached copy of the resource can be used.</span></span> <span data-ttu-id="ea8b3-127">此策略的作用是使缓存条目在过期日之前过期，因此，最低新鲜度和最长过期时间设置是相互排斥的。</span><span class="sxs-lookup"><span data-stu-id="ea8b3-127">This policy has the effect of causing a cache entry to expire before its expiration date; therefore, the minimum freshness and maximum staleness settings are mutually exclusive.</span></span>  
  
## <a name="cache-synchronization-date"></a><span data-ttu-id="ea8b3-128">缓存同步日期</span><span class="sxs-lookup"><span data-stu-id="ea8b3-128">Cache Synchronization Date</span></span>  
 <span data-ttu-id="ea8b3-129">缓存同步日期策略条件确定必须根据服务器上的内容进行检查以重新验证资源的缓存副本的时间。</span><span class="sxs-lookup"><span data-stu-id="ea8b3-129">The cache synchronization date policy criterion determines when a cached copy of a resource must be revalidated by checking it against the content on the server.</span></span> <span data-ttu-id="ea8b3-130">如果缓存项目后内容发生更改，则将从服务器检索内容并存储在缓存中，然后返回到应用程序。</span><span class="sxs-lookup"><span data-stu-id="ea8b3-130">If the content has changed since the item was cached, it is retrieved from the server, stored in the cache, and returned to the application.</span></span> <span data-ttu-id="ea8b3-131">如果内容未更改，则会更新其时间戳，并且应用程序将获取缓存内容。</span><span class="sxs-lookup"><span data-stu-id="ea8b3-131">If the content has not changed, its timestamp is updated and the application gets the cached content.</span></span>  
  
 <span data-ttu-id="ea8b3-132">缓存同步日期允许指定必须重新验证缓存内容的绝对日期。</span><span class="sxs-lookup"><span data-stu-id="ea8b3-132">The cache synchronization date allows you to specify an absolute date when cached contents must be revalidated.</span></span> <span data-ttu-id="ea8b3-133">如果上一次重新验证新缓存条目是在缓存同步日期之前，则仍将根据服务器重新验证。</span><span class="sxs-lookup"><span data-stu-id="ea8b3-133">If a fresh cache entry was last revalidated prior to the cache synchronization date, revalidation with the server still occurs.</span></span> <span data-ttu-id="ea8b3-134">如果在缓存同步日期后重新验证缓存条目，且无其他新鲜度或服务器重新验证要求使缓存条目无效，则使用缓存中的条目。</span><span class="sxs-lookup"><span data-stu-id="ea8b3-134">If the cache entry was revalidated after the cache synchronization date and there are no additional freshness or server revalidation requirements that invalidate the cached entry, the entry from the cache is used.</span></span> <span data-ttu-id="ea8b3-135">如果缓存同步日期设置为未来某个日期，则每次请求时都会重新验证该条目，直到缓存同步日期过去。</span><span class="sxs-lookup"><span data-stu-id="ea8b3-135">If the cache synchronization date is set to a future date, the entry is revalidated every time it is requested, until the cache synchronization date passes.</span></span>  
  
 <span data-ttu-id="ea8b3-136">以下主题介绍组合基于时间的缓存策略条件的影响：</span><span class="sxs-lookup"><span data-stu-id="ea8b3-136">The following topics provide information about the effects of combining time-based cache policy criteria:</span></span>  
  
- [<span data-ttu-id="ea8b3-137">缓存策略交互 — 最长使用时间和最长过期时间</span><span class="sxs-lookup"><span data-stu-id="ea8b3-137">Cache Policy Interaction—Maximum Age and Maximum Staleness</span></span>](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-maximum-staleness.md)  
  
- [<span data-ttu-id="ea8b3-138">缓存策略交互 — 最长使用时间和最低新鲜度</span><span class="sxs-lookup"><span data-stu-id="ea8b3-138">Cache Policy Interaction—Maximum Age and Minimum Freshness</span></span>](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-minimum-freshness.md)  
  
## <a name="see-also"></a><span data-ttu-id="ea8b3-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea8b3-139">See also</span></span>

- [<span data-ttu-id="ea8b3-140">网络应用程序的缓存管理</span><span class="sxs-lookup"><span data-stu-id="ea8b3-140">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)
- [<span data-ttu-id="ea8b3-141">缓存策略</span><span class="sxs-lookup"><span data-stu-id="ea8b3-141">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)
- [<span data-ttu-id="ea8b3-142">基于位置的缓存策略</span><span class="sxs-lookup"><span data-stu-id="ea8b3-142">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)
- [<span data-ttu-id="ea8b3-143">在网络应用程序中配置缓存</span><span class="sxs-lookup"><span data-stu-id="ea8b3-143">Configuring Caching in Network Applications</span></span>](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)
- [<span data-ttu-id="ea8b3-144">\<requestCaching> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="ea8b3-144">\<requestCaching> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
