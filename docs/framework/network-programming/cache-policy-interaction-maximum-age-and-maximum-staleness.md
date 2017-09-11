---
title: "缓存策略交互 — 最长使用期限和最长过期时间"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- maximum staleness
- freshness of cached resources
- time, cached resources
- maximum age policy
- staleness of cached resources
- age of cached resources
ms.assetid: 7f775925-89a1-4956-ba90-c869c1749a94
caps.latest.revision: 11
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 834deeff69687e0edf1671b35328d41842914b4d
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="cache-policy-interactionmaximum-age-and-maximum-staleness"></a><span data-ttu-id="431ba-102">缓存策略交互 — 最长使用期限和最长过期时间</span><span class="sxs-lookup"><span data-stu-id="431ba-102">Cache Policy Interaction—Maximum Age and Maximum Staleness</span></span>
<span data-ttu-id="431ba-103">为了帮助确保将最新鲜的内容返回给客户端应用程序，客户端缓存策略和服务器重新验证要求的交互始终会造成最保守的缓存策略。</span><span class="sxs-lookup"><span data-stu-id="431ba-103">To help ensure that the freshest content is returned to the client application, the interaction of client cache policy and server revalidation requirements always results in the most conservative cache policy.</span></span> <span data-ttu-id="431ba-104">本主题中的所有示例阐明针对在 1 月 1 日缓存、1 月 4 日过期的资源的缓存策略。</span><span class="sxs-lookup"><span data-stu-id="431ba-104">All the examples in this topic illustrate the cache policy for a resource that is cached on January 1 and expires on January 4.</span></span>  
  
 <span data-ttu-id="431ba-105">在以下示例中，结合使用了最长过期时间值 (`maxStale`) 与最长使用时间 (`maxAge`)：</span><span class="sxs-lookup"><span data-stu-id="431ba-105">In the following examples, the maximum staleness value (`maxStale`) is used in conjunction with a maximum age (`maxAge`):</span></span>  
  
-   <span data-ttu-id="431ba-106">如果缓存策略设置 `maxAge` = 5 天，且未指定 `maxStale` 值，根据 `maxAge` 值，此内容在 1 月 6 日前可用。</span><span class="sxs-lookup"><span data-stu-id="431ba-106">If the cache policy sets `maxAge` = 5 days and does not specify a `maxStale` value, according to the `maxAge` value, the content is usable until January 6.</span></span> <span data-ttu-id="431ba-107">但是，根据服务器的重新验证要求，内容会在 1 月 4 日过期。</span><span class="sxs-lookup"><span data-stu-id="431ba-107">However, according to the server's revalidation requirements, the content expires on January 4.</span></span> <span data-ttu-id="431ba-108">因为内容过期日期更保守（更早），所以它优先于 `maxAge` 策略。</span><span class="sxs-lookup"><span data-stu-id="431ba-108">Because the content expiration date is more conservative (sooner), it takes precedence over the `maxAge` policy.</span></span> <span data-ttu-id="431ba-109">因此，即使尚未达到最长使用时间，此内容在 1 月 4 日便会过期，并且必须进行重新验证。</span><span class="sxs-lookup"><span data-stu-id="431ba-109">Therefore, the content expires on January 4 and must be revalidated even though its maximum age has not been reached.</span></span>  
  
-   <span data-ttu-id="431ba-110">如果缓存策略设置 `maxAge` = 5 天，`maxStale` = 3 天，根据 `maxAge` 值，此内容在 1 月 6 日前可用。</span><span class="sxs-lookup"><span data-stu-id="431ba-110">If the cache policy sets `maxAge` = 5 days and `maxStale` = 3 days, according to the `maxAge` value, the content is usable until January 6.</span></span> <span data-ttu-id="431ba-111">根据 `maxStale` 值，此内容在 1 月 7 日前可用。</span><span class="sxs-lookup"><span data-stu-id="431ba-111">According to the `maxStale` value, the content is usable until January 7.</span></span> <span data-ttu-id="431ba-112">因此，会在 1 月 6 日重新验证此内容。</span><span class="sxs-lookup"><span data-stu-id="431ba-112">Therefore, the content gets revalidated on January 6.</span></span>  
  
