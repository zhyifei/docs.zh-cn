---
title: "&lt;forcePerformanceCounterUniqueSharedMemoryReads&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4c90799ed2db061e8f42cde79804789eb8d2da0a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltforceperformancecounteruniquesharedmemoryreadsgt-element"></a><span data-ttu-id="d69f8-102">&lt;forcePerformanceCounterUniqueSharedMemoryReads&gt;元素</span><span class="sxs-lookup"><span data-stu-id="d69f8-102">&lt;forcePerformanceCounterUniqueSharedMemoryReads&gt; Element</span></span>
<span data-ttu-id="d69f8-103">指定 PerfCounter.dll 是否使用 .NET Framework 版本 1.1 应用程序中的 CategoryOptions 注册表设置，以确定是否加载来自特定于类别的共享内存或全局内存的性能计数器数据。</span><span class="sxs-lookup"><span data-stu-id="d69f8-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
 <span data-ttu-id="d69f8-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d69f8-104">\<configuration></span></span>  
<span data-ttu-id="d69f8-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="d69f8-105">\<runtime></span></span>  
<span data-ttu-id="d69f8-106">\<forcePerformanceCounterUniqueSharedMemoryReads ></span><span class="sxs-lookup"><span data-stu-id="d69f8-106">\<forcePerformanceCounterUniqueSharedMemoryReads></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d69f8-107">语法</span><span class="sxs-lookup"><span data-stu-id="d69f8-107">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d69f8-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d69f8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d69f8-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d69f8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d69f8-110">特性</span><span class="sxs-lookup"><span data-stu-id="d69f8-110">Attributes</span></span>  
  
