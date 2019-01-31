---
title: <forcePerformanceCounterUniqueSharedMemoryReads> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ba70e7cc94f90fa4fd44a12ffb6ffb2dba1ccc7
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275894"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a><span data-ttu-id="0b480-102">\<forcePerformanceCounterUniqueSharedMemoryReads > 元素</span><span class="sxs-lookup"><span data-stu-id="0b480-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span></span>
<span data-ttu-id="0b480-103">指定 PerfCounter.dll 是否使用 .NET Framework 版本 1.1 应用程序中的 CategoryOptions 注册表设置，以确定是否加载来自特定于类别的共享内存或全局内存的性能计数器数据。</span><span class="sxs-lookup"><span data-stu-id="0b480-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
 <span data-ttu-id="0b480-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0b480-104">\<configuration></span></span>  
<span data-ttu-id="0b480-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="0b480-105">\<runtime></span></span>  
<span data-ttu-id="0b480-106">\<forcePerformanceCounterUniqueSharedMemoryReads></span><span class="sxs-lookup"><span data-stu-id="0b480-106">\<forcePerformanceCounterUniqueSharedMemoryReads></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b480-107">语法</span><span class="sxs-lookup"><span data-stu-id="0b480-107">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b480-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0b480-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0b480-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0b480-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b480-110">特性</span><span class="sxs-lookup"><span data-stu-id="0b480-110">Attributes</span></span>  
  
|<span data-ttu-id="0b480-111">特性</span><span class="sxs-lookup"><span data-stu-id="0b480-111">Attribute</span></span>|<span data-ttu-id="0b480-112">描述</span><span class="sxs-lookup"><span data-stu-id="0b480-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="0b480-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="0b480-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="0b480-114">指示 PerfCounter.dll 是否使用 CategoryOptions 注册表设置来确定是否要从特定于类别的共享的内存或全局内存加载性能计数器数据。</span><span class="sxs-lookup"><span data-stu-id="0b480-114">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="0b480-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="0b480-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="0b480-116">值</span><span class="sxs-lookup"><span data-stu-id="0b480-116">Value</span></span>|<span data-ttu-id="0b480-117">描述</span><span class="sxs-lookup"><span data-stu-id="0b480-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="0b480-118">PerfCounter.dll 不使用 CategoryOptions 注册表设置这是默认值。</span><span class="sxs-lookup"><span data-stu-id="0b480-118">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="0b480-119">PerfCounter.dll 确实使用的 CategoryOptions 注册表设置。</span><span class="sxs-lookup"><span data-stu-id="0b480-119">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b480-120">子元素</span><span class="sxs-lookup"><span data-stu-id="0b480-120">Child Elements</span></span>  
 <span data-ttu-id="0b480-121">无。</span><span class="sxs-lookup"><span data-stu-id="0b480-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0b480-122">父元素</span><span class="sxs-lookup"><span data-stu-id="0b480-122">Parent Elements</span></span>  
  
