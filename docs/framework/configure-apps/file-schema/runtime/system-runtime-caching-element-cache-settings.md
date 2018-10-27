---
title: '&lt;system.runtime.caching&gt;元素 （缓存设置）'
ms.date: 03/30/2017
helpviewer_keywords:
- <system.runtime.caching> element
- caching [.NET Framework], configuration
- system.runtime.caching element
ms.assetid: 9b44daee-874a-4bd1-954e-83bf53565590
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c9932d1328f010158535b096e4ead599c7b3f47
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/25/2018
ms.locfileid: "50043434"
---
# <a name="ltsystemruntimecachinggt-element-cache-settings"></a><span data-ttu-id="9cf7e-102">&lt;system.runtime.caching&gt;元素 （缓存设置）</span><span class="sxs-lookup"><span data-stu-id="9cf7e-102">&lt;system.runtime.caching&gt; Element (Cache Settings)</span></span>
<span data-ttu-id="9cf7e-103">通过配置文件中的 <xref:System.Runtime.Caching.ObjectCache> 条目为默认内存中的 `memoryCache` 实现提供配置。</span><span class="sxs-lookup"><span data-stu-id="9cf7e-103">Provides configuration for the default in-memory <xref:System.Runtime.Caching.ObjectCache> implementation through the `memoryCache` entry in the configuration file.</span></span>  
  
 <span data-ttu-id="9cf7e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9cf7e-104">\<configuration></span></span>  
<span data-ttu-id="9cf7e-105">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="9cf7e-105">\<system.runtime.caching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cf7e-106">语法</span><span class="sxs-lookup"><span data-stu-id="9cf7e-106">Syntax</span></span>  
  
```xml  
<system.runtime.caching >  
   <!-- child elements -->  
</system.runtime.caching >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9cf7e-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9cf7e-107">Attributes and Elements</span></span>  
 <span data-ttu-id="9cf7e-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9cf7e-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9cf7e-109">特性</span><span class="sxs-lookup"><span data-stu-id="9cf7e-109">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="9cf7e-110">子元素</span><span class="sxs-lookup"><span data-stu-id="9cf7e-110">Child Elements</span></span>  
  
|<span data-ttu-id="9cf7e-111">元素</span><span class="sxs-lookup"><span data-stu-id="9cf7e-111">Element</span></span>|<span data-ttu-id="9cf7e-112">描述</span><span class="sxs-lookup"><span data-stu-id="9cf7e-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9cf7e-113">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="9cf7e-113">\<memoryCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|<span data-ttu-id="9cf7e-114">定义一个用于配置基于 <xref:System.Runtime.Caching.MemoryCache> 类的缓存的元素。</span><span class="sxs-lookup"><span data-stu-id="9cf7e-114">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9cf7e-115">父元素</span><span class="sxs-lookup"><span data-stu-id="9cf7e-115">Parent Elements</span></span>  
  
|<span data-ttu-id="9cf7e-116">元素</span><span class="sxs-lookup"><span data-stu-id="9cf7e-116">Element</span></span>|<span data-ttu-id="9cf7e-117">描述</span><span class="sxs-lookup"><span data-stu-id="9cf7e-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9cf7e-118">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9cf7e-118">\<configuration></span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="9cf7e-119">指定公共语言运行时和 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="9cf7e-119">Specifies the root element in every configuration file that is used by the common language runtime and [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9cf7e-120">备注</span><span class="sxs-lookup"><span data-stu-id="9cf7e-120">Remarks</span></span>  
 <span data-ttu-id="9cf7e-121">此命名空间中的类提供一种使用诸如 ASP.NET 中缓存功能的方法，但不会在 `System.Web` 程序集上产生依赖。</span><span class="sxs-lookup"><span data-stu-id="9cf7e-121">The classes in this namespace provide a way to use caching facilities like those in ASP.NET, but without a dependency on the `System.Web` assembly.</span></span> <span data-ttu-id="9cf7e-122">有关详细信息，请参阅 [Caching in .NET Framework Applications](../../../../../docs/framework/performance/caching-in-net-framework-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="9cf7e-122">For more information, see [Caching in .NET Framework Applications](../../../../../docs/framework/performance/caching-in-net-framework-applications.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9cf7e-123"><xref:System.Runtime.Caching> 命名空间中的输出缓存功能和类型对于 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]而言是全新的。</span><span class="sxs-lookup"><span data-stu-id="9cf7e-123">The output caching functionality and types in the <xref:System.Runtime.Caching> namespace are new in [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="9cf7e-124">示例</span><span class="sxs-lookup"><span data-stu-id="9cf7e-124">Example</span></span>  
 <span data-ttu-id="9cf7e-125">下面的示例演示如何配置基于 <xref:System.Runtime.Caching.MemoryCache> 类的缓存。</span><span class="sxs-lookup"><span data-stu-id="9cf7e-125">The following example shows how to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="9cf7e-126">该示例演示如何为内存缓存配置 `namedCaches` 条目实例。</span><span class="sxs-lookup"><span data-stu-id="9cf7e-126">The example shows how to configure an instance of the `namedCaches` entry for memory cache.</span></span> <span data-ttu-id="9cf7e-127">通过将 `name` 属性设置为“默认”，可以将缓存名称设置为默认缓存项名称。</span><span class="sxs-lookup"><span data-stu-id="9cf7e-127">The name of the cache is set to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="9cf7e-128">将 `cacheMemoryLimitMegabytes` 属性和 `physicalMemoryPercentage` 属性设置为零。</span><span class="sxs-lookup"><span data-stu-id="9cf7e-128">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="9cf7e-129">将这些特性设置为零意味着默认情况下使用 <xref:System.Runtime.Caching.MemoryCache> 自动调整大小试探法。</span><span class="sxs-lookup"><span data-stu-id="9cf7e-129">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="9cf7e-130">每隔两分钟，缓存实现应对当前内存负载和基于百分比的绝对内存限制进行比较。</span><span class="sxs-lookup"><span data-stu-id="9cf7e-130">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
```xml  
<configuration>  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9cf7e-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="9cf7e-131">See Also</span></span>  
 [<span data-ttu-id="9cf7e-132">\<memoryCache > 元素 （缓存设置）</span><span class="sxs-lookup"><span data-stu-id="9cf7e-132">\<memoryCache> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)
