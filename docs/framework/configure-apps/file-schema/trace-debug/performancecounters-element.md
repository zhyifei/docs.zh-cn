---
title: "&lt;performanceCounters&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <perfomanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 64afd62c6eeca7bce14e331fdc65fccfa3d02bce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltperformancecountersgt-element"></a><span data-ttu-id="5618b-102">&lt;performanceCounters&gt;元素</span><span class="sxs-lookup"><span data-stu-id="5618b-102">&lt;performanceCounters&gt; Element</span></span>
<span data-ttu-id="5618b-103">指定由性能计数器共享的全局内存的大小。</span><span class="sxs-lookup"><span data-stu-id="5618b-103">Specifies the size of the global memory shared by performance counters.</span></span>  
  
 <span data-ttu-id="5618b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5618b-104">\<configuration></span></span>  
<span data-ttu-id="5618b-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="5618b-105">\<system.diagnostics></span></span>  
<span data-ttu-id="5618b-106">\<performanceCounters ></span><span class="sxs-lookup"><span data-stu-id="5618b-106">\<performanceCounters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5618b-107">语法</span><span class="sxs-lookup"><span data-stu-id="5618b-107">Syntax</span></span>  
  
```xml  
<performanceCounters filemappingsize="524288" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5618b-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5618b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5618b-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5618b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5618b-110">特性</span><span class="sxs-lookup"><span data-stu-id="5618b-110">Attributes</span></span>  
  
|<span data-ttu-id="5618b-111">特性</span><span class="sxs-lookup"><span data-stu-id="5618b-111">Attribute</span></span>|<span data-ttu-id="5618b-112">描述</span><span class="sxs-lookup"><span data-stu-id="5618b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5618b-113">filemappingsize</span><span class="sxs-lookup"><span data-stu-id="5618b-113">filemappingsize</span></span>|<span data-ttu-id="5618b-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="5618b-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="5618b-115">指定的大小，以字节为单位由性能计数器共享的全局内存。</span><span class="sxs-lookup"><span data-stu-id="5618b-115">Specifies the size, in bytes, of the global memory shared by performance counters.</span></span> <span data-ttu-id="5618b-116">默认值为 524288。</span><span class="sxs-lookup"><span data-stu-id="5618b-116">The default is 524288.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5618b-117">子元素</span><span class="sxs-lookup"><span data-stu-id="5618b-117">Child Elements</span></span>  
 <span data-ttu-id="5618b-118">无。</span><span class="sxs-lookup"><span data-stu-id="5618b-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5618b-119">父元素</span><span class="sxs-lookup"><span data-stu-id="5618b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="5618b-120">元素</span><span class="sxs-lookup"><span data-stu-id="5618b-120">Element</span></span>|<span data-ttu-id="5618b-121">说明</span><span class="sxs-lookup"><span data-stu-id="5618b-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="5618b-122">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="5618b-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="5618b-123">为 ASP.NET 配置节指定根元素。</span><span class="sxs-lookup"><span data-stu-id="5618b-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5618b-124">备注</span><span class="sxs-lookup"><span data-stu-id="5618b-124">Remarks</span></span>  
 <span data-ttu-id="5618b-125">性能计数器使用内存映射文件或共享的内存，发布性能数据。</span><span class="sxs-lookup"><span data-stu-id="5618b-125">Performance counters use a memory mapped file, or shared memory, to publish performance data.</span></span>  <span data-ttu-id="5618b-126">共享内存的大小确定可以在一次使用多少个实例。</span><span class="sxs-lookup"><span data-stu-id="5618b-126">The size of the shared memory determines how many instances can be used at once.</span></span>  <span data-ttu-id="5618b-127">有两种类型的共享内存： 全局共享内存和单独的共享的内存。</span><span class="sxs-lookup"><span data-stu-id="5618b-127">There are two types of shared memory: global shared memory and separate shared memory.</span></span>  <span data-ttu-id="5618b-128">安装的.NET Framework 版本 1.0 或 1.1 的所有性能计数器类别都使用全局共享的内存。</span><span class="sxs-lookup"><span data-stu-id="5618b-128">The global shared memory is used by all performance counter categories installed with the .NET Framework versions 1.0 or 1.1.</span></span>  <span data-ttu-id="5618b-129">随.NET Framework 2.0 版一起安装的性能计数器类别使用单独的共享的内存，每个性能计数器类别都有自己的内存。</span><span class="sxs-lookup"><span data-stu-id="5618b-129">Performance counter categories installed with the .NET Framework version 2.0 use separate shared memory, with each performance counter category having its own memory.</span></span>  
  
 <span data-ttu-id="5618b-130">可以仅使用配置文件设置全局共享内存的大小。</span><span class="sxs-lookup"><span data-stu-id="5618b-130">The size of global shared memory can be set only with a configuration file.</span></span>  <span data-ttu-id="5618b-131">默认大小为 524288 字节、 最大大小为 33554432 字节，和的最小大小为 32,768 字节。</span><span class="sxs-lookup"><span data-stu-id="5618b-131">The default size is 524,288 byes, the maximum size is 33,554,432 bytes, and the minimum size is 32,768 bytes.</span></span>  <span data-ttu-id="5618b-132">由于全局共享的内存共享由所有进程和类别的第一个创建者指定的大小。</span><span class="sxs-lookup"><span data-stu-id="5618b-132">Since the global shared memory is shared by all processes and categories, the first creator specifies the size.</span></span>  <span data-ttu-id="5618b-133">如果应用程序配置文件中定义的大小，如果你的应用程序的第一个应用程序会导致要执行的性能计数器才会使用该大小。</span><span class="sxs-lookup"><span data-stu-id="5618b-133">If you define the size in your application configuration file, that size is only used if your application is the first application that causes the performance counters to execute.</span></span>  <span data-ttu-id="5618b-134">因此指定的正确位置`filemappingsize`值是 Machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="5618b-134">Therefore the correct location to specify the `filemappingsize` value is the Machine.config file.</span></span>  <span data-ttu-id="5618b-135">无法通过单个性能计数器，因此，最终全局共享的内存用完时，如果创建了大量的具有不同名称的性能计数器实例释放全局共享内存中的内存。</span><span class="sxs-lookup"><span data-stu-id="5618b-135">Memory in the global shared memory cannot be released by individual performance counters, so eventually global shared memory is exhausted if a large number of performance counter instances with different names are created.</span></span>  
  
 <span data-ttu-id="5618b-136">对于单独的共享内存大小，在注册表中的 DWORD FileMappingSize 值密钥 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<类别名称 >*引用 \Performance首先后, 跟为配置文件中的全局共享内存指定的值。</span><span class="sxs-lookup"><span data-stu-id="5618b-136">For the size of separate shared memory, the DWORD FileMappingSize value in the registry key HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<category name>*\Performance is referenced first, followed by the value specified for the global shared memory in the configuration file.</span></span> <span data-ttu-id="5618b-137">如果 FileMappingSize 值不存在，则单独的共享的内存大小设置为一个第四个 (1/4) 配置文件中的全局设置。</span><span class="sxs-lookup"><span data-stu-id="5618b-137">If the FileMappingSize value does not exist, then the separate shared memory size is set to one fourth (1/4) the global setting in the configuration file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5618b-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="5618b-138">See Also</span></span>  
 <xref:System.Diagnostics.PerformanceCounter>  
 <xref:System.Diagnostics.PerformanceCounterCategory>  
 <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>  
 <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
