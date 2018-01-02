---
title: "&lt;添加&gt;元素&lt;namedCaches&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 0000e92c89920b05e0ffc93fab58fb0bd6ea6b13
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-element-for-ltnamedcachesgt"></a><span data-ttu-id="69f83-102">&lt;添加&gt;元素&lt;namedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="69f83-102">&lt;add&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="69f83-103">将添加`namedCache`进入`namedCaches`内存缓存的集合。</span><span class="sxs-lookup"><span data-stu-id="69f83-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="69f83-104">\<system.runtime.caching ></span><span class="sxs-lookup"><span data-stu-id="69f83-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="69f83-105">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="69f83-105">\<memoryCache></span></span>  
<span data-ttu-id="69f83-106">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="69f83-106">\<namedCaches></span></span>  
<span data-ttu-id="69f83-107">\<add></span><span class="sxs-lookup"><span data-stu-id="69f83-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69f83-108">语法</span><span class="sxs-lookup"><span data-stu-id="69f83-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="69f83-109">类型</span><span class="sxs-lookup"><span data-stu-id="69f83-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69f83-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="69f83-110">Attributes and Elements</span></span>  
 <span data-ttu-id="69f83-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="69f83-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69f83-112">特性</span><span class="sxs-lookup"><span data-stu-id="69f83-112">Attributes</span></span>  
  
|<span data-ttu-id="69f83-113">特性</span><span class="sxs-lookup"><span data-stu-id="69f83-113">Attribute</span></span>|<span data-ttu-id="69f83-114">描述</span><span class="sxs-lookup"><span data-stu-id="69f83-114">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="69f83-115">一个整数值，指定的最大允许大小 （以兆字节为单位） 的实例<xref:System.Runtime.Caching.MemoryCache>可以增长到。</span><span class="sxs-lookup"><span data-stu-id="69f83-115">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="69f83-116">默认值为 0，这意味着<xref:System.Runtime.Caching.MemoryCache>默认情况下使用类的自动调整大小试探法。</span><span class="sxs-lookup"><span data-stu-id="69f83-116">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="69f83-117">缓存的名称。</span><span class="sxs-lookup"><span data-stu-id="69f83-117">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="69f83-118">指定以物理方式安装的计算机可以由缓存使用的内存的最大百分比整数值介于 0 和 100 之间。</span><span class="sxs-lookup"><span data-stu-id="69f83-118">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="69f83-119">默认值为 0，这意味着<xref:System.Runtime.Caching.MemoryCache>默认情况下使用类的自动调整大小试探法。</span><span class="sxs-lookup"><span data-stu-id="69f83-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="69f83-120">一个时间间隔的值，在该时间间隔之后，缓存实现会将当前内存负载与为缓存实例设置的基于绝对值和百分比的内存限制进行比较。</span><span class="sxs-lookup"><span data-stu-id="69f83-120">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="69f83-121">"Hh: mm:"格式输入此值。</span><span class="sxs-lookup"><span data-stu-id="69f83-121">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="69f83-122">子元素</span><span class="sxs-lookup"><span data-stu-id="69f83-122">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="69f83-123">父元素</span><span class="sxs-lookup"><span data-stu-id="69f83-123">Parent Elements</span></span>  
  
|<span data-ttu-id="69f83-124">元素</span><span class="sxs-lookup"><span data-stu-id="69f83-124">Element</span></span>|<span data-ttu-id="69f83-125">描述</span><span class="sxs-lookup"><span data-stu-id="69f83-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69f83-126">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="69f83-126">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="69f83-127">包含的配置设置的命名集合<xref:System.Runtime.Caching.MemoryCache>实例。</span><span class="sxs-lookup"><span data-stu-id="69f83-127">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69f83-128">备注</span><span class="sxs-lookup"><span data-stu-id="69f83-128">Remarks</span></span>  
 <span data-ttu-id="69f83-129">`add`元素添加到一个条目`namedCaches`内存缓存的集合。</span><span class="sxs-lookup"><span data-stu-id="69f83-129">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="69f83-130">你可以使用[清除](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)元素在使用之前`add`元素能够确定不是否存在任何其他命名缓存在集合中的。</span><span class="sxs-lookup"><span data-stu-id="69f83-130">You can use the [clear](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="69f83-131">在 machine.config 文件中并在 Web.config 文件中，可以使用此元素。</span><span class="sxs-lookup"><span data-stu-id="69f83-131">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69f83-132">示例</span><span class="sxs-lookup"><span data-stu-id="69f83-132">Example</span></span>  
 <span data-ttu-id="69f83-133">下面的示例演示如何定义默认设置`namedCache`进入`namedCaches`内存缓存的集合。</span><span class="sxs-lookup"><span data-stu-id="69f83-133">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="69f83-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="69f83-134">See Also</span></span>  
 [<span data-ttu-id="69f83-135">\<namedCaches > 元素 （缓存设置）</span><span class="sxs-lookup"><span data-stu-id="69f83-135">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
