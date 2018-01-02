---
title: "&lt;侦听器&gt;元素&lt;跟踪&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
caps.latest.revision: "17"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: b9c1f52f880a38791a9a8d5b5372b2ad53c5569f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltlistenersgt-element-for-lttracegt"></a><span data-ttu-id="c8713-102">&lt;侦听器&gt;元素&lt;跟踪&gt;</span><span class="sxs-lookup"><span data-stu-id="c8713-102">&lt;listeners&gt; Element for &lt;trace&gt;</span></span>
<span data-ttu-id="c8713-103">指定收集，侦听器存储区，并将消息路由。</span><span class="sxs-lookup"><span data-stu-id="c8713-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="c8713-104">侦听器将跟踪输出定向到适当的目标。</span><span class="sxs-lookup"><span data-stu-id="c8713-104">Listeners direct the tracing output to an appropriate target.</span></span>  
  
 <span data-ttu-id="c8713-105">\<配置 > 元素</span><span class="sxs-lookup"><span data-stu-id="c8713-105">\<configuration> Element</span></span>  
<span data-ttu-id="c8713-106">\<system.diagnostics > 元素</span><span class="sxs-lookup"><span data-stu-id="c8713-106">\<system.diagnostics> Element</span></span>  
<span data-ttu-id="c8713-107">\<跟踪 > 元素</span><span class="sxs-lookup"><span data-stu-id="c8713-107">\<trace> Element</span></span>  
<span data-ttu-id="c8713-108">\<侦听器 > 元素\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="c8713-108">\<listeners> Element for \<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8713-109">语法</span><span class="sxs-lookup"><span data-stu-id="c8713-109">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8713-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c8713-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c8713-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c8713-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8713-112">特性</span><span class="sxs-lookup"><span data-stu-id="c8713-112">Attributes</span></span>  
 <span data-ttu-id="c8713-113">无。</span><span class="sxs-lookup"><span data-stu-id="c8713-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c8713-114">子元素</span><span class="sxs-lookup"><span data-stu-id="c8713-114">Child Elements</span></span>  
  
|<span data-ttu-id="c8713-115">元素</span><span class="sxs-lookup"><span data-stu-id="c8713-115">Element</span></span>|<span data-ttu-id="c8713-116">描述</span><span class="sxs-lookup"><span data-stu-id="c8713-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8713-117">\<add></span><span class="sxs-lookup"><span data-stu-id="c8713-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|<span data-ttu-id="c8713-118">将侦听器添加到 `Listeners` 集合中。</span><span class="sxs-lookup"><span data-stu-id="c8713-118">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="c8713-119">\<clear></span><span class="sxs-lookup"><span data-stu-id="c8713-119">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-trace.md)|<span data-ttu-id="c8713-120">清除跟踪的 `Listeners` 集合。</span><span class="sxs-lookup"><span data-stu-id="c8713-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="c8713-121">\<remove></span><span class="sxs-lookup"><span data-stu-id="c8713-121">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)|<span data-ttu-id="c8713-122">删除从侦听器`Listeners`集合。</span><span class="sxs-lookup"><span data-stu-id="c8713-122">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c8713-123">父元素</span><span class="sxs-lookup"><span data-stu-id="c8713-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c8713-124">元素</span><span class="sxs-lookup"><span data-stu-id="c8713-124">Element</span></span>|<span data-ttu-id="c8713-125">说明</span><span class="sxs-lookup"><span data-stu-id="c8713-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c8713-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="c8713-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="c8713-127">为 ASP.NET 配置节指定根元素。</span><span class="sxs-lookup"><span data-stu-id="c8713-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="c8713-128">包含用于收集、存储和路由跟踪消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="c8713-128">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8713-129">备注</span><span class="sxs-lookup"><span data-stu-id="c8713-129">Remarks</span></span>  
 <span data-ttu-id="c8713-130"><xref:System.Diagnostics.Debug>和<xref:System.Diagnostics.Trace>类共用同一个**侦听器**集合。</span><span class="sxs-lookup"><span data-stu-id="c8713-130">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="c8713-131">如果你将侦听器对象添加到这些类之一中的集合，其他类将使用相同的侦听器。</span><span class="sxs-lookup"><span data-stu-id="c8713-131">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="c8713-132">随.NET Framework 提供的侦听器类派生自<xref:System.Diagnostics.TraceListener>类。</span><span class="sxs-lookup"><span data-stu-id="c8713-132">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="c8713-133">配置文件</span><span class="sxs-lookup"><span data-stu-id="c8713-133">Configuration File</span></span>  
 <span data-ttu-id="c8713-134">计算机配置文件 (Machine.config) 和应用程序配置文件中，可以使用此元素。</span><span class="sxs-lookup"><span data-stu-id="c8713-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8713-135">示例</span><span class="sxs-lookup"><span data-stu-id="c8713-135">Example</span></span>  
 <span data-ttu-id="c8713-136">下面的示例演示如何使用**\<侦听器 >**元素将侦听器`MyListener`和`MyEventListener`到**侦听器**集合。</span><span class="sxs-lookup"><span data-stu-id="c8713-136">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="c8713-137">`MyListener`创建名为的文件`MyListener.log`并将输出写入文件。</span><span class="sxs-lookup"><span data-stu-id="c8713-137">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="c8713-138">`MyEventListener`事件日志中创建的项。</span><span class="sxs-lookup"><span data-stu-id="c8713-138">`MyEventListener` creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="true" indentsize="0">  
      <listeners>  
        <add name="myListener"   
          type="System.Diagnostics.TextWriterTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"   
          initializeData="c:\myListener.log" />  
        <add name="MyEventListener"  
          type="System.Diagnostics.EventLogTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"  
          initializeData="MyConfigEventLog"/>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8713-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8713-139">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="c8713-140">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="c8713-140">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
