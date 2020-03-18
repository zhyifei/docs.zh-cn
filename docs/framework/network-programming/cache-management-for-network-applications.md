---
title: 网络应用程序的缓存管理
ms.date: 03/30/2017
helpviewer_keywords:
- cache [.NET Framework], network applications
- network resources, caching
- Internet, caching
ms.assetid: fc258a40-f370-434f-ae09-4a8cb11ddaeb
ms.openlocfilehash: 7e131963999db3e3d5e0e6f3fa110da36e6452a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048875"
---
# <a name="cache-management-for-network-applications"></a><span data-ttu-id="da796-102">网络应用程序的缓存管理</span><span class="sxs-lookup"><span data-stu-id="da796-102">Cache Management for Network Applications</span></span>
<span data-ttu-id="da796-103">本主题及其相关的副主题描述针对使用 <xref:System.Net.WebClient>、<xref:System.Net.WebRequest>、<xref:System.Net.HttpWebRequest> 和 <xref:System.Net.FtpWebRequest> 类获取的资源的缓存。</span><span class="sxs-lookup"><span data-stu-id="da796-103">This topic and its related subtopics describe caching for resources obtained using the <xref:System.Net.WebClient>, <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest>, and <xref:System.Net.FtpWebRequest> classes.</span></span>  
  
 <span data-ttu-id="da796-104">缓存为已由应用程序请求的资源提供临时存储。</span><span class="sxs-lookup"><span data-stu-id="da796-104">A cache provides temporary storage of resources that have been requested by an application.</span></span> <span data-ttu-id="da796-105">如果应用程序多次请求同一资源，则可以从此缓存中返回此资源，避免了重复向服务器发出请求的开销。</span><span class="sxs-lookup"><span data-stu-id="da796-105">If an application requests the same resource more than once, the resource can be returned from the cache, avoiding the overhead of re-requesting it from the server.</span></span> <span data-ttu-id="da796-106">缓存可以通过减少获取请求的资源所需的时间，以提高应用程序性能。</span><span class="sxs-lookup"><span data-stu-id="da796-106">Caching can improve application performance by reducing the time required to get a requested resource.</span></span> <span data-ttu-id="da796-107">缓存还可以通过减少对服务器的访问次数，以减少网络流量。</span><span class="sxs-lookup"><span data-stu-id="da796-107">Caching can also decrease network traffic by reducing the number of trips to the server.</span></span> <span data-ttu-id="da796-108">虽然缓存提高了性能，但会增加返回到应用程序的资源已过时的风险，这意味着如果未使用缓存，返回到应用程序的资源则与由服务器发送的资源不同。</span><span class="sxs-lookup"><span data-stu-id="da796-108">While caching improves performance, it increases the risk that the resource returned to the application is stale, meaning that it is not identical to the resource that would have been sent by the server if caching were not in use.</span></span>  
  
 <span data-ttu-id="da796-109">缓存可以允许未经授权的用户或进程读取敏感数据。</span><span class="sxs-lookup"><span data-stu-id="da796-109">Caching may allow unauthorized users or processes to read sensitive data.</span></span> <span data-ttu-id="da796-110">在无需进行额外授权的情况下，可以从缓存中检索缓存的已经过身份验证的响应。</span><span class="sxs-lookup"><span data-stu-id="da796-110">An authenticated response that is cached may be retrieved from the cache without an additional authorization.</span></span> <span data-ttu-id="da796-111">如果已启用缓存，请将 <xref:System.Net.WebRequest.CachePolicy%2A> 更改为 <xref:System.Net.Cache.RequestCacheLevel.BypassCache> 或 <xref:System.Net.Cache.RequestCacheLevel.NoCacheNoStore> 以针对此请求禁用缓存。</span><span class="sxs-lookup"><span data-stu-id="da796-111">If caching is enabled, change to <xref:System.Net.WebRequest.CachePolicy%2A> to <xref:System.Net.Cache.RequestCacheLevel.BypassCache> or <xref:System.Net.Cache.RequestCacheLevel.NoCacheNoStore> to disable caching for this request.</span></span>  
  
 <span data-ttu-id="da796-112">出于安全考虑，不建议将缓存用于中间层方案  。</span><span class="sxs-lookup"><span data-stu-id="da796-112">Due to security concerns, caching is **not** recommended for middle tier scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="da796-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="da796-113">In This Section</span></span>  
 [<span data-ttu-id="da796-114">缓存策略</span><span class="sxs-lookup"><span data-stu-id="da796-114">Cache Policy</span></span>](cache-policy.md)  
 <span data-ttu-id="da796-115">说明什么是缓存策略以及如何定义一个缓存策略。</span><span class="sxs-lookup"><span data-stu-id="da796-115">Explains what a cache policy is and how to define one.</span></span>  
  
 [<span data-ttu-id="da796-116">基于位置的缓存策略</span><span class="sxs-lookup"><span data-stu-id="da796-116">Location-Based Cache Policies</span></span>](location-based-cache-policies.md)  
 <span data-ttu-id="da796-117">定义基于位置的缓存策略的每个类型，此策略可用于超文本传输协议（http 和 https）资源。</span><span class="sxs-lookup"><span data-stu-id="da796-117">Defines each type of location-based cache policy available for Hypertext Transfer Protocol (http and https) resources.</span></span>  
  
 [<span data-ttu-id="da796-118">基于时间的缓存策略</span><span class="sxs-lookup"><span data-stu-id="da796-118">Time-Based Cache Policies</span></span>](time-based-cache-policies.md)  
 <span data-ttu-id="da796-119">描述可用于自定义基于时间的缓存策略的条件。</span><span class="sxs-lookup"><span data-stu-id="da796-119">Describes the criteria that can be used to customize a time-based cache policy.</span></span>  
  
 [<span data-ttu-id="da796-120">在网络应用程序中配置缓存</span><span class="sxs-lookup"><span data-stu-id="da796-120">Configuring Caching in Network Applications</span></span>](configuring-caching-in-network-applications.md)  
 <span data-ttu-id="da796-121">描述如何以编程方式创建缓存策略以及使用缓存的请求。</span><span class="sxs-lookup"><span data-stu-id="da796-121">Describes how to programmatically create cache policies and requests that use caching.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="da796-122">引用</span><span class="sxs-lookup"><span data-stu-id="da796-122">Reference</span></span>  
 <xref:System.Net.Cache>  
 <span data-ttu-id="da796-123">定义类型和枚举，这些类型和枚举用于为使用 <xref:System.Net.WebRequest><xref:System.Net.HttpWebRequest> 和 <xref:System.Net.FtpWebRequest> 类获取的资源定义缓存策略。</span><span class="sxs-lookup"><span data-stu-id="da796-123">Defines the types and enumerations used to define cache policies for resources obtained using the <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest>, and <xref:System.Net.FtpWebRequest> classes.</span></span>
