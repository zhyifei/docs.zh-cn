---
title: <forcePerformanceCounterUniqueSharedMemoryReads> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
ms.openlocfilehash: efa6dce1035f7d2cf63b74c6a03d911b5dede722
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116956"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a><span data-ttu-id="3ae70-102">\<s > 元素</span><span class="sxs-lookup"><span data-stu-id="3ae70-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span></span>
<span data-ttu-id="3ae70-103">指定 PerfCounter.dll 是否使用 .NET Framework 版本 1.1 应用程序中的 CategoryOptions 注册表设置，以确定是否加载来自特定于类别的共享内存或全局内存的性能计数器数据。</span><span class="sxs-lookup"><span data-stu-id="3ae70-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
<span data-ttu-id="3ae70-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3ae70-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3ae70-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="3ae70-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="3ae70-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<s >**</span><span class="sxs-lookup"><span data-stu-id="3ae70-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<forcePerformanceCounterUniqueSharedMemoryReads>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ae70-107">语法</span><span class="sxs-lookup"><span data-stu-id="3ae70-107">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ae70-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3ae70-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3ae70-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3ae70-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ae70-110">特性</span><span class="sxs-lookup"><span data-stu-id="3ae70-110">Attributes</span></span>  
  
|<span data-ttu-id="3ae70-111">特性</span><span class="sxs-lookup"><span data-stu-id="3ae70-111">Attribute</span></span>|<span data-ttu-id="3ae70-112">描述</span><span class="sxs-lookup"><span data-stu-id="3ae70-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="3ae70-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="3ae70-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="3ae70-114">指示 Perfcounter finish 是否使用 CategoryOptions 注册表设置来确定是否从特定于类别的共享内存或全局内存加载性能计数器数据。</span><span class="sxs-lookup"><span data-stu-id="3ae70-114">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="3ae70-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="3ae70-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="3ae70-116">“值”</span><span class="sxs-lookup"><span data-stu-id="3ae70-116">Value</span></span>|<span data-ttu-id="3ae70-117">描述</span><span class="sxs-lookup"><span data-stu-id="3ae70-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="3ae70-118">Perfcounter finish 不使用 CategoryOptions 注册表设置，这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="3ae70-118">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="3ae70-119">Perfcounter finish 使用 CategoryOptions 注册表设置。</span><span class="sxs-lookup"><span data-stu-id="3ae70-119">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ae70-120">子元素</span><span class="sxs-lookup"><span data-stu-id="3ae70-120">Child Elements</span></span>  
 <span data-ttu-id="3ae70-121">无。</span><span class="sxs-lookup"><span data-stu-id="3ae70-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3ae70-122">父元素</span><span class="sxs-lookup"><span data-stu-id="3ae70-122">Parent Elements</span></span>  
  
