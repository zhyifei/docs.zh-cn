---
title: "&lt;筛选器&gt;元素&lt;添加&gt;为&lt;侦听器&gt;为&lt;跟踪&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: efd31d03960fa516886586c4cf0a3e080d904977
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="f6d07-102">&lt;筛选器&gt;元素&lt;添加&gt;为&lt;侦听器&gt;为&lt;跟踪&gt;</span><span class="sxs-lookup"><span data-stu-id="f6d07-102">&lt;filter&gt; Element for &lt;add&gt; for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="f6d07-103">将筛选器添加到中的侦听器`Listeners`跟踪的集合。</span><span class="sxs-lookup"><span data-stu-id="f6d07-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  
  
 <span data-ttu-id="f6d07-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f6d07-104">\<configuration></span></span>  
<span data-ttu-id="f6d07-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="f6d07-105">\<system.diagnostics></span></span>  
<span data-ttu-id="f6d07-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="f6d07-106">\<trace></span></span>  
<span data-ttu-id="f6d07-107">\<侦听器 ></span><span class="sxs-lookup"><span data-stu-id="f6d07-107">\<listeners></span></span>  
<span data-ttu-id="f6d07-108">\<add></span><span class="sxs-lookup"><span data-stu-id="f6d07-108">\<add></span></span>  
<span data-ttu-id="f6d07-109">\<筛选器 ></span><span class="sxs-lookup"><span data-stu-id="f6d07-109">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6d07-110">语法</span><span class="sxs-lookup"><span data-stu-id="f6d07-110">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6d07-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f6d07-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f6d07-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f6d07-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6d07-113">特性</span><span class="sxs-lookup"><span data-stu-id="f6d07-113">Attributes</span></span>  
  
|<span data-ttu-id="f6d07-114">特性</span><span class="sxs-lookup"><span data-stu-id="f6d07-114">Attribute</span></span>|<span data-ttu-id="f6d07-115">描述</span><span class="sxs-lookup"><span data-stu-id="f6d07-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="f6d07-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="f6d07-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="f6d07-117">指定的类型的筛选器，它们应继承自<xref:System.Diagnostics.TraceFilter>类。</span><span class="sxs-lookup"><span data-stu-id="f6d07-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="f6d07-118">你可以使用命名空间限定的名称的类型，它对应于该类型的<xref:System.Type.FullName%2A>属性，也可以使用的完全限定的类型名称，包括程序集信息，它对应于<xref:System.Type.AssemblyQualifiedName%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="f6d07-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="f6d07-119">有关完全限定的类型名称的信息，请参阅[指定完全限定的类型名称](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)。</span><span class="sxs-lookup"><span data-stu-id="f6d07-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="f6d07-120">可选特性。</span><span class="sxs-lookup"><span data-stu-id="f6d07-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f6d07-121">传递给构造函数指定的筛选器类的字符串。</span><span class="sxs-lookup"><span data-stu-id="f6d07-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f6d07-122">子元素</span><span class="sxs-lookup"><span data-stu-id="f6d07-122">Child Elements</span></span>  
 <span data-ttu-id="f6d07-123">无。</span><span class="sxs-lookup"><span data-stu-id="f6d07-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f6d07-124">父元素</span><span class="sxs-lookup"><span data-stu-id="f6d07-124">Parent Elements</span></span>  
  
|<span data-ttu-id="f6d07-125">元素</span><span class="sxs-lookup"><span data-stu-id="f6d07-125">Element</span></span>|<span data-ttu-id="f6d07-126">说明</span><span class="sxs-lookup"><span data-stu-id="f6d07-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f6d07-127">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="f6d07-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="f6d07-128">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="f6d07-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="f6d07-129">包含用于收集、存储和路由跟踪消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="f6d07-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="f6d07-130">包含收集、 存储和将消息路由的侦听器。</span><span class="sxs-lookup"><span data-stu-id="f6d07-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="f6d07-131">侦听器将跟踪输出定向到适当的目标。</span><span class="sxs-lookup"><span data-stu-id="f6d07-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="f6d07-132">将侦听器添加到 `Listeners` 集合中。</span><span class="sxs-lookup"><span data-stu-id="f6d07-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6d07-133">备注</span><span class="sxs-lookup"><span data-stu-id="f6d07-133">Remarks</span></span>  
 <span data-ttu-id="f6d07-134">`<filter>`元素必须包含在`<add>`中定义的跟踪侦听器的指定侦听器的类型的元素，而不仅仅是侦听器的名称[ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)。</span><span class="sxs-lookup"><span data-stu-id="f6d07-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span></span> <span data-ttu-id="f6d07-135">如果在中定义侦听器[ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)，必须在该元素中定义该侦听器的筛选器。</span><span class="sxs-lookup"><span data-stu-id="f6d07-135">If the listener is defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="f6d07-136">计算机配置文件 (Machine.config) 和应用程序配置文件中，可以使用此元素。</span><span class="sxs-lookup"><span data-stu-id="f6d07-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6d07-137">示例</span><span class="sxs-lookup"><span data-stu-id="f6d07-137">Example</span></span>  
 <span data-ttu-id="f6d07-138">下面的示例演示如何使用`<filter>`元素添加到侦听器的筛选器`console`中`Listeners`跟踪，并作为筛选器事件级别指定的集合`Error`。</span><span class="sxs-lookup"><span data-stu-id="f6d07-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
        <remove name="Default" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f6d07-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6d07-139">See Also</span></span>  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>  
 <xref:System.Diagnostics.TraceFilter>  
 [<span data-ttu-id="f6d07-140">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="f6d07-140">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