|<span data-ttu-id="d69f8-111">特性</span><span class="sxs-lookup"><span data-stu-id="d69f8-111">Attribute</span></span>|<span data-ttu-id="d69f8-112">描述</span><span class="sxs-lookup"><span data-stu-id="d69f8-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="d69f8-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="d69f8-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="d69f8-114">指示是否 PerfCounter.dll 使用 CategoryOptions 注册表设置来确定是否要从特定于类别的共享的内存或全局内存加载性能计数器数据。</span><span class="sxs-lookup"><span data-stu-id="d69f8-114">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="d69f8-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="d69f8-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="d69f8-116">值</span><span class="sxs-lookup"><span data-stu-id="d69f8-116">Value</span></span>|<span data-ttu-id="d69f8-117">描述</span><span class="sxs-lookup"><span data-stu-id="d69f8-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="d69f8-118">PerfCounter.dll 不使用 CategoryOptions 注册表设置这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="d69f8-118">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="d69f8-119">PerfCounter.dll 使用 CategoryOptions 注册表设置。</span><span class="sxs-lookup"><span data-stu-id="d69f8-119">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d69f8-120">子元素</span><span class="sxs-lookup"><span data-stu-id="d69f8-120">Child Elements</span></span>  
 <span data-ttu-id="d69f8-121">无。</span><span class="sxs-lookup"><span data-stu-id="d69f8-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d69f8-122">父元素</span><span class="sxs-lookup"><span data-stu-id="d69f8-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d69f8-123">元素</span><span class="sxs-lookup"><span data-stu-id="d69f8-123">Element</span></span>|<span data-ttu-id="d69f8-124">描述</span><span class="sxs-lookup"><span data-stu-id="d69f8-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d69f8-125">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="d69f8-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d69f8-126">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="d69f8-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d69f8-127">备注</span><span class="sxs-lookup"><span data-stu-id="d69f8-127">Remarks</span></span>  
 <span data-ttu-id="d69f8-128">在之前的.NET framework 的版本[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]，PerfCounter.dll 加载的版本对应于进程中加载的运行时。</span><span class="sxs-lookup"><span data-stu-id="d69f8-128">In versions of the .NET Framework before the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="d69f8-129">如果一台计算机有两个.NET Framework 1.1 版和[!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)]安装，.NET Framework 1.1 应用程序将加载 PerfCounter.dll 的.NET Framework 1.1 版本。</span><span class="sxs-lookup"><span data-stu-id="d69f8-129">If a computer had both the .NET Framework version 1.1 and the [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="d69f8-130">从开始[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]，加载 PerfCounter.dll 的最新安装的版本。</span><span class="sxs-lookup"><span data-stu-id="d69f8-130">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="d69f8-131">这意味着.NET Framework 1.1 应用程序将加载[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]PerfCounter.dll 版本如果[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]计算机上安装。</span><span class="sxs-lookup"><span data-stu-id="d69f8-131">This means that a .NET Framework 1.1 application will load the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] version of PerfCounter.dll if the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] is installed on the computer.</span></span>  
  
 <span data-ttu-id="d69f8-132">从开始[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]，PerfCounter.dll 时使用性能计数器，检查每个提供商联系，以确定是否应从特定于类别的共享的内存或全局共享的内存读取的 CategoryOptions 注册表项。</span><span class="sxs-lookup"><span data-stu-id="d69f8-132">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="d69f8-133">.NET Framework 1.1 PerfCounter.dll 不会读取该注册表项，因为它不是特定于类别的共享内存; 感知它始终从全局共享内存读取。</span><span class="sxs-lookup"><span data-stu-id="d69f8-133">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="d69f8-134">为了向后兼容， [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll 不会检查 CategoryOptions 注册表项，在.NET Framework 1.1 应用程序中运行时。</span><span class="sxs-lookup"><span data-stu-id="d69f8-134">For backward compatibility, the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="d69f8-135">它只需使用全局共享的内存，就像.NET Framework 1.1 PerfCounter.dll 一样。</span><span class="sxs-lookup"><span data-stu-id="d69f8-135">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="d69f8-136">但是，你可以指示[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]PerfCounter.dll 通过检查注册表设置`<forcePerformanceCounterUniqueSharedMemoryReads>`元素。</span><span class="sxs-lookup"><span data-stu-id="d69f8-136">However, you can instruct the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d69f8-137">启用`<forcePerformanceCounterUniqueSharedMemoryReads>`元素并不保证将使用特定于类别的共享的内存。</span><span class="sxs-lookup"><span data-stu-id="d69f8-137">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="d69f8-138">启用到设置`true`仅会导致 PerfCounter.dll 引用 CategoryOptions 注册表设置。</span><span class="sxs-lookup"><span data-stu-id="d69f8-138">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="d69f8-139">CategoryOptions 的默认设置是使用特定于类别的共享的内存;但是，你可以更改 CategoryOptions 以指示应使用全局共享的内存。</span><span class="sxs-lookup"><span data-stu-id="d69f8-139">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="d69f8-140">包含 CategoryOptions 设置的注册表项是 HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\< categoryName\>\Performance。</span><span class="sxs-lookup"><span data-stu-id="d69f8-140">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="d69f8-141">默认情况下，CategoryOptions 设置为 3，它指示 PerfCounter.dll 为使用特定于类别的共享的内存。</span><span class="sxs-lookup"><span data-stu-id="d69f8-141">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="d69f8-142">如果 CategoryOptions 设置为 0，PerfCounter.dll 使用全局共享的内存。</span><span class="sxs-lookup"><span data-stu-id="d69f8-142">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="d69f8-143">仅当正在创建的实例的名称是重复使用与实例相同，则仍将使用实例数据。</span><span class="sxs-lookup"><span data-stu-id="d69f8-143">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="d69f8-144">所有版本将都能够写入该类别。</span><span class="sxs-lookup"><span data-stu-id="d69f8-144">All versions will be able to write to the category.</span></span> <span data-ttu-id="d69f8-145">如果 CategoryOptions 设置为 1，则使用全局共享的内存，但可以重复使用实例数据，类别名称是否与要重复使用的类别的长度相同。</span><span class="sxs-lookup"><span data-stu-id="d69f8-145">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="d69f8-146">0 和 1 的设置可能导致内存泄漏和性能计数器内存填满。</span><span class="sxs-lookup"><span data-stu-id="d69f8-146">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d69f8-147">示例</span><span class="sxs-lookup"><span data-stu-id="d69f8-147">Example</span></span>  
 <span data-ttu-id="d69f8-148">下面的示例演示如何指定 PerfCounter.dll 应引用 CategoryOptions 注册表条目，以确定是否应使用特定于类别的共享的内存。</span><span class="sxs-lookup"><span data-stu-id="d69f8-148">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d69f8-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d69f8-149">See Also</span></span>  
 [<span data-ttu-id="d69f8-150">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="d69f8-150">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="d69f8-151">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="d69f8-151">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
