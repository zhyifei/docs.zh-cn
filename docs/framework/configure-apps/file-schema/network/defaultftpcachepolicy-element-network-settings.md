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
ms.openlocfilehash: fd1649edbf7a2c8546992019df667f27df68e02c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698318"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a><span data-ttu-id="84ca4-102">\<defaultFtpCachePolicy > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="84ca4-102">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="84ca4-103">介绍 FTP 缓存是否处于活动状态，并描述默认缓存策略。</span><span class="sxs-lookup"><span data-stu-id="84ca4-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  
  
[<span data-ttu-id="84ca4-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="84ca4-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="84ca4-105">&nbsp; @ no__t[ **\<system >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="84ca4-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="84ca4-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<requestCaching >** ](requestcaching-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="84ca4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)</span></span>  
<span data-ttu-id="84ca4-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<defaultFtpCachePolicy >**</span><span class="sxs-lookup"><span data-stu-id="84ca4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultFtpCachePolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84ca4-108">语法</span><span class="sxs-lookup"><span data-stu-id="84ca4-108">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="84ca4-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="84ca4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="84ca4-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="84ca4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="84ca4-111">特性</span><span class="sxs-lookup"><span data-stu-id="84ca4-111">Attributes</span></span>  
  
|<span data-ttu-id="84ca4-112">特性</span><span class="sxs-lookup"><span data-stu-id="84ca4-112">Attribute</span></span>|<span data-ttu-id="84ca4-113">描述</span><span class="sxs-lookup"><span data-stu-id="84ca4-113">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="84ca4-114">指定 FTP 缓存策略。</span><span class="sxs-lookup"><span data-stu-id="84ca4-114">Specifies the FTP caching policy.</span></span> <span data-ttu-id="84ca4-115">默认值为 `Default`。</span><span class="sxs-lookup"><span data-stu-id="84ca4-115">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="84ca4-116">policyLevel 特性</span><span class="sxs-lookup"><span data-stu-id="84ca4-116">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="84ca4-117">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="84ca4-117">Value</span></span>|<span data-ttu-id="84ca4-118">描述</span><span class="sxs-lookup"><span data-stu-id="84ca4-118">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="84ca4-119">如果资源是最新的，则返回缓存的资源，内容长度准确，并且存在过期、修改和内容长度属性。</span><span class="sxs-lookup"><span data-stu-id="84ca4-119">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="84ca4-120">从服务器返回资源。</span><span class="sxs-lookup"><span data-stu-id="84ca4-120">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="84ca4-121">如果内容长度存在并且与条目大小匹配，则返回缓存的资源。</span><span class="sxs-lookup"><span data-stu-id="84ca4-121">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="84ca4-122">如果提供了内容长度并与条目大小匹配，则返回缓存的资源;否则，将从服务器下载资源，并将其返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="84ca4-122">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="84ca4-123">如果缓存资源的时间戳与服务器上资源的时间戳相同，则返回缓存的资源;否则，将从服务器下载资源，并将其存储在缓存中，并将其返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="84ca4-123">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="84ca4-124">从服务器下载资源，将其存储在缓存中，并将资源返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="84ca4-124">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="84ca4-125">如果缓存的资源存在，则将其删除。</span><span class="sxs-lookup"><span data-stu-id="84ca4-125">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="84ca4-126">从服务器下载资源，并将其返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="84ca4-126">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="84ca4-127">如果时间戳与服务器上的资源的时间戳相同，则使用资源的缓存副本满足请求；否则从服务器下载资源，将资源展示给调用方，然后再存储在缓存中。</span><span class="sxs-lookup"><span data-stu-id="84ca4-127">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="84ca4-128">子元素</span><span class="sxs-lookup"><span data-stu-id="84ca4-128">Child Elements</span></span>  
 <span data-ttu-id="84ca4-129">无。</span><span class="sxs-lookup"><span data-stu-id="84ca4-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="84ca4-130">父元素</span><span class="sxs-lookup"><span data-stu-id="84ca4-130">Parent Elements</span></span>  
  
|<span data-ttu-id="84ca4-131">元素</span><span class="sxs-lookup"><span data-stu-id="84ca4-131">Element</span></span>|<span data-ttu-id="84ca4-132">描述</span><span class="sxs-lookup"><span data-stu-id="84ca4-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="84ca4-133">requestCaching</span><span class="sxs-lookup"><span data-stu-id="84ca4-133">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="84ca4-134">控制网络请求的缓存机制。</span><span class="sxs-lookup"><span data-stu-id="84ca4-134">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84ca4-135">备注</span><span class="sxs-lookup"><span data-stu-id="84ca4-135">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="84ca4-136">示例</span><span class="sxs-lookup"><span data-stu-id="84ca4-136">Example</span></span>  
 <span data-ttu-id="84ca4-137">下面的示例演示如何将 FTP 缓存策略指定 `NoCacheNoStore`。</span><span class="sxs-lookup"><span data-stu-id="84ca4-137">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="84ca4-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="84ca4-138">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="84ca4-139">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="84ca4-139">Network Settings Schema</span></span>](index.md)
