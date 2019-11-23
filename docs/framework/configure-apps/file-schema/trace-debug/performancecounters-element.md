---
title: <performanceCounters> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <performanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
ms.openlocfilehash: f52fdb2d5b0b7911de63f96663e70735d2f2496c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697156"
---
# <a name="performancecounters-element"></a><span data-ttu-id="a92ca-102">\<performanceCounters > 元素</span><span class="sxs-lookup"><span data-stu-id="a92ca-102">\<performanceCounters> Element</span></span>

<span data-ttu-id="a92ca-103">指定由性能计数器共享的全局内存的大小。</span><span class="sxs-lookup"><span data-stu-id="a92ca-103">Specifies the size of the global memory shared by performance counters.</span></span>

[<span data-ttu-id="a92ca-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="a92ca-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="a92ca-105">&nbsp;&nbsp;[ **\<的 >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="a92ca-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="a92ca-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<performanceCounters >**</span><span class="sxs-lookup"><span data-stu-id="a92ca-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<performanceCounters>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="a92ca-107">语法</span><span class="sxs-lookup"><span data-stu-id="a92ca-107">Syntax</span></span>

```xml
<performanceCounters filemappingsize="524288" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a92ca-108">属性和元素</span><span class="sxs-lookup"><span data-stu-id="a92ca-108">Attributes and Elements</span></span>

<span data-ttu-id="a92ca-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a92ca-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a92ca-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="a92ca-110">Attributes</span></span>

|<span data-ttu-id="a92ca-111">属性</span><span class="sxs-lookup"><span data-stu-id="a92ca-111">Attribute</span></span>|<span data-ttu-id="a92ca-112">说明</span><span class="sxs-lookup"><span data-stu-id="a92ca-112">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="a92ca-113">filemappingsize</span><span class="sxs-lookup"><span data-stu-id="a92ca-113">filemappingsize</span></span>|<span data-ttu-id="a92ca-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="a92ca-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="a92ca-115">指定由性能计数器共享的全局内存的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="a92ca-115">Specifies the size, in bytes, of the global memory shared by performance counters.</span></span> <span data-ttu-id="a92ca-116">默认值为 524288。</span><span class="sxs-lookup"><span data-stu-id="a92ca-116">The default is 524288.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="a92ca-117">子元素</span><span class="sxs-lookup"><span data-stu-id="a92ca-117">Child Elements</span></span>

<span data-ttu-id="a92ca-118">无。</span><span class="sxs-lookup"><span data-stu-id="a92ca-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a92ca-119">父元素</span><span class="sxs-lookup"><span data-stu-id="a92ca-119">Parent Elements</span></span>

|<span data-ttu-id="a92ca-120">元素</span><span class="sxs-lookup"><span data-stu-id="a92ca-120">Element</span></span>|<span data-ttu-id="a92ca-121">说明</span><span class="sxs-lookup"><span data-stu-id="a92ca-121">Description</span></span>|
|-------------|-----------------|
|`Configuration`|<span data-ttu-id="a92ca-122">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="a92ca-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`system.diagnostics`|<span data-ttu-id="a92ca-123">为 ASP.NET 配置节指定根元素。</span><span class="sxs-lookup"><span data-stu-id="a92ca-123">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a92ca-124">备注</span><span class="sxs-lookup"><span data-stu-id="a92ca-124">Remarks</span></span>

<span data-ttu-id="a92ca-125">性能计数器使用内存映射文件或共享内存来发布性能数据。</span><span class="sxs-lookup"><span data-stu-id="a92ca-125">Performance counters use a memory mapped file, or shared memory, to publish performance data.</span></span>  <span data-ttu-id="a92ca-126">共享内存的大小决定了可同时使用的实例数。</span><span class="sxs-lookup"><span data-stu-id="a92ca-126">The size of the shared memory determines how many instances can be used at once.</span></span>  <span data-ttu-id="a92ca-127">共有两种类型的共享内存：全局共享内存和单独的共享内存。</span><span class="sxs-lookup"><span data-stu-id="a92ca-127">There are two types of shared memory: global shared memory and separate shared memory.</span></span>  <span data-ttu-id="a92ca-128">与 .NET Framework 版本1.0 或1.1 一起安装的所有性能计数器类别均使用全局共享内存。</span><span class="sxs-lookup"><span data-stu-id="a92ca-128">The global shared memory is used by all performance counter categories installed with the .NET Framework versions 1.0 or 1.1.</span></span>  <span data-ttu-id="a92ca-129">随 .NET Framework 版本2.0 一起安装的性能计数器类别使用单独的共享内存，其中每个性能计数器类别都有自己的内存。</span><span class="sxs-lookup"><span data-stu-id="a92ca-129">Performance counter categories installed with the .NET Framework version 2.0 use separate shared memory, with each performance counter category having its own memory.</span></span>

<span data-ttu-id="a92ca-130">全局共享内存的大小只能与配置文件一起设置。</span><span class="sxs-lookup"><span data-stu-id="a92ca-130">The size of global shared memory can be set only with a configuration file.</span></span>  <span data-ttu-id="a92ca-131">默认大小为 524288 byes，最大大小为33554432个字节，最小大小为32768个字节。</span><span class="sxs-lookup"><span data-stu-id="a92ca-131">The default size is 524,288 byes, the maximum size is 33,554,432 bytes, and the minimum size is 32,768 bytes.</span></span>  <span data-ttu-id="a92ca-132">由于全局共享内存由所有进程和类别共享，因此第一个创建者指定大小。</span><span class="sxs-lookup"><span data-stu-id="a92ca-132">Since the global shared memory is shared by all processes and categories, the first creator specifies the size.</span></span>  <span data-ttu-id="a92ca-133">如果在应用程序配置文件中定义大小，则仅当应用程序是导致性能计数器执行的第一个应用程序时，才使用该大小。</span><span class="sxs-lookup"><span data-stu-id="a92ca-133">If you define the size in your application configuration file, that size is only used if your application is the first application that causes the performance counters to execute.</span></span>  <span data-ttu-id="a92ca-134">因此，指定 `filemappingsize` 值的正确位置是 Machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="a92ca-134">Therefore the correct location to specify the `filemappingsize` value is the Machine.config file.</span></span>  <span data-ttu-id="a92ca-135">全局共享内存中的内存不能由单独的性能计数器释放，因此，如果创建了大量具有不同名称的性能计数器实例，则最终的全局共享内存会耗尽。</span><span class="sxs-lookup"><span data-stu-id="a92ca-135">Memory in the global shared memory cannot be released by individual performance counters, so eventually global shared memory is exhausted if a large number of performance counter instances with different names are created.</span></span>

<span data-ttu-id="a92ca-136">对于单独的共享内存的大小，将首先引用注册表项 HKEY_LOCAL_MACHINE \SYSTEM\CurrentControlSet\Services\\ *\<类别名称 >* \PERFORMANCE 的 DWORD FileMappingSize 值，然后引用在配置文件中为全局共享内存指定的值。</span><span class="sxs-lookup"><span data-stu-id="a92ca-136">For the size of separate shared memory, the DWORD FileMappingSize value in the registry key HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<category name>* \Performance is referenced first, followed by the value specified for the global shared memory in the configuration file.</span></span> <span data-ttu-id="a92ca-137">如果 FileMappingSize 值不存在，则会在配置文件中将单独的共享内存大小设置为第四（1/4）个全局设置。</span><span class="sxs-lookup"><span data-stu-id="a92ca-137">If the FileMappingSize value does not exist, then the separate shared memory size is set to one fourth (1/4) the global setting in the configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="a92ca-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a92ca-138">See also</span></span>

- <xref:System.Diagnostics.PerformanceCounter>
- <xref:System.Diagnostics.PerformanceCounterCategory>
- <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>
- <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