-   <span data-ttu-id="431ba-113">如果缓存策略设置 `maxAge` = 5 天，`maxStale` = 1 天，根据 `maxAge` 值，此内容在 1 月 6 日前可用。</span><span class="sxs-lookup"><span data-stu-id="431ba-113">If the cache policy sets `maxAge` = 5 days and `maxStale` = 1 day, according to the `maxAge` value, the content is usable until January 6.</span></span> <span data-ttu-id="431ba-114">根据 `maxStale` 值，此内容在 1 月 5 日前可用。</span><span class="sxs-lookup"><span data-stu-id="431ba-114">According to the `maxStale` value, the content is usable until January 5.</span></span> <span data-ttu-id="431ba-115">因此，会在 1 月 5 日重新验证此内容。</span><span class="sxs-lookup"><span data-stu-id="431ba-115">Therefore, the content gets revalidated on January 5.</span></span>  
  
 <span data-ttu-id="431ba-116">当内容的最长使用时间小于过期日期时，更保守的缓存行为占据优先级，且最长过期时间值不会有任何效果。</span><span class="sxs-lookup"><span data-stu-id="431ba-116">When the maximum age is less than the content expiration date, the more conservative caching behavior always prevails and the maximum staleness value has no effect.</span></span> <span data-ttu-id="431ba-117">以下示例阐明了在内容过期之前到达最长使用时间 (`maxAge`) 时设置最长过期时间 (`maxStale`) 值的效果：</span><span class="sxs-lookup"><span data-stu-id="431ba-117">The following examples illustrate the effect of setting a maximum staleness (`maxStale`) value when the maximum age (`maxAge`) is reached before the content expires:</span></span>  
  
-   <span data-ttu-id="431ba-118">如果缓存策略设置 `maxAge` = 1 天，且未指定 `maxStale` 值，即使内容尚未过期，也会在 1 月 2 日重新验证此内容。</span><span class="sxs-lookup"><span data-stu-id="431ba-118">If the cache policy sets `maxAge` = 1 day and does not specify a value for `maxStale` value, the content is revalidated on January 2 even though it has not expired.</span></span>  
  
-   <span data-ttu-id="431ba-119">如果设缓存策略设置 `maxAge` = 1 天，`maxStale` = 3 天，会在 1 月 2 日重新验证此内容以强制实施更保守的策略设置。</span><span class="sxs-lookup"><span data-stu-id="431ba-119">If the cache policy sets `maxAge` = 1 day and `maxStale` = 3 days, the content is revalidated on January 2 to enforce the more conservative policy setting.</span></span>  
  
-   <span data-ttu-id="431ba-120">如果缓存策略设置 `maxAge` = 1 天，`maxStale` = 1 天，会在 1 月 2 日重新验证此内容。</span><span class="sxs-lookup"><span data-stu-id="431ba-120">If the cache policy sets `maxAge` = 1 day and `maxStale` = 1 day, the content is revalidated on January 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="431ba-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="431ba-121">See Also</span></span>  
 <span data-ttu-id="431ba-122">[网络应用程序的缓存管理](../../../docs/framework/network-programming/cache-management-for-network-applications.md) </span><span class="sxs-lookup"><span data-stu-id="431ba-122">[Cache Management for Network Applications](../../../docs/framework/network-programming/cache-management-for-network-applications.md) </span></span>  
 <span data-ttu-id="431ba-123">[缓存策略](../../../docs/framework/network-programming/cache-policy.md) </span><span class="sxs-lookup"><span data-stu-id="431ba-123">[Cache Policy](../../../docs/framework/network-programming/cache-policy.md) </span></span>  
 <span data-ttu-id="431ba-124">[基于位置的缓存策略](../../../docs/framework/network-programming/location-based-cache-policies.md) </span><span class="sxs-lookup"><span data-stu-id="431ba-124">[Location-Based Cache Policies](../../../docs/framework/network-programming/location-based-cache-policies.md) </span></span>  
 <span data-ttu-id="431ba-125">[基于时间的缓存策略](../../../docs/framework/network-programming/time-based-cache-policies.md) </span><span class="sxs-lookup"><span data-stu-id="431ba-125">[Time-Based Cache Policies](../../../docs/framework/network-programming/time-based-cache-policies.md) </span></span>  
 <span data-ttu-id="431ba-126">[在网络应用程序中配置缓存](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md) </span><span class="sxs-lookup"><span data-stu-id="431ba-126">[Configuring Caching in Network Applications](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md) </span></span>  
 [<span data-ttu-id="431ba-127">缓存策略交互 — 最长使用时间和最低新鲜度</span><span class="sxs-lookup"><span data-stu-id="431ba-127">Cache Policy Interaction—Maximum Age and Minimum Freshness</span></span>](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-minimum-freshness.md)

