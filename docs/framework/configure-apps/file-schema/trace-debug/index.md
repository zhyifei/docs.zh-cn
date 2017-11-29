---
title: "跟踪和调试设置架构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tracing [.NET Framework], trace and debug settings schema
- configuration schema [.NET Framework], trace and debug settings
- configuration settings [.NET Framework], tracing
- schema configuration settings
- configuration settings [.NET Framework], debugging
- trace listeners, trace and debug settings schema
- configuration sections [.NET Framework]
- elements [.NET Framework], trace and debug settings
ms.assetid: 277ca5f6-e1c4-41b6-a47f-3a67ce5b94ac
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 97c96fbb1abf969d902159709ca0e738f475fab9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="trace-and-debug-settings-schema"></a><span data-ttu-id="33fcf-102">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="33fcf-102">Trace and Debug Settings Schema</span></span>
<span data-ttu-id="33fcf-103">跟踪和调试设置指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="33fcf-103">Trace and debug settings specify trace listeners that collect, store, and route messages, and the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="33fcf-104">下表介绍每个跟踪和调试设置元素的功能。</span><span class="sxs-lookup"><span data-stu-id="33fcf-104">The following table describes the function of each trace and debug settings element.</span></span>  
  
|<span data-ttu-id="33fcf-105">元素</span><span class="sxs-lookup"><span data-stu-id="33fcf-105">Element</span></span>|<span data-ttu-id="33fcf-106">说明</span><span class="sxs-lookup"><span data-stu-id="33fcf-106">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33fcf-107">\<add></span><span class="sxs-lookup"><span data-stu-id="33fcf-107">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-source.md)|<span data-ttu-id="33fcf-108">将侦听器添加到跟踪源的 `Listeners` 集合中。</span><span class="sxs-lookup"><span data-stu-id="33fcf-108">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
|[<span data-ttu-id="33fcf-109">\<add></span><span class="sxs-lookup"><span data-stu-id="33fcf-109">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|<span data-ttu-id="33fcf-110">将侦听器添加到 `Listeners` 集合中。</span><span class="sxs-lookup"><span data-stu-id="33fcf-110">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="33fcf-111">\<add></span><span class="sxs-lookup"><span data-stu-id="33fcf-111">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-sharedlisteners.md)|<span data-ttu-id="33fcf-112">将侦听器添加到 `sharedListeners` 集合中。</span><span class="sxs-lookup"><span data-stu-id="33fcf-112">Adds a listener to the `sharedListeners` collection.</span></span>|  
|[<span data-ttu-id="33fcf-113">\<add></span><span class="sxs-lookup"><span data-stu-id="33fcf-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|<span data-ttu-id="33fcf-114">指定对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="33fcf-114">Specifies the level where a trace switch is set.</span></span>|  
|[<span data-ttu-id="33fcf-115">\<assert></span><span class="sxs-lookup"><span data-stu-id="33fcf-115">\<assert></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|<span data-ttu-id="33fcf-116">指定调用 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> 方法时是否显示消息框；另外指定要写入消息的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="33fcf-116">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[<span data-ttu-id="33fcf-117">\<clear></span><span class="sxs-lookup"><span data-stu-id="33fcf-117">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)|<span data-ttu-id="33fcf-118">清除跟踪源的 `Listeners` 集合。</span><span class="sxs-lookup"><span data-stu-id="33fcf-118">Clears the `Listeners` collection for a trace source.</span></span>|  
|[<span data-ttu-id="33fcf-119">\<clear></span><span class="sxs-lookup"><span data-stu-id="33fcf-119">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-trace.md)|<span data-ttu-id="33fcf-120">清除跟踪的 `Listeners` 集合。</span><span class="sxs-lookup"><span data-stu-id="33fcf-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="33fcf-121">\<filter></span><span class="sxs-lookup"><span data-stu-id="33fcf-121">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="33fcf-122">将筛选器添加到跟踪源的 `Listeners` 集合中的侦听器。</span><span class="sxs-lookup"><span data-stu-id="33fcf-122">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
|[<span data-ttu-id="33fcf-123">\<filter></span><span class="sxs-lookup"><span data-stu-id="33fcf-123">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="33fcf-124">将筛选器添加到跟踪的 `Listeners` 集合中的侦听器。</span><span class="sxs-lookup"><span data-stu-id="33fcf-124">Adds a filter to a listener in the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="33fcf-125">\<filter></span><span class="sxs-lookup"><span data-stu-id="33fcf-125">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="33fcf-126">将筛选器添加到 `sharedListeners` 集合中的侦听器。</span><span class="sxs-lookup"><span data-stu-id="33fcf-126">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
|[<span data-ttu-id="33fcf-127">\<listeners></span><span class="sxs-lookup"><span data-stu-id="33fcf-127">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|<span data-ttu-id="33fcf-128">指定跟踪源的 `Listeners` 集合中的侦听器。</span><span class="sxs-lookup"><span data-stu-id="33fcf-128">Specifies listeners for the `Listeners` collection for a trace source.</span></span>|  
|[<span data-ttu-id="33fcf-129">\<listeners></span><span class="sxs-lookup"><span data-stu-id="33fcf-129">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|<span data-ttu-id="33fcf-130">指定跟踪的 `Listeners` 集合中的侦听器。</span><span class="sxs-lookup"><span data-stu-id="33fcf-130">Specifies listeners for the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="33fcf-131">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="33fcf-131">\<performanceCounters></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|<span data-ttu-id="33fcf-132">指定由性能计数器共享的全局内存的大小。</span><span class="sxs-lookup"><span data-stu-id="33fcf-132">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[<span data-ttu-id="33fcf-133">\<remove></span><span class="sxs-lookup"><span data-stu-id="33fcf-133">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)|<span data-ttu-id="33fcf-134">从跟踪的 `Listeners` 集合中删除侦听器。</span><span class="sxs-lookup"><span data-stu-id="33fcf-134">Removes a listener from the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="33fcf-135">\<remove></span><span class="sxs-lookup"><span data-stu-id="33fcf-135">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-source.md)|<span data-ttu-id="33fcf-136">从跟踪源的 `Listeners` 集合中删除侦听器。</span><span class="sxs-lookup"><span data-stu-id="33fcf-136">Removes a listener from the `Listeners` collection for a trace source.</span></span>|  
|[<span data-ttu-id="33fcf-137">\<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="33fcf-137">\<sharedListeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|<span data-ttu-id="33fcf-138">包含任何源或跟踪元素可以引用的侦听器。</span><span class="sxs-lookup"><span data-stu-id="33fcf-138">Contains listeners that any source or trace element can reference.</span></span>|  
|[<span data-ttu-id="33fcf-139">\<sources></span><span class="sxs-lookup"><span data-stu-id="33fcf-139">\<sources></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|<span data-ttu-id="33fcf-140">包含用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="33fcf-140">Contains trace sources that initiate tracing messages.</span></span>|  
|[<span data-ttu-id="33fcf-141">\<source></span><span class="sxs-lookup"><span data-stu-id="33fcf-141">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)|<span data-ttu-id="33fcf-142">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="33fcf-142">Specifies a trace source that initiates tracing messages.</span></span>|  
|[<span data-ttu-id="33fcf-143">\<switches></span><span class="sxs-lookup"><span data-stu-id="33fcf-143">\<switches></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|<span data-ttu-id="33fcf-144">包含跟踪开关和对该跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="33fcf-144">Contains trace switches and the level where the trace switches are set.</span></span>|  
|[<span data-ttu-id="33fcf-145">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="33fcf-145">\<system.diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/system-diagnostics-element.md)|<span data-ttu-id="33fcf-146">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="33fcf-146">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|[<span data-ttu-id="33fcf-147">\<trace></span><span class="sxs-lookup"><span data-stu-id="33fcf-147">\<trace></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|<span data-ttu-id="33fcf-148">包含用于收集、存储和路由跟踪消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="33fcf-148">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="33fcf-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33fcf-149">See Also</span></span>  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.Debug>  
 [<span data-ttu-id="33fcf-150">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="33fcf-150">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
