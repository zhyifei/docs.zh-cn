---
title: <forcePerformanceCounterUniqueSharedMemoryReads> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
ms.openlocfilehash: 742b444c445ba67d6977b622e615a6a8f591826e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154135"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a><span data-ttu-id="ab1be-102">\<强制性能计数器唯一共享内存读取>元素</span><span class="sxs-lookup"><span data-stu-id="ab1be-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span></span>
<span data-ttu-id="ab1be-103">指定 PerfCounter.dll 是否使用 .NET Framework 版本 1.1 应用程序中的 CategoryOptions 注册表设置，以确定是否加载来自特定于类别的共享内存或全局内存的性能计数器数据。</span><span class="sxs-lookup"><span data-stu-id="ab1be-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
<span data-ttu-id="ab1be-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ab1be-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ab1be-105">&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="ab1be-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="ab1be-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<强制性能计数器唯一共享内存读取>**</span><span class="sxs-lookup"><span data-stu-id="ab1be-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<forcePerformanceCounterUniqueSharedMemoryReads>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab1be-107">语法</span><span class="sxs-lookup"><span data-stu-id="ab1be-107">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ab1be-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ab1be-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ab1be-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ab1be-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ab1be-110">属性</span><span class="sxs-lookup"><span data-stu-id="ab1be-110">Attributes</span></span>  
  
