---
title: <filter>用于<add><listeners><source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: 0cb668782de263d5f784691f46cb8b74541d942b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153511"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a><span data-ttu-id="665ee-102">\<筛选器>元素，\<用于为\<\<源>>的侦听器添加></span><span class="sxs-lookup"><span data-stu-id="665ee-102">\<filter> Element for \<add> for \<listeners> for \<source></span></span>
<span data-ttu-id="665ee-103">将筛选器添加到跟踪源的 `Listeners` 集合中的侦听器。</span><span class="sxs-lookup"><span data-stu-id="665ee-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="665ee-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="665ee-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="665ee-105">&nbsp;&nbsp;[**\<系统.诊断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="665ee-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="665ee-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<来源>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="665ee-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="665ee-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<源>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="665ee-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="665ee-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<听众>**](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="665ee-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="665ee-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<添加>**](add-element-for-listeners-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="665ee-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-source.md)</span></span>\
<span data-ttu-id="665ee-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<过滤器>**</span><span class="sxs-lookup"><span data-stu-id="665ee-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>

## <a name="syntax"></a><span data-ttu-id="665ee-111">语法</span><span class="sxs-lookup"><span data-stu-id="665ee-111">Syntax</span></span>  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="665ee-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="665ee-112">Attributes and Elements</span></span>  
 <span data-ttu-id="665ee-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="665ee-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="665ee-114">属性</span><span class="sxs-lookup"><span data-stu-id="665ee-114">Attributes</span></span>  
  
|<span data-ttu-id="665ee-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="665ee-115">Attribute</span></span>|<span data-ttu-id="665ee-116">说明</span><span class="sxs-lookup"><span data-stu-id="665ee-116">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="665ee-117">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="665ee-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="665ee-118">指定筛选器的类型，该筛选器应从<xref:System.Diagnostics.TraceFilter>类继承。</span><span class="sxs-lookup"><span data-stu-id="665ee-118">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="665ee-119">可以使用类型的名称空间限定名称（对应于类型的属性<xref:System.Type.FullName%2A>），也可以使用完全限定的类型名称（包括对应于该属性的<xref:System.Type.AssemblyQualifiedName%2A>程序集信息）。</span><span class="sxs-lookup"><span data-stu-id="665ee-119">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="665ee-120">有关完全限定类型名称的信息，请参阅[指定完全限定类型名称](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)。</span><span class="sxs-lookup"><span data-stu-id="665ee-120">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="665ee-121">可选特性。</span><span class="sxs-lookup"><span data-stu-id="665ee-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="665ee-122">字符串传递给指定筛选器类的构造函数。</span><span class="sxs-lookup"><span data-stu-id="665ee-122">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="665ee-123">子元素</span><span class="sxs-lookup"><span data-stu-id="665ee-123">Child Elements</span></span>  
 <span data-ttu-id="665ee-124">无。</span><span class="sxs-lookup"><span data-stu-id="665ee-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="665ee-125">父元素</span><span class="sxs-lookup"><span data-stu-id="665ee-125">Parent Elements</span></span>  
  
|<span data-ttu-id="665ee-126">元素</span><span class="sxs-lookup"><span data-stu-id="665ee-126">Element</span></span>|<span data-ttu-id="665ee-127">说明</span><span class="sxs-lookup"><span data-stu-id="665ee-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="665ee-128">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="665ee-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="665ee-129">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="665ee-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="665ee-130">包含用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="665ee-130">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="665ee-131">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="665ee-131">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="665ee-132">包含收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="665ee-132">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="665ee-133">侦听器将跟踪输出定向到适当的目标。</span><span class="sxs-lookup"><span data-stu-id="665ee-133">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="665ee-134">将侦听器添加到跟踪源的 `Listeners` 集合中。</span><span class="sxs-lookup"><span data-stu-id="665ee-134">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="665ee-135">备注</span><span class="sxs-lookup"><span data-stu-id="665ee-135">Remarks</span></span>  
 <span data-ttu-id="665ee-136">元素`<filter>`必须包含在指定侦听器`<add>`类型的跟踪源侦听器的元素中，而不仅仅是[\<在共享侦听器>](sharedlisteners-element.md)中定义的侦听器的名称。</span><span class="sxs-lookup"><span data-stu-id="665ee-136">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="665ee-137">如果在[\<共享侦听器>](sharedlisteners-element.md)中定义侦听器，则必须在该元素中定义该侦听器的筛选器。</span><span class="sxs-lookup"><span data-stu-id="665ee-137">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="665ee-138">此元素可用于计算机配置文件 （Machine.config） 和应用程序配置文件。</span><span class="sxs-lookup"><span data-stu-id="665ee-138">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="665ee-139">示例</span><span class="sxs-lookup"><span data-stu-id="665ee-139">Example</span></span>  
 <span data-ttu-id="665ee-140">下面的示例演示如何`<filter>`使用 元素向跟踪源`console``Listeners``myTraceSource`集合中的侦听器添加筛选器，将筛选器事件级别指定为`Error`。</span><span class="sxs-lookup"><span data-stu-id="665ee-140">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="665ee-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="665ee-141">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="665ee-142">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="665ee-142">Trace and Debug Settings Schema</span></span>](index.md)
