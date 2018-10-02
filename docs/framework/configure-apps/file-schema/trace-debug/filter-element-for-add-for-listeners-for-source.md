---
title: '&lt;筛选器&gt;的元素&lt;添加&gt;有关&lt;侦听器&gt;为&lt;源&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 19b28c3391a10cc522f17c5353c9ec0726b0a2f8
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2018
ms.locfileid: "48033423"
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltlistenersgt-for-ltsourcegt"></a><span data-ttu-id="848b4-102">&lt;筛选器&gt;的元素&lt;添加&gt;有关&lt;侦听器&gt;为&lt;源&gt;</span><span class="sxs-lookup"><span data-stu-id="848b4-102">&lt;filter&gt; Element for &lt;add&gt; for &lt;listeners&gt; for &lt;source&gt;</span></span>
<span data-ttu-id="848b4-103">将筛选器添加到跟踪源的 `Listeners` 集合中的侦听器。</span><span class="sxs-lookup"><span data-stu-id="848b4-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="848b4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="848b4-104">\<configuration></span></span>  
<span data-ttu-id="848b4-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="848b4-105">\<system.diagnostics></span></span>  
<span data-ttu-id="848b4-106">\<源 ></span><span class="sxs-lookup"><span data-stu-id="848b4-106">\<sources></span></span>  
<span data-ttu-id="848b4-107">\<源 ></span><span class="sxs-lookup"><span data-stu-id="848b4-107">\<source></span></span>  
<span data-ttu-id="848b4-108">\<侦听器 ></span><span class="sxs-lookup"><span data-stu-id="848b4-108">\<listeners></span></span>  
<span data-ttu-id="848b4-109">\<add></span><span class="sxs-lookup"><span data-stu-id="848b4-109">\<add></span></span>  
<span data-ttu-id="848b4-110">\<筛选器 ></span><span class="sxs-lookup"><span data-stu-id="848b4-110">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="848b4-111">语法</span><span class="sxs-lookup"><span data-stu-id="848b4-111">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="848b4-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="848b4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="848b4-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="848b4-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="848b4-114">特性</span><span class="sxs-lookup"><span data-stu-id="848b4-114">Attributes</span></span>  
  
|<span data-ttu-id="848b4-115">特性</span><span class="sxs-lookup"><span data-stu-id="848b4-115">Attribute</span></span>|<span data-ttu-id="848b4-116">描述</span><span class="sxs-lookup"><span data-stu-id="848b4-116">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="848b4-117">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="848b4-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="848b4-118">指定的筛选器，它应继承自类型<xref:System.Diagnostics.TraceFilter>类。</span><span class="sxs-lookup"><span data-stu-id="848b4-118">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="848b4-119">可以使用的类型相对应的类型的命名空间限定名称<xref:System.Type.FullName%2A>属性，也可以使用完全限定的类型名称包括程序集信息，它对应于<xref:System.Type.AssemblyQualifiedName%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="848b4-119">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="848b4-120">有关完全限定的类型名称的信息，请参阅[指定完全限定的类型名称](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)。</span><span class="sxs-lookup"><span data-stu-id="848b4-120">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="848b4-121">可选特性。</span><span class="sxs-lookup"><span data-stu-id="848b4-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="848b4-122">传递给构造函数指定的筛选器类的字符串。</span><span class="sxs-lookup"><span data-stu-id="848b4-122">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="848b4-123">子元素</span><span class="sxs-lookup"><span data-stu-id="848b4-123">Child Elements</span></span>  
 <span data-ttu-id="848b4-124">无。</span><span class="sxs-lookup"><span data-stu-id="848b4-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="848b4-125">父元素</span><span class="sxs-lookup"><span data-stu-id="848b4-125">Parent Elements</span></span>  
  
|<span data-ttu-id="848b4-126">元素</span><span class="sxs-lookup"><span data-stu-id="848b4-126">Element</span></span>|<span data-ttu-id="848b4-127">描述</span><span class="sxs-lookup"><span data-stu-id="848b4-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="848b4-128">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="848b4-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="848b4-129">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="848b4-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="848b4-130">包含用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="848b4-130">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="848b4-131">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="848b4-131">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="848b4-132">包含用于收集、 存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="848b4-132">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="848b4-133">侦听器将跟踪输出定向到适当的目标。</span><span class="sxs-lookup"><span data-stu-id="848b4-133">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="848b4-134">将侦听器添加到跟踪源的 `Listeners` 集合中。</span><span class="sxs-lookup"><span data-stu-id="848b4-134">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="848b4-135">备注</span><span class="sxs-lookup"><span data-stu-id="848b4-135">Remarks</span></span>  
 <span data-ttu-id="848b4-136">`<filter>`元素必须包含在`<add>`中定义的跟踪源侦听器指定的侦听器的类型的元素，而不仅仅是侦听器的名称[ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)。</span><span class="sxs-lookup"><span data-stu-id="848b4-136">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span></span> <span data-ttu-id="848b4-137">如果在中定义侦听器[ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)，必须在该元素中定义为该侦听器的筛选器。</span><span class="sxs-lookup"><span data-stu-id="848b4-137">If the listener is defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="848b4-138">计算机配置文件 (Machine.config) 和应用程序配置文件中，可以使用此元素。</span><span class="sxs-lookup"><span data-stu-id="848b4-138">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="848b4-139">示例</span><span class="sxs-lookup"><span data-stu-id="848b4-139">Example</span></span>  
 <span data-ttu-id="848b4-140">下面的示例演示如何使用`<filter>`元素添加到侦听器的筛选器`console`中`Listeners`跟踪源集合`myTraceSource`，并作为筛选器事件级别指定`Error`。</span><span class="sxs-lookup"><span data-stu-id="848b4-140">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="848b4-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="848b4-141">See Also</span></span>  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>  
 <xref:System.Diagnostics.TraceFilter>  
 [<span data-ttu-id="848b4-142">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="848b4-142">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
