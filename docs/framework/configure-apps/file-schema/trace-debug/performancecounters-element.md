---
title: '&lt;performanceCounters&gt;元素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <perfomanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 69d6deafb6aad88f5d379c7e8d4ac707e4c51815
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47209816"
---
# <a name="ltperformancecountersgt-element"></a><span data-ttu-id="a915e-102">&lt;performanceCounters&gt;元素</span><span class="sxs-lookup"><span data-stu-id="a915e-102">&lt;performanceCounters&gt; Element</span></span>
<span data-ttu-id="a915e-103">指定由性能计数器共享的全局内存的大小。</span><span class="sxs-lookup"><span data-stu-id="a915e-103">Specifies the size of the global memory shared by performance counters.</span></span>  
  
 <span data-ttu-id="a915e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a915e-104">\<configuration></span></span>  
<span data-ttu-id="a915e-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="a915e-105">\<system.diagnostics></span></span>  
<span data-ttu-id="a915e-106">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="a915e-106">\<performanceCounters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a915e-107">语法</span><span class="sxs-lookup"><span data-stu-id="a915e-107">Syntax</span></span>  
  
```xml  
<performanceCounters filemappingsize="524288" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a915e-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a915e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a915e-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a915e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a915e-110">特性</span><span class="sxs-lookup"><span data-stu-id="a915e-110">Attributes</span></span>  
  
|<span data-ttu-id="a915e-111">特性</span><span class="sxs-lookup"><span data-stu-id="a915e-111">Attribute</span></span>|<span data-ttu-id="a915e-112">描述</span><span class="sxs-lookup"><span data-stu-id="a915e-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a915e-113">filemappingsize</span><span class="sxs-lookup"><span data-stu-id="a915e-113">filemappingsize</span></span>|<span data-ttu-id="a915e-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="a915e-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="a915e-115">指定的大小，以字节为单位的性能计数器共享的全局内存。</span><span class="sxs-lookup"><span data-stu-id="a915e-115">Specifies the size, in bytes, of the global memory shared by performance counters.</span></span> <span data-ttu-id="a915e-116">默认值为 524288。</span><span class="sxs-lookup"><span data-stu-id="a915e-116">The default is 524288.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a915e-117">子元素</span><span class="sxs-lookup"><span data-stu-id="a915e-117">Child Elements</span></span>  
 <span data-ttu-id="a915e-118">无。</span><span class="sxs-lookup"><span data-stu-id="a915e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a915e-119">父元素</span><span class="sxs-lookup"><span data-stu-id="a915e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a915e-120">元素</span><span class="sxs-lookup"><span data-stu-id="a915e-120">Element</span></span>|<span data-ttu-id="a915e-121">描述</span><span class="sxs-lookup"><span data-stu-id="a915e-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="a915e-122">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="a915e-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="a915e-123">为 ASP.NET 配置节指定根元素。</span><span class="sxs-lookup"><span data-stu-id="a915e-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a915e-124">备注</span><span class="sxs-lookup"><span data-stu-id="a915e-124">Remarks</span></span>  
 <span data-ttu-id="a915e-125">性能计数器使用内存映射文件或共享的内存，发布性能数据。</span><span class="sxs-lookup"><span data-stu-id="a915e-125">Performance counters use a memory mapped file, or shared memory, to publish performance data.</span></span>  <span data-ttu-id="a915e-126">共享内存的大小决定可以在一次使用多少个实例。</span><span class="sxs-lookup"><span data-stu-id="a915e-126">The size of the shared memory determines how many instances can be used at once.</span></span>  <span data-ttu-id="a915e-127">有两种类型的共享内存： 全局共享内存和单独的共享的内存。</span><span class="sxs-lookup"><span data-stu-id="a915e-127">There are two types of shared memory: global shared memory and separate shared memory.</span></span>  <span data-ttu-id="a915e-128">使用.NET framework 1.0 或 1.1 版安装的所有性能计数器类别都使用全局共享的内存。</span><span class="sxs-lookup"><span data-stu-id="a915e-128">The global shared memory is used by all performance counter categories installed with the .NET Framework versions 1.0 or 1.1.</span></span>  <span data-ttu-id="a915e-129">安装.NET framework 2.0 版的性能计数器类别使用单独的共享的内存，每个性能计数器类别都有自己的内存。</span><span class="sxs-lookup"><span data-stu-id="a915e-129">Performance counter categories installed with the .NET Framework version 2.0 use separate shared memory, with each performance counter category having its own memory.</span></span>  
  
 <span data-ttu-id="a915e-130">可以仅使用配置文件设置全局共享内存的大小。</span><span class="sxs-lookup"><span data-stu-id="a915e-130">The size of global shared memory can be set only with a configuration file.</span></span>  <span data-ttu-id="a915e-131">默认大小为 524288 字节，最大大小是 33554432 字节的最小大小为 32,768 字节。</span><span class="sxs-lookup"><span data-stu-id="a915e-131">The default size is 524,288 byes, the maximum size is 33,554,432 bytes, and the minimum size is 32,768 bytes.</span></span>  <span data-ttu-id="a915e-132">由于全局共享的内存中共享的所有进程和类别时，第一个创建者指定的大小。</span><span class="sxs-lookup"><span data-stu-id="a915e-132">Since the global shared memory is shared by all processes and categories, the first creator specifies the size.</span></span>  <span data-ttu-id="a915e-133">如果在应用程序配置文件中定义的大小，如果你的应用程序是会导致要执行的性能计数器的第一个应用程序才会使用该大小。</span><span class="sxs-lookup"><span data-stu-id="a915e-133">If you define the size in your application configuration file, that size is only used if your application is the first application that causes the performance counters to execute.</span></span>  <span data-ttu-id="a915e-134">因此正确的位置来指定`filemappingsize`值是 Machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="a915e-134">Therefore the correct location to specify the `filemappingsize` value is the Machine.config file.</span></span>  <span data-ttu-id="a915e-135">不能由单个性能计数器，因此，最终全局共享的内存已用尽，如果将创建大量具有不同名称的性能计数器实例的发布中全局共享内存的内存。</span><span class="sxs-lookup"><span data-stu-id="a915e-135">Memory in the global shared memory cannot be released by individual performance counters, so eventually global shared memory is exhausted if a large number of performance counter instances with different names are created.</span></span>  
  
 <span data-ttu-id="a915e-136">对于单独共享内存的大小，在注册表中的 DWORD FileMappingSize 值密钥 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<类别名称 >* \Performance 引用首先后, 跟为全局共享内存配置文件中指定的值。</span><span class="sxs-lookup"><span data-stu-id="a915e-136">For the size of separate shared memory, the DWORD FileMappingSize value in the registry key HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<category name>* \Performance is referenced first, followed by the value specified for the global shared memory in the configuration file.</span></span> <span data-ttu-id="a915e-137">如果 FileMappingSize 值不存在，则单独的共享的内存大小设置为一个第四个 (1/4) 配置文件中的全局设置。</span><span class="sxs-lookup"><span data-stu-id="a915e-137">If the FileMappingSize value does not exist, then the separate shared memory size is set to one fourth (1/4) the global setting in the configuration file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a915e-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="a915e-138">See Also</span></span>  
 <xref:System.Diagnostics.PerformanceCounter>  
 <xref:System.Diagnostics.PerformanceCounterCategory>  
 <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>  
 <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
