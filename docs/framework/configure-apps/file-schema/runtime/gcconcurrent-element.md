---
title: <gcConcurrent> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e2be4d9384f1e1ef73ce6064184aa2621a517a8
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2019
ms.locfileid: "55674589"
---
# <a name="gcconcurrent-element"></a><span data-ttu-id="cb268-102">\<gcConcurrent > 元素</span><span class="sxs-lookup"><span data-stu-id="cb268-102">\<gcConcurrent> Element</span></span>

<span data-ttu-id="cb268-103">指定公共语言运行时是否在单独线程上运行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="cb268-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>

<span data-ttu-id="cb268-104">\<configuration>\\</span><span class="sxs-lookup"><span data-stu-id="cb268-104">\<configuration>\\</span></span>
<span data-ttu-id="cb268-105">\<runtime>\\</span><span class="sxs-lookup"><span data-stu-id="cb268-105">\<runtime>\\</span></span>
<span data-ttu-id="cb268-106">\<gcConcurrent></span><span class="sxs-lookup"><span data-stu-id="cb268-106">\<gcConcurrent></span></span>

## <a name="syntax"></a><span data-ttu-id="cb268-107">语法</span><span class="sxs-lookup"><span data-stu-id="cb268-107">Syntax</span></span>

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cb268-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="cb268-108">Attributes and elements</span></span>

<span data-ttu-id="cb268-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="cb268-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="cb268-110">特性</span><span class="sxs-lookup"><span data-stu-id="cb268-110">Attributes</span></span>

|<span data-ttu-id="cb268-111">特性</span><span class="sxs-lookup"><span data-stu-id="cb268-111">Attribute</span></span>|<span data-ttu-id="cb268-112">描述</span><span class="sxs-lookup"><span data-stu-id="cb268-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="cb268-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="cb268-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="cb268-114">指定运行时是否并发运行服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="cb268-114">Specifies whether the runtime runs garbage collection concurrently.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="cb268-115">已启用的属性</span><span class="sxs-lookup"><span data-stu-id="cb268-115">enabled attribute</span></span>

|<span data-ttu-id="cb268-116">值</span><span class="sxs-lookup"><span data-stu-id="cb268-116">Value</span></span>|<span data-ttu-id="cb268-117">描述</span><span class="sxs-lookup"><span data-stu-id="cb268-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="cb268-118">不会同时运行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="cb268-118">Doesn't run garbage collection concurrently.</span></span>|
|`true`|<span data-ttu-id="cb268-119">并发运行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="cb268-119">Runs garbage collection concurrently.</span></span> <span data-ttu-id="cb268-120">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="cb268-120">This is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="cb268-121">子元素</span><span class="sxs-lookup"><span data-stu-id="cb268-121">Child elements</span></span>

<span data-ttu-id="cb268-122">无。</span><span class="sxs-lookup"><span data-stu-id="cb268-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="cb268-123">父元素</span><span class="sxs-lookup"><span data-stu-id="cb268-123">Parent elements</span></span>

|<span data-ttu-id="cb268-124">元素</span><span class="sxs-lookup"><span data-stu-id="cb268-124">Element</span></span>|<span data-ttu-id="cb268-125">描述</span><span class="sxs-lookup"><span data-stu-id="cb268-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="cb268-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="cb268-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="cb268-127">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="cb268-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cb268-128">备注</span><span class="sxs-lookup"><span data-stu-id="cb268-128">Remarks</span></span>

<span data-ttu-id="cb268-129">在.NET Framework 4 之前，工作站垃圾回收支持并发垃圾回收，在后台对一个单独线程执行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="cb268-129">Prior to the .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="cb268-130">在.NET Framework 4 中，并发垃圾回收被后台 GC 取代，它还在单独的线程上在后台中执行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="cb268-130">In the .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="cb268-131">从 .NET Framework 4.5 开始，服务器垃圾回收可提供后台垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="cb268-131">Starting with the .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="cb268-132">`<gcConcurrent>`元素控制运行时是否执行并发还是后台垃圾回收，如果可用，或是否在前台执行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="cb268-132">The `<gcConcurrent>` element controls whether the runtime performs either concurrent or background garbage collection, if it's available, or whether it performs garbage collection in the foreground.</span></span>

### <a name="to-disable-background-garbage-collection"></a><span data-ttu-id="cb268-133">若要禁用后台垃圾回收</span><span class="sxs-lookup"><span data-stu-id="cb268-133">To disable background garbage collection</span></span>

> [!WARNING]
> <span data-ttu-id="cb268-134">从.NET Framework 4 开始，并发垃圾回收替换为后台垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="cb268-134">Starting with the .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="cb268-135">条款*并发*并*背景*.NET Framework 文档中互换使用。</span><span class="sxs-lookup"><span data-stu-id="cb268-135">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="cb268-136">若要禁用后台垃圾回收，请使用 `<gcConcurrent>` 元素，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="cb268-136">To disable background garbage collection, use the `<gcConcurrent>` element, as discussed in this article.</span></span>

<span data-ttu-id="cb268-137">默认情况下，运行时使用并发或后台垃圾回收，回收针对延迟进行了优化。</span><span class="sxs-lookup"><span data-stu-id="cb268-137">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="cb268-138">如果应用程序涉及大量用户交互，则通过让并发垃圾回收保持启用状态，可最大限度缩短应用程序执行垃圾回收时的暂停时间。</span><span class="sxs-lookup"><span data-stu-id="cb268-138">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="cb268-139">如果将 `enabled` 元素的 `<gcConcurrent>` 特性设置为 `false`，运行时将使用针对吞吐量优化的非并发垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="cb268-139">If you set the `enabled` attribute of the `<gcConcurrent>` element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span> <span data-ttu-id="cb268-140">下列配置文件会禁用后台垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="cb268-140">The following configuration file disables background garbage collection.</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

 <span data-ttu-id="cb268-141">如果没有`<gcConcurrentSetting>`设置计算机配置文件中，它定义所有.NET Framework 应用程序的默认值。</span><span class="sxs-lookup"><span data-stu-id="cb268-141">If there's a `<gcConcurrentSetting>` setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="cb268-142">计算机配置文件设置将重写应用程序配置文件设置。</span><span class="sxs-lookup"><span data-stu-id="cb268-142">The machine configuration file setting overrides the application configuration file setting.</span></span>

 <span data-ttu-id="cb268-143">有关详细信息并发和后台垃圾回收，请参阅[并发垃圾回收](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection)主题中[垃圾回收的基础](../../../../standard/garbage-collection/fundamentals.md)一文。</span><span class="sxs-lookup"><span data-stu-id="cb268-143">For more information on concurrent and background garbage collection, see the [Concurrent garbage collection](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection) section in the [Fundamentals of Garbage Collection](../../../../standard/garbage-collection/fundamentals.md) article.</span></span>

## <a name="example"></a><span data-ttu-id="cb268-144">示例</span><span class="sxs-lookup"><span data-stu-id="cb268-144">Example</span></span>

<span data-ttu-id="cb268-145">下面的示例启用并发垃圾回收：</span><span class="sxs-lookup"><span data-stu-id="cb268-145">The following example enables concurrent garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="cb268-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="cb268-146">See also</span></span>

- [<span data-ttu-id="cb268-147">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="cb268-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="cb268-148">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="cb268-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="cb268-149">垃圾回收的基础知识</span><span class="sxs-lookup"><span data-stu-id="cb268-149">Fundamentals of Garbage Collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
