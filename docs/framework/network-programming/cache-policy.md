---
title: "缓存策略"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- time-based cache policies
- location-based cache policies
- cache [.NET Framework], policies
- request cache policies
- freshness of cached resources
- content cache policies
- expired content
ms.assetid: 1a7e04ec-7872-41c2-96c6-52566dcb412b
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 375c3b44f505a9bf36ce721c5ccde9b888114309
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="cache-policy"></a><span data-ttu-id="12483-102">缓存策略</span><span class="sxs-lookup"><span data-stu-id="12483-102">Cache Policy</span></span>
<span data-ttu-id="12483-103">缓存策略定义规则，这些规则用于确定使用已请求资源的缓存副本是否可以满足请求。</span><span class="sxs-lookup"><span data-stu-id="12483-103">A cache policy defines rules that are used to determine whether a request can be satisfied using a cached copy of the requested resource.</span></span> <span data-ttu-id="12483-104">尽管应用程序为新鲜度指定客户端缓存要求，但有效的缓存策略是由客户端缓存要求、服务器的内容有效期限要求以及服务器的重新验证要求确定的。</span><span class="sxs-lookup"><span data-stu-id="12483-104">Applications specify client cache requirements for freshness, but the effective cache policy is determined by the client cache requirements, the server's content expiration requirements, and the server's revalidation requirements.</span></span> <span data-ttu-id="12483-105">客户端缓存策略和服务器要求的交互始终会造成最保守的缓存策略，有助于确保将最新鲜的内容返回给客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="12483-105">The interaction of client cache policy and server requirements always results in the most conservative cache policy, to help ensure that the freshest content is returned to the client application.</span></span>  
  
 <span data-ttu-id="12483-106">缓存策略是基于位置或基于时间的。</span><span class="sxs-lookup"><span data-stu-id="12483-106">Cache policies are either location-based or time-based.</span></span> <span data-ttu-id="12483-107">基于位置的缓存策略根据可从中获取已请求资源的位置定义缓存条目的新鲜度。</span><span class="sxs-lookup"><span data-stu-id="12483-107">A location-based cache policy defines the freshness of cached entries based on where the requested resource can be taken from.</span></span> <span data-ttu-id="12483-108">基于时间的缓存策略使用检索资源的时间、随资源返回的标头和当前时间来定义缓存条目的新鲜度。</span><span class="sxs-lookup"><span data-stu-id="12483-108">A time-based cache policy defines the freshness of cached entries using the time the resource was retrieved, headers returned with the resource, and the current time.</span></span> <span data-ttu-id="12483-109">大多数应用程序可以使用基于默认时间的缓存策略，这可在 [http://www.ietf.org](http://www.ietf.org/) 上实现 RFC 2616 中指定的缓存策略。</span><span class="sxs-lookup"><span data-stu-id="12483-109">Most applications can use the default time-based cache policy, which implements the caching policy specified in RFC 2616, available at [http://www.ietf.org](http://www.ietf.org/).</span></span>  
  
 <span data-ttu-id="12483-110">下表中所述的类用于指定缓存策略。</span><span class="sxs-lookup"><span data-stu-id="12483-110">The classes described in the following table are used to specify cache policies.</span></span>  
  
|<span data-ttu-id="12483-111">类名</span><span class="sxs-lookup"><span data-stu-id="12483-111">Class name</span></span>|<span data-ttu-id="12483-112">描述</span><span class="sxs-lookup"><span data-stu-id="12483-112">Description</span></span>|  
|----------------|-----------------|  
|<xref:System.Net.Cache.HttpRequestCachePolicy>|<span data-ttu-id="12483-113">表示使用 <xref:System.Net.HttpWebRequest> 对象请求的资源的基于位置和基于时间的缓存策略。</span><span class="sxs-lookup"><span data-stu-id="12483-113">Represents location-based and time-based cache policies for resources requested using <xref:System.Net.HttpWebRequest> objects.</span></span>|  
|<xref:System.Net.Cache.RequestCachePolicy>|<span data-ttu-id="12483-114">表示使用 <xref:System.Net.WebRequest> 对象请求的资源的基于位置的缓存策略或基于 <xref:System.Net.Cache.RequestCacheLevel.Default> 时间的缓存策略。</span><span class="sxs-lookup"><span data-stu-id="12483-114">Represents location-based cache policies or the <xref:System.Net.Cache.RequestCacheLevel.Default> time-based cache policy for resources requested using <xref:System.Net.WebRequest> objects.</span></span>|  
|<xref:System.Net.Cache.HttpCacheAgeControl>|<span data-ttu-id="12483-115">指定用于创建基于时间的 <xref:System.Net.Cache.HttpRequestCachePolicy> 对象的值。</span><span class="sxs-lookup"><span data-stu-id="12483-115">Specifies values used to create time-based <xref:System.Net.Cache.HttpRequestCachePolicy> objects.</span></span>|  
|<xref:System.Net.Cache.HttpRequestCacheLevel>|<span data-ttu-id="12483-116">指定用于创建基于位置和基于时间的 <xref:System.Net.Cache.HttpRequestCachePolicy> 对象的值。</span><span class="sxs-lookup"><span data-stu-id="12483-116">Specifies values used to create location-based and time-based <xref:System.Net.Cache.HttpRequestCachePolicy> objects.</span></span>|  
|<xref:System.Net.Cache.RequestCacheLevel>|<span data-ttu-id="12483-117">指定用于创建基于位置或基于 <xref:System.Net.Cache.RequestCacheLevel.Default> 时间的 <xref:System.Net.Cache.RequestCachePolicy> 对象的值。</span><span class="sxs-lookup"><span data-stu-id="12483-117">Specifies values used to create location-based or the <xref:System.Net.Cache.RequestCacheLevel.Default> time-based <xref:System.Net.Cache.RequestCachePolicy> objects.</span></span>|  
  
 <span data-ttu-id="12483-118">可以为应用程序发出的所有请求或为各个单独的请求定义一个缓存策略。</span><span class="sxs-lookup"><span data-stu-id="12483-118">You can define a cache policy for all requests made by your application or for individual requests.</span></span> <span data-ttu-id="12483-119">在同时指定应用程序级缓存策略和请求级缓存策略的情况下，会使用请求级策略。</span><span class="sxs-lookup"><span data-stu-id="12483-119">When you specify both an application-level cache policy and a request-level cache policy, the request-level policy is used.</span></span> <span data-ttu-id="12483-120">通过以编程方式或通过使用应用程序或计算机配置文件，以指定应用程序级缓存策略。</span><span class="sxs-lookup"><span data-stu-id="12483-120">You can specify an application-level cache policy programmatically or by using the application or machine configuration files.</span></span> <span data-ttu-id="12483-121">有关详细信息，请参阅 [\<requestCaching> 元素（网络设置）](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="12483-121">For more information, see [\<requestCaching> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md).</span></span>  
  
 <span data-ttu-id="12483-122">若要创建缓存策略，必须通过创建 <xref:System.Net.Cache.RequestCachePolicy> 或 <xref:System.Net.Cache.HttpRequestCachePolicy> 类的实例来创建策略对象。</span><span class="sxs-lookup"><span data-stu-id="12483-122">To create a cache policy, you must create a policy object by creating an instance of the <xref:System.Net.Cache.RequestCachePolicy> or <xref:System.Net.Cache.HttpRequestCachePolicy> class.</span></span> <span data-ttu-id="12483-123">若要针对某个请求指定策略，请将此请求的 <xref:System.Net.WebRequest.CachePolicy%2A> 属性设置为策略对象。</span><span class="sxs-lookup"><span data-stu-id="12483-123">To specify the policy on a request, set the request's <xref:System.Net.WebRequest.CachePolicy%2A> property to the policy object.</span></span> <span data-ttu-id="12483-124">在以编程方式设置应用程序级策略时，请将 <xref:System.Net.HttpWebRequest.DefaultCachePolicy%2A> 属性设置为策略对象。</span><span class="sxs-lookup"><span data-stu-id="12483-124">When setting an application-level policy programmatically, set the <xref:System.Net.HttpWebRequest.DefaultCachePolicy%2A> property to the policy object.</span></span>  
  
 <span data-ttu-id="12483-125">有关演示如何创建和使用缓存策略的代码示例，请参阅[在网络应用程序中配置缓存](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="12483-125">For code examples that demonstrate creating and using cache policies, see [Configuring Caching in Network Applications](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12483-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12483-126">See Also</span></span>  
 [<span data-ttu-id="12483-127">网络应用程序的缓存管理</span><span class="sxs-lookup"><span data-stu-id="12483-127">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [<span data-ttu-id="12483-128">基于位置的缓存策略</span><span class="sxs-lookup"><span data-stu-id="12483-128">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [<span data-ttu-id="12483-129">基于时间的缓存策略</span><span class="sxs-lookup"><span data-stu-id="12483-129">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 [<span data-ttu-id="12483-130">在网络应用程序中配置缓存</span><span class="sxs-lookup"><span data-stu-id="12483-130">Configuring Caching in Network Applications</span></span>](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)
