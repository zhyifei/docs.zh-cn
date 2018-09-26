---
title: '&lt;system.diagnostics&gt;元素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 35fe167beb53c27aa511e08507415a26b1749ca2
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47193221"
---
# <a name="ltsystemdiagnosticsgt-element"></a><span data-ttu-id="87e7b-102">&lt;system.diagnostics&gt;元素</span><span class="sxs-lookup"><span data-stu-id="87e7b-102">&lt;system.diagnostics&gt; Element</span></span>
<span data-ttu-id="87e7b-103">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="87e7b-103">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="87e7b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="87e7b-104">\<configuration></span></span>  
<span data-ttu-id="87e7b-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="87e7b-105">\<system.diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87e7b-106">语法</span><span class="sxs-lookup"><span data-stu-id="87e7b-106">Syntax</span></span>  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87e7b-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="87e7b-107">Attributes and Elements</span></span>  
 <span data-ttu-id="87e7b-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="87e7b-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87e7b-109">特性</span><span class="sxs-lookup"><span data-stu-id="87e7b-109">Attributes</span></span>  
 <span data-ttu-id="87e7b-110">无。</span><span class="sxs-lookup"><span data-stu-id="87e7b-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="87e7b-111">子元素</span><span class="sxs-lookup"><span data-stu-id="87e7b-111">Child Elements</span></span>  
  
|<span data-ttu-id="87e7b-112">元素</span><span class="sxs-lookup"><span data-stu-id="87e7b-112">Element</span></span>|<span data-ttu-id="87e7b-113">描述</span><span class="sxs-lookup"><span data-stu-id="87e7b-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87e7b-114">\<assert></span><span class="sxs-lookup"><span data-stu-id="87e7b-114">\<assert></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|<span data-ttu-id="87e7b-115">指定调用 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> 方法时是否显示消息框；另外指定要写入消息的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="87e7b-115">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[<span data-ttu-id="87e7b-116">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="87e7b-116">\<performanceCounters></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|<span data-ttu-id="87e7b-117">指定由性能计数器共享的全局内存的大小。</span><span class="sxs-lookup"><span data-stu-id="87e7b-117">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[<span data-ttu-id="87e7b-118">\<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="87e7b-118">\<sharedListeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|<span data-ttu-id="87e7b-119">包含任何源或跟踪元素可以引用的侦听器。</span><span class="sxs-lookup"><span data-stu-id="87e7b-119">Contains listeners that any source or trace element can reference.</span></span> <span data-ttu-id="87e7b-120">标识为共享的侦听器可以按名称添加到源或跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="87e7b-120">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>|  
|[<span data-ttu-id="87e7b-121">\<sources></span><span class="sxs-lookup"><span data-stu-id="87e7b-121">\<sources></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|<span data-ttu-id="87e7b-122">指定启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="87e7b-122">Specifies trace sources that initiate tracing messages.</span></span>|  
|[<span data-ttu-id="87e7b-123">\<switches></span><span class="sxs-lookup"><span data-stu-id="87e7b-123">\<switches></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|<span data-ttu-id="87e7b-124">包含跟踪开关和跟踪开关设置其中的级别。</span><span class="sxs-lookup"><span data-stu-id="87e7b-124">Contains trace switches and the levels where the trace switches are set.</span></span>|  
|[<span data-ttu-id="87e7b-125">\<trace></span><span class="sxs-lookup"><span data-stu-id="87e7b-125">\<trace></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|<span data-ttu-id="87e7b-126">包含用于收集、存储和路由跟踪消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="87e7b-126">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="87e7b-127">父元素</span><span class="sxs-lookup"><span data-stu-id="87e7b-127">Parent Elements</span></span>  
  
|<span data-ttu-id="87e7b-128">元素</span><span class="sxs-lookup"><span data-stu-id="87e7b-128">Element</span></span>|<span data-ttu-id="87e7b-129">描述</span><span class="sxs-lookup"><span data-stu-id="87e7b-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="87e7b-130">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="87e7b-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="87e7b-131">示例</span><span class="sxs-lookup"><span data-stu-id="87e7b-131">Example</span></span>  
 <span data-ttu-id="87e7b-132">下面的示例演示如何嵌入跟踪开关和跟踪侦听器 **\<system.diagnostics >** 元素。</span><span class="sxs-lookup"><span data-stu-id="87e7b-132">The following example shows how to embed a trace switch and a trace listener inside the **\<system.diagnostics>** element.</span></span> <span data-ttu-id="87e7b-133">`General`跟踪开关设置为<xref:System.Diagnostics.TraceLevel>级别。</span><span class="sxs-lookup"><span data-stu-id="87e7b-133">The `General` trace switch is set to the <xref:System.Diagnostics.TraceLevel> level.</span></span> <span data-ttu-id="87e7b-134">跟踪侦听器`myListener`创建一个名为文件`MyListener.log`并将输出写入到该文件。</span><span class="sxs-lookup"><span data-stu-id="87e7b-134">The trace listener `myListener` creates a file called `MyListener.log` and writes the output to the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87e7b-135">在 .NET Framework 2.0 版中，你可以使用文本指定开关值。</span><span class="sxs-lookup"><span data-stu-id="87e7b-135">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="87e7b-136">例如，可以指定`true`有关<xref:System.Diagnostics.BooleanSwitch>或使用表示一个枚举值，例如文本`Error`为<xref:System.Diagnostics.TraceSwitch>。</span><span class="sxs-lookup"><span data-stu-id="87e7b-136">For example, you can specify `true` for a <xref:System.Diagnostics.BooleanSwitch> or use the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="87e7b-137">行 `<add name="myTraceSwitch" value="Error" />` 等于 `<add name="myTraceSwitch" value="1" />`。</span><span class="sxs-lookup"><span data-stu-id="87e7b-137">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="87e7b-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="87e7b-138">See Also</span></span>  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 [<span data-ttu-id="87e7b-139">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="87e7b-139">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
