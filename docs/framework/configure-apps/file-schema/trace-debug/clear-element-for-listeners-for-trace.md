---
title: "&lt;清除&gt;元素&lt;侦听器&gt;为&lt;跟踪&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: b2739cc5eaa6a1e43c06849e1b00f7ac8bd531e7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltcleargt-element-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="e498f-102">&lt;清除&gt;元素&lt;侦听器&gt;为&lt;跟踪&gt;</span><span class="sxs-lookup"><span data-stu-id="e498f-102">&lt;clear&gt; Element for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="e498f-103">清除跟踪的 `Listeners` 集合。</span><span class="sxs-lookup"><span data-stu-id="e498f-103">Clears the `Listeners` collection for trace.</span></span>  
  
 <span data-ttu-id="e498f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e498f-104">\<configuration></span></span>  
<span data-ttu-id="e498f-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="e498f-105">\<system.diagnostics></span></span>  
<span data-ttu-id="e498f-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="e498f-106">\<trace></span></span>  
<span data-ttu-id="e498f-107">\<侦听器 ></span><span class="sxs-lookup"><span data-stu-id="e498f-107">\<listeners></span></span>  
<span data-ttu-id="e498f-108">\<清除 ></span><span class="sxs-lookup"><span data-stu-id="e498f-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e498f-109">语法</span><span class="sxs-lookup"><span data-stu-id="e498f-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e498f-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e498f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e498f-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e498f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e498f-112">特性</span><span class="sxs-lookup"><span data-stu-id="e498f-112">Attributes</span></span>  
 <span data-ttu-id="e498f-113">无。</span><span class="sxs-lookup"><span data-stu-id="e498f-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e498f-114">子元素</span><span class="sxs-lookup"><span data-stu-id="e498f-114">Child Elements</span></span>  
 <span data-ttu-id="e498f-115">无。</span><span class="sxs-lookup"><span data-stu-id="e498f-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e498f-116">父元素</span><span class="sxs-lookup"><span data-stu-id="e498f-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e498f-117">元素</span><span class="sxs-lookup"><span data-stu-id="e498f-117">Element</span></span>|<span data-ttu-id="e498f-118">说明</span><span class="sxs-lookup"><span data-stu-id="e498f-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e498f-119">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="e498f-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="e498f-120">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="e498f-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="e498f-121">包含用于收集、存储和路由跟踪消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="e498f-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="e498f-122">包含收集、 存储和将消息路由的侦听器。</span><span class="sxs-lookup"><span data-stu-id="e498f-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="e498f-123">侦听器将跟踪输出定向到适当的目标。</span><span class="sxs-lookup"><span data-stu-id="e498f-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e498f-124">备注</span><span class="sxs-lookup"><span data-stu-id="e498f-124">Remarks</span></span>  
 <span data-ttu-id="e498f-125">`<clear>`元素中移除所有侦听器从`Listeners`跟踪的集合。</span><span class="sxs-lookup"><span data-stu-id="e498f-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="e498f-126">你可以使用`<clear>`元素之前使用`<add>`被某些有没有其他活动的侦听器集合中的元素。</span><span class="sxs-lookup"><span data-stu-id="e498f-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="e498f-127">您可以清除`Listeners`集合以编程方式通过调用<xref:System.Diagnostics.TraceListenerCollection.Clear%2A>方法<xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType>属性 (`System.Diagnostics.Trace.Listeners.Clear()`)。</span><span class="sxs-lookup"><span data-stu-id="e498f-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="e498f-128">计算机配置文件 (Machine.config) 和应用程序配置文件中，可以使用此元素。</span><span class="sxs-lookup"><span data-stu-id="e498f-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e498f-129">`<clear>`元素中删除<xref:System.Diagnostics.DefaultTraceListener>从`Listeners`集合，行为<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>， <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>， <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>，和<xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="e498f-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="e498f-130">调用`Assert`或`Fail`方法通常会导致显示一个消息框。</span><span class="sxs-lookup"><span data-stu-id="e498f-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="e498f-131">但是，消息框如果不显示<xref:System.Diagnostics.DefaultTraceListener>不在`Listeners`集合。</span><span class="sxs-lookup"><span data-stu-id="e498f-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e498f-132">示例</span><span class="sxs-lookup"><span data-stu-id="e498f-132">Example</span></span>  
 <span data-ttu-id="e498f-133">下面的示例演示如何使用`<clear>`元素之前使用`<add>`元素添加侦听器`console`到`Listeners`跟踪的集合。</span><span class="sxs-lookup"><span data-stu-id="e498f-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="e498f-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="e498f-134">See Also</span></span>  
 <xref:System.Diagnostics.Trace.Listeners%2A>  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 <xref:System.Diagnostics.TraceSource>  
 [<span data-ttu-id="e498f-135">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="e498f-135">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="e498f-136">\<remove></span><span class="sxs-lookup"><span data-stu-id="e498f-136">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)  
 [<span data-ttu-id="e498f-137">跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="e498f-137">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
