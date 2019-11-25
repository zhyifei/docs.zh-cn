---
title: 用于 <listeners> 的 <add> <filter> 元素 <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: 766088b8a26ce3218031df74b193658ba8024280
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088907"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a><span data-ttu-id="85310-102">\<筛选器的 > 元素 \<为 \<的 > 侦听器添加 > \<</span><span class="sxs-lookup"><span data-stu-id="85310-102">\<filter> Element for \<add> for \<listeners> for \<source></span></span>
<span data-ttu-id="85310-103">将筛选器添加到跟踪源的 `Listeners` 集合中的侦听器。</span><span class="sxs-lookup"><span data-stu-id="85310-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="85310-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="85310-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="85310-105">&nbsp;&nbsp;[ **\<的 >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="85310-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="85310-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](sources-element.md) ></span><span class="sxs-lookup"><span data-stu-id="85310-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="85310-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **&nbsp;&nbsp;\<** ](source-element.md) ></span><span class="sxs-lookup"><span data-stu-id="85310-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="85310-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**侦听器 >** ](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="85310-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="85310-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<添加 >** ](add-element-for-listeners-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="85310-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-source.md)</span></span>\
<span data-ttu-id="85310-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<筛选 >**</span><span class="sxs-lookup"><span data-stu-id="85310-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>

## <a name="syntax"></a><span data-ttu-id="85310-111">语法</span><span class="sxs-lookup"><span data-stu-id="85310-111">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85310-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="85310-112">Attributes and Elements</span></span>  
 <span data-ttu-id="85310-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="85310-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85310-114">特性</span><span class="sxs-lookup"><span data-stu-id="85310-114">Attributes</span></span>  
  
|<span data-ttu-id="85310-115">特性</span><span class="sxs-lookup"><span data-stu-id="85310-115">Attribute</span></span>|<span data-ttu-id="85310-116">描述</span><span class="sxs-lookup"><span data-stu-id="85310-116">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="85310-117">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="85310-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="85310-118">指定筛选器的类型，该类型应继承自 <xref:System.Diagnostics.TraceFilter> 类。</span><span class="sxs-lookup"><span data-stu-id="85310-118">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="85310-119">您可以使用与类型的 <xref:System.Type.FullName%2A> 属性对应的命名空间限定名称，也可以使用包含程序集信息（对应于 <xref:System.Type.AssemblyQualifiedName%2A> 属性）的完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="85310-119">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="85310-120">有关完全限定类型名称的信息，请参阅[指定完全限定的类型名称](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)。</span><span class="sxs-lookup"><span data-stu-id="85310-120">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="85310-121">可选特性。</span><span class="sxs-lookup"><span data-stu-id="85310-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="85310-122">传递给指定筛选器类的构造函数的字符串。</span><span class="sxs-lookup"><span data-stu-id="85310-122">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85310-123">子元素</span><span class="sxs-lookup"><span data-stu-id="85310-123">Child Elements</span></span>  
 <span data-ttu-id="85310-124">无。</span><span class="sxs-lookup"><span data-stu-id="85310-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="85310-125">父元素</span><span class="sxs-lookup"><span data-stu-id="85310-125">Parent Elements</span></span>  
  
|<span data-ttu-id="85310-126">元素</span><span class="sxs-lookup"><span data-stu-id="85310-126">Element</span></span>|<span data-ttu-id="85310-127">描述</span><span class="sxs-lookup"><span data-stu-id="85310-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="85310-128">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="85310-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="85310-129">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="85310-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="85310-130">包含用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="85310-130">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="85310-131">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="85310-131">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="85310-132">包含收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="85310-132">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="85310-133">侦听器将跟踪输出定向到适当的目标。</span><span class="sxs-lookup"><span data-stu-id="85310-133">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="85310-134">将侦听器添加到跟踪源的 `Listeners` 集合中。</span><span class="sxs-lookup"><span data-stu-id="85310-134">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85310-135">备注</span><span class="sxs-lookup"><span data-stu-id="85310-135">Remarks</span></span>  
 <span data-ttu-id="85310-136">`<filter>` 元素必须包含在指定侦听器类型的 trace 源侦听器的 `<add>` 元素中，而不只是[\<sharedListeners >](sharedlisteners-element.md)中定义的侦听器的名称。</span><span class="sxs-lookup"><span data-stu-id="85310-136">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="85310-137">如果侦听器是在[\<sharedListeners >](sharedlisteners-element.md)中定义的，则必须在该元素中定义该侦听器的筛选器。</span><span class="sxs-lookup"><span data-stu-id="85310-137">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="85310-138">此元素可在计算机配置文件（Machine.config）和应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="85310-138">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85310-139">示例</span><span class="sxs-lookup"><span data-stu-id="85310-139">Example</span></span>  
 <span data-ttu-id="85310-140">下面的示例演示如何使用 `<filter>` 元素将筛选器添加到跟踪源 `myTraceSource``Listeners` 集合中的侦听器 `console`，并将筛选器事件级别指定为 `Error`。</span><span class="sxs-lookup"><span data-stu-id="85310-140">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="85310-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="85310-141">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="85310-142">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="85310-142">Trace and Debug Settings Schema</span></span>](index.md)