|<span data-ttu-id="0b480-123">元素</span><span class="sxs-lookup"><span data-stu-id="0b480-123">Element</span></span>|<span data-ttu-id="0b480-124">描述</span><span class="sxs-lookup"><span data-stu-id="0b480-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0b480-125">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="0b480-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="0b480-126">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="0b480-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b480-127">备注</span><span class="sxs-lookup"><span data-stu-id="0b480-127">Remarks</span></span>  
 <span data-ttu-id="0b480-128">在之前的.NET framework 版本[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]，PerfCounter.dll 加载的版本对应于进程中加载的运行时。</span><span class="sxs-lookup"><span data-stu-id="0b480-128">In versions of the .NET Framework before the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="0b480-129">如果计算机有两个.NET Framework 1.1 版和[!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)]安装，.NET Framework 1.1 应用程序将加载 PerfCounter.dll 的.NET Framework 1.1 版本。</span><span class="sxs-lookup"><span data-stu-id="0b480-129">If a computer had both the .NET Framework version 1.1 and the [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="0b480-130">从开始[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]，加载最新安装的 PerfCounter.dll 版本。</span><span class="sxs-lookup"><span data-stu-id="0b480-130">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="0b480-131">这意味着.NET Framework 1.1 应用程序将加载[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]PerfCounter.dll 版本如果[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]的计算机上安装。</span><span class="sxs-lookup"><span data-stu-id="0b480-131">This means that a .NET Framework 1.1 application will load the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] version of PerfCounter.dll if the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] is installed on the computer.</span></span>  
  
 <span data-ttu-id="0b480-132">从开始[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]，PerfCounter.dll 时使用性能计数器，检查每个提供程序，以确定是否应从特定于类别的共享的内存或全局共享的内存读取的 CategoryOptions 注册表项。</span><span class="sxs-lookup"><span data-stu-id="0b480-132">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="0b480-133">.NET Framework 1.1 PerfCounter.dll 不读取该注册表项，因为它没有感知的特定于类别的共享内存;它始终从全局共享内存读取。</span><span class="sxs-lookup"><span data-stu-id="0b480-133">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="0b480-134">为了向后兼容， [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll 在.NET Framework 1.1 应用程序中运行时不检查 CategoryOptions 注册表项。</span><span class="sxs-lookup"><span data-stu-id="0b480-134">For backward compatibility, the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="0b480-135">它只需使用全局共享的内存，就像.NET Framework 1.1 PerfCounter.dll 一样。</span><span class="sxs-lookup"><span data-stu-id="0b480-135">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="0b480-136">但是，您可以指示[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]PerfCounter.dll 若要检查的注册表设置，从而`<forcePerformanceCounterUniqueSharedMemoryReads>`元素。</span><span class="sxs-lookup"><span data-stu-id="0b480-136">However, you can instruct the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b480-137">启用`<forcePerformanceCounterUniqueSharedMemoryReads>`元素不能保证将使用特定于类别的共享的内存。</span><span class="sxs-lookup"><span data-stu-id="0b480-137">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="0b480-138">启用到设置`true`仅会导致 PerfCounter.dll 要引用的 CategoryOptions 注册表设置。</span><span class="sxs-lookup"><span data-stu-id="0b480-138">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="0b480-139">CategoryOptions 的默认设置是使用特定于类别的共享的内存;但是，可以更改 CategoryOptions 若要指示应使用全局共享的内存。</span><span class="sxs-lookup"><span data-stu-id="0b480-139">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="0b480-140">包含 CategoryOptions 设置的注册表项是 HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\< categoryName\>\Performance。</span><span class="sxs-lookup"><span data-stu-id="0b480-140">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="0b480-141">默认情况下，CategoryOptions 设置为 3，它指示 PerfCounter.dll 为使用特定于类别的共享的内存。</span><span class="sxs-lookup"><span data-stu-id="0b480-141">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="0b480-142">如果 CategoryOptions 设置为 0，PerfCounter.dll 使用全局共享的内存。</span><span class="sxs-lookup"><span data-stu-id="0b480-142">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="0b480-143">仅当要创建的实例的名称是与实例被重复使用相同，则会重复使用实例数据。</span><span class="sxs-lookup"><span data-stu-id="0b480-143">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="0b480-144">所有版本将都能够写入该类别。</span><span class="sxs-lookup"><span data-stu-id="0b480-144">All versions will be able to write to the category.</span></span> <span data-ttu-id="0b480-145">如果 CategoryOptions 设置为 1，则使用全局共享的内存，但可以重复使用实例数据，类别名称是否被重复使用的类别相同的长度。</span><span class="sxs-lookup"><span data-stu-id="0b480-145">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="0b480-146">0 和 1 的设置可能会导致内存泄漏和性能计数器内存填满。</span><span class="sxs-lookup"><span data-stu-id="0b480-146">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b480-147">示例</span><span class="sxs-lookup"><span data-stu-id="0b480-147">Example</span></span>  
 <span data-ttu-id="0b480-148">下面的示例演示如何指定 PerfCounter.dll 应引用 CategoryOptions 注册表条目，以确定是否应使用特定于类别的共享的内存。</span><span class="sxs-lookup"><span data-stu-id="0b480-148">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b480-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b480-149">See also</span></span>
- [<span data-ttu-id="0b480-150">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="0b480-150">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="0b480-151">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="0b480-151">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
