---
title: "&lt;defaultFtpCachePolicy&gt;元素 （网络设置）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy
helpviewer_keywords:
- <defaultFtpCachePolicy> element
- defaultFtpCachePolicy element
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 0c62be73db6d9d0b6ce67dd87021c589502d5fec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltdefaultftpcachepolicygt-element-network-settings"></a><span data-ttu-id="fb3ca-102">&lt;defaultFtpCachePolicy&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="fb3ca-102">&lt;defaultFtpCachePolicy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="fb3ca-103">描述 FTP 缓存功能是否处于活动状态并描述默认缓存策略。</span><span class="sxs-lookup"><span data-stu-id="fb3ca-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="fb3ca-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="fb3ca-104">\<configuration></span></span>  
<span data-ttu-id="fb3ca-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="fb3ca-105">\<system.net></span></span>  
<span data-ttu-id="fb3ca-106">\<requestCaching ></span><span class="sxs-lookup"><span data-stu-id="fb3ca-106">\<requestCaching></span></span>  
<span data-ttu-id="fb3ca-107">\<defaultFtpCachePolicy ></span><span class="sxs-lookup"><span data-stu-id="fb3ca-107">\<defaultFtpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb3ca-108">语法</span><span class="sxs-lookup"><span data-stu-id="fb3ca-108">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb3ca-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fb3ca-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fb3ca-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="fb3ca-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb3ca-111">特性</span><span class="sxs-lookup"><span data-stu-id="fb3ca-111">Attributes</span></span>  
  
|<span data-ttu-id="fb3ca-112">特性</span><span class="sxs-lookup"><span data-stu-id="fb3ca-112">Attribute</span></span>|<span data-ttu-id="fb3ca-113">描述</span><span class="sxs-lookup"><span data-stu-id="fb3ca-113">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="fb3ca-114">指定 FTP 缓存策略。</span><span class="sxs-lookup"><span data-stu-id="fb3ca-114">Specifies the FTP caching policy.</span></span> <span data-ttu-id="fb3ca-115">默认值为 `Default`。</span><span class="sxs-lookup"><span data-stu-id="fb3ca-115">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="fb3ca-116">policyLevel 属性</span><span class="sxs-lookup"><span data-stu-id="fb3ca-116">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="fb3ca-117">值</span><span class="sxs-lookup"><span data-stu-id="fb3ca-117">Value</span></span>|<span data-ttu-id="fb3ca-118">描述</span><span class="sxs-lookup"><span data-stu-id="fb3ca-118">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="fb3ca-119">如果资源是最新，内容的长度是准确的并且存在过期、 修改和内容长度属性将，返回缓存的资源。</span><span class="sxs-lookup"><span data-stu-id="fb3ca-119">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="fb3ca-120">从服务器返回的资源。</span><span class="sxs-lookup"><span data-stu-id="fb3ca-120">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="fb3ca-121">如果内容长度存在并且匹配的项大小，则返回缓存的资源。</span><span class="sxs-lookup"><span data-stu-id="fb3ca-121">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="fb3ca-122">如果提供了内容的长度，并且匹配的项大小;，返回缓存的资源否则为该资源从服务器下载，并返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="fb3ca-122">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="fb3ca-123">如果缓存的资源的时间戳是与服务器; 上的资源的时间戳相同，则返回缓存的资源否则为资源是从服务器下载、 存储在缓存中，并返回至调用方。</span><span class="sxs-lookup"><span data-stu-id="fb3ca-123">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="fb3ca-124">从服务器下载的资源、 将其存储在缓存中，和将资源返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="fb3ca-124">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="fb3ca-125">如果缓存的资源存在，则删除它。</span><span class="sxs-lookup"><span data-stu-id="fb3ca-125">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="fb3ca-126">资源从服务器下载，并返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="fb3ca-126">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="fb3ca-127">如果时间戳与服务器上的资源的时间戳相同，则使用资源的缓存副本满足请求；否则从服务器下载资源，将资源展示给调用方，然后再存储在缓存中。</span><span class="sxs-lookup"><span data-stu-id="fb3ca-127">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fb3ca-128">子元素</span><span class="sxs-lookup"><span data-stu-id="fb3ca-128">Child Elements</span></span>  
 <span data-ttu-id="fb3ca-129">无。</span><span class="sxs-lookup"><span data-stu-id="fb3ca-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fb3ca-130">父元素</span><span class="sxs-lookup"><span data-stu-id="fb3ca-130">Parent Elements</span></span>  
  
|<span data-ttu-id="fb3ca-131">元素</span><span class="sxs-lookup"><span data-stu-id="fb3ca-131">Element</span></span>|<span data-ttu-id="fb3ca-132">描述</span><span class="sxs-lookup"><span data-stu-id="fb3ca-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fb3ca-133">requestCaching</span><span class="sxs-lookup"><span data-stu-id="fb3ca-133">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="fb3ca-134">控制网络请求的缓存机制。</span><span class="sxs-lookup"><span data-stu-id="fb3ca-134">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb3ca-135">备注</span><span class="sxs-lookup"><span data-stu-id="fb3ca-135">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb3ca-136">示例</span><span class="sxs-lookup"><span data-stu-id="fb3ca-136">Example</span></span>  
 <span data-ttu-id="fb3ca-137">下面的示例演示如何指定缓存策略的 FTP `NoCacheNoStore`。</span><span class="sxs-lookup"><span data-stu-id="fb3ca-137">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultFtpCachePolicy  
        policyLevel="NoCacheNoStore">  
      </defaultFtpCachePolicy>  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fb3ca-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb3ca-138">See Also</span></span>  
 <xref:System.Net.Cache>  
 <xref:System.Net.WebRequest>  
 <xref:System.Net.Cache.RequestCacheLevel>  
 [<span data-ttu-id="fb3ca-139">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="fb3ca-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
