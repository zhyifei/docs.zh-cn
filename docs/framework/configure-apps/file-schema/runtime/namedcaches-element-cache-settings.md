---
title: <namedCaches> 元素（缓存设置）
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: 4587234ad91fa3b1abbb376bd7ae517d5abea6c3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252453"
---
# <a name="namedcaches-element-cache-settings"></a><span data-ttu-id="106e2-102">\<namedCaches > 元素（缓存设置）</span><span class="sxs-lookup"><span data-stu-id="106e2-102">\<namedCaches> Element (Cache Settings)</span></span>
<span data-ttu-id="106e2-103">指定命名<xref:System.Runtime.Caching.MemoryCache>实例的配置设置的集合。</span><span class="sxs-lookup"><span data-stu-id="106e2-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="106e2-104">属性从配置文件的一个或多个`namedCaches`元素中引用配置设置的集合。 <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A></span><span class="sxs-lookup"><span data-stu-id="106e2-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
<span data-ttu-id="106e2-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="106e2-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="106e2-106">&nbsp;&nbsp;[ **\<> 缓存**](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="106e2-106">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="106e2-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<memoryCache >** ](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="106e2-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="106e2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<namedCaches >**</span><span class="sxs-lookup"><span data-stu-id="106e2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedCaches>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="106e2-109">语法</span><span class="sxs-lookup"><span data-stu-id="106e2-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>   
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="106e2-110">类型</span><span class="sxs-lookup"><span data-stu-id="106e2-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="106e2-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="106e2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="106e2-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="106e2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="106e2-113">特性</span><span class="sxs-lookup"><span data-stu-id="106e2-113">Attributes</span></span>  
  
|<span data-ttu-id="106e2-114">特性</span><span class="sxs-lookup"><span data-stu-id="106e2-114">Attribute</span></span>|<span data-ttu-id="106e2-115">描述</span><span class="sxs-lookup"><span data-stu-id="106e2-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="106e2-116">一个整数值，指定的<xref:System.Runtime.Caching.MemoryCache>实例可以增长到的最大允许大小（以 mb 为单位）。</span><span class="sxs-lookup"><span data-stu-id="106e2-116">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="106e2-117">默认值为0，这意味着默认情况下使用<xref:System.Runtime.Caching.MemoryCache>类的自动调整试探法。</span><span class="sxs-lookup"><span data-stu-id="106e2-117">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="106e2-118">缓存的名称。</span><span class="sxs-lookup"><span data-stu-id="106e2-118">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="106e2-119">一个介于0到100之间的整数值，用于指定缓存可使用的实际安装计算机内存的最大百分比。</span><span class="sxs-lookup"><span data-stu-id="106e2-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="106e2-120">默认值为0，这意味着默认情况下使用<xref:System.Runtime.Caching.MemoryCache>类的自动调整试探法。</span><span class="sxs-lookup"><span data-stu-id="106e2-120">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="106e2-121">一个时间间隔的值，在该时间间隔之后，缓存实现会将当前内存负载与为缓存实例设置的基于绝对值和百分比的内存限制进行比较。</span><span class="sxs-lookup"><span data-stu-id="106e2-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="106e2-122">此值以 "HH： MM： SS" 格式输入。</span><span class="sxs-lookup"><span data-stu-id="106e2-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="106e2-123">子元素</span><span class="sxs-lookup"><span data-stu-id="106e2-123">Child Elements</span></span>  
  
|<span data-ttu-id="106e2-124">元素</span><span class="sxs-lookup"><span data-stu-id="106e2-124">Element</span></span>|<span data-ttu-id="106e2-125">描述</span><span class="sxs-lookup"><span data-stu-id="106e2-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="106e2-126">\<add></span><span class="sxs-lookup"><span data-stu-id="106e2-126">\<add></span></span>](add-element-for-namedcaches.md)|<span data-ttu-id="106e2-127">向内存缓存的 `namedCaches` 集合添加一个命名的缓存。</span><span class="sxs-lookup"><span data-stu-id="106e2-127">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="106e2-128">\<clear></span><span class="sxs-lookup"><span data-stu-id="106e2-128">\<clear></span></span>](clear-element-for-namedcaches.md)|<span data-ttu-id="106e2-129">清除内存缓存的 `namedCaches` 集合。</span><span class="sxs-lookup"><span data-stu-id="106e2-129">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="106e2-130">\<remove></span><span class="sxs-lookup"><span data-stu-id="106e2-130">\<remove></span></span>](remove-element-for-namedcaches.md)|<span data-ttu-id="106e2-131">从内存缓存的 `namedCaches` 集合中删除一个命名的缓存条目。</span><span class="sxs-lookup"><span data-stu-id="106e2-131">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="106e2-132">父元素</span><span class="sxs-lookup"><span data-stu-id="106e2-132">Parent Elements</span></span>  
  
|<span data-ttu-id="106e2-133">元素</span><span class="sxs-lookup"><span data-stu-id="106e2-133">Element</span></span>|<span data-ttu-id="106e2-134">描述</span><span class="sxs-lookup"><span data-stu-id="106e2-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="106e2-135">\<configuration></span><span class="sxs-lookup"><span data-stu-id="106e2-135">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="106e2-136">指定公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="106e2-136">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="106e2-137">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="106e2-137">\<memoryCache></span></span>](memorycache-element-cache-settings.md)|<span data-ttu-id="106e2-138">定义一个用于配置基于 <xref:System.Runtime.Caching.MemoryCache> 类的缓存的元素。</span><span class="sxs-lookup"><span data-stu-id="106e2-138">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
|[<span data-ttu-id="106e2-139">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="106e2-139">\<system.runtime.caching></span></span>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="106e2-140">包含使你可以在 .NET Framework 中内置的应用程序中实现输出缓存的类型。</span><span class="sxs-lookup"><span data-stu-id="106e2-140">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="106e2-141">备注</span><span class="sxs-lookup"><span data-stu-id="106e2-141">Remarks</span></span>  
 <span data-ttu-id="106e2-142">Web.config 文件的内存缓存配置节`add`可以包含`namedCaches`集合的、 `remove`和`clear`特性。</span><span class="sxs-lookup"><span data-stu-id="106e2-142">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="106e2-143">每`namedCaches`个项都`name`由特性唯一标识。</span><span class="sxs-lookup"><span data-stu-id="106e2-143">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="106e2-144">可以通过引用应用程序配置文件中的信息来检索内存缓存项的实例。</span><span class="sxs-lookup"><span data-stu-id="106e2-144">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="106e2-145">默认情况下，只有默认的缓存实例在配置文件中有一个条目。</span><span class="sxs-lookup"><span data-stu-id="106e2-145">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="106e2-146">默认缓存实例是从<xref:System.Runtime.Caching.MemoryCache.Default%2A>属性返回的实例。</span><span class="sxs-lookup"><span data-stu-id="106e2-146">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="106e2-147">如果将 name 属性设置为 "default"，则元素将使用默认内存缓存实例。</span><span class="sxs-lookup"><span data-stu-id="106e2-147">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="106e2-148">示例</span><span class="sxs-lookup"><span data-stu-id="106e2-148">Example</span></span>  
 <span data-ttu-id="106e2-149">下面的示例演示如何通过将`name`属性设置为 "default"，将缓存的名称设置为默认缓存项名称。</span><span class="sxs-lookup"><span data-stu-id="106e2-149">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="106e2-150">将 `cacheMemoryLimitMegabytes` 属性和 `physicalMemoryPercentage` 属性设置为零。</span><span class="sxs-lookup"><span data-stu-id="106e2-150">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="106e2-151">将这些特性设置为零意味着使用<xref:System.Runtime.Caching.MemoryCache>类的自动调整试探法。</span><span class="sxs-lookup"><span data-stu-id="106e2-151">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="106e2-152">缓存实现将当前内存负载与基于百分比的绝对内存和每两分钟的内存限制进行比较。</span><span class="sxs-lookup"><span data-stu-id="106e2-152">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="106e2-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="106e2-153">See also</span></span>

- [<span data-ttu-id="106e2-154">\<memoryCache > 元素（缓存设置）</span><span class="sxs-lookup"><span data-stu-id="106e2-154">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
