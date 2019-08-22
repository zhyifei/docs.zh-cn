---
title: <requestCaching> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching
helpviewer_keywords:
- requestCaching element
- <requestCaching> element
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
ms.openlocfilehash: 2a3d0b182acad2351ed095934ca97c6194d344fc
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659137"
---
# <a name="requestcaching-element-network-settings"></a><span data-ttu-id="b79e8-102">\<requestCaching> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="b79e8-102">\<requestCaching> Element (Network Settings)</span></span>
<span data-ttu-id="b79e8-103">控制网络请求的缓存机制。</span><span class="sxs-lookup"><span data-stu-id="b79e8-103">Controls the caching mechanism for network requests.</span></span>  
  
 <span data-ttu-id="b79e8-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b79e8-104">\<configuration></span></span>  
<span data-ttu-id="b79e8-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="b79e8-105">\<system.net></span></span>  
<span data-ttu-id="b79e8-106">\<requestCaching></span><span class="sxs-lookup"><span data-stu-id="b79e8-106">\<requestCaching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b79e8-107">语法</span><span class="sxs-lookup"><span data-stu-id="b79e8-107">Syntax</span></span>  
  
```xml  
<requestCaching  
  isPrivateCache ="true|false"  
  disableAllCaching="true|false"  
  defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
  unspecifiedMaximumAge= "d.hh.mm.ss">  
    <defaultHttpCachePolicy>...</defaultHttpCachePolicy>  
    <defaultFtpCachePolicy>...</defaultFtpCachePolicy>  
</requestCaching>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b79e8-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b79e8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b79e8-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b79e8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b79e8-110">特性</span><span class="sxs-lookup"><span data-stu-id="b79e8-110">Attributes</span></span>  
  
|<span data-ttu-id="b79e8-111">特性</span><span class="sxs-lookup"><span data-stu-id="b79e8-111">Attribute</span></span>|<span data-ttu-id="b79e8-112">描述</span><span class="sxs-lookup"><span data-stu-id="b79e8-112">Description</span></span>|  
|---------------|-----------------|  
|`isPrivateCache`|<span data-ttu-id="b79e8-113">指定缓存是否在不同用户的信息之间提供隔离。</span><span class="sxs-lookup"><span data-stu-id="b79e8-113">Specifies whether the cache provides isolation between the information of different users.</span></span> <span data-ttu-id="b79e8-114">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="b79e8-114">The default value is `true`.</span></span> <span data-ttu-id="b79e8-115">此值应该`false`适用于中间层应用程序。</span><span class="sxs-lookup"><span data-stu-id="b79e8-115">This value should be `false` for middle tier applications.</span></span>|  
|`disableAllCaching`|<span data-ttu-id="b79e8-116">指定为所有 Web 响应禁用缓存, 且不能以编程方式重写。</span><span class="sxs-lookup"><span data-stu-id="b79e8-116">Specifies that caching is disabled for all Web responses, and cannot be overridden programmatically.</span></span>|  
|`defaultPolicyLevel`|<span data-ttu-id="b79e8-117"><xref:System.Net.Cache.RequestCacheLevel> 枚举中的值之一。</span><span class="sxs-lookup"><span data-stu-id="b79e8-117">One of the values in the <xref:System.Net.Cache.RequestCacheLevel> enumeration.</span></span> <span data-ttu-id="b79e8-118">默认值为 `BypassCache`。</span><span class="sxs-lookup"><span data-stu-id="b79e8-118">The default value is `BypassCache`.</span></span>|  
|`unspecifiedMaximumAge`|<span data-ttu-id="b79e8-119">指定将内容标记为过期的默认时间。</span><span class="sxs-lookup"><span data-stu-id="b79e8-119">Specifies the default time after which content is marked as expired.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="b79e8-120">policyLevel 特性</span><span class="sxs-lookup"><span data-stu-id="b79e8-120">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="b79e8-121">值</span><span class="sxs-lookup"><span data-stu-id="b79e8-121">Value</span></span>|<span data-ttu-id="b79e8-122">描述</span><span class="sxs-lookup"><span data-stu-id="b79e8-122">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="b79e8-123">如果资源是最新的, 则返回缓存的资源, 内容长度准确, 并且存在过期、修改和内容长度属性。</span><span class="sxs-lookup"><span data-stu-id="b79e8-123">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="b79e8-124">从服务器返回资源。</span><span class="sxs-lookup"><span data-stu-id="b79e8-124">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="b79e8-125">如果内容长度存在并且与条目大小匹配, 则返回缓存的资源。</span><span class="sxs-lookup"><span data-stu-id="b79e8-125">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="b79e8-126">如果提供了内容长度并与条目大小匹配, 则返回缓存的资源;否则, 将从服务器下载资源, 并将其返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="b79e8-126">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="b79e8-127">如果缓存资源的时间戳与服务器上资源的时间戳相同, 则返回缓存的资源;否则, 将从服务器下载资源, 并将其存储在缓存中, 并将其返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="b79e8-127">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and is returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="b79e8-128">从服务器下载资源, 将其存储在缓存中, 并将资源返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="b79e8-128">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="b79e8-129">如果缓存的资源存在, 则将其删除。</span><span class="sxs-lookup"><span data-stu-id="b79e8-129">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="b79e8-130">从服务器下载资源, 并将其返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="b79e8-130">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="b79e8-131">如果时间戳与服务器上资源的时间戳相同, 则使用资源的缓存副本满足请求;否则, 会从服务器下载资源, 并将其提供给调用方, 并存储在缓存中。</span><span class="sxs-lookup"><span data-stu-id="b79e8-131">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and is stored in the cache,</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b79e8-132">子元素</span><span class="sxs-lookup"><span data-stu-id="b79e8-132">Child Elements</span></span>  
  
|<span data-ttu-id="b79e8-133">元素</span><span class="sxs-lookup"><span data-stu-id="b79e8-133">Element</span></span>|<span data-ttu-id="b79e8-134">描述</span><span class="sxs-lookup"><span data-stu-id="b79e8-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b79e8-135">defaultHttpCachePolicy</span><span class="sxs-lookup"><span data-stu-id="b79e8-135">defaultHttpCachePolicy</span></span>](defaulthttpcachepolicy-element-network-settings.md)|<span data-ttu-id="b79e8-136">可选元素。</span><span class="sxs-lookup"><span data-stu-id="b79e8-136">Optional element.</span></span><br /><br /> <span data-ttu-id="b79e8-137">描述 HTTP 缓存是否处于活动状态, 并描述默认缓存策略。</span><span class="sxs-lookup"><span data-stu-id="b79e8-137">Describes whether HTTP caching is active and describes the default caching policy.</span></span>|  
|[<span data-ttu-id="b79e8-138">\<defaultFtpCachePolicy > 元素 (网络设置)</span><span class="sxs-lookup"><span data-stu-id="b79e8-138">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>](defaultftpcachepolicy-element-network-settings.md)|<span data-ttu-id="b79e8-139">可选元素。</span><span class="sxs-lookup"><span data-stu-id="b79e8-139">Optional element.</span></span><br /><br /> <span data-ttu-id="b79e8-140">介绍 FTP 缓存是否处于活动状态, 并描述默认缓存策略。</span><span class="sxs-lookup"><span data-stu-id="b79e8-140">Describes whether FTP caching is active and describes the default caching policy.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b79e8-141">父元素</span><span class="sxs-lookup"><span data-stu-id="b79e8-141">Parent Elements</span></span>  
  
|<span data-ttu-id="b79e8-142">元素</span><span class="sxs-lookup"><span data-stu-id="b79e8-142">Element</span></span>|<span data-ttu-id="b79e8-143">描述</span><span class="sxs-lookup"><span data-stu-id="b79e8-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b79e8-144">system.net</span><span class="sxs-lookup"><span data-stu-id="b79e8-144">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="b79e8-145">包含指定 .NET Framework 如何连接到网络的设置。</span><span class="sxs-lookup"><span data-stu-id="b79e8-145">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b79e8-146">示例</span><span class="sxs-lookup"><span data-stu-id="b79e8-146">Example</span></span>  
 <span data-ttu-id="b79e8-147">下面的示例演示如何禁用所有缓存。</span><span class="sxs-lookup"><span data-stu-id="b79e8-147">The following example shows how to disable all caching.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b79e8-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="b79e8-148">See also</span></span>

- <xref:System.Net.Cache?displayProperty=nameWithType>
- [<span data-ttu-id="b79e8-149">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="b79e8-149">Network Settings Schema</span></span>](index.md)
