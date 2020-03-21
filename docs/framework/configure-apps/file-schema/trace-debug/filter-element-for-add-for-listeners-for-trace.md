---
title: <filter>用于<add><listeners><trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: b6c2c2bf7fe953a75f9d8129039ef33b4d8a3f56
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153461"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a><span data-ttu-id="3da24-102">\<筛选器>元素，\<用于添加\<>跟踪>的\<侦听器></span><span class="sxs-lookup"><span data-stu-id="3da24-102">\<filter> Element for \<add> for \<listeners> for \<trace></span></span>
<span data-ttu-id="3da24-103">将筛选器添加到跟踪集合中的`Listeners`侦听器。</span><span class="sxs-lookup"><span data-stu-id="3da24-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  

<span data-ttu-id="3da24-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3da24-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3da24-105">&nbsp;&nbsp;[**\<系统.诊断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="3da24-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="3da24-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<跟踪>**](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="3da24-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="3da24-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<听众>**](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="3da24-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="3da24-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<添加>**](add-element-for-listeners-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="3da24-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-trace.md)</span></span>\
<span data-ttu-id="3da24-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<过滤器>**</span><span class="sxs-lookup"><span data-stu-id="3da24-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>

## <a name="syntax"></a><span data-ttu-id="3da24-110">语法</span><span class="sxs-lookup"><span data-stu-id="3da24-110">Syntax</span></span>  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3da24-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3da24-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3da24-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3da24-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3da24-113">属性</span><span class="sxs-lookup"><span data-stu-id="3da24-113">Attributes</span></span>  
  
|<span data-ttu-id="3da24-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="3da24-114">Attribute</span></span>|<span data-ttu-id="3da24-115">说明</span><span class="sxs-lookup"><span data-stu-id="3da24-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="3da24-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="3da24-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="3da24-117">指定筛选器的类型，该筛选器应从<xref:System.Diagnostics.TraceFilter>类继承。</span><span class="sxs-lookup"><span data-stu-id="3da24-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="3da24-118">可以使用类型的名称空间限定名称（对应于类型的属性<xref:System.Type.FullName%2A>），也可以使用完全限定的类型名称（包括对应于该属性的<xref:System.Type.AssemblyQualifiedName%2A>程序集信息）。</span><span class="sxs-lookup"><span data-stu-id="3da24-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="3da24-119">有关完全限定类型名称的信息，请参阅[指定完全限定类型名称](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)。</span><span class="sxs-lookup"><span data-stu-id="3da24-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="3da24-120">可选特性。</span><span class="sxs-lookup"><span data-stu-id="3da24-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="3da24-121">字符串传递给指定筛选器类的构造函数。</span><span class="sxs-lookup"><span data-stu-id="3da24-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3da24-122">子元素</span><span class="sxs-lookup"><span data-stu-id="3da24-122">Child Elements</span></span>  
 <span data-ttu-id="3da24-123">无。</span><span class="sxs-lookup"><span data-stu-id="3da24-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3da24-124">父元素</span><span class="sxs-lookup"><span data-stu-id="3da24-124">Parent Elements</span></span>  
  
|<span data-ttu-id="3da24-125">元素</span><span class="sxs-lookup"><span data-stu-id="3da24-125">Element</span></span>|<span data-ttu-id="3da24-126">说明</span><span class="sxs-lookup"><span data-stu-id="3da24-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3da24-127">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="3da24-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="3da24-128">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="3da24-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="3da24-129">包含用于收集、存储和路由跟踪消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="3da24-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="3da24-130">包含收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="3da24-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="3da24-131">侦听器将跟踪输出定向到适当的目标。</span><span class="sxs-lookup"><span data-stu-id="3da24-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="3da24-132">将侦听器添加到 `Listeners` 集合中。</span><span class="sxs-lookup"><span data-stu-id="3da24-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3da24-133">备注</span><span class="sxs-lookup"><span data-stu-id="3da24-133">Remarks</span></span>  
 <span data-ttu-id="3da24-134">元素`<filter>`必须包含在指定侦听器`<add>`类型的跟踪侦听器的元素中，而不仅仅是[\<在共享侦听器>](sharedlisteners-element.md)中定义的侦听器的名称。</span><span class="sxs-lookup"><span data-stu-id="3da24-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="3da24-135">如果在[\<共享侦听器>](sharedlisteners-element.md)中定义侦听器，则必须在该元素中定义该侦听器的筛选器。</span><span class="sxs-lookup"><span data-stu-id="3da24-135">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="3da24-136">此元素可用于计算机配置文件 （Machine.config） 和应用程序配置文件。</span><span class="sxs-lookup"><span data-stu-id="3da24-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3da24-137">示例</span><span class="sxs-lookup"><span data-stu-id="3da24-137">Example</span></span>  
 <span data-ttu-id="3da24-138">下面的示例演示如何使用`<filter>`元素向跟踪集合中的`console``Listeners`侦听器添加筛选器，将筛选器事件级别指定为`Error`。</span><span class="sxs-lookup"><span data-stu-id="3da24-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3da24-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3da24-139">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="3da24-140">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="3da24-140">Trace and Debug Settings Schema</span></span>](index.md)
