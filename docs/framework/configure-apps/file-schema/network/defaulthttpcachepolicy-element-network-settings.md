---
title: '&lt;defaultHttpCachePolicy&gt;元素 （网络设置）'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 1e1b27cb8c0df4450c1a08151af19913b65fc2b3
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47172886"
---
# <a name="ltdefaulthttpcachepolicygt-element-network-settings"></a><span data-ttu-id="de8ab-102">&lt;defaultHttpCachePolicy&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="de8ab-102">&lt;defaultHttpCachePolicy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="de8ab-103">描述 HTTP 缓存功能是否处于活动状态并介绍了默认的缓存策略。</span><span class="sxs-lookup"><span data-stu-id="de8ab-103">Describes whether HTTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="de8ab-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="de8ab-104">\<configuration></span></span>  
<span data-ttu-id="de8ab-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="de8ab-105">\<system.net></span></span>  
<span data-ttu-id="de8ab-106">\<requestCaching ></span><span class="sxs-lookup"><span data-stu-id="de8ab-106">\<requestCaching></span></span>  
<span data-ttu-id="de8ab-107">\<defaultHttpCachePolicy ></span><span class="sxs-lookup"><span data-stu-id="de8ab-107">\<defaultHttpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de8ab-108">语法</span><span class="sxs-lookup"><span data-stu-id="de8ab-108">Syntax</span></span>  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de8ab-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="de8ab-109">Attributes and Elements</span></span>  
 <span data-ttu-id="de8ab-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="de8ab-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de8ab-111">特性</span><span class="sxs-lookup"><span data-stu-id="de8ab-111">Attributes</span></span>  
  
|<span data-ttu-id="de8ab-112">特性</span><span class="sxs-lookup"><span data-stu-id="de8ab-112">Attribute</span></span>|<span data-ttu-id="de8ab-113">描述</span><span class="sxs-lookup"><span data-stu-id="de8ab-113">Description</span></span>|  
|---------------|-----------------|  
|`maximumAge`|<span data-ttu-id="de8ab-114">指定的最大时间间隔之前将缓存的对象标记为已过期。</span><span class="sxs-lookup"><span data-stu-id="de8ab-114">Specifies the maximum time interval before a cached object is marked as expired.</span></span>|  
|`maximumStale`|<span data-ttu-id="de8ab-115">指定过去的缓存的对象标记为过期前的计算出的新鲜时间的最大时间。</span><span class="sxs-lookup"><span data-stu-id="de8ab-115">Specifies the maximum time past the computed freshness time before a cached object is marked as expired.</span></span>|  
|`minimumFresh`|<span data-ttu-id="de8ab-116">指定缓存的对象视为新鲜的最小时间。</span><span class="sxs-lookup"><span data-stu-id="de8ab-116">Specifies the minimum time for a cached object to be considered fresh.</span></span>|  
|`policyLevel`|<span data-ttu-id="de8ab-117">指定是否缓存策略是自动的或是否绕过缓存。</span><span class="sxs-lookup"><span data-stu-id="de8ab-117">Specifies whether the caching policy is automatic, or whether the cache is bypassed.</span></span> <span data-ttu-id="de8ab-118">默认值为 `BypassCache`。</span><span class="sxs-lookup"><span data-stu-id="de8ab-118">The default value is `BypassCache`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="de8ab-119">子元素</span><span class="sxs-lookup"><span data-stu-id="de8ab-119">Child Elements</span></span>  
 <span data-ttu-id="de8ab-120">无</span><span class="sxs-lookup"><span data-stu-id="de8ab-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="de8ab-121">父元素</span><span class="sxs-lookup"><span data-stu-id="de8ab-121">Parent Elements</span></span>  
  
|<span data-ttu-id="de8ab-122">元素</span><span class="sxs-lookup"><span data-stu-id="de8ab-122">Element</span></span>|<span data-ttu-id="de8ab-123">描述</span><span class="sxs-lookup"><span data-stu-id="de8ab-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de8ab-124">requestCaching</span><span class="sxs-lookup"><span data-stu-id="de8ab-124">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="de8ab-125">控制网络请求的缓存机制。</span><span class="sxs-lookup"><span data-stu-id="de8ab-125">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de8ab-126">备注</span><span class="sxs-lookup"><span data-stu-id="de8ab-126">Remarks</span></span>  
 <span data-ttu-id="de8ab-127">值`policyLevel`属性是`BypassCache`或`Default`。</span><span class="sxs-lookup"><span data-stu-id="de8ab-127">The value for the `policyLevel` attribute is either `BypassCache` or `Default`.</span></span>  
  
 <span data-ttu-id="de8ab-128">值为`maximumAge`， `maximumStale`，并`minimumFresh`元素是格式为的显式时间间隔*d*。*hh*:*mm*:*ss* （天、 小时、 分钟和秒为单位），或者为常数`minValue`或`maxValue`根据。</span><span class="sxs-lookup"><span data-stu-id="de8ab-128">Values for the `maximumAge`, `maximumStale`, and `minimumFresh` elements are either an explicit time interval with a format of *d*.*hh*:*mm*:*ss* (days, hours, minutes, and seconds), or the constants `minValue` or `maxValue`, as appropriate.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="de8ab-129">配置文件</span><span class="sxs-lookup"><span data-stu-id="de8ab-129">Configuration Files</span></span>  
 <span data-ttu-id="de8ab-130">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="de8ab-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="de8ab-131">示例</span><span class="sxs-lookup"><span data-stu-id="de8ab-131">Example</span></span>  
 <span data-ttu-id="de8ab-132">下面的示例演示如何指定六个小时，为两天，最长使用期限时间和四个小时的最长过期时间将最小新鲜时间。</span><span class="sxs-lookup"><span data-stu-id="de8ab-132">The following example shows how to specify a minimum fresh time of six hours, a maximum age time of two days, and a maximum stale time of four hours.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultHttpCachePolicy  
        minimumFresh="0.06:00:00"  
        maximumAge="2.00:00:00"  
        maximumStale="0.04:00:00"
      />  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="de8ab-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="de8ab-133">See Also</span></span>  
 <xref:System.Net.Cache>  
 <xref:System.Net.WebRequest>  
 <xref:System.Net.Cache.RequestCacheLevel>  
 [<span data-ttu-id="de8ab-134">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="de8ab-134">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