|<span data-ttu-id="3ae70-123">元素</span><span class="sxs-lookup"><span data-stu-id="3ae70-123">Element</span></span>|<span data-ttu-id="3ae70-124">描述</span><span class="sxs-lookup"><span data-stu-id="3ae70-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3ae70-125">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="3ae70-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3ae70-126">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="3ae70-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ae70-127">备注</span><span class="sxs-lookup"><span data-stu-id="3ae70-127">Remarks</span></span>  
 <span data-ttu-id="3ae70-128">在 .NET Framework 4 之前的 .NET Framework 版本中，已加载到进程中加载的运行时的 Perfcounter finish 的版本。</span><span class="sxs-lookup"><span data-stu-id="3ae70-128">In versions of the .NET Framework before the .NET Framework 4, the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="3ae70-129">如果计算机已安装 .NET Framework 版本1.1 和 .NET Framework 2.0，.NET Framework 1.1 应用程序会加载 .NET Framework 1.1 版本的 Perfcounter finish。</span><span class="sxs-lookup"><span data-stu-id="3ae70-129">If a computer had both the .NET Framework version 1.1 and the .NET Framework 2.0 installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="3ae70-130">从 .NET Framework 4 开始，将加载 Perfcounter finish 的最新安装版本。</span><span class="sxs-lookup"><span data-stu-id="3ae70-130">Starting with the .NET Framework 4, the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="3ae70-131">这意味着，如果计算机上安装了 .NET Framework 4 版本，.NET Framework 1.1 应用程序将加载 Perfcounter finish 的 .NET Framework 4 版本。</span><span class="sxs-lookup"><span data-stu-id="3ae70-131">This means that a .NET Framework 1.1 application will load the .NET Framework 4 version of PerfCounter.dll if the .NET Framework 4 is installed on the computer.</span></span>  
  
 <span data-ttu-id="3ae70-132">从 .NET Framework 4 开始，使用性能计数器时，Perfcounter finish 会检查每个提供程序的 CategoryOptions 注册表项，以确定是否应从特定于类别的共享内存或全局共享内存中读取。</span><span class="sxs-lookup"><span data-stu-id="3ae70-132">Starting with the .NET Framework 4, when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="3ae70-133">.NET Framework 1.1 Perfcounter finish 无法读取该注册表项，因为它不知道特定于类别的共享内存;它始终从全局共享内存进行读取。</span><span class="sxs-lookup"><span data-stu-id="3ae70-133">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="3ae70-134">为实现向后兼容性，在 .NET Framework 1.1 应用程序中运行时，.NET Framework 4 Perfcounter finish 不检查 CategoryOptions 注册表项。</span><span class="sxs-lookup"><span data-stu-id="3ae70-134">For backward compatibility, the .NET Framework 4 PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="3ae70-135">它只使用全局共享内存，就像 .NET Framework 1.1 Perfcounter finish 一样。</span><span class="sxs-lookup"><span data-stu-id="3ae70-135">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="3ae70-136">但是，可以通过启用 `<forcePerformanceCounterUniqueSharedMemoryReads>` 元素指示 .NET Framework 4 Perfcounter finish 检查注册表设置。</span><span class="sxs-lookup"><span data-stu-id="3ae70-136">However, you can instruct the .NET Framework 4 PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3ae70-137">启用 `<forcePerformanceCounterUniqueSharedMemoryReads>` 元素不保证将使用特定于类别的共享内存。</span><span class="sxs-lookup"><span data-stu-id="3ae70-137">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="3ae70-138">"启用" 设置为 "`true` 仅导致 Perfcounter finish 引用 CategoryOptions 注册表设置。</span><span class="sxs-lookup"><span data-stu-id="3ae70-138">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="3ae70-139">CategoryOptions 的默认设置是使用特定于类别的共享内存;但是，您可以更改 CategoryOptions 以指示应使用全局共享内存。</span><span class="sxs-lookup"><span data-stu-id="3ae70-139">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="3ae70-140">包含 CategoryOptions 设置的注册表项为 HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\< 类别名称\>\Performance。</span><span class="sxs-lookup"><span data-stu-id="3ae70-140">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="3ae70-141">默认情况下，CategoryOptions 设置为3，指示 Perfcounter finish 使用特定于类别的共享内存。</span><span class="sxs-lookup"><span data-stu-id="3ae70-141">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="3ae70-142">如果将 CategoryOptions 设置为0，则 Perfcounter finish 将使用全局共享内存。</span><span class="sxs-lookup"><span data-stu-id="3ae70-142">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="3ae70-143">仅当正在创建的实例的名称与重复使用的实例相同时，才会重新使用实例数据。</span><span class="sxs-lookup"><span data-stu-id="3ae70-143">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="3ae70-144">所有版本都可以写入该类别。</span><span class="sxs-lookup"><span data-stu-id="3ae70-144">All versions will be able to write to the category.</span></span> <span data-ttu-id="3ae70-145">如果 CategoryOptions 设置为1，则使用全局共享内存，但如果类别名称与要重用的类别的长度相同，则可以重用实例数据。</span><span class="sxs-lookup"><span data-stu-id="3ae70-145">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="3ae70-146">设置0和1可能会导致内存泄漏和填充性能计数器内存。</span><span class="sxs-lookup"><span data-stu-id="3ae70-146">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ae70-147">示例</span><span class="sxs-lookup"><span data-stu-id="3ae70-147">Example</span></span>  
 <span data-ttu-id="3ae70-148">下面的示例演示如何指定 Perfcounter finish 应引用 CategoryOptions 注册表项，以确定它是否应使用特定于类别的共享内存。</span><span class="sxs-lookup"><span data-stu-id="3ae70-148">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3ae70-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="3ae70-149">See also</span></span>

- [<span data-ttu-id="3ae70-150">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="3ae70-150">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3ae70-151">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="3ae70-151">Configuration File Schema</span></span>](../index.md)
