---
title: <namedCaches> 的 <add> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: c1345022b79df371ad9c89a39a0a8b625e26608c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154500"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="fae95-102">\<为\<命名缓存添加>元素></span><span class="sxs-lookup"><span data-stu-id="fae95-102">\<add> Element for \<namedCaches></span></span>
<span data-ttu-id="fae95-103">向`namedCache`内存缓存`namedCaches`的集合添加条目。</span><span class="sxs-lookup"><span data-stu-id="fae95-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
<span data-ttu-id="fae95-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fae95-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fae95-105">&nbsp;&nbsp;[**\<系统.运行时.缓存>**](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="fae95-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="fae95-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<内存缓存>**](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="fae95-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="fae95-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<命名缓存>**](namedcaches-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="fae95-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span></span>\
<span data-ttu-id="fae95-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<添加>**</span><span class="sxs-lookup"><span data-stu-id="fae95-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fae95-109">语法</span><span class="sxs-lookup"><span data-stu-id="fae95-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="fae95-110">类型</span><span class="sxs-lookup"><span data-stu-id="fae95-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fae95-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fae95-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fae95-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="fae95-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fae95-113">属性</span><span class="sxs-lookup"><span data-stu-id="fae95-113">Attributes</span></span>  
  
|<span data-ttu-id="fae95-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="fae95-114">Attribute</span></span>|<span data-ttu-id="fae95-115">说明</span><span class="sxs-lookup"><span data-stu-id="fae95-115">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="fae95-116">指定 a<xref:System.Runtime.Caching.MemoryCache>实例可以增长到的最大允许大小（以兆字节为单位）的整数值。</span><span class="sxs-lookup"><span data-stu-id="fae95-116">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="fae95-117">默认值为 0，这意味着默认情况下使用<xref:System.Runtime.Caching.MemoryCache>类的自动调整启发式。</span><span class="sxs-lookup"><span data-stu-id="fae95-117">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="fae95-118">缓存的名称。</span><span class="sxs-lookup"><span data-stu-id="fae95-118">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="fae95-119">介于 0 和 100 之间的整数值，指定缓存可以使用的物理安装计算机内存的最大百分比。</span><span class="sxs-lookup"><span data-stu-id="fae95-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="fae95-120">默认值为 0，这意味着默认情况下使用<xref:System.Runtime.Caching.MemoryCache>类的自动调整启发式。</span><span class="sxs-lookup"><span data-stu-id="fae95-120">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="fae95-121">一个时间间隔的值，在该时间间隔之后，缓存实现会将当前内存负载与为缓存实例设置的基于绝对值和百分比的内存限制进行比较。</span><span class="sxs-lookup"><span data-stu-id="fae95-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="fae95-122">此值以"HH：MM：SS"格式输入。</span><span class="sxs-lookup"><span data-stu-id="fae95-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fae95-123">子元素</span><span class="sxs-lookup"><span data-stu-id="fae95-123">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="fae95-124">父元素</span><span class="sxs-lookup"><span data-stu-id="fae95-124">Parent Elements</span></span>  
  
|<span data-ttu-id="fae95-125">元素</span><span class="sxs-lookup"><span data-stu-id="fae95-125">Element</span></span>|<span data-ttu-id="fae95-126">说明</span><span class="sxs-lookup"><span data-stu-id="fae95-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fae95-127">\<命名缓存></span><span class="sxs-lookup"><span data-stu-id="fae95-127">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="fae95-128">包含命名<xref:System.Runtime.Caching.MemoryCache>实例的配置设置集合。</span><span class="sxs-lookup"><span data-stu-id="fae95-128">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fae95-129">备注</span><span class="sxs-lookup"><span data-stu-id="fae95-129">Remarks</span></span>  
 <span data-ttu-id="fae95-130">该`add`元素向内存缓存`namedCaches`的集合添加一个条目。</span><span class="sxs-lookup"><span data-stu-id="fae95-130">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="fae95-131">在使用 元素[clear](clear-element-for-namedcaches.md)之前，`add`可以使用 clear 元素来确保集合中没有其他命名缓存。</span><span class="sxs-lookup"><span data-stu-id="fae95-131">You can use the [clear](clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="fae95-132">此元素可用于计算机.config 文件和 Web.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="fae95-132">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fae95-133">示例</span><span class="sxs-lookup"><span data-stu-id="fae95-133">Example</span></span>  
 <span data-ttu-id="fae95-134">下面的示例演示如何为内存缓存集合的`namedCache``namedCaches`默认条目定义设置。</span><span class="sxs-lookup"><span data-stu-id="fae95-134">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fae95-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fae95-135">See also</span></span>

- [<span data-ttu-id="fae95-136">\<命名缓存>元素（缓存设置）</span><span class="sxs-lookup"><span data-stu-id="fae95-136">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
