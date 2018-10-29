---
title: 基于位置的缓存策略
ms.date: 03/30/2017
helpviewer_keywords:
- Cache If Available policy
- reload policy
- location-based cache policies
- Cache Only policy
- local cache
- intermediate cache
- No Cache No Store policy
- cache [.NET Framework], location-based policies
- Revalidate policy
- freshness of cached resources
- Cache Or Next Cache Only policy
- Refresh policy
ms.assetid: e41d7f1a-0a6a-4dee-97d1-c6a8b6a07fc2
ms.openlocfilehash: 1bbaf4fc85fe4d7e3d3737cf62cb63d8e09927cd
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50194392"
---
# <a name="location-based-cache-policies"></a><span data-ttu-id="1fda6-102">基于位置的缓存策略</span><span class="sxs-lookup"><span data-stu-id="1fda6-102">Location-Based Cache Policies</span></span>
<span data-ttu-id="1fda6-103">基于位置的缓存策略根据可从中获取所请求资源的位置来定义有效缓存条目的新鲜度。</span><span class="sxs-lookup"><span data-stu-id="1fda6-103">A location-based cache policy defines the freshness of valid cached entries based on where the requested resource can be taken from.</span></span> <span data-ttu-id="1fda6-104">如果使用它不违反服务器指定的重新验证要求，则缓存资源为有效。</span><span class="sxs-lookup"><span data-stu-id="1fda6-104">A cached resource is valid if using it does not does not violate server-specified revalidation requirements.</span></span> <span data-ttu-id="1fda6-105">基于位置的缓存策略通过使用 <xref:System.Net.Cache.RequestCachePolicy> 或 <xref:System.Net.Cache.HttpRequestCachePolicy> 类构造函数以编程方式创建。</span><span class="sxs-lookup"><span data-stu-id="1fda6-105">A location-based cache policy is created programmatically by using a <xref:System.Net.Cache.RequestCachePolicy> or <xref:System.Net.Cache.HttpRequestCachePolicy> class constructor.</span></span> <span data-ttu-id="1fda6-106">使用 <xref:System.Net.Cache.RequestCacheLevel> 或 <xref:System.Net.Cache.HttpRequestCacheLevel> 枚举值将基于位置的策略的类型传递给构造函数。</span><span class="sxs-lookup"><span data-stu-id="1fda6-106">The type of location-based policy is passed to the constructor using a <xref:System.Net.Cache.RequestCacheLevel> or <xref:System.Net.Cache.HttpRequestCacheLevel> enumeration value.</span></span> <span data-ttu-id="1fda6-107">有关创建基于位置的缓存策略的代码示例，请参阅[如何：为应用程序设置基于位置的缓存策略](../../../docs/framework/network-programming/how-to-set-a-location-based-cache-policy-for-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="1fda6-107">For code examples that create location-based cache policies, see [How to: Set a Location-Based Cache Policy for an Application](../../../docs/framework/network-programming/how-to-set-a-location-based-cache-policy-for-an-application.md).</span></span> <span data-ttu-id="1fda6-108">以下部分介绍超文本传输协议（http 和 https）资源每种基于位置的缓存策略。</span><span class="sxs-lookup"><span data-stu-id="1fda6-108">The following sections explain each type of location-based cache policy for Hypertext Transfer Protocol (http and https) resources.</span></span>  
  
## <a name="cache-if-available-policy"></a><span data-ttu-id="1fda6-109">“如果可用则缓存”策略</span><span class="sxs-lookup"><span data-stu-id="1fda6-109">Cache If Available Policy</span></span>  
 <span data-ttu-id="1fda6-110">如果本地缓存中存在有效的请求资源，则使用缓存资源；否则，将资源请求发送到服务器。</span><span class="sxs-lookup"><span data-stu-id="1fda6-110">If a valid requested resource is in the local cache, the cached resource is used; otherwise, the request for the resource is sent to the server.</span></span> <span data-ttu-id="1fda6-111">如果客户端和服务器之间的任何缓存中存在请求资源，则可由中间缓存满足该请求。</span><span class="sxs-lookup"><span data-stu-id="1fda6-111">If the requested resource is available in any cache between the client and the server, the request can be satisfied by an intermediate cache.</span></span>  
  
## <a name="cache-only-policy"></a><span data-ttu-id="1fda6-112">“仅缓存”策略</span><span class="sxs-lookup"><span data-stu-id="1fda6-112">Cache Only Policy</span></span>  
 <span data-ttu-id="1fda6-113">如果本地缓存中存在有效的请求资源，则使用缓存资源。</span><span class="sxs-lookup"><span data-stu-id="1fda6-113">If a valid requested resource is in the local cache, the cached resource is used.</span></span> <span data-ttu-id="1fda6-114">指定此缓存策略级别时，如果本地缓存中没有该项，将引发 <xref:System.Net.WebException> 异常。</span><span class="sxs-lookup"><span data-stu-id="1fda6-114">When this cache policy level is specified, a <xref:System.Net.WebException> exception is thrown if the item is not in the local cache.</span></span>  
  
## <a name="cache-or-next-cache-only-policy"></a><span data-ttu-id="1fda6-115">“缓存或仅下一个缓存”策略</span><span class="sxs-lookup"><span data-stu-id="1fda6-115">Cache Or Next Cache Only Policy</span></span>  
 <span data-ttu-id="1fda6-116">如果有效的请求资源位于本地缓存或局域网的中间缓存，则使用缓存资源。</span><span class="sxs-lookup"><span data-stu-id="1fda6-116">If a valid requested resource is in the local cache or an intermediate cache on the local area network, the cached resource is used.</span></span> <span data-ttu-id="1fda6-117">否则，将引发 <xref:System.Net.WebException> 异常。</span><span class="sxs-lookup"><span data-stu-id="1fda6-117">Otherwise, a <xref:System.Net.WebException> exception is thrown.</span></span> <span data-ttu-id="1fda6-118">在 HTTP 缓存协议中，这是通过 only-if-cached 缓存控制指令实现的。</span><span class="sxs-lookup"><span data-stu-id="1fda6-118">In the HTTP caching protocol, this is achieved using the only-if-cached cache control directive.</span></span>  
  
## <a name="no-cache-no-store-policy"></a><span data-ttu-id="1fda6-119">“无缓存无存储”策略</span><span class="sxs-lookup"><span data-stu-id="1fda6-119">No Cache No Store Policy</span></span>  
 <span data-ttu-id="1fda6-120">请求资源未从任何缓存中使用，并且未放于任何缓存中。</span><span class="sxs-lookup"><span data-stu-id="1fda6-120">A requested resource is never used from any cache and is never placed in any cache.</span></span> <span data-ttu-id="1fda6-121">如果请求资源存在于本地缓存，则会将其删除。</span><span class="sxs-lookup"><span data-stu-id="1fda6-121">If a requested resource is present in the local cache, it is removed.</span></span> <span data-ttu-id="1fda6-122">此策略级别向中间缓存指示 - 它们也应删除资源。</span><span class="sxs-lookup"><span data-stu-id="1fda6-122">This policy level indicates to intermediate caches that they should also remove the resource.</span></span> <span data-ttu-id="1fda6-123">在 HTTP 缓存协议中，这是通过 no-store 缓存控制指令实现的。</span><span class="sxs-lookup"><span data-stu-id="1fda6-123">In the HTTP caching protocol, this is achieved using the no-store cache control directive.</span></span>  
  
## <a name="refresh-policy"></a><span data-ttu-id="1fda6-124">刷新策略</span><span class="sxs-lookup"><span data-stu-id="1fda6-124">Refresh Policy</span></span>  
 <span data-ttu-id="1fda6-125">如果可从服务器获取请求资源，或可在本地缓存之外的缓存中找到请求资源，则可使用请求资源。</span><span class="sxs-lookup"><span data-stu-id="1fda6-125">A requested resource can be used if it is obtained from the server or found in a cache other than the local cache.</span></span> <span data-ttu-id="1fda6-126">在请求可由中间缓存满足之前，该缓存必须通过服务器重新验证其缓存条目。</span><span class="sxs-lookup"><span data-stu-id="1fda6-126">Before the request can be satisfied by an intermediate cache, that cache must revalidate its cached entry with the server.</span></span> <span data-ttu-id="1fda6-127">在 HTTP 缓存协议中，这是通过 max-age = 0 缓存控制指令和 no-cache Pragma 标头实现的。</span><span class="sxs-lookup"><span data-stu-id="1fda6-127">In the HTTP caching protocol, this is achieved using the max-age = 0 cache control directive and the no-cache Pragma header.</span></span>  
  
## <a name="reload-policy"></a><span data-ttu-id="1fda6-128">重新加载策略</span><span class="sxs-lookup"><span data-stu-id="1fda6-128">Reload Policy</span></span>  
 <span data-ttu-id="1fda6-129">请求资源必须从服务器获取。</span><span class="sxs-lookup"><span data-stu-id="1fda6-129">Requested resources must be obtained from the server.</span></span> <span data-ttu-id="1fda6-130">响应可能保存在本地缓存。</span><span class="sxs-lookup"><span data-stu-id="1fda6-130">The response might be saved in the local cache.</span></span> <span data-ttu-id="1fda6-131">在 HTTP 缓存协议中，这是通过 no-cache 缓存控制指令和 no-cache Pragma 标头实现的。</span><span class="sxs-lookup"><span data-stu-id="1fda6-131">In the HTTP caching protocol, this is achieved using the no-cache cache control directive and the no-cache Pragma header.</span></span>  
  
## <a name="revalidate-policy"></a><span data-ttu-id="1fda6-132">重新验证策略</span><span class="sxs-lookup"><span data-stu-id="1fda6-132">Revalidate Policy</span></span>  
 <span data-ttu-id="1fda6-133">将缓存中的资源副本与服务器上的副本进行比较。</span><span class="sxs-lookup"><span data-stu-id="1fda6-133">Compares the copy of the resource in the cache with the copy on the server.</span></span> <span data-ttu-id="1fda6-134">如果服务器上的副本较新，则用它来满足请求并替换缓存中的副本。</span><span class="sxs-lookup"><span data-stu-id="1fda6-134">If the copy on the server is newer, it is used to satisfy the request and replaces the copy in the cache.</span></span> <span data-ttu-id="1fda6-135">如果缓存中的副本与服务器副本相同，则使用缓存副本。</span><span class="sxs-lookup"><span data-stu-id="1fda6-135">If the copy in the cache is the same as the server copy, the cached copy is used.</span></span> <span data-ttu-id="1fda6-136">在 HTTP 缓存协议中，这是通过条件请求来实现的。</span><span class="sxs-lookup"><span data-stu-id="1fda6-136">In the HTTP caching protocol, this is achieved using a conditional request.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fda6-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="1fda6-137">See Also</span></span>  
 [<span data-ttu-id="1fda6-138">网络应用程序的缓存管理</span><span class="sxs-lookup"><span data-stu-id="1fda6-138">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [<span data-ttu-id="1fda6-139">缓存策略</span><span class="sxs-lookup"><span data-stu-id="1fda6-139">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)  
 [<span data-ttu-id="1fda6-140">基于时间的缓存策略</span><span class="sxs-lookup"><span data-stu-id="1fda6-140">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 [<span data-ttu-id="1fda6-141">在网络应用程序中配置缓存</span><span class="sxs-lookup"><span data-stu-id="1fda6-141">Configuring Caching in Network Applications</span></span>](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)  
 [<span data-ttu-id="1fda6-142">\<requestCaching> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="1fda6-142">\<requestCaching> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
