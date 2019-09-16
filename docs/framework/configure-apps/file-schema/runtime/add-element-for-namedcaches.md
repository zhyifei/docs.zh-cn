---
title: <namedCaches> 的 <add> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: 076d940e0c15cf48013480fef68b8fac42cf76e9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252893"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="f67ab-102">\<添加 namedCaches 的\<> 元素 ></span><span class="sxs-lookup"><span data-stu-id="f67ab-102">\<add> Element for \<namedCaches></span></span>
<span data-ttu-id="f67ab-103">向内存缓存的`namedCaches`集合中添加项。`namedCache`</span><span class="sxs-lookup"><span data-stu-id="f67ab-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
<span data-ttu-id="f67ab-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f67ab-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f67ab-105">&nbsp;&nbsp;[ **\<> 缓存**](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f67ab-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="f67ab-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<memoryCache >** ](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f67ab-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="f67ab-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<namedCaches >** ](namedcaches-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f67ab-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span></span>\
<span data-ttu-id="f67ab-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="f67ab-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f67ab-109">语法</span><span class="sxs-lookup"><span data-stu-id="f67ab-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="f67ab-110">类型</span><span class="sxs-lookup"><span data-stu-id="f67ab-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f67ab-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f67ab-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f67ab-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f67ab-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f67ab-113">特性</span><span class="sxs-lookup"><span data-stu-id="f67ab-113">Attributes</span></span>  
  
|<span data-ttu-id="f67ab-114">特性</span><span class="sxs-lookup"><span data-stu-id="f67ab-114">Attribute</span></span>|<span data-ttu-id="f67ab-115">描述</span><span class="sxs-lookup"><span data-stu-id="f67ab-115">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="f67ab-116">一个整数值，指定的<xref:System.Runtime.Caching.MemoryCache>实例可以增长到的最大允许大小（以 mb 为单位）。</span><span class="sxs-lookup"><span data-stu-id="f67ab-116">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="f67ab-117">默认值为0，这意味着<xref:System.Runtime.Caching.MemoryCache>默认情况下使用类的自动调整试探法。</span><span class="sxs-lookup"><span data-stu-id="f67ab-117">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="f67ab-118">缓存的名称。</span><span class="sxs-lookup"><span data-stu-id="f67ab-118">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="f67ab-119">一个介于0到100之间的整数值，用于指定缓存可使用的实际安装计算机内存的最大百分比。</span><span class="sxs-lookup"><span data-stu-id="f67ab-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="f67ab-120">默认值为0，这意味着<xref:System.Runtime.Caching.MemoryCache>默认情况下使用类的自动调整试探法。</span><span class="sxs-lookup"><span data-stu-id="f67ab-120">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="f67ab-121">一个时间间隔的值，在该时间间隔之后，缓存实现会将当前内存负载与为缓存实例设置的基于绝对值和百分比的内存限制进行比较。</span><span class="sxs-lookup"><span data-stu-id="f67ab-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="f67ab-122">此值以 "HH： MM： SS" 格式输入。</span><span class="sxs-lookup"><span data-stu-id="f67ab-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f67ab-123">子元素</span><span class="sxs-lookup"><span data-stu-id="f67ab-123">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="f67ab-124">父元素</span><span class="sxs-lookup"><span data-stu-id="f67ab-124">Parent Elements</span></span>  
  
|<span data-ttu-id="f67ab-125">元素</span><span class="sxs-lookup"><span data-stu-id="f67ab-125">Element</span></span>|<span data-ttu-id="f67ab-126">描述</span><span class="sxs-lookup"><span data-stu-id="f67ab-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f67ab-127">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="f67ab-127">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="f67ab-128">包含命名<xref:System.Runtime.Caching.MemoryCache>实例的配置设置的集合。</span><span class="sxs-lookup"><span data-stu-id="f67ab-128">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f67ab-129">备注</span><span class="sxs-lookup"><span data-stu-id="f67ab-129">Remarks</span></span>  
 <span data-ttu-id="f67ab-130">元素向内存缓存的`namedCaches`集合中添加项。 `add`</span><span class="sxs-lookup"><span data-stu-id="f67ab-130">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="f67ab-131">您可以在使用 `add` 元素之前使用 [clear](clear-element-for-namedcaches.md) 元素，以确保集合中没有其他命名缓存。</span><span class="sxs-lookup"><span data-stu-id="f67ab-131">You can use the [clear](clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="f67ab-132">此元素可在 machine.config 文件和 web.config 文件中使用。</span><span class="sxs-lookup"><span data-stu-id="f67ab-132">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f67ab-133">示例</span><span class="sxs-lookup"><span data-stu-id="f67ab-133">Example</span></span>  
 <span data-ttu-id="f67ab-134">下面的示例演示如何为内存缓存的`namedCache` `namedCaches`集合定义默认项的设置。</span><span class="sxs-lookup"><span data-stu-id="f67ab-134">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f67ab-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="f67ab-135">See also</span></span>

- [<span data-ttu-id="f67ab-136">\<namedCaches > 元素（缓存设置）</span><span class="sxs-lookup"><span data-stu-id="f67ab-136">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
