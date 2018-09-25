---
title: '&lt;namedCaches&gt;元素 （缓存设置）'
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
author: mcleblanc
ms.author: markl
ms.openlocfilehash: a74dfaf883ea23514c6bc4641d9d576f5baf10b4
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47071666"
---
# <a name="ltnamedcachesgt-element-cache-settings"></a><span data-ttu-id="edac6-102">&lt;namedCaches&gt;元素 （缓存设置）</span><span class="sxs-lookup"><span data-stu-id="edac6-102">&lt;namedCaches&gt; Element (Cache Settings)</span></span>
<span data-ttu-id="edac6-103">指定的配置设置的命名集合<xref:System.Runtime.Caching.MemoryCache>实例。</span><span class="sxs-lookup"><span data-stu-id="edac6-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="edac6-104"><xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A>属性引用的配置设置集合中一个或多个`namedCaches`配置文件中的元素。</span><span class="sxs-lookup"><span data-stu-id="edac6-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
 <span data-ttu-id="edac6-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="edac6-105">\<configuration></span></span>  
<span data-ttu-id="edac6-106">\< system.runtime.caching ></span><span class="sxs-lookup"><span data-stu-id="edac6-106">\< system.runtime.caching></span></span>  
<span data-ttu-id="edac6-107">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="edac6-107">\<memoryCache></span></span>  
<span data-ttu-id="edac6-108">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="edac6-108">\<namedCaches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edac6-109">语法</span><span class="sxs-lookup"><span data-stu-id="edac6-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>   
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="edac6-110">类型</span><span class="sxs-lookup"><span data-stu-id="edac6-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="edac6-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="edac6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="edac6-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="edac6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="edac6-113">特性</span><span class="sxs-lookup"><span data-stu-id="edac6-113">Attributes</span></span>  
  
|<span data-ttu-id="edac6-114">特性</span><span class="sxs-lookup"><span data-stu-id="edac6-114">Attribute</span></span>|<span data-ttu-id="edac6-115">描述</span><span class="sxs-lookup"><span data-stu-id="edac6-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="edac6-116">指定的最大大小，以兆字节为单位，一个整数值的实例<xref:System.Runtime.Caching.MemoryCache>可以增长到。</span><span class="sxs-lookup"><span data-stu-id="edac6-116">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="edac6-117">默认值为 0，这意味着的自动调整大小试探法<xref:System.Runtime.Caching.MemoryCache>类默认情况下使用。</span><span class="sxs-lookup"><span data-stu-id="edac6-117">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="edac6-118">缓存的名称。</span><span class="sxs-lookup"><span data-stu-id="edac6-118">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="edac6-119">一个整数值介于 0 和 100 之间，指定可以使用由缓存以物理方式安装的计算机内存的最大百分比。</span><span class="sxs-lookup"><span data-stu-id="edac6-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="edac6-120">默认值为 0，这意味着的自动调整大小试探法<xref:System.Runtime.Caching.MemoryCache>类默认情况下使用。</span><span class="sxs-lookup"><span data-stu-id="edac6-120">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="edac6-121">一个时间间隔的值，在该时间间隔之后，缓存实现会将当前内存负载与为缓存实例设置的基于绝对值和百分比的内存限制进行比较。</span><span class="sxs-lookup"><span data-stu-id="edac6-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="edac6-122">"Hh: mm:"格式输入此值。</span><span class="sxs-lookup"><span data-stu-id="edac6-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="edac6-123">子元素</span><span class="sxs-lookup"><span data-stu-id="edac6-123">Child Elements</span></span>  
  