|<span data-ttu-id="ab1be-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="ab1be-111">Attribute</span></span>|<span data-ttu-id="ab1be-112">说明</span><span class="sxs-lookup"><span data-stu-id="ab1be-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="ab1be-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="ab1be-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="ab1be-114">指示 PerfCounter.dll 是否使用"类别选项"注册表设置来确定是从特定于类别的共享内存或全局内存加载性能计数器数据。</span><span class="sxs-lookup"><span data-stu-id="ab1be-114">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="ab1be-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="ab1be-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="ab1be-116">值</span><span class="sxs-lookup"><span data-stu-id="ab1be-116">Value</span></span>|<span data-ttu-id="ab1be-117">说明</span><span class="sxs-lookup"><span data-stu-id="ab1be-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="ab1be-118">PerfCounter.dll 不使用类别选项注册表设置这是默认值。</span><span class="sxs-lookup"><span data-stu-id="ab1be-118">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="ab1be-119">PerfCounter.dll 确实使用类别选项注册表设置。</span><span class="sxs-lookup"><span data-stu-id="ab1be-119">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ab1be-120">子元素</span><span class="sxs-lookup"><span data-stu-id="ab1be-120">Child Elements</span></span>  
 <span data-ttu-id="ab1be-121">无。</span><span class="sxs-lookup"><span data-stu-id="ab1be-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ab1be-122">父元素</span><span class="sxs-lookup"><span data-stu-id="ab1be-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ab1be-123">元素</span><span class="sxs-lookup"><span data-stu-id="ab1be-123">Element</span></span>|<span data-ttu-id="ab1be-124">说明</span><span class="sxs-lookup"><span data-stu-id="ab1be-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ab1be-125">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="ab1be-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ab1be-126">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="ab1be-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab1be-127">备注</span><span class="sxs-lookup"><span data-stu-id="ab1be-127">Remarks</span></span>  
 <span data-ttu-id="ab1be-128">在 .NET 框架 4 之前的 .NET 框架版本中，加载的 PerfCounter.dll 版本对应于进程中加载的运行时。</span><span class="sxs-lookup"><span data-stu-id="ab1be-128">In versions of the .NET Framework before the .NET Framework 4, the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="ab1be-129">如果计算机同时安装了 .NET 框架版本 1.1 和 .NET Framework 2.0，则 .NET 框架 1.1 应用程序将加载 PerfCounter.dll 的 .NET 框架 1.1 版本。</span><span class="sxs-lookup"><span data-stu-id="ab1be-129">If a computer had both the .NET Framework version 1.1 and the .NET Framework 2.0 installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="ab1be-130">从 .NET 框架 4 开始，将加载最新的已安装版本的 PerfCounter.dll。</span><span class="sxs-lookup"><span data-stu-id="ab1be-130">Starting with the .NET Framework 4, the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="ab1be-131">这意味着.NET 框架 1.1 应用程序将加载 .NET 框架 4 版本的 PerfCounter.dll，如果 .NET 框架 4 安装在计算机上。</span><span class="sxs-lookup"><span data-stu-id="ab1be-131">This means that a .NET Framework 1.1 application will load the .NET Framework 4 version of PerfCounter.dll if the .NET Framework 4 is installed on the computer.</span></span>  
  
 <span data-ttu-id="ab1be-132">从 .NET 框架 4 开始，使用性能计数器时，PerfCounter.dll 会检查每个提供程序的类别选项注册表项，以确定是否应从特定于类别的共享内存或全局共享内存读取该条目。</span><span class="sxs-lookup"><span data-stu-id="ab1be-132">Starting with the .NET Framework 4, when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="ab1be-133">.NET 框架 1.1 PerfCounter.dll 不读取该注册表项，因为它不知道特定于类别的共享内存;它总是从全局共享内存读取。</span><span class="sxs-lookup"><span data-stu-id="ab1be-133">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="ab1be-134">对于向后兼容性，.NET 框架 4 PerfCounter.dll 在 .NET 框架 1.1 应用程序中运行时不检查类别选项注册表项。</span><span class="sxs-lookup"><span data-stu-id="ab1be-134">For backward compatibility, the .NET Framework 4 PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="ab1be-135">它只使用全局共享内存，就像 .NET 框架 1.1 PerfCounter.dll 一样。</span><span class="sxs-lookup"><span data-stu-id="ab1be-135">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="ab1be-136">但是，您可以指示 .NET 框架 4 PerfCounter.dll 通过启用`<forcePerformanceCounterUniqueSharedMemoryReads>`该元素来检查注册表设置。</span><span class="sxs-lookup"><span data-stu-id="ab1be-136">However, you can instruct the .NET Framework 4 PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ab1be-137">启用该`<forcePerformanceCounterUniqueSharedMemoryReads>`元素并不保证将使用特定于类别的共享内存。</span><span class="sxs-lookup"><span data-stu-id="ab1be-137">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="ab1be-138">设置为仅启用`true`PerfCounter.dll 以引用类别选项注册表设置。</span><span class="sxs-lookup"><span data-stu-id="ab1be-138">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="ab1be-139">"类别选项"的默认设置是使用特定于类别的共享内存;但是，您可以更改类别选项以指示应使用全局共享内存。</span><span class="sxs-lookup"><span data-stu-id="ab1be-139">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="ab1be-140">包含"类别选项"设置的注册表项HKEY_LOCAL_MACHINE_System_CurrentControlSet_服务\\<类别名称\>\性能。</span><span class="sxs-lookup"><span data-stu-id="ab1be-140">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="ab1be-141">默认情况下，类别选项设置为 3，指示 PerfCounter.dll 使用特定于类别的共享内存。</span><span class="sxs-lookup"><span data-stu-id="ab1be-141">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="ab1be-142">如果类别选项设置为 0，PerfCounter.dll 将使用全局共享内存。</span><span class="sxs-lookup"><span data-stu-id="ab1be-142">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="ab1be-143">仅当要创建的实例的名称与正在重用的实例相同时，才会重用实例数据。</span><span class="sxs-lookup"><span data-stu-id="ab1be-143">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="ab1be-144">所有版本将能够写入类别。</span><span class="sxs-lookup"><span data-stu-id="ab1be-144">All versions will be able to write to the category.</span></span> <span data-ttu-id="ab1be-145">如果"类别选项"设置为 1，则使用全局共享内存，但如果类别名称的长度与正在重用的类别长度相同，则可以重复使用实例数据。</span><span class="sxs-lookup"><span data-stu-id="ab1be-145">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="ab1be-146">设置 0 和 1 可能导致内存泄漏和性能计数器内存填满。</span><span class="sxs-lookup"><span data-stu-id="ab1be-146">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab1be-147">示例</span><span class="sxs-lookup"><span data-stu-id="ab1be-147">Example</span></span>  
 <span data-ttu-id="ab1be-148">下面的示例演示如何指定 PerfCounter.dll 应引用类别选项注册表项以确定是否应使用特定于类别的共享内存。</span><span class="sxs-lookup"><span data-stu-id="ab1be-148">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ab1be-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab1be-149">See also</span></span>

- [<span data-ttu-id="ab1be-150">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="ab1be-150">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ab1be-151">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="ab1be-151">Configuration File Schema</span></span>](../index.md)
