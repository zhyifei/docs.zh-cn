---
title: t 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
ms.openlocfilehash: 5957337aa960a0d5f445249b410dbfaddb7b08e9
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73969236"
---
# <a name="gcconcurrent-element"></a><span data-ttu-id="3e016-102">\<t > 元素</span><span class="sxs-lookup"><span data-stu-id="3e016-102">\<gcConcurrent> element</span></span>

<span data-ttu-id="3e016-103">指定公共语言运行时是否在单独线程上运行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="3e016-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>

<span data-ttu-id="3e016-104">[\<configuration>](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3e016-104">[\<configuration>](../configuration-element.md)</span></span>\
<span data-ttu-id="3e016-105">&nbsp;&nbsp;[\<运行时 >](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="3e016-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span></span>\
<span data-ttu-id="3e016-106">&nbsp;&nbsp;&nbsp;&nbsp;\<t ></span><span class="sxs-lookup"><span data-stu-id="3e016-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcConcurrent></span></span>

## <a name="syntax"></a><span data-ttu-id="3e016-107">语法</span><span class="sxs-lookup"><span data-stu-id="3e016-107">Syntax</span></span>

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3e016-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3e016-108">Attributes and elements</span></span>

<span data-ttu-id="3e016-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3e016-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="3e016-110">特性</span><span class="sxs-lookup"><span data-stu-id="3e016-110">Attributes</span></span>

|<span data-ttu-id="3e016-111">特性</span><span class="sxs-lookup"><span data-stu-id="3e016-111">Attribute</span></span>|<span data-ttu-id="3e016-112">描述</span><span class="sxs-lookup"><span data-stu-id="3e016-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="3e016-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="3e016-113">Required attribute.</span></span><br /><br /><span data-ttu-id="3e016-114">指定运行时是否并发运行服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="3e016-114">Specifies whether the runtime runs garbage collection concurrently.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="3e016-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="3e016-115">enabled attribute</span></span>

|<span data-ttu-id="3e016-116">“值”</span><span class="sxs-lookup"><span data-stu-id="3e016-116">Value</span></span>|<span data-ttu-id="3e016-117">描述</span><span class="sxs-lookup"><span data-stu-id="3e016-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="3e016-118">不并发运行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="3e016-118">Doesn't run garbage collection concurrently.</span></span>|
|`true`|<span data-ttu-id="3e016-119">并发运行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="3e016-119">Runs garbage collection concurrently.</span></span> <span data-ttu-id="3e016-120">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="3e016-120">This is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="3e016-121">子元素</span><span class="sxs-lookup"><span data-stu-id="3e016-121">Child elements</span></span>

<span data-ttu-id="3e016-122">无。</span><span class="sxs-lookup"><span data-stu-id="3e016-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3e016-123">父元素</span><span class="sxs-lookup"><span data-stu-id="3e016-123">Parent elements</span></span>

|<span data-ttu-id="3e016-124">元素</span><span class="sxs-lookup"><span data-stu-id="3e016-124">Element</span></span>|<span data-ttu-id="3e016-125">描述</span><span class="sxs-lookup"><span data-stu-id="3e016-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="3e016-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="3e016-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="3e016-127">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="3e016-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3e016-128">备注</span><span class="sxs-lookup"><span data-stu-id="3e016-128">Remarks</span></span>

<span data-ttu-id="3e016-129">在 .NET Framework 4 之前，工作站垃圾回收支持并发垃圾回收，这会在单独的线程上以后台执行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="3e016-129">Prior to .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="3e016-130">在 .NET Framework 4 中，并发垃圾回收已替换为后台 GC，此操作还在单独的线程上的后台执行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="3e016-130">In .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="3e016-131">从 .NET Framework 4.5 开始，后台收集在服务器垃圾回收中变为可用。</span><span class="sxs-lookup"><span data-stu-id="3e016-131">Starting with .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="3e016-132">**T**元素控制运行时是执行并发还是后台垃圾回收（如果可用），或者是否执行前台垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="3e016-132">The **gcConcurrent** element controls whether the runtime performs either concurrent or background garbage collection, if it's available, or whether it performs garbage collection in the foreground.</span></span>

### <a name="to-disable-background-garbage-collection"></a><span data-ttu-id="3e016-133">禁用后台垃圾回收</span><span class="sxs-lookup"><span data-stu-id="3e016-133">To disable background garbage collection</span></span>

> [!WARNING]
> <span data-ttu-id="3e016-134">从 .NET Framework 4 开始，将由后台垃圾回收取代了并发垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="3e016-134">Starting with .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="3e016-135">在 .NET Framework 文档中，术语 "*并发*" 和 "*背景*" 可互换使用。</span><span class="sxs-lookup"><span data-stu-id="3e016-135">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="3e016-136">若要禁用后台垃圾回收，请使用**t**元素，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="3e016-136">To disable background garbage collection, use the **gcConcurrent** element, as discussed in this article.</span></span>

<span data-ttu-id="3e016-137">默认情况下，运行时使用并发或后台垃圾回收，回收针对延迟进行了优化。</span><span class="sxs-lookup"><span data-stu-id="3e016-137">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="3e016-138">如果应用程序涉及大量用户交互，则通过让并发垃圾回收保持启用状态，可最大限度缩短应用程序执行垃圾回收时的暂停时间。</span><span class="sxs-lookup"><span data-stu-id="3e016-138">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="3e016-139">如果将**t**元素的 `enabled` 属性设置为 `false`，则运行时将使用非并发垃圾回收，这是针对吞吐量进行优化的。</span><span class="sxs-lookup"><span data-stu-id="3e016-139">If you set the `enabled` attribute of the **gcConcurrent** element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span>

<span data-ttu-id="3e016-140">以下配置文件禁用后台垃圾回收：</span><span class="sxs-lookup"><span data-stu-id="3e016-140">The following configuration file disables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

<span data-ttu-id="3e016-141">如果计算机配置文件中存在**gcConcurrentSetting**设置，则它将为所有 .NET Framework 应用程序定义默认值。</span><span class="sxs-lookup"><span data-stu-id="3e016-141">If there's a **gcConcurrentSetting** setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="3e016-142">计算机配置文件设置将重写应用程序配置文件设置。</span><span class="sxs-lookup"><span data-stu-id="3e016-142">The machine configuration file setting overrides the application configuration file setting.</span></span>

<span data-ttu-id="3e016-143">有关并发和后台垃圾回收的详细信息，请参阅[垃圾回收基础知识一](../../../../standard/garbage-collection/fundamentals.md)文中的[并发垃圾](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection)回收、[后台工作站垃圾](../../../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection)回收和[后台服务器垃圾](../../../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection)回收部分。</span><span class="sxs-lookup"><span data-stu-id="3e016-143">For more information on concurrent and background garbage collection, see the [Concurrent garbage collection](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection), [Background workstation garbage collection](../../../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection), and [Background server garbage collection](../../../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection) sections in the [Fundamentals of Garbage Collection](../../../../standard/garbage-collection/fundamentals.md) article.</span></span>

## <a name="example"></a><span data-ttu-id="3e016-144">示例</span><span class="sxs-lookup"><span data-stu-id="3e016-144">Example</span></span>

<span data-ttu-id="3e016-145">下面的示例启用后台垃圾回收：</span><span class="sxs-lookup"><span data-stu-id="3e016-145">The following example enables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="3e016-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e016-146">See also</span></span>

- [<span data-ttu-id="3e016-147">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="3e016-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3e016-148">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="3e016-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="3e016-149">垃圾回收的基础知识</span><span class="sxs-lookup"><span data-stu-id="3e016-149">Fundamentals of Garbage Collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