|<span data-ttu-id="edac6-124">元素</span><span class="sxs-lookup"><span data-stu-id="edac6-124">Element</span></span>|<span data-ttu-id="edac6-125">描述</span><span class="sxs-lookup"><span data-stu-id="edac6-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="edac6-126">\<add></span><span class="sxs-lookup"><span data-stu-id="edac6-126">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/add-element-for-namedcaches.md)|<span data-ttu-id="edac6-127">向内存缓存的 `namedCaches` 集合添加一个命名的缓存。</span><span class="sxs-lookup"><span data-stu-id="edac6-127">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="edac6-128">\<clear></span><span class="sxs-lookup"><span data-stu-id="edac6-128">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)|<span data-ttu-id="edac6-129">清除内存缓存的 `namedCaches` 集合。</span><span class="sxs-lookup"><span data-stu-id="edac6-129">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="edac6-130">\<remove></span><span class="sxs-lookup"><span data-stu-id="edac6-130">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/remove-element-for-namedcaches.md)|<span data-ttu-id="edac6-131">从内存缓存的 `namedCaches` 集合中删除一个命名的缓存条目。</span><span class="sxs-lookup"><span data-stu-id="edac6-131">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="edac6-132">父元素</span><span class="sxs-lookup"><span data-stu-id="edac6-132">Parent Elements</span></span>  
  
|<span data-ttu-id="edac6-133">元素</span><span class="sxs-lookup"><span data-stu-id="edac6-133">Element</span></span>|<span data-ttu-id="edac6-134">描述</span><span class="sxs-lookup"><span data-stu-id="edac6-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="edac6-135">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="edac6-135">\<memoryCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|<span data-ttu-id="edac6-136">定义一个用于配置基于 <xref:System.Runtime.Caching.MemoryCache> 类的缓存的元素。</span><span class="sxs-lookup"><span data-stu-id="edac6-136">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="edac6-137">备注</span><span class="sxs-lookup"><span data-stu-id="edac6-137">Remarks</span></span>  
 <span data-ttu-id="edac6-138">可以包含 Web.config 文件的内存缓存配置部分`add`， `remove`，并`clear`属性`namedCaches`集合。</span><span class="sxs-lookup"><span data-stu-id="edac6-138">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="edac6-139">每个`namedCaches`由唯一标识条目`name`属性。</span><span class="sxs-lookup"><span data-stu-id="edac6-139">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="edac6-140">可以通过引用应用程序配置文件中的信息来检索实例的内存缓存项。</span><span class="sxs-lookup"><span data-stu-id="edac6-140">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="edac6-141">默认情况下，默认的缓存实例配置文件中具有条目。</span><span class="sxs-lookup"><span data-stu-id="edac6-141">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="edac6-142">默认缓存实例是从返回的实例<xref:System.Runtime.Caching.MemoryCache.Default%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="edac6-142">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="edac6-143">如果设置为"default"的 name 属性，该元素使用的默认内存缓存实例。</span><span class="sxs-lookup"><span data-stu-id="edac6-143">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="edac6-144">示例</span><span class="sxs-lookup"><span data-stu-id="edac6-144">Example</span></span>  
 <span data-ttu-id="edac6-145">下面的示例演示如何通过设置缓存的名称设置为默认缓存项名称`name`属性设置为"default"。</span><span class="sxs-lookup"><span data-stu-id="edac6-145">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="edac6-146">将 `cacheMemoryLimitMegabytes` 属性和 `physicalMemoryPercentage` 属性设置为零。</span><span class="sxs-lookup"><span data-stu-id="edac6-146">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="edac6-147">将这些属性设置为零意味着的自动调整大小试探法<xref:System.Runtime.Caching.MemoryCache>类使用。</span><span class="sxs-lookup"><span data-stu-id="edac6-147">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="edac6-148">缓存实现将当前内存负载与每隔两分钟的绝对内存和基于百分比的内存限制进行比较。</span><span class="sxs-lookup"><span data-stu-id="edac6-148">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="edac6-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="edac6-149">See Also</span></span>  
 [<span data-ttu-id="edac6-150">\<memoryCache > 元素 （缓存设置）</span><span class="sxs-lookup"><span data-stu-id="edac6-150">\<memoryCache> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)
