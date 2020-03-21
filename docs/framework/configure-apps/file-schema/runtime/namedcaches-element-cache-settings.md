---
title: <namedCaches> 元素（缓存设置）
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: e0640ca18d386141f3c03135019eb4fe959b5bf8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153953"
---
# <a name="namedcaches-element-cache-settings"></a><span data-ttu-id="9e146-102">\<命名缓存>元素（缓存设置）</span><span class="sxs-lookup"><span data-stu-id="9e146-102">\<namedCaches> Element (Cache Settings)</span></span>
<span data-ttu-id="9e146-103">指定命名<xref:System.Runtime.Caching.MemoryCache>实例的配置设置集合。</span><span class="sxs-lookup"><span data-stu-id="9e146-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="9e146-104">该<xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A>属性引用配置文件的一个或多个`namedCaches`元素的配置设置集合。</span><span class="sxs-lookup"><span data-stu-id="9e146-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
<span data-ttu-id="9e146-105">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9e146-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9e146-106">&nbsp;&nbsp;[**\<系统.运行时.缓存>**](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9e146-106">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="9e146-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<内存缓存>**](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9e146-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="9e146-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<命名缓存>**</span><span class="sxs-lookup"><span data-stu-id="9e146-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedCaches>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e146-109">语法</span><span class="sxs-lookup"><span data-stu-id="9e146-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="9e146-110">类型</span><span class="sxs-lookup"><span data-stu-id="9e146-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e146-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9e146-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9e146-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9e146-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e146-113">属性</span><span class="sxs-lookup"><span data-stu-id="9e146-113">Attributes</span></span>  
  
|<span data-ttu-id="9e146-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="9e146-114">Attribute</span></span>|<span data-ttu-id="9e146-115">说明</span><span class="sxs-lookup"><span data-stu-id="9e146-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="9e146-116">指定 a<xref:System.Runtime.Caching.MemoryCache>实例可以增长到的最大允许大小（以兆字节为单位）的整数值。</span><span class="sxs-lookup"><span data-stu-id="9e146-116">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="9e146-117">默认值为 0，这意味着默认情况下使用<xref:System.Runtime.Caching.MemoryCache>类的自动启发式调整大小。</span><span class="sxs-lookup"><span data-stu-id="9e146-117">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="9e146-118">缓存的名称。</span><span class="sxs-lookup"><span data-stu-id="9e146-118">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="9e146-119">介于 0 和 100 之间的整数值，指定缓存可以使用的物理安装计算机内存的最大百分比。</span><span class="sxs-lookup"><span data-stu-id="9e146-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="9e146-120">默认值为 0，这意味着默认情况下使用<xref:System.Runtime.Caching.MemoryCache>类的自动启发式调整大小。</span><span class="sxs-lookup"><span data-stu-id="9e146-120">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="9e146-121">一个时间间隔的值，在该时间间隔之后，缓存实现会将当前内存负载与为缓存实例设置的基于绝对值和百分比的内存限制进行比较。</span><span class="sxs-lookup"><span data-stu-id="9e146-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="9e146-122">此值以"HH：MM：SS"格式输入。</span><span class="sxs-lookup"><span data-stu-id="9e146-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9e146-123">子元素</span><span class="sxs-lookup"><span data-stu-id="9e146-123">Child Elements</span></span>  
  
|<span data-ttu-id="9e146-124">元素</span><span class="sxs-lookup"><span data-stu-id="9e146-124">Element</span></span>|<span data-ttu-id="9e146-125">说明</span><span class="sxs-lookup"><span data-stu-id="9e146-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9e146-126">\<添加></span><span class="sxs-lookup"><span data-stu-id="9e146-126">\<add></span></span>](add-element-for-namedcaches.md)|<span data-ttu-id="9e146-127">向内存缓存的 `namedCaches` 集合添加一个命名的缓存。</span><span class="sxs-lookup"><span data-stu-id="9e146-127">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="9e146-128">\<明确></span><span class="sxs-lookup"><span data-stu-id="9e146-128">\<clear></span></span>](clear-element-for-namedcaches.md)|<span data-ttu-id="9e146-129">清除内存缓存的 `namedCaches` 集合。</span><span class="sxs-lookup"><span data-stu-id="9e146-129">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="9e146-130">\<删除></span><span class="sxs-lookup"><span data-stu-id="9e146-130">\<remove></span></span>](remove-element-for-namedcaches.md)|<span data-ttu-id="9e146-131">从内存缓存的 `namedCaches` 集合中删除一个命名的缓存条目。</span><span class="sxs-lookup"><span data-stu-id="9e146-131">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9e146-132">父元素</span><span class="sxs-lookup"><span data-stu-id="9e146-132">Parent Elements</span></span>  
  
