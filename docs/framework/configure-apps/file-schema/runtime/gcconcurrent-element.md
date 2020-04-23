---
title: gc并发元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
ms.openlocfilehash: 249518ae7477d284d50f9010757db83b7752c657
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102900"
---
# <a name="gcconcurrent-element"></a><span data-ttu-id="29f26-102">\<gc并发>元素</span><span class="sxs-lookup"><span data-stu-id="29f26-102">\<gcConcurrent> element</span></span>

<span data-ttu-id="29f26-103">指定公共语言运行时是否在单独线程上运行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="29f26-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>

<span data-ttu-id="29f26-104">[\<配置>](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="29f26-104">[\<configuration>](../configuration-element.md)</span></span>\
<span data-ttu-id="29f26-105">&nbsp;&nbsp;[\<运行时>](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="29f26-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span></span>\
<span data-ttu-id="29f26-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gc 并发></span><span class="sxs-lookup"><span data-stu-id="29f26-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcConcurrent></span></span>

## <a name="syntax"></a><span data-ttu-id="29f26-107">语法</span><span class="sxs-lookup"><span data-stu-id="29f26-107">Syntax</span></span>

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="29f26-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="29f26-108">Attributes and elements</span></span>

<span data-ttu-id="29f26-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="29f26-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="29f26-110">特性</span><span class="sxs-lookup"><span data-stu-id="29f26-110">Attributes</span></span>

|<span data-ttu-id="29f26-111">特性</span><span class="sxs-lookup"><span data-stu-id="29f26-111">Attribute</span></span>|<span data-ttu-id="29f26-112">描述</span><span class="sxs-lookup"><span data-stu-id="29f26-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="29f26-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="29f26-113">Required attribute.</span></span><br /><br /><span data-ttu-id="29f26-114">指定运行时是否并发运行服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="29f26-114">Specifies whether the runtime runs garbage collection concurrently.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="29f26-115">启用的属性</span><span class="sxs-lookup"><span data-stu-id="29f26-115">enabled attribute</span></span>

|<span data-ttu-id="29f26-116">值</span><span class="sxs-lookup"><span data-stu-id="29f26-116">Value</span></span>|<span data-ttu-id="29f26-117">描述</span><span class="sxs-lookup"><span data-stu-id="29f26-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="29f26-118">不同时运行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="29f26-118">Doesn't run garbage collection concurrently.</span></span>|
|`true`|<span data-ttu-id="29f26-119">并发运行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="29f26-119">Runs garbage collection concurrently.</span></span> <span data-ttu-id="29f26-120">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="29f26-120">This is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="29f26-121">子元素</span><span class="sxs-lookup"><span data-stu-id="29f26-121">Child elements</span></span>

<span data-ttu-id="29f26-122">无。</span><span class="sxs-lookup"><span data-stu-id="29f26-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="29f26-123">父元素</span><span class="sxs-lookup"><span data-stu-id="29f26-123">Parent elements</span></span>

|<span data-ttu-id="29f26-124">元素</span><span class="sxs-lookup"><span data-stu-id="29f26-124">Element</span></span>|<span data-ttu-id="29f26-125">描述</span><span class="sxs-lookup"><span data-stu-id="29f26-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="29f26-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="29f26-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="29f26-127">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="29f26-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="29f26-128">备注</span><span class="sxs-lookup"><span data-stu-id="29f26-128">Remarks</span></span>

<span data-ttu-id="29f26-129">在 .NET 框架 4 之前，工作站垃圾回收支持并发垃圾回收，该回收在后台在单独的线程上执行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="29f26-129">Prior to .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="29f26-130">在 .NET 框架 4 中，并发垃圾回收被后台 GC 替换，后台 GC 也在单独的线程的后台执行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="29f26-130">In .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="29f26-131">从 .NET 框架 4.5 开始，后台收集在服务器垃圾回收中可用。</span><span class="sxs-lookup"><span data-stu-id="29f26-131">Starting with .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="29f26-132">**gcConcurrent**元素控制运行时是否执行并发或后台垃圾回收，是否可用，或者它是否在前台执行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="29f26-132">The **gcConcurrent** element controls whether the runtime performs either concurrent or background garbage collection, if it's available, or whether it performs garbage collection in the foreground.</span></span>

### <a name="to-disable-background-garbage-collection"></a><span data-ttu-id="29f26-133">禁用后台垃圾回收</span><span class="sxs-lookup"><span data-stu-id="29f26-133">To disable background garbage collection</span></span>

> [!WARNING]
> <span data-ttu-id="29f26-134">从 .NET 框架 4 开始，并发垃圾回收将被后台垃圾回收替换。</span><span class="sxs-lookup"><span data-stu-id="29f26-134">Starting with .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="29f26-135">术语*并发*和*背景*在 .NET 框架文档中可互换使用。</span><span class="sxs-lookup"><span data-stu-id="29f26-135">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="29f26-136">要禁用后台垃圾回收，请使用**gcConcurrent**元素，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="29f26-136">To disable background garbage collection, use the **gcConcurrent** element, as discussed in this article.</span></span>

<span data-ttu-id="29f26-137">默认情况下，运行时使用并发或后台垃圾回收，回收针对延迟进行了优化。</span><span class="sxs-lookup"><span data-stu-id="29f26-137">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="29f26-138">如果应用程序涉及大量用户交互，则通过让并发垃圾回收保持启用状态，可最大限度缩短应用程序执行垃圾回收时的暂停时间。</span><span class="sxs-lookup"><span data-stu-id="29f26-138">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="29f26-139">如果将`enabled`**gcConcurrent**元素的属性设置为`false`，运行时将使用非并发垃圾回收，该回收针对吞吐量进行了优化。</span><span class="sxs-lookup"><span data-stu-id="29f26-139">If you set the `enabled` attribute of the **gcConcurrent** element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span>

<span data-ttu-id="29f26-140">以下配置文件禁用后台垃圾回收：</span><span class="sxs-lookup"><span data-stu-id="29f26-140">The following configuration file disables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

<span data-ttu-id="29f26-141">如果计算机配置文件中有**gcConcurrent设置，** 它将为所有 .NET Framework 应用程序定义默认值。</span><span class="sxs-lookup"><span data-stu-id="29f26-141">If there's a **gcConcurrentSetting** setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="29f26-142">计算机配置文件设置将重写应用程序配置文件设置。</span><span class="sxs-lookup"><span data-stu-id="29f26-142">The machine configuration file setting overrides the application configuration file setting.</span></span>

<span data-ttu-id="29f26-143">有关并发和后台垃圾回收的详细信息，请参阅[后台垃圾回收](../../../../standard/garbage-collection/background-gc.md)。</span><span class="sxs-lookup"><span data-stu-id="29f26-143">For more information on concurrent and background garbage collection, see [Background garbage collection](../../../../standard/garbage-collection/background-gc.md).</span></span>

## <a name="example"></a><span data-ttu-id="29f26-144">示例</span><span class="sxs-lookup"><span data-stu-id="29f26-144">Example</span></span>

<span data-ttu-id="29f26-145">以下示例支持后台垃圾回收：</span><span class="sxs-lookup"><span data-stu-id="29f26-145">The following example enables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="29f26-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29f26-146">See also</span></span>

- [<span data-ttu-id="29f26-147">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="29f26-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="29f26-148">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="29f26-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="29f26-149">垃圾回收的基础</span><span class="sxs-lookup"><span data-stu-id="29f26-149">Fundamentals of Garbage Collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
