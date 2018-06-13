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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f25f04a144fa806297b018bf3548b8feb506f67d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33392546"
---
# <a name="time-based-cache-policies"></a><span data-ttu-id="9cefc-102">基于时间的缓存策略</span><span class="sxs-lookup"><span data-stu-id="9cefc-102">Time-Based Cache Policies</span></span>
<span data-ttu-id="9cefc-103">基于时间的缓存策略使用检索资源的时间、随资源返回的标头和当前时间来定义缓存条目的新鲜度。</span><span class="sxs-lookup"><span data-stu-id="9cefc-103">A time-based cache policy defines the freshness of cached entries using the time the resource was retrieved, the headers returned with the resource, and the current time.</span></span> <span data-ttu-id="9cefc-104">设置基于时间的缓存策略时，可使用 <xref:System.Net.Cache.HttpRequestCacheLevel.Default> 基于时间的策略，也可创建自定义的基于时间的策略。</span><span class="sxs-lookup"><span data-stu-id="9cefc-104">When setting a time-based cache policy, you can either use the <xref:System.Net.Cache.HttpRequestCacheLevel.Default> time-based policy or create a customized time-based policy.</span></span> <span data-ttu-id="9cefc-105">当对使用超文本传输协议 (HTTP) 获得的资源使用默认的基于时间的策略时，由缓存响应中包含的标头以及 RFC 2616 第 13 和 14 节（可在 [http://www.ietf.org](http://www.ietf.org/) 处查找）中指定的行为来确定精确的缓存行为。有关演示如何为 HTTP 资源设置默认的基于时间策略的代码示例，请参阅[如何：为应用程序设置默认基于时间的缓存策略](../../../docs/framework/network-programming/how-to-set-the-default-time-based-cache-policy-for-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="9cefc-105">When using the default time-based policy for resources obtained using Hypertext Transfer Protocol (HTTP), the exact cache behavior is determined by the headers included in the cached response and by the behaviors specified in sections 13 and 14 of RFC 2616, available at [http://www.ietf.org](http://www.ietf.org/). For a code example that demonstrates setting the default time-based policy for HTTP resources, see [How to: Set the Default Time-Based Cache Policy for an Application](../../../docs/framework/network-programming/how-to-set-the-default-time-based-cache-policy-for-an-application.md).</span></span> <span data-ttu-id="9cefc-106">有关演示如何创建和使用缓存策略的代码示例，请参阅[在网络应用程序中配置缓存](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="9cefc-106">For code examples that demonstrate creating and using cache policies, see [Configuring Caching in Network Applications](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md).</span></span>  
  
## <a name="criteria-to-determine-freshness-of-cached-entries"></a><span data-ttu-id="9cefc-107">用于确定已缓存条目新鲜度的条件</span><span class="sxs-lookup"><span data-stu-id="9cefc-107">Criteria to Determine Freshness of Cached Entries</span></span>  
 <span data-ttu-id="9cefc-108">要自定义基于时间的缓存策略，可指定使用以下一个或多个条件来确定已缓存条目的新鲜度：</span><span class="sxs-lookup"><span data-stu-id="9cefc-108">To customize a time-based cache policy, you can specify that one or more of the following criteria be used to determine the freshness of cached entries:</span></span>  
  
-   <span data-ttu-id="9cefc-109">最长使用时间</span><span class="sxs-lookup"><span data-stu-id="9cefc-109">Maximum age</span></span>  
  
-   <span data-ttu-id="9cefc-110">最长过期时间</span><span class="sxs-lookup"><span data-stu-id="9cefc-110">Maximum staleness</span></span>  
  
-   <span data-ttu-id="9cefc-111">最低新鲜度</span><span class="sxs-lookup"><span data-stu-id="9cefc-111">Minimum freshness</span></span>  
  
-   <span data-ttu-id="9cefc-112">缓存同步日期</span><span class="sxs-lookup"><span data-stu-id="9cefc-112">Cache synchronization date</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9cefc-113">使用默认的基于时间的缓存策略不应与设置应用程序的默认缓存策略混淆。</span><span class="sxs-lookup"><span data-stu-id="9cefc-113">Using the default time-based cache policy should not be confused with setting a default cache policy for your application.</span></span> <span data-ttu-id="9cefc-114">默认的基于时间的策略是可在请求级别或应用程序级别使用的特定策略。</span><span class="sxs-lookup"><span data-stu-id="9cefc-114">The default time-based policy is a specific policy that can be used at the request or application level.</span></span> <span data-ttu-id="9cefc-115">应用程序的默认缓存策略是当未在请求中设置任何策略时生效的策略（基于位置或基于时间）。</span><span class="sxs-lookup"><span data-stu-id="9cefc-115">The default cache policy for your application is a policy (location-based or time-based) that takes effect when no policy is set on a request.</span></span> <span data-ttu-id="9cefc-116">有关为应用程序设置默认缓存策略的详细信息，请参阅 <xref:System.Net.WebRequest.DefaultCachePolicy%2A>。</span><span class="sxs-lookup"><span data-stu-id="9cefc-116">For details on setting a default cache policy for your application, see <xref:System.Net.WebRequest.DefaultCachePolicy%2A>.</span></span>  
  
### <a name="maximum-age"></a><span data-ttu-id="9cefc-117">最长使用时间</span><span class="sxs-lookup"><span data-stu-id="9cefc-117">Maximum Age</span></span>  
 <span data-ttu-id="9cefc-118">最长使用时间策略条件指定资源的缓存副本可使用的时间。</span><span class="sxs-lookup"><span data-stu-id="9cefc-118">The maximum age policy criterion specifies the amount of time a cached copy of a resource can be used.</span></span> <span data-ttu-id="9cefc-119">如果资源的缓存副本超过指定的时间，则必须根据服务器上的内容进行检查，重新验证该资源。</span><span class="sxs-lookup"><span data-stu-id="9cefc-119">If the cached copy of the resource is older than the amount of time specified, the resource must be revalidated by checking it against the content on the server.</span></span> <span data-ttu-id="9cefc-120">如果最长使用时间允许在资源过期后使用资源，则不符合此条件，除非还指定了最长过期时间值。</span><span class="sxs-lookup"><span data-stu-id="9cefc-120">If the maximum age would allow the resource to be used after it expires, this criteria is not honored unless a maximum staleness value is also specified.</span></span>  
  
### <a name="maximum-staleness"></a><span data-ttu-id="9cefc-121">最长过期时间</span><span class="sxs-lookup"><span data-stu-id="9cefc-121">Maximum Staleness</span></span>  
 <span data-ttu-id="9cefc-122">最长过期时间策略条件指定资源的缓存副本内容过期后可使用的时间。</span><span class="sxs-lookup"><span data-stu-id="9cefc-122">The maximum staleness policy criterion specifies the length of time after content expiration that the cached copy of the resource can be used.</span></span> <span data-ttu-id="9cefc-123">这是允许在资源过期后使用资源的唯一缓存策略条件。</span><span class="sxs-lookup"><span data-stu-id="9cefc-123">This is the only cache policy criterion that permits resources to be used after they have expired.</span></span>  
  
### <a name="minimum-freshness"></a><span data-ttu-id="9cefc-124">最低新鲜度</span><span class="sxs-lookup"><span data-stu-id="9cefc-124">Minimum Freshness</span></span>  
 <span data-ttu-id="9cefc-125">最低新鲜度策略条件指定资源的缓存副本内容过期前可使用的时间。</span><span class="sxs-lookup"><span data-stu-id="9cefc-125">The minimum freshness policy criterion specifies the length of time before content expiration that the cached copy of the resource can be used.</span></span> <span data-ttu-id="9cefc-126">此策略的作用是使缓存条目在过期日之前过期，因此，最低新鲜度和最长过期时间设置是相互排斥的。</span><span class="sxs-lookup"><span data-stu-id="9cefc-126">This policy has the effect of causing a cache entry to expire before its expiration date; therefore, the minimum freshness and maximum staleness settings are mutually exclusive.</span></span>  
  
## <a name="cache-synchronization-date"></a><span data-ttu-id="9cefc-127">缓存同步日期</span><span class="sxs-lookup"><span data-stu-id="9cefc-127">Cache Synchronization Date</span></span>  
 <span data-ttu-id="9cefc-128">缓存同步日期策略条件确定必须根据服务器上的内容进行检查以重新验证资源的缓存副本的时间。</span><span class="sxs-lookup"><span data-stu-id="9cefc-128">The cache synchronization date policy criterion determines when a cached copy of a resource must be revalidated by checking it against the content on the server.</span></span> <span data-ttu-id="9cefc-129">如果缓存项目后内容发生更改，则将从服务器检索内容并存储在缓存中，然后返回到应用程序。</span><span class="sxs-lookup"><span data-stu-id="9cefc-129">If the content has changed since the item was cached, it is retrieved from the server, stored in the cache, and returned to the application.</span></span> <span data-ttu-id="9cefc-130">如果内容未更改，则会更新其时间戳，并且应用程序将获取缓存内容。</span><span class="sxs-lookup"><span data-stu-id="9cefc-130">If the content has not changed, its timestamp is updated and the application gets the cached content.</span></span>  
  
 <span data-ttu-id="9cefc-131">缓存同步日期允许指定必须重新验证缓存内容的绝对日期。</span><span class="sxs-lookup"><span data-stu-id="9cefc-131">The cache synchronization date allows you to specify an absolute date when cached contents must be revalidated.</span></span> <span data-ttu-id="9cefc-132">如果上一次重新验证新缓存条目是在缓存同步日期之前，则仍将根据服务器重新验证。</span><span class="sxs-lookup"><span data-stu-id="9cefc-132">If a fresh cache entry was last revalidated prior to the cache synchronization date, revalidation with the server still occurs.</span></span> <span data-ttu-id="9cefc-133">如果在缓存同步日期后重新验证缓存条目，且无其他新鲜度或服务器重新验证要求使缓存条目无效，则使用缓存中的条目。</span><span class="sxs-lookup"><span data-stu-id="9cefc-133">If the cache entry was revalidated after the cache synchronization date and there are no additional freshness or server revalidation requirements that invalidate the cached entry, the entry from the cache is used.</span></span> <span data-ttu-id="9cefc-134">如果缓存同步日期设置为未来某个日期，则每次请求时都会重新验证该条目，直到缓存同步日期过去。</span><span class="sxs-lookup"><span data-stu-id="9cefc-134">If the cache synchronization date is set to a future date, the entry is revalidated every time it is requested, until the cache synchronization date passes.</span></span>  
  
 <span data-ttu-id="9cefc-135">以下主题介绍组合基于时间的缓存策略条件的影响：</span><span class="sxs-lookup"><span data-stu-id="9cefc-135">The following topics provide information about the effects of combining time-based cache policy criteria:</span></span>  
  
-   [<span data-ttu-id="9cefc-136">缓存策略交互 — 最长使用时间和最长过期时间</span><span class="sxs-lookup"><span data-stu-id="9cefc-136">Cache Policy Interaction—Maximum Age and Maximum Staleness</span></span>](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-maximum-staleness.md)  
  
-   [<span data-ttu-id="9cefc-137">缓存策略交互 — 最长使用时间和最低新鲜度</span><span class="sxs-lookup"><span data-stu-id="9cefc-137">Cache Policy Interaction—Maximum Age and Minimum Freshness</span></span>](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-minimum-freshness.md)  
  
## <a name="see-also"></a><span data-ttu-id="9cefc-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="9cefc-138">See Also</span></span>  
 [<span data-ttu-id="9cefc-139">网络应用程序的缓存管理</span><span class="sxs-lookup"><span data-stu-id="9cefc-139">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [<span data-ttu-id="9cefc-140">缓存策略</span><span class="sxs-lookup"><span data-stu-id="9cefc-140">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)  
 [<span data-ttu-id="9cefc-141">基于位置的缓存策略</span><span class="sxs-lookup"><span data-stu-id="9cefc-141">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [<span data-ttu-id="9cefc-142">在网络应用程序中配置缓存</span><span class="sxs-lookup"><span data-stu-id="9cefc-142">Configuring Caching in Network Applications</span></span>](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)  
 [<span data-ttu-id="9cefc-143">\<requestCaching> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="9cefc-143">\<requestCaching> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
