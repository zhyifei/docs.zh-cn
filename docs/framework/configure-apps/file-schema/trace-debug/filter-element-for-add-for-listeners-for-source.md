---
title: "&lt;筛选器&gt;元素&lt;添加&gt;为&lt;侦听器&gt;为&lt;源&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 3b02f97caeef2a560682e5746c6c24986d5a3ad2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltlistenersgt-for-ltsourcegt"></a><span data-ttu-id="4b5b7-102">&lt;筛选器&gt;元素&lt;添加&gt;为&lt;侦听器&gt;为&lt;源&gt;</span><span class="sxs-lookup"><span data-stu-id="4b5b7-102">&lt;filter&gt; Element for &lt;add&gt; for &lt;listeners&gt; for &lt;source&gt;</span></span>
<span data-ttu-id="4b5b7-103">将筛选器添加到跟踪源的 `Listeners` 集合中的侦听器。</span><span class="sxs-lookup"><span data-stu-id="4b5b7-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="4b5b7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4b5b7-104">\<configuration></span></span>  
<span data-ttu-id="4b5b7-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="4b5b7-105">\<system.diagnostics></span></span>  
<span data-ttu-id="4b5b7-106">\<源 ></span><span class="sxs-lookup"><span data-stu-id="4b5b7-106">\<sources></span></span>  
<span data-ttu-id="4b5b7-107">\<源 ></span><span class="sxs-lookup"><span data-stu-id="4b5b7-107">\<source></span></span>  
<span data-ttu-id="4b5b7-108">\<侦听器 ></span><span class="sxs-lookup"><span data-stu-id="4b5b7-108">\<listeners></span></span>  
<span data-ttu-id="4b5b7-109">\<add></span><span class="sxs-lookup"><span data-stu-id="4b5b7-109">\<add></span></span>  
<span data-ttu-id="4b5b7-110">\<筛选器 ></span><span class="sxs-lookup"><span data-stu-id="4b5b7-110">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b5b7-111">语法</span><span class="sxs-lookup"><span data-stu-id="4b5b7-111">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b5b7-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4b5b7-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4b5b7-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4b5b7-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b5b7-114">特性</span><span class="sxs-lookup"><span data-stu-id="4b5b7-114">Attributes</span></span>  
  
|<span data-ttu-id="4b5b7-115">特性</span><span class="sxs-lookup"><span data-stu-id="4b5b7-115">Attribute</span></span>|<span data-ttu-id="4b5b7-116">描述</span><span class="sxs-lookup"><span data-stu-id="4b5b7-116">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="4b5b7-117">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="4b5b7-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="4b5b7-118">指定的类型的筛选器，它们应继承自<xref:System.Diagnostics.TraceFilter>类。</span><span class="sxs-lookup"><span data-stu-id="4b5b7-118">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="4b5b7-119">你可以使用命名空间限定的名称的类型，它对应于该类型的<xref:System.Type.FullName%2A>属性，也可以使用的完全限定的类型名称，包括程序集信息，它对应于<xref:System.Type.AssemblyQualifiedName%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="4b5b7-119">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="4b5b7-120">有关完全限定的类型名称的信息，请参阅[指定完全限定的类型名称](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)。</span><span class="sxs-lookup"><span data-stu-id="4b5b7-120">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="4b5b7-121">可选特性。</span><span class="sxs-lookup"><span data-stu-id="4b5b7-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4b5b7-122">传递给构造函数指定的筛选器类的字符串。</span><span class="sxs-lookup"><span data-stu-id="4b5b7-122">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4b5b7-123">子元素</span><span class="sxs-lookup"><span data-stu-id="4b5b7-123">Child Elements</span></span>  
 <span data-ttu-id="4b5b7-124">无。</span><span class="sxs-lookup"><span data-stu-id="4b5b7-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4b5b7-125">父元素</span><span class="sxs-lookup"><span data-stu-id="4b5b7-125">Parent Elements</span></span>  
  
|<span data-ttu-id="4b5b7-126">元素</span><span class="sxs-lookup"><span data-stu-id="4b5b7-126">Element</span></span>|<span data-ttu-id="4b5b7-127">描述</span><span class="sxs-lookup"><span data-stu-id="4b5b7-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4b5b7-128">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="4b5b7-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="4b5b7-129">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="4b5b7-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="4b5b7-130">包含用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="4b5b7-130">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="4b5b7-131">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="4b5b7-131">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="4b5b7-132">包含收集、 存储和将消息路由的侦听器。</span><span class="sxs-lookup"><span data-stu-id="4b5b7-132">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="4b5b7-133">侦听器将跟踪输出定向到适当的目标。</span><span class="sxs-lookup"><span data-stu-id="4b5b7-133">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="4b5b7-134">将侦听器添加到跟踪源的 `Listeners` 集合中。</span><span class="sxs-lookup"><span data-stu-id="4b5b7-134">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b5b7-135">备注</span><span class="sxs-lookup"><span data-stu-id="4b5b7-135">Remarks</span></span>  
 <span data-ttu-id="4b5b7-136">`<filter>`元素必须包含在`<add>`中定义的跟踪源侦听器的指定侦听器的类型的元素，而不仅仅是侦听器的名称[ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)。</span><span class="sxs-lookup"><span data-stu-id="4b5b7-136">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span></span> <span data-ttu-id="4b5b7-137">如果在中定义侦听器[ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)，必须在该元素中定义该侦听器的筛选器。</span><span class="sxs-lookup"><span data-stu-id="4b5b7-137">If the listener is defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="4b5b7-138">计算机配置文件 (Machine.config) 和应用程序配置文件中，可以使用此元素。</span><span class="sxs-lookup"><span data-stu-id="4b5b7-138">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b5b7-139">示例</span><span class="sxs-lookup"><span data-stu-id="4b5b7-139">Example</span></span>  
 <span data-ttu-id="4b5b7-140">下面的示例演示如何使用`<filter>`元素添加到侦听器的筛选器`console`中`Listeners`跟踪源集合`myTraceSource`，指定为筛选事件级别`Error`。</span><span class="sxs-lookup"><span data-stu-id="4b5b7-140">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" switchName="SourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="SourceSwitch" value="Warning" />  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4b5b7-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b5b7-141">See Also</span></span>  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>  
 <xref:System.Diagnostics.TraceFilter>  
 [<span data-ttu-id="4b5b7-142">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="4b5b7-142">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