|<span data-ttu-id="9e146-133">元素</span><span class="sxs-lookup"><span data-stu-id="9e146-133">Element</span></span>|<span data-ttu-id="9e146-134">说明</span><span class="sxs-lookup"><span data-stu-id="9e146-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9e146-135">\<配置></span><span class="sxs-lookup"><span data-stu-id="9e146-135">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="9e146-136">指定通用语言运行时和 .NET Framework 应用程序使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="9e146-136">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="9e146-137">\<内存缓存></span><span class="sxs-lookup"><span data-stu-id="9e146-137">\<memoryCache></span></span>](memorycache-element-cache-settings.md)|<span data-ttu-id="9e146-138">定义一个用于配置基于 <xref:System.Runtime.Caching.MemoryCache> 类的缓存的元素。</span><span class="sxs-lookup"><span data-stu-id="9e146-138">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
|[<span data-ttu-id="9e146-139">\<系统.运行时.缓存></span><span class="sxs-lookup"><span data-stu-id="9e146-139">\<system.runtime.caching></span></span>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="9e146-140">包含允许您在内置于 .NET 框架中的应用程序中实现输出缓存的类型。</span><span class="sxs-lookup"><span data-stu-id="9e146-140">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e146-141">备注</span><span class="sxs-lookup"><span data-stu-id="9e146-141">Remarks</span></span>  
 <span data-ttu-id="9e146-142">Web.config`add`文件的内存缓存配置部分可以包含 集合`remove`的`namedCaches``clear`和 属性。</span><span class="sxs-lookup"><span data-stu-id="9e146-142">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="9e146-143">每个`namedCaches`条目都由`name`属性唯一标识。</span><span class="sxs-lookup"><span data-stu-id="9e146-143">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="9e146-144">您可以通过引用应用程序配置文件中的信息来检索内存缓存条目的实例。</span><span class="sxs-lookup"><span data-stu-id="9e146-144">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="9e146-145">默认情况下，只有默认缓存实例在配置文件中具有条目。</span><span class="sxs-lookup"><span data-stu-id="9e146-145">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="9e146-146">默认缓存实例是从属性返回的<xref:System.Runtime.Caching.MemoryCache.Default%2A>实例。</span><span class="sxs-lookup"><span data-stu-id="9e146-146">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="9e146-147">如果将名称属性设置为"默认"，则元素将使用默认内存缓存实例。</span><span class="sxs-lookup"><span data-stu-id="9e146-147">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e146-148">示例</span><span class="sxs-lookup"><span data-stu-id="9e146-148">Example</span></span>  
 <span data-ttu-id="9e146-149">下面的示例演示如何通过将`name`属性设置为"默认"来将缓存的名称设置为默认缓存条目名称。</span><span class="sxs-lookup"><span data-stu-id="9e146-149">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="9e146-150">将 `cacheMemoryLimitMegabytes` 属性和 `physicalMemoryPercentage` 属性设置为零。</span><span class="sxs-lookup"><span data-stu-id="9e146-150">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="9e146-151">将这些属性设置为零意味着使用<xref:System.Runtime.Caching.MemoryCache>类的自动启发式调整大小。</span><span class="sxs-lookup"><span data-stu-id="9e146-151">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="9e146-152">缓存实现将当前内存负载与绝对内存限制和基于百分比的内存限制每两分钟进行比较。</span><span class="sxs-lookup"><span data-stu-id="9e146-152">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9e146-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e146-153">See also</span></span>

- [<span data-ttu-id="9e146-154">\<内存缓存>元素（缓存设置）</span><span class="sxs-lookup"><span data-stu-id="9e146-154">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
