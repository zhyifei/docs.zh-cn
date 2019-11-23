---
title: < > 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: dc05c46cb1ba74baceaaeadc2959a6889faf19c9
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699199"
---
# <a name="systemdiagnostics-element"></a><span data-ttu-id="dc728-102">\<> 元素</span><span class="sxs-lookup"><span data-stu-id="dc728-102">\<system.diagnostics> Element</span></span>
<span data-ttu-id="dc728-103">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="dc728-103">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>  
  
[<span data-ttu-id="dc728-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="dc728-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="dc728-105">&nbsp;&nbsp; **\<的 >**</span><span class="sxs-lookup"><span data-stu-id="dc728-105">&nbsp;&nbsp;**\<system.diagnostics>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc728-106">语法</span><span class="sxs-lookup"><span data-stu-id="dc728-106">Syntax</span></span>  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc728-107">属性和元素</span><span class="sxs-lookup"><span data-stu-id="dc728-107">Attributes and Elements</span></span>  
 <span data-ttu-id="dc728-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="dc728-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc728-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="dc728-109">Attributes</span></span>  
 <span data-ttu-id="dc728-110">无。</span><span class="sxs-lookup"><span data-stu-id="dc728-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dc728-111">子元素</span><span class="sxs-lookup"><span data-stu-id="dc728-111">Child Elements</span></span>  
  
|<span data-ttu-id="dc728-112">元素</span><span class="sxs-lookup"><span data-stu-id="dc728-112">Element</span></span>|<span data-ttu-id="dc728-113">说明</span><span class="sxs-lookup"><span data-stu-id="dc728-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc728-114">\<assert></span><span class="sxs-lookup"><span data-stu-id="dc728-114">\<assert></span></span>](assert-element.md)|<span data-ttu-id="dc728-115">指定调用 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> 方法时是否显示消息框；另外指定要写入消息的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="dc728-115">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[<span data-ttu-id="dc728-116">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="dc728-116">\<performanceCounters></span></span>](performancecounters-element.md)|<span data-ttu-id="dc728-117">指定由性能计数器共享的全局内存的大小。</span><span class="sxs-lookup"><span data-stu-id="dc728-117">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[<span data-ttu-id="dc728-118">\<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="dc728-118">\<sharedListeners></span></span>](sharedlisteners-element.md)|<span data-ttu-id="dc728-119">包含任何源或跟踪元素可以引用的侦听器。</span><span class="sxs-lookup"><span data-stu-id="dc728-119">Contains listeners that any source or trace element can reference.</span></span> <span data-ttu-id="dc728-120">可以按名称将标识为共享侦听器的侦听器添加到源或跟踪。</span><span class="sxs-lookup"><span data-stu-id="dc728-120">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>|  
|[<span data-ttu-id="dc728-121">\<sources></span><span class="sxs-lookup"><span data-stu-id="dc728-121">\<sources></span></span>](sources-element.md)|<span data-ttu-id="dc728-122">指定启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="dc728-122">Specifies trace sources that initiate tracing messages.</span></span>|  
|[<span data-ttu-id="dc728-123">\<switches></span><span class="sxs-lookup"><span data-stu-id="dc728-123">\<switches></span></span>](switches-element.md)|<span data-ttu-id="dc728-124">包含跟踪开关和设置跟踪开关的级别。</span><span class="sxs-lookup"><span data-stu-id="dc728-124">Contains trace switches and the levels where the trace switches are set.</span></span>|  
|[<span data-ttu-id="dc728-125">\<trace></span><span class="sxs-lookup"><span data-stu-id="dc728-125">\<trace></span></span>](trace-element.md)|<span data-ttu-id="dc728-126">包含用于收集、存储和路由跟踪消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="dc728-126">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dc728-127">父元素</span><span class="sxs-lookup"><span data-stu-id="dc728-127">Parent Elements</span></span>  
  
|<span data-ttu-id="dc728-128">元素</span><span class="sxs-lookup"><span data-stu-id="dc728-128">Element</span></span>|<span data-ttu-id="dc728-129">说明</span><span class="sxs-lookup"><span data-stu-id="dc728-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="dc728-130">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="dc728-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dc728-131">示例</span><span class="sxs-lookup"><span data-stu-id="dc728-131">Example</span></span>  
 <span data-ttu-id="dc728-132">下面的示例演示如何在 **\<diagnostics >** 元素中嵌入跟踪开关和跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="dc728-132">The following example shows how to embed a trace switch and a trace listener inside the **\<system.diagnostics>** element.</span></span> <span data-ttu-id="dc728-133">`General` trace 开关设置为 <xref:System.Diagnostics.TraceLevel> 级别。</span><span class="sxs-lookup"><span data-stu-id="dc728-133">The `General` trace switch is set to the <xref:System.Diagnostics.TraceLevel> level.</span></span> <span data-ttu-id="dc728-134">跟踪侦听器 `myListener` 创建一个名为 `MyListener.log` 的文件，并将输出写入文件。</span><span class="sxs-lookup"><span data-stu-id="dc728-134">The trace listener `myListener` creates a file called `MyListener.log` and writes the output to the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dc728-135">在 .NET Framework 2.0 版中，你可以使用文本指定开关值。</span><span class="sxs-lookup"><span data-stu-id="dc728-135">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="dc728-136">例如，你可以为 <xref:System.Diagnostics.BooleanSwitch> 指定 `true` 或使用表示枚举值的文本，例如 <xref:System.Diagnostics.TraceSwitch>的 `Error`。</span><span class="sxs-lookup"><span data-stu-id="dc728-136">For example, you can specify `true` for a <xref:System.Diagnostics.BooleanSwitch> or use the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="dc728-137">行 `<add name="myTraceSwitch" value="Error" />` 等于 `<add name="myTraceSwitch" value="1" />`。</span><span class="sxs-lookup"><span data-stu-id="dc728-137">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dc728-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc728-138">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="dc728-139">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="dc728-139">Trace and Debug Settings Schema</span></span>](index.md)
