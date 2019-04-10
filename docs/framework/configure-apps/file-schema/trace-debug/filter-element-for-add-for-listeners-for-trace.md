---
title: <filter> 有关元素<add>为<listeners>为 <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: 5961125e1b8d0d0f5711f8b942b68ba71d61888f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143424"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a><span data-ttu-id="85fe9-102">\<筛选器 > 元素\<添加 > 有关\<侦听器 > 为\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="85fe9-102">\<filter> Element for \<add> for \<listeners> for \<trace></span></span>
<span data-ttu-id="85fe9-103">将筛选器添加到中的侦听器`Listeners`跟踪的集合。</span><span class="sxs-lookup"><span data-stu-id="85fe9-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  
  
 <span data-ttu-id="85fe9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="85fe9-104">\<configuration></span></span>  
<span data-ttu-id="85fe9-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="85fe9-105">\<system.diagnostics></span></span>  
<span data-ttu-id="85fe9-106">\<trace></span><span class="sxs-lookup"><span data-stu-id="85fe9-106">\<trace></span></span>  
<span data-ttu-id="85fe9-107">\<listeners></span><span class="sxs-lookup"><span data-stu-id="85fe9-107">\<listeners></span></span>  
<span data-ttu-id="85fe9-108">\<add></span><span class="sxs-lookup"><span data-stu-id="85fe9-108">\<add></span></span>  
<span data-ttu-id="85fe9-109">\<filter></span><span class="sxs-lookup"><span data-stu-id="85fe9-109">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85fe9-110">语法</span><span class="sxs-lookup"><span data-stu-id="85fe9-110">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85fe9-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="85fe9-111">Attributes and Elements</span></span>  
 <span data-ttu-id="85fe9-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="85fe9-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85fe9-113">特性</span><span class="sxs-lookup"><span data-stu-id="85fe9-113">Attributes</span></span>  
  
|<span data-ttu-id="85fe9-114">特性</span><span class="sxs-lookup"><span data-stu-id="85fe9-114">Attribute</span></span>|<span data-ttu-id="85fe9-115">描述</span><span class="sxs-lookup"><span data-stu-id="85fe9-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="85fe9-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="85fe9-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="85fe9-117">指定的筛选器，它应继承自类型<xref:System.Diagnostics.TraceFilter>类。</span><span class="sxs-lookup"><span data-stu-id="85fe9-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="85fe9-118">可以使用的类型相对应的类型的命名空间限定名称<xref:System.Type.FullName%2A>属性，也可以使用完全限定的类型名称包括程序集信息，它对应于<xref:System.Type.AssemblyQualifiedName%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="85fe9-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="85fe9-119">有关完全限定的类型名称的信息，请参阅[指定完全限定的类型名称](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)。</span><span class="sxs-lookup"><span data-stu-id="85fe9-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="85fe9-120">可选特性。</span><span class="sxs-lookup"><span data-stu-id="85fe9-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="85fe9-121">传递给构造函数指定的筛选器类的字符串。</span><span class="sxs-lookup"><span data-stu-id="85fe9-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85fe9-122">子元素</span><span class="sxs-lookup"><span data-stu-id="85fe9-122">Child Elements</span></span>  
 <span data-ttu-id="85fe9-123">无。</span><span class="sxs-lookup"><span data-stu-id="85fe9-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="85fe9-124">父元素</span><span class="sxs-lookup"><span data-stu-id="85fe9-124">Parent Elements</span></span>  
  
|<span data-ttu-id="85fe9-125">元素</span><span class="sxs-lookup"><span data-stu-id="85fe9-125">Element</span></span>|<span data-ttu-id="85fe9-126">描述</span><span class="sxs-lookup"><span data-stu-id="85fe9-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="85fe9-127">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="85fe9-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="85fe9-128">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="85fe9-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="85fe9-129">包含用于收集、存储和路由跟踪消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="85fe9-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="85fe9-130">包含用于收集、 存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="85fe9-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="85fe9-131">侦听器将跟踪输出定向到适当的目标。</span><span class="sxs-lookup"><span data-stu-id="85fe9-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="85fe9-132">将侦听器添加到 `Listeners` 集合中。</span><span class="sxs-lookup"><span data-stu-id="85fe9-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85fe9-133">备注</span><span class="sxs-lookup"><span data-stu-id="85fe9-133">Remarks</span></span>  
 <span data-ttu-id="85fe9-134">`<filter>`元素必须包含在`<add>`中定义的跟踪侦听器，用于指定该侦听器的类型的元素，而不仅仅是侦听器的名称[ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)。</span><span class="sxs-lookup"><span data-stu-id="85fe9-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span></span> <span data-ttu-id="85fe9-135">如果在中定义侦听器[ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)，必须在该元素中定义为该侦听器的筛选器。</span><span class="sxs-lookup"><span data-stu-id="85fe9-135">If the listener is defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="85fe9-136">计算机配置文件 (Machine.config) 和应用程序配置文件中，可以使用此元素。</span><span class="sxs-lookup"><span data-stu-id="85fe9-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85fe9-137">示例</span><span class="sxs-lookup"><span data-stu-id="85fe9-137">Example</span></span>  
 <span data-ttu-id="85fe9-138">下面的示例演示如何使用`<filter>`元素添加到侦听器的筛选器`console`中`Listeners`的跟踪，同时指定为筛选器事件级别收集`Error`。</span><span class="sxs-lookup"><span data-stu-id="85fe9-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="85fe9-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="85fe9-139">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="85fe9-140">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="85fe9-140">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
