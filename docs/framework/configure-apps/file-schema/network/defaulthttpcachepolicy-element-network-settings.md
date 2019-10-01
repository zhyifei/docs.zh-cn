---
title: <defaultHttpCachePolicy> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
ms.openlocfilehash: f3b029e8b931e976bee85c98dd926e020c5b8743
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698267"
---
# <a name="defaulthttpcachepolicy-element-network-settings"></a><span data-ttu-id="4e947-102">\<defaultHttpCachePolicy > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="4e947-102">\<defaultHttpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="4e947-103">描述 HTTP 缓存是否处于活动状态，并描述默认缓存策略。</span><span class="sxs-lookup"><span data-stu-id="4e947-103">Describes whether HTTP caching is active and describes the default caching policy.</span></span>  
  
[<span data-ttu-id="4e947-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="4e947-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="4e947-105">&nbsp; @ no__t[ **\<system >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4e947-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="4e947-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<requestCaching >** ](requestcaching-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4e947-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)</span></span>  
<span data-ttu-id="4e947-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<defaultHttpCachePolicy >**</span><span class="sxs-lookup"><span data-stu-id="4e947-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultHttpCachePolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e947-108">语法</span><span class="sxs-lookup"><span data-stu-id="4e947-108">Syntax</span></span>  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e947-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4e947-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4e947-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4e947-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e947-111">特性</span><span class="sxs-lookup"><span data-stu-id="4e947-111">Attributes</span></span>  
  
|<span data-ttu-id="4e947-112">特性</span><span class="sxs-lookup"><span data-stu-id="4e947-112">Attribute</span></span>|<span data-ttu-id="4e947-113">描述</span><span class="sxs-lookup"><span data-stu-id="4e947-113">Description</span></span>|  
|---------------|-----------------|  
|`maximumAge`|<span data-ttu-id="4e947-114">指定将缓存的对象标记为过期之前的最大时间间隔。</span><span class="sxs-lookup"><span data-stu-id="4e947-114">Specifies the maximum time interval before a cached object is marked as expired.</span></span>|  
|`maximumStale`|<span data-ttu-id="4e947-115">指定在将缓存对象标记为过期之前计算的新鲜度时间之后的最长时间。</span><span class="sxs-lookup"><span data-stu-id="4e947-115">Specifies the maximum time past the computed freshness time before a cached object is marked as expired.</span></span>|  
|`minimumFresh`|<span data-ttu-id="4e947-116">指定将缓存的对象视为最新的最短时间。</span><span class="sxs-lookup"><span data-stu-id="4e947-116">Specifies the minimum time for a cached object to be considered fresh.</span></span>|  
|`policyLevel`|<span data-ttu-id="4e947-117">指定缓存策略是否为自动，或是否绕过缓存。</span><span class="sxs-lookup"><span data-stu-id="4e947-117">Specifies whether the caching policy is automatic, or whether the cache is bypassed.</span></span> <span data-ttu-id="4e947-118">默认值为 `BypassCache`。</span><span class="sxs-lookup"><span data-stu-id="4e947-118">The default value is `BypassCache`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4e947-119">子元素</span><span class="sxs-lookup"><span data-stu-id="4e947-119">Child Elements</span></span>  
 <span data-ttu-id="4e947-120">None</span><span class="sxs-lookup"><span data-stu-id="4e947-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4e947-121">父元素</span><span class="sxs-lookup"><span data-stu-id="4e947-121">Parent Elements</span></span>  
  
|<span data-ttu-id="4e947-122">元素</span><span class="sxs-lookup"><span data-stu-id="4e947-122">Element</span></span>|<span data-ttu-id="4e947-123">描述</span><span class="sxs-lookup"><span data-stu-id="4e947-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e947-124">requestCaching</span><span class="sxs-lookup"><span data-stu-id="4e947-124">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="4e947-125">控制网络请求的缓存机制。</span><span class="sxs-lookup"><span data-stu-id="4e947-125">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e947-126">备注</span><span class="sxs-lookup"><span data-stu-id="4e947-126">Remarks</span></span>  
 <span data-ttu-id="4e947-127">@No__t-0 属性的值为 `BypassCache` 或 `Default`。</span><span class="sxs-lookup"><span data-stu-id="4e947-127">The value for the `policyLevel` attribute is either `BypassCache` or `Default`.</span></span>  
  
 <span data-ttu-id="4e947-128">@No__t 的值为-0、@no__t 为-1，`minimumFresh` 元素是采用*d*格式的显式时间间隔。*hh*：*mm*：*ss* （天、小时、分钟和秒），或常量 `minValue` 或 `maxValue` （视情况而成）。</span><span class="sxs-lookup"><span data-stu-id="4e947-128">Values for the `maximumAge`, `maximumStale`, and `minimumFresh` elements are either an explicit time interval with a format of *d*.*hh*:*mm*:*ss* (days, hours, minutes, and seconds), or the constants `minValue` or `maxValue`, as appropriate.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4e947-129">配置文件</span><span class="sxs-lookup"><span data-stu-id="4e947-129">Configuration Files</span></span>  
 <span data-ttu-id="4e947-130">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="4e947-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e947-131">示例</span><span class="sxs-lookup"><span data-stu-id="4e947-131">Example</span></span>  
 <span data-ttu-id="4e947-132">下面的示例演示如何指定最小的最短时间为6小时，最长生存期为两天，最大陈旧时间为四小时。</span><span class="sxs-lookup"><span data-stu-id="4e947-132">The following example shows how to specify a minimum fresh time of six hours, a maximum age time of two days, and a maximum stale time of four hours.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4e947-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e947-133">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="4e947-134">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="4e947-134">Network Settings Schema</span></span>](index.md)
