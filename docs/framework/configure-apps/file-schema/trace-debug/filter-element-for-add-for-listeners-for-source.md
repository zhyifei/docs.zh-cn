---
title: <filter> 有关元素<add>为<listeners>为 <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: 3abfd0bdd40f98a9e4774677fc2cd5068c14333f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186727"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a><span data-ttu-id="d2cae-102">\<筛选器 > 元素\<添加 > 有关\<侦听器 > 为\<源 ></span><span class="sxs-lookup"><span data-stu-id="d2cae-102">\<filter> Element for \<add> for \<listeners> for \<source></span></span>
<span data-ttu-id="d2cae-103">将筛选器添加到跟踪源的 `Listeners` 集合中的侦听器。</span><span class="sxs-lookup"><span data-stu-id="d2cae-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="d2cae-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d2cae-104">\<configuration></span></span>  
<span data-ttu-id="d2cae-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="d2cae-105">\<system.diagnostics></span></span>  
<span data-ttu-id="d2cae-106">\<sources></span><span class="sxs-lookup"><span data-stu-id="d2cae-106">\<sources></span></span>  
<span data-ttu-id="d2cae-107">\<source></span><span class="sxs-lookup"><span data-stu-id="d2cae-107">\<source></span></span>  
<span data-ttu-id="d2cae-108">\<listeners></span><span class="sxs-lookup"><span data-stu-id="d2cae-108">\<listeners></span></span>  
<span data-ttu-id="d2cae-109">\<add></span><span class="sxs-lookup"><span data-stu-id="d2cae-109">\<add></span></span>  
<span data-ttu-id="d2cae-110">\<filter></span><span class="sxs-lookup"><span data-stu-id="d2cae-110">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2cae-111">语法</span><span class="sxs-lookup"><span data-stu-id="d2cae-111">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2cae-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d2cae-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d2cae-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d2cae-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2cae-114">特性</span><span class="sxs-lookup"><span data-stu-id="d2cae-114">Attributes</span></span>  
  
|<span data-ttu-id="d2cae-115">特性</span><span class="sxs-lookup"><span data-stu-id="d2cae-115">Attribute</span></span>|<span data-ttu-id="d2cae-116">描述</span><span class="sxs-lookup"><span data-stu-id="d2cae-116">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="d2cae-117">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="d2cae-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="d2cae-118">指定的筛选器，它应继承自类型<xref:System.Diagnostics.TraceFilter>类。</span><span class="sxs-lookup"><span data-stu-id="d2cae-118">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="d2cae-119">可以使用的类型相对应的类型的命名空间限定名称<xref:System.Type.FullName%2A>属性，也可以使用完全限定的类型名称包括程序集信息，它对应于<xref:System.Type.AssemblyQualifiedName%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="d2cae-119">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="d2cae-120">有关完全限定的类型名称的信息，请参阅[指定完全限定的类型名称](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)。</span><span class="sxs-lookup"><span data-stu-id="d2cae-120">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="d2cae-121">可选特性。</span><span class="sxs-lookup"><span data-stu-id="d2cae-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d2cae-122">传递给构造函数指定的筛选器类的字符串。</span><span class="sxs-lookup"><span data-stu-id="d2cae-122">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d2cae-123">子元素</span><span class="sxs-lookup"><span data-stu-id="d2cae-123">Child Elements</span></span>  
 <span data-ttu-id="d2cae-124">无。</span><span class="sxs-lookup"><span data-stu-id="d2cae-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d2cae-125">父元素</span><span class="sxs-lookup"><span data-stu-id="d2cae-125">Parent Elements</span></span>  
  
|<span data-ttu-id="d2cae-126">元素</span><span class="sxs-lookup"><span data-stu-id="d2cae-126">Element</span></span>|<span data-ttu-id="d2cae-127">描述</span><span class="sxs-lookup"><span data-stu-id="d2cae-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d2cae-128">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="d2cae-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="d2cae-129">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="d2cae-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="d2cae-130">包含用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="d2cae-130">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="d2cae-131">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="d2cae-131">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="d2cae-132">包含用于收集、 存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="d2cae-132">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="d2cae-133">侦听器将跟踪输出定向到适当的目标。</span><span class="sxs-lookup"><span data-stu-id="d2cae-133">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="d2cae-134">将侦听器添加到跟踪源的 `Listeners` 集合中。</span><span class="sxs-lookup"><span data-stu-id="d2cae-134">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2cae-135">备注</span><span class="sxs-lookup"><span data-stu-id="d2cae-135">Remarks</span></span>  
 <span data-ttu-id="d2cae-136">`<filter>`元素必须包含在`<add>`中定义的跟踪源侦听器指定的侦听器的类型的元素，而不仅仅是侦听器的名称[ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)。</span><span class="sxs-lookup"><span data-stu-id="d2cae-136">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span></span> <span data-ttu-id="d2cae-137">如果在中定义侦听器[ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)，必须在该元素中定义为该侦听器的筛选器。</span><span class="sxs-lookup"><span data-stu-id="d2cae-137">If the listener is defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="d2cae-138">计算机配置文件 (Machine.config) 和应用程序配置文件中，可以使用此元素。</span><span class="sxs-lookup"><span data-stu-id="d2cae-138">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2cae-139">示例</span><span class="sxs-lookup"><span data-stu-id="d2cae-139">Example</span></span>  
 <span data-ttu-id="d2cae-140">下面的示例演示如何使用`<filter>`元素添加到侦听器的筛选器`console`中`Listeners`跟踪源集合`myTraceSource`，并作为筛选器事件级别指定`Error`。</span><span class="sxs-lookup"><span data-stu-id="d2cae-140">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d2cae-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2cae-141">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="d2cae-142">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="d2cae-142">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
