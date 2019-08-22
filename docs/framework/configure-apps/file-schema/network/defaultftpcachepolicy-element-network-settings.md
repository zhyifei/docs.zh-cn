---
title: <defaultFtpCachePolicy> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy
helpviewer_keywords:
- <defaultFtpCachePolicy> element
- defaultFtpCachePolicy element
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
ms.openlocfilehash: 7ff44f0251936d51b4e396c37c53322efa110227
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659422"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a><span data-ttu-id="978cb-102">\<defaultFtpCachePolicy > 元素 (网络设置)</span><span class="sxs-lookup"><span data-stu-id="978cb-102">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="978cb-103">介绍 FTP 缓存是否处于活动状态, 并描述默认缓存策略。</span><span class="sxs-lookup"><span data-stu-id="978cb-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="978cb-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="978cb-104">\<configuration></span></span>  
<span data-ttu-id="978cb-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="978cb-105">\<system.net></span></span>  
<span data-ttu-id="978cb-106">\<requestCaching></span><span class="sxs-lookup"><span data-stu-id="978cb-106">\<requestCaching></span></span>  
<span data-ttu-id="978cb-107">\<defaultFtpCachePolicy></span><span class="sxs-lookup"><span data-stu-id="978cb-107">\<defaultFtpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="978cb-108">语法</span><span class="sxs-lookup"><span data-stu-id="978cb-108">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="978cb-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="978cb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="978cb-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="978cb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="978cb-111">特性</span><span class="sxs-lookup"><span data-stu-id="978cb-111">Attributes</span></span>  
  
|<span data-ttu-id="978cb-112">特性</span><span class="sxs-lookup"><span data-stu-id="978cb-112">Attribute</span></span>|<span data-ttu-id="978cb-113">描述</span><span class="sxs-lookup"><span data-stu-id="978cb-113">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="978cb-114">指定 FTP 缓存策略。</span><span class="sxs-lookup"><span data-stu-id="978cb-114">Specifies the FTP caching policy.</span></span> <span data-ttu-id="978cb-115">默认值为 `Default`。</span><span class="sxs-lookup"><span data-stu-id="978cb-115">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="978cb-116">policyLevel 特性</span><span class="sxs-lookup"><span data-stu-id="978cb-116">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="978cb-117">值</span><span class="sxs-lookup"><span data-stu-id="978cb-117">Value</span></span>|<span data-ttu-id="978cb-118">描述</span><span class="sxs-lookup"><span data-stu-id="978cb-118">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="978cb-119">如果资源是最新的, 则返回缓存的资源, 内容长度准确, 并且存在过期、修改和内容长度属性。</span><span class="sxs-lookup"><span data-stu-id="978cb-119">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="978cb-120">从服务器返回资源。</span><span class="sxs-lookup"><span data-stu-id="978cb-120">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="978cb-121">如果内容长度存在并且与条目大小匹配, 则返回缓存的资源。</span><span class="sxs-lookup"><span data-stu-id="978cb-121">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="978cb-122">如果提供了内容长度并与条目大小匹配, 则返回缓存的资源;否则, 将从服务器下载资源, 并将其返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="978cb-122">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="978cb-123">如果缓存资源的时间戳与服务器上资源的时间戳相同, 则返回缓存的资源;否则, 将从服务器下载资源, 并将其存储在缓存中, 并将其返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="978cb-123">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="978cb-124">从服务器下载资源, 将其存储在缓存中, 并将资源返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="978cb-124">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="978cb-125">如果缓存的资源存在, 则将其删除。</span><span class="sxs-lookup"><span data-stu-id="978cb-125">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="978cb-126">从服务器下载资源, 并将其返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="978cb-126">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="978cb-127">如果时间戳与服务器上的资源的时间戳相同，则使用资源的缓存副本满足请求；否则从服务器下载资源，将资源展示给调用方，然后再存储在缓存中。</span><span class="sxs-lookup"><span data-stu-id="978cb-127">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="978cb-128">子元素</span><span class="sxs-lookup"><span data-stu-id="978cb-128">Child Elements</span></span>  
 <span data-ttu-id="978cb-129">无。</span><span class="sxs-lookup"><span data-stu-id="978cb-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="978cb-130">父元素</span><span class="sxs-lookup"><span data-stu-id="978cb-130">Parent Elements</span></span>  
  
|<span data-ttu-id="978cb-131">元素</span><span class="sxs-lookup"><span data-stu-id="978cb-131">Element</span></span>|<span data-ttu-id="978cb-132">描述</span><span class="sxs-lookup"><span data-stu-id="978cb-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="978cb-133">requestCaching</span><span class="sxs-lookup"><span data-stu-id="978cb-133">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="978cb-134">控制网络请求的缓存机制。</span><span class="sxs-lookup"><span data-stu-id="978cb-134">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="978cb-135">备注</span><span class="sxs-lookup"><span data-stu-id="978cb-135">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="978cb-136">示例</span><span class="sxs-lookup"><span data-stu-id="978cb-136">Example</span></span>  
 <span data-ttu-id="978cb-137">下面的示例演示如何指定的`NoCacheNoStore`FTP 缓存策略。</span><span class="sxs-lookup"><span data-stu-id="978cb-137">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="978cb-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="978cb-138">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="978cb-139">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="978cb-139">Network Settings Schema</span></span>](index.md)
