---
title: "&lt;namedCaches&gt;元素 （缓存设置）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 7c25f0039f75ba1c736cff946dbaaff9252dc93e
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2018
---
# <a name="ltnamedcachesgt-element-cache-settings"></a><span data-ttu-id="523d5-102">&lt;namedCaches&gt;元素 （缓存设置）</span><span class="sxs-lookup"><span data-stu-id="523d5-102">&lt;namedCaches&gt; Element (Cache Settings)</span></span>
<span data-ttu-id="523d5-103">指定的配置设置的命名集合<xref:System.Runtime.Caching.MemoryCache>实例。</span><span class="sxs-lookup"><span data-stu-id="523d5-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="523d5-104"><xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A>属性引用的配置设置的集合从一个或多个`namedCaches`配置文件的元素。</span><span class="sxs-lookup"><span data-stu-id="523d5-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
 <span data-ttu-id="523d5-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="523d5-105">\<configuration></span></span>  
<span data-ttu-id="523d5-106">\<system.runtime.caching ></span><span class="sxs-lookup"><span data-stu-id="523d5-106">\< system.runtime.caching></span></span>  
<span data-ttu-id="523d5-107">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="523d5-107">\<memoryCache></span></span>  
<span data-ttu-id="523d5-108">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="523d5-108">\<namedCaches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="523d5-109">语法</span><span class="sxs-lookup"><span data-stu-id="523d5-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>   
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="523d5-110">类型</span><span class="sxs-lookup"><span data-stu-id="523d5-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="523d5-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="523d5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="523d5-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="523d5-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="523d5-113">特性</span><span class="sxs-lookup"><span data-stu-id="523d5-113">Attributes</span></span>  
  
|<span data-ttu-id="523d5-114">特性</span><span class="sxs-lookup"><span data-stu-id="523d5-114">Attribute</span></span>|<span data-ttu-id="523d5-115">描述</span><span class="sxs-lookup"><span data-stu-id="523d5-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="523d5-116">一个整数值，指定的最大大小，单位为兆字节，该实例<xref:System.Runtime.Caching.MemoryCache>可以增长到。</span><span class="sxs-lookup"><span data-stu-id="523d5-116">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="523d5-117">默认值为 0，这意味着的自动调整大小试探法<xref:System.Runtime.Caching.MemoryCache>默认情况下使用类。</span><span class="sxs-lookup"><span data-stu-id="523d5-117">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="523d5-118">缓存的名称。</span><span class="sxs-lookup"><span data-stu-id="523d5-118">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="523d5-119">指定以物理方式安装的计算机可以由缓存使用的内存的最大百分比整数值介于 0 和 100 之间。</span><span class="sxs-lookup"><span data-stu-id="523d5-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="523d5-120">默认值为 0，这意味着的自动调整大小试探法<xref:System.Runtime.Caching.MemoryCache>默认情况下使用类。</span><span class="sxs-lookup"><span data-stu-id="523d5-120">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="523d5-121">一个时间间隔的值，在该时间间隔之后，缓存实现会将当前内存负载与为缓存实例设置的基于绝对值和百分比的内存限制进行比较。</span><span class="sxs-lookup"><span data-stu-id="523d5-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="523d5-122">"Hh: mm:"格式输入此值。</span><span class="sxs-lookup"><span data-stu-id="523d5-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="523d5-123">子元素</span><span class="sxs-lookup"><span data-stu-id="523d5-123">Child Elements</span></span>  
  
|<span data-ttu-id="523d5-124">元素</span><span class="sxs-lookup"><span data-stu-id="523d5-124">Element</span></span>|<span data-ttu-id="523d5-125">描述</span><span class="sxs-lookup"><span data-stu-id="523d5-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="523d5-126">\<add></span><span class="sxs-lookup"><span data-stu-id="523d5-126">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/add-element-for-namedcaches.md)|<span data-ttu-id="523d5-127">向内存缓存的 `namedCaches` 集合添加一个命名的缓存。</span><span class="sxs-lookup"><span data-stu-id="523d5-127">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="523d5-128">\<clear></span><span class="sxs-lookup"><span data-stu-id="523d5-128">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)|<span data-ttu-id="523d5-129">清除内存缓存的 `namedCaches` 集合。</span><span class="sxs-lookup"><span data-stu-id="523d5-129">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="523d5-130">\<remove></span><span class="sxs-lookup"><span data-stu-id="523d5-130">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/remove-element-for-namedcaches.md)|<span data-ttu-id="523d5-131">从内存缓存的 `namedCaches` 集合中删除一个命名的缓存条目。</span><span class="sxs-lookup"><span data-stu-id="523d5-131">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="523d5-132">父元素</span><span class="sxs-lookup"><span data-stu-id="523d5-132">Parent Elements</span></span>  
  
|<span data-ttu-id="523d5-133">元素</span><span class="sxs-lookup"><span data-stu-id="523d5-133">Element</span></span>|<span data-ttu-id="523d5-134">描述</span><span class="sxs-lookup"><span data-stu-id="523d5-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="523d5-135">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="523d5-135">\<memoryCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|<span data-ttu-id="523d5-136">定义一个用于配置基于 <xref:System.Runtime.Caching.MemoryCache> 类的缓存的元素。</span><span class="sxs-lookup"><span data-stu-id="523d5-136">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="523d5-137">备注</span><span class="sxs-lookup"><span data-stu-id="523d5-137">Remarks</span></span>  
 <span data-ttu-id="523d5-138">Web.config 文件的内存缓存配置节可以包含`add`， `remove`，和`clear`属性`namedCaches`集合。</span><span class="sxs-lookup"><span data-stu-id="523d5-138">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="523d5-139">每个`namedCaches`项都由唯一标识`name`属性。</span><span class="sxs-lookup"><span data-stu-id="523d5-139">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="523d5-140">可以通过引用应用程序配置文件中的信息来检索实例的内存缓存条目。</span><span class="sxs-lookup"><span data-stu-id="523d5-140">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="523d5-141">默认情况下，默认的缓存实例配置文件中有一个条目。</span><span class="sxs-lookup"><span data-stu-id="523d5-141">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="523d5-142">默认缓存实例是从返回的实例<xref:System.Runtime.Caching.MemoryCache.Default%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="523d5-142">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="523d5-143">如果设置为"默认值"的名称属性，元素将使用默认内存缓存实例。</span><span class="sxs-lookup"><span data-stu-id="523d5-143">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="523d5-144">示例</span><span class="sxs-lookup"><span data-stu-id="523d5-144">Example</span></span>  
 <span data-ttu-id="523d5-145">下面的示例演示如何将缓存的名称设置为默认缓存项名称，通过设置`name`属性设置为"default"。</span><span class="sxs-lookup"><span data-stu-id="523d5-145">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="523d5-146">将 `cacheMemoryLimitMegabytes` 属性和 `physicalMemoryPercentage` 属性设置为零。</span><span class="sxs-lookup"><span data-stu-id="523d5-146">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="523d5-147">将这些特性设置为零意味着的自动调整大小试探法<xref:System.Runtime.Caching.MemoryCache>类使用。</span><span class="sxs-lookup"><span data-stu-id="523d5-147">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="523d5-148">缓存实现将比较当前的内存负载与每隔两分钟的绝对和基于百分比的内存限制。</span><span class="sxs-lookup"><span data-stu-id="523d5-148">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="523d5-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="523d5-149">See Also</span></span>  
 [<span data-ttu-id="523d5-150">\<memoryCache > 元素 （缓存设置）</span><span class="sxs-lookup"><span data-stu-id="523d5-150">\<memoryCache> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)
