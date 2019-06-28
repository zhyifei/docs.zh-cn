---
title: <namedCaches> 的 <add> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: b0487ba5025557f07d9991f911cd71a677a04e2c
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423376"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="5793f-102">\<添加 > 元素\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="5793f-102">\<add> Element for \<namedCaches></span></span>
<span data-ttu-id="5793f-103">将添加`namedCache`进入`namedCaches`内存缓存的集合。</span><span class="sxs-lookup"><span data-stu-id="5793f-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="5793f-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="5793f-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="5793f-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="5793f-105">\<memoryCache></span></span>  
<span data-ttu-id="5793f-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="5793f-106">\<namedCaches></span></span>  
<span data-ttu-id="5793f-107">\<add></span><span class="sxs-lookup"><span data-stu-id="5793f-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5793f-108">语法</span><span class="sxs-lookup"><span data-stu-id="5793f-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="5793f-109">类型</span><span class="sxs-lookup"><span data-stu-id="5793f-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5793f-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5793f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5793f-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5793f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5793f-112">特性</span><span class="sxs-lookup"><span data-stu-id="5793f-112">Attributes</span></span>  
  
|<span data-ttu-id="5793f-113">特性</span><span class="sxs-lookup"><span data-stu-id="5793f-113">Attribute</span></span>|<span data-ttu-id="5793f-114">描述</span><span class="sxs-lookup"><span data-stu-id="5793f-114">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="5793f-115">一个整数值，指定的最大允许大小 （以兆字节为单位） 的实例<xref:System.Runtime.Caching.MemoryCache>可以增长到。</span><span class="sxs-lookup"><span data-stu-id="5793f-115">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="5793f-116">默认值为 0，这意味着<xref:System.Runtime.Caching.MemoryCache>默认情况下使用类的自动调整大小试探法。</span><span class="sxs-lookup"><span data-stu-id="5793f-116">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="5793f-117">缓存的名称。</span><span class="sxs-lookup"><span data-stu-id="5793f-117">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="5793f-118">一个整数值介于 0 和 100 之间，指定可以使用由缓存以物理方式安装的计算机内存的最大百分比。</span><span class="sxs-lookup"><span data-stu-id="5793f-118">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="5793f-119">默认值为 0，这意味着<xref:System.Runtime.Caching.MemoryCache>默认情况下使用类的自动调整大小试探法。</span><span class="sxs-lookup"><span data-stu-id="5793f-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="5793f-120">一个时间间隔的值，在该时间间隔之后，缓存实现会将当前内存负载与为缓存实例设置的基于绝对值和百分比的内存限制进行比较。</span><span class="sxs-lookup"><span data-stu-id="5793f-120">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="5793f-121">"Hh: mm:"格式输入此值。</span><span class="sxs-lookup"><span data-stu-id="5793f-121">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5793f-122">子元素</span><span class="sxs-lookup"><span data-stu-id="5793f-122">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="5793f-123">父元素</span><span class="sxs-lookup"><span data-stu-id="5793f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5793f-124">元素</span><span class="sxs-lookup"><span data-stu-id="5793f-124">Element</span></span>|<span data-ttu-id="5793f-125">描述</span><span class="sxs-lookup"><span data-stu-id="5793f-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5793f-126">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="5793f-126">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="5793f-127">包含的配置设置的命名集合<xref:System.Runtime.Caching.MemoryCache>实例。</span><span class="sxs-lookup"><span data-stu-id="5793f-127">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5793f-128">备注</span><span class="sxs-lookup"><span data-stu-id="5793f-128">Remarks</span></span>  
 <span data-ttu-id="5793f-129">`add`元素添加一个条目`namedCaches`内存缓存的集合。</span><span class="sxs-lookup"><span data-stu-id="5793f-129">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="5793f-130">可以使用[清除](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)元素在使用之前`add`元素以确认是否不存在任何其他命名缓存在集合中的。</span><span class="sxs-lookup"><span data-stu-id="5793f-130">You can use the [clear](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="5793f-131">在 machine.config 文件中并在 Web.config 文件中，可以使用此元素。</span><span class="sxs-lookup"><span data-stu-id="5793f-131">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5793f-132">示例</span><span class="sxs-lookup"><span data-stu-id="5793f-132">Example</span></span>  
 <span data-ttu-id="5793f-133">下面的示例演示如何定义的默认设置`namedCache`进入`namedCaches`内存缓存的集合。</span><span class="sxs-lookup"><span data-stu-id="5793f-133">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5793f-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="5793f-134">See also</span></span>

- [<span data-ttu-id="5793f-135">\<namedCaches > 元素 （缓存设置）</span><span class="sxs-lookup"><span data-stu-id="5793f-135">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
