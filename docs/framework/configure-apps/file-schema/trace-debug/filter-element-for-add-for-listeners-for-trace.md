---
title: 用于 <listeners> 的 <add> <filter> 元素 <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: cc970240ac07ad3ea72be50d1e9af452da638fa9
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088896"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a><span data-ttu-id="be6fb-102">\<筛选器 > 元素 \<为 \<跟踪 > 添加 \<侦听器的 > ></span><span class="sxs-lookup"><span data-stu-id="be6fb-102">\<filter> Element for \<add> for \<listeners> for \<trace></span></span>
<span data-ttu-id="be6fb-103">将筛选器添加到跟踪的 `Listeners` 集合中的侦听器。</span><span class="sxs-lookup"><span data-stu-id="be6fb-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  

<span data-ttu-id="be6fb-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="be6fb-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="be6fb-105">&nbsp;&nbsp;[ **\<的 >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="be6fb-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="be6fb-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="be6fb-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="be6fb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**侦听器**](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="be6fb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="be6fb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<添加 >** ](add-element-for-listeners-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="be6fb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-trace.md)</span></span>\
<span data-ttu-id="be6fb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<筛选 >**</span><span class="sxs-lookup"><span data-stu-id="be6fb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>

## <a name="syntax"></a><span data-ttu-id="be6fb-110">语法</span><span class="sxs-lookup"><span data-stu-id="be6fb-110">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="be6fb-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="be6fb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="be6fb-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="be6fb-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be6fb-113">特性</span><span class="sxs-lookup"><span data-stu-id="be6fb-113">Attributes</span></span>  
  
|<span data-ttu-id="be6fb-114">特性</span><span class="sxs-lookup"><span data-stu-id="be6fb-114">Attribute</span></span>|<span data-ttu-id="be6fb-115">描述</span><span class="sxs-lookup"><span data-stu-id="be6fb-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="be6fb-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="be6fb-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="be6fb-117">指定筛选器的类型，该类型应继承自 <xref:System.Diagnostics.TraceFilter> 类。</span><span class="sxs-lookup"><span data-stu-id="be6fb-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="be6fb-118">您可以使用与类型的 <xref:System.Type.FullName%2A> 属性对应的命名空间限定名称，也可以使用包含程序集信息（对应于 <xref:System.Type.AssemblyQualifiedName%2A> 属性）的完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="be6fb-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="be6fb-119">有关完全限定类型名称的信息，请参阅[指定完全限定的类型名称](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)。</span><span class="sxs-lookup"><span data-stu-id="be6fb-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="be6fb-120">可选特性。</span><span class="sxs-lookup"><span data-stu-id="be6fb-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="be6fb-121">传递给指定筛选器类的构造函数的字符串。</span><span class="sxs-lookup"><span data-stu-id="be6fb-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="be6fb-122">子元素</span><span class="sxs-lookup"><span data-stu-id="be6fb-122">Child Elements</span></span>  
 <span data-ttu-id="be6fb-123">无。</span><span class="sxs-lookup"><span data-stu-id="be6fb-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="be6fb-124">父元素</span><span class="sxs-lookup"><span data-stu-id="be6fb-124">Parent Elements</span></span>  
  
|<span data-ttu-id="be6fb-125">元素</span><span class="sxs-lookup"><span data-stu-id="be6fb-125">Element</span></span>|<span data-ttu-id="be6fb-126">描述</span><span class="sxs-lookup"><span data-stu-id="be6fb-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="be6fb-127">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="be6fb-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="be6fb-128">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="be6fb-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="be6fb-129">包含用于收集、存储和路由跟踪消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="be6fb-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="be6fb-130">包含收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="be6fb-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="be6fb-131">侦听器将跟踪输出定向到适当的目标。</span><span class="sxs-lookup"><span data-stu-id="be6fb-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="be6fb-132">将侦听器添加到 `Listeners` 集合中。</span><span class="sxs-lookup"><span data-stu-id="be6fb-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be6fb-133">备注</span><span class="sxs-lookup"><span data-stu-id="be6fb-133">Remarks</span></span>  
 <span data-ttu-id="be6fb-134">`<filter>` 元素必须包含在跟踪侦听器的 `<add>` 元素中，后者指定侦听器的类型，而不仅仅是[\<sharedListeners >](sharedlisteners-element.md)中定义的侦听器的名称。</span><span class="sxs-lookup"><span data-stu-id="be6fb-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="be6fb-135">如果侦听器是在[\<sharedListeners >](sharedlisteners-element.md)中定义的，则必须在该元素中定义该侦听器的筛选器。</span><span class="sxs-lookup"><span data-stu-id="be6fb-135">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="be6fb-136">此元素可在计算机配置文件（Machine.config）和应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="be6fb-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be6fb-137">示例</span><span class="sxs-lookup"><span data-stu-id="be6fb-137">Example</span></span>  
 <span data-ttu-id="be6fb-138">下面的示例演示如何使用 `<filter>` 元素将筛选器添加到跟踪的 `Listeners` 集合中的侦听器 `console`，并将筛选器事件级别指定为 `Error`。</span><span class="sxs-lookup"><span data-stu-id="be6fb-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="be6fb-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="be6fb-139">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="be6fb-140">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="be6fb-140">Trace and Debug Settings Schema</span></span>](index.md)
