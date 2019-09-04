---
title: <system.runtime.caching> 元素（缓存设置）
ms.date: 03/30/2017
helpviewer_keywords:
- <system.runtime.caching> element
- caching [.NET Framework], configuration
- system.runtime.caching element
ms.assetid: 9b44daee-874a-4bd1-954e-83bf53565590
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e36e2ed96a0748a69f2bd9ee32432901f0bf0898
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252293"
---
# <a name="systemruntimecaching-element-cache-settings"></a><span data-ttu-id="3083e-102">\<system.object > 元素（缓存设置）</span><span class="sxs-lookup"><span data-stu-id="3083e-102">\<system.runtime.caching> Element (Cache Settings)</span></span>

<span data-ttu-id="3083e-103">通过配置文件中的 <xref:System.Runtime.Caching.ObjectCache> 条目为默认内存中的 `memoryCache` 实现提供配置。</span><span class="sxs-lookup"><span data-stu-id="3083e-103">Provides configuration for the default in-memory <xref:System.Runtime.Caching.ObjectCache> implementation through the `memoryCache` entry in the configuration file.</span></span>  
  
<span data-ttu-id="3083e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3083e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3083e-105">&nbsp;&nbsp; **\<> 缓存**</span><span class="sxs-lookup"><span data-stu-id="3083e-105">&nbsp;&nbsp;**\<system.runtime.caching>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3083e-106">语法</span><span class="sxs-lookup"><span data-stu-id="3083e-106">Syntax</span></span>  
  
```xml  
<system.runtime.caching >  
   <!-- child elements -->  
</system.runtime.caching >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3083e-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3083e-107">Attributes and Elements</span></span>

<span data-ttu-id="3083e-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3083e-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3083e-109">特性</span><span class="sxs-lookup"><span data-stu-id="3083e-109">Attributes</span></span>

`None`  

### <a name="child-elements"></a><span data-ttu-id="3083e-110">子元素</span><span class="sxs-lookup"><span data-stu-id="3083e-110">Child Elements</span></span>

|<span data-ttu-id="3083e-111">元素</span><span class="sxs-lookup"><span data-stu-id="3083e-111">Element</span></span>|<span data-ttu-id="3083e-112">描述</span><span class="sxs-lookup"><span data-stu-id="3083e-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3083e-113">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="3083e-113">\<memoryCache></span></span>](memorycache-element-cache-settings.md)|<span data-ttu-id="3083e-114">定义一个用于配置基于 <xref:System.Runtime.Caching.MemoryCache> 类的缓存的元素。</span><span class="sxs-lookup"><span data-stu-id="3083e-114">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3083e-115">父元素</span><span class="sxs-lookup"><span data-stu-id="3083e-115">Parent Elements</span></span>  
  
|<span data-ttu-id="3083e-116">元素</span><span class="sxs-lookup"><span data-stu-id="3083e-116">Element</span></span>|<span data-ttu-id="3083e-117">描述</span><span class="sxs-lookup"><span data-stu-id="3083e-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3083e-118">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3083e-118">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="3083e-119">指定公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="3083e-119">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3083e-120">备注</span><span class="sxs-lookup"><span data-stu-id="3083e-120">Remarks</span></span>

<span data-ttu-id="3083e-121">此命名空间中的类提供一种使用诸如 ASP.NET 中缓存功能的方法，但不会在 `System.Web` 程序集上产生依赖。</span><span class="sxs-lookup"><span data-stu-id="3083e-121">The classes in this namespace provide a way to use caching facilities like those in ASP.NET, but without a dependency on the `System.Web` assembly.</span></span> <span data-ttu-id="3083e-122">有关详细信息，请参阅 [Caching in .NET Framework Applications](../../../performance/caching-in-net-framework-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="3083e-122">For more information, see [Caching in .NET Framework Applications](../../../performance/caching-in-net-framework-applications.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3083e-123"><xref:System.Runtime.Caching>命名空间中的输出缓存功能和类型是 .NET Framework 4 中的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3083e-123">The output caching functionality and types in the <xref:System.Runtime.Caching> namespace are new in .NET Framework 4.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3083e-124">示例</span><span class="sxs-lookup"><span data-stu-id="3083e-124">Example</span></span>

<span data-ttu-id="3083e-125">下面的示例演示如何配置基于 <xref:System.Runtime.Caching.MemoryCache> 类的缓存。</span><span class="sxs-lookup"><span data-stu-id="3083e-125">The following example shows how to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="3083e-126">该示例演示如何为内存缓存配置 `namedCaches` 条目实例。</span><span class="sxs-lookup"><span data-stu-id="3083e-126">The example shows how to configure an instance of the `namedCaches` entry for memory cache.</span></span> <span data-ttu-id="3083e-127">缓存的名称设置为默认缓存项名称，方法是将`name`属性设置为 "default"。</span><span class="sxs-lookup"><span data-stu-id="3083e-127">The name of the cache is set to the default cache entry name by setting the `name` attribute to "Default".</span></span>  
  
<span data-ttu-id="3083e-128">将 `cacheMemoryLimitMegabytes` 属性和 `physicalMemoryPercentage` 属性设置为零。</span><span class="sxs-lookup"><span data-stu-id="3083e-128">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="3083e-129">将这些特性设置为零意味着默认情况下使用 <xref:System.Runtime.Caching.MemoryCache> 自动调整大小试探法。</span><span class="sxs-lookup"><span data-stu-id="3083e-129">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="3083e-130">每隔两分钟，缓存实现应对当前内存负载和基于百分比的绝对内存限制进行比较。</span><span class="sxs-lookup"><span data-stu-id="3083e-130">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
```xml  
<configuration>  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3083e-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="3083e-131">See also</span></span>

- [<span data-ttu-id="3083e-132">\<memoryCache > 元素（缓存设置）</span><span class="sxs-lookup"><span data-stu-id="3083e-132">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
