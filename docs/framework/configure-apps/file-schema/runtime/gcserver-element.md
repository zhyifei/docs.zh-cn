---
title: r 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer
helpviewer_keywords:
- gcServer element
- <gcServer> element
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
ms.openlocfilehash: 8eab5e36bab90510aff4f1a3e15328197ac59ed7
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968946"
---
# <a name="gcserver-element"></a><span data-ttu-id="7bb75-102">\<r > 元素</span><span class="sxs-lookup"><span data-stu-id="7bb75-102">\<gcServer> element</span></span>

<span data-ttu-id="7bb75-103">指定公共语言运行时是否运行服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="7bb75-103">Specifies whether the common language runtime runs server garbage collection.</span></span>

<span data-ttu-id="7bb75-104">[\<configuration>](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7bb75-104">[\<configuration>](../configuration-element.md)</span></span>\
<span data-ttu-id="7bb75-105">&nbsp;&nbsp;[\<运行时 >](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="7bb75-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span></span>\
<span data-ttu-id="7bb75-106">&nbsp;&nbsp;&nbsp;&nbsp;\<r ></span><span class="sxs-lookup"><span data-stu-id="7bb75-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcServer></span></span>

## <a name="syntax"></a><span data-ttu-id="7bb75-107">语法</span><span class="sxs-lookup"><span data-stu-id="7bb75-107">Syntax</span></span>

```xml
<gcServer
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7bb75-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7bb75-108">Attributes and elements</span></span>

<span data-ttu-id="7bb75-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7bb75-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7bb75-110">特性</span><span class="sxs-lookup"><span data-stu-id="7bb75-110">Attributes</span></span>

|<span data-ttu-id="7bb75-111">特性</span><span class="sxs-lookup"><span data-stu-id="7bb75-111">Attribute</span></span>|<span data-ttu-id="7bb75-112">描述</span><span class="sxs-lookup"><span data-stu-id="7bb75-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="7bb75-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="7bb75-113">Required attribute.</span></span><br /><br /><span data-ttu-id="7bb75-114">指定运行时是否运行服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="7bb75-114">Specifies whether the runtime runs server garbage collection.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="7bb75-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="7bb75-115">enabled attribute</span></span>

|<span data-ttu-id="7bb75-116">“值”</span><span class="sxs-lookup"><span data-stu-id="7bb75-116">Value</span></span>|<span data-ttu-id="7bb75-117">描述</span><span class="sxs-lookup"><span data-stu-id="7bb75-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="7bb75-118">请勿运行服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="7bb75-118">Does not run server garbage collection.</span></span> <span data-ttu-id="7bb75-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="7bb75-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="7bb75-120">运行服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="7bb75-120">Runs server garbage collection.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="7bb75-121">子元素</span><span class="sxs-lookup"><span data-stu-id="7bb75-121">Child elements</span></span>

<span data-ttu-id="7bb75-122">无。</span><span class="sxs-lookup"><span data-stu-id="7bb75-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7bb75-123">父元素</span><span class="sxs-lookup"><span data-stu-id="7bb75-123">Parent elements</span></span>

|<span data-ttu-id="7bb75-124">元素</span><span class="sxs-lookup"><span data-stu-id="7bb75-124">Element</span></span>|<span data-ttu-id="7bb75-125">描述</span><span class="sxs-lookup"><span data-stu-id="7bb75-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="7bb75-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="7bb75-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="7bb75-127">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="7bb75-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7bb75-128">备注</span><span class="sxs-lookup"><span data-stu-id="7bb75-128">Remarks</span></span>

<span data-ttu-id="7bb75-129">公共语言运行时 (CLR) 支持两种类型的垃圾回收：工作站垃圾回收（适用于所有系统）和服务器垃圾回收（适用于多处理器系统）。</span><span class="sxs-lookup"><span data-stu-id="7bb75-129">The common language runtime (CLR) supports two types of garbage collection: workstation garbage collection, which is available on all systems, and server garbage collection, which is available on multiprocessor systems.</span></span> <span data-ttu-id="7bb75-130">使用**r**元素可控制 CLR 执行的垃圾回收的类型。</span><span class="sxs-lookup"><span data-stu-id="7bb75-130">Use the **gcServer** element to control the type of garbage collection the CLR performs.</span></span> <span data-ttu-id="7bb75-131">使用 <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> 属性以确定是否启用服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="7bb75-131">Use the <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> property to determine if server garbage collection is enabled.</span></span>

<span data-ttu-id="7bb75-132">对于单处理器计算机，默认的工作站垃圾回收应该是最快捷的选项。</span><span class="sxs-lookup"><span data-stu-id="7bb75-132">For single-processor computers, the default workstation garbage collection should be the fastest option.</span></span> <span data-ttu-id="7bb75-133">对于双处理器计算机，最快捷的选项既可以是工作站垃圾回收又可以是服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="7bb75-133">Either workstation or server can be used for two-processor computers.</span></span> <span data-ttu-id="7bb75-134">对于两个以上处理器的计算机，服务器垃圾回收应该是最快捷的选项。</span><span class="sxs-lookup"><span data-stu-id="7bb75-134">Server garbage collection should be the fastest option for more than two processors.</span></span> <span data-ttu-id="7bb75-135">在同一台计算机上运行多个服务器应用实例时，最常见的多处理器服务器系统禁用服务器 GC 并使用工作站 GC。</span><span class="sxs-lookup"><span data-stu-id="7bb75-135">Most commonly, multiprocessor server systems disable server GC and use workstation GC instead when many instances of a server app run on the same machine.</span></span>

<span data-ttu-id="7bb75-136">此元素只能在应用程序配置文件中使用；如果此元素在计算机配置文件中，请忽略。</span><span class="sxs-lookup"><span data-stu-id="7bb75-136">This element can be used only in the application configuration file; it is ignored if it is in the machine configuration file.</span></span>

> [!NOTE]
> <span data-ttu-id="7bb75-137">在 .NET Framework 4 和更低版本中，启用服务器垃圾回收之后，并发垃圾回收不可用。</span><span class="sxs-lookup"><span data-stu-id="7bb75-137">In the .NET Framework 4 and earlier versions, concurrent garbage collection is not available when server garbage collection is enabled.</span></span> <span data-ttu-id="7bb75-138">从 .NET Framework 4.5 开始，服务器垃圾回收将并发执行。</span><span class="sxs-lookup"><span data-stu-id="7bb75-138">Starting with the .NET Framework 4.5, server garbage collection is concurrent.</span></span> <span data-ttu-id="7bb75-139">若要使用非并发服务器垃圾回收，请将**r**元素设置为 `true`，并将[t 元素](gcconcurrent-element.md)设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="7bb75-139">To use non-concurrent server garbage collection, set the **gcServer** element to `true` and the [gcConcurrent element](gcconcurrent-element.md) to `false`.</span></span>

<span data-ttu-id="7bb75-140">从 .NET Framework 4.6.2 开始，你还可以使用以下元素来配置服务器 GC：</span><span class="sxs-lookup"><span data-stu-id="7bb75-140">Starting with .NET Framework 4.6.2, you can also use the following elements to configure server GC:</span></span>

- <span data-ttu-id="7bb75-141">[GCNoAffinitize](gcnoaffinitize-element.md)，用于指定服务器 GC 堆与处理器之间是否存在关联。</span><span class="sxs-lookup"><span data-stu-id="7bb75-141">[GCNoAffinitize](gcnoaffinitize-element.md), which specifies whether there is an affinity between server GC heaps and processors.</span></span> <span data-ttu-id="7bb75-142">默认情况下，每个处理器都有一个服务器 GC 堆。</span><span class="sxs-lookup"><span data-stu-id="7bb75-142">By default, there is one server GC heap for each processor.</span></span>

- <span data-ttu-id="7bb75-143">[GCHeapCount](gcheapcount-element.md)，用于限制进程使用的堆数。</span><span class="sxs-lookup"><span data-stu-id="7bb75-143">[GCHeapCount](gcheapcount-element.md), which limits the number of heaps used by a process.</span></span>

- <span data-ttu-id="7bb75-144">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md)，用于定义可用服务器 GC 堆和单个处理器之间的关联。</span><span class="sxs-lookup"><span data-stu-id="7bb75-144">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), which defines the affinity between the available server GC heaps and individual processors.</span></span>

## <a name="example"></a><span data-ttu-id="7bb75-145">示例</span><span class="sxs-lookup"><span data-stu-id="7bb75-145">Example</span></span>

<span data-ttu-id="7bb75-146">下面的示例启用服务器垃圾回收：</span><span class="sxs-lookup"><span data-stu-id="7bb75-146">The following example enables server garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="7bb75-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="7bb75-147">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="7bb75-148">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="7bb75-148">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7bb75-149">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="7bb75-149">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="7bb75-150">禁用并发垃圾回收</span><span class="sxs-lookup"><span data-stu-id="7bb75-150">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
