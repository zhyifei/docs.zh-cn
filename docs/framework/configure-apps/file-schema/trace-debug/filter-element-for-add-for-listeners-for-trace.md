---
title: <filter><add> 的<listeners>的的元素<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: afde5381a7dd7dfe6a1a9d238a2029511bd9bae2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927132"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a><span data-ttu-id="7b537-102">\<筛选用于\<添加\<侦听器的 > > 元素 > \<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="7b537-102">\<filter> Element for \<add> for \<listeners> for \<trace></span></span>
<span data-ttu-id="7b537-103">将筛选器添加到跟踪的`Listeners`集合中的侦听器。</span><span class="sxs-lookup"><span data-stu-id="7b537-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  
  
 <span data-ttu-id="7b537-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7b537-104">\<configuration></span></span>  
<span data-ttu-id="7b537-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="7b537-105">\<system.diagnostics></span></span>  
<span data-ttu-id="7b537-106">\<trace></span><span class="sxs-lookup"><span data-stu-id="7b537-106">\<trace></span></span>  
<span data-ttu-id="7b537-107">\<侦听器 ></span><span class="sxs-lookup"><span data-stu-id="7b537-107">\<listeners></span></span>  
<span data-ttu-id="7b537-108">\<add></span><span class="sxs-lookup"><span data-stu-id="7b537-108">\<add></span></span>  
<span data-ttu-id="7b537-109">\<filter></span><span class="sxs-lookup"><span data-stu-id="7b537-109">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b537-110">语法</span><span class="sxs-lookup"><span data-stu-id="7b537-110">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b537-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7b537-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7b537-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7b537-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b537-113">特性</span><span class="sxs-lookup"><span data-stu-id="7b537-113">Attributes</span></span>  
  
|<span data-ttu-id="7b537-114">特性</span><span class="sxs-lookup"><span data-stu-id="7b537-114">Attribute</span></span>|<span data-ttu-id="7b537-115">描述</span><span class="sxs-lookup"><span data-stu-id="7b537-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="7b537-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="7b537-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="7b537-117">指定筛选器的类型, 该类型应继承自<xref:System.Diagnostics.TraceFilter>类。</span><span class="sxs-lookup"><span data-stu-id="7b537-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="7b537-118">你可以使用类型的命名空间限定名称, 该名称与类型的<xref:System.Type.FullName%2A>属性相对应, 或者你可以使用包含程序集信息 (与<xref:System.Type.AssemblyQualifiedName%2A>属性相对应) 的完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="7b537-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="7b537-119">有关完全限定类型名称的信息, 请参阅[指定完全限定的类型名称](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)。</span><span class="sxs-lookup"><span data-stu-id="7b537-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="7b537-120">可选特性。</span><span class="sxs-lookup"><span data-stu-id="7b537-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="7b537-121">传递给指定筛选器类的构造函数的字符串。</span><span class="sxs-lookup"><span data-stu-id="7b537-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7b537-122">子元素</span><span class="sxs-lookup"><span data-stu-id="7b537-122">Child Elements</span></span>  
 <span data-ttu-id="7b537-123">无。</span><span class="sxs-lookup"><span data-stu-id="7b537-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7b537-124">父元素</span><span class="sxs-lookup"><span data-stu-id="7b537-124">Parent Elements</span></span>  
  
|<span data-ttu-id="7b537-125">元素</span><span class="sxs-lookup"><span data-stu-id="7b537-125">Element</span></span>|<span data-ttu-id="7b537-126">描述</span><span class="sxs-lookup"><span data-stu-id="7b537-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7b537-127">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="7b537-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="7b537-128">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="7b537-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="7b537-129">包含用于收集、存储和路由跟踪消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="7b537-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="7b537-130">包含收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="7b537-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="7b537-131">侦听器将跟踪输出定向到适当的目标。</span><span class="sxs-lookup"><span data-stu-id="7b537-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="7b537-132">将侦听器添加到 `Listeners` 集合中。</span><span class="sxs-lookup"><span data-stu-id="7b537-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b537-133">备注</span><span class="sxs-lookup"><span data-stu-id="7b537-133">Remarks</span></span>  
 <span data-ttu-id="7b537-134">元素必须包含`<add>`在指定侦听器类型的跟踪侦听器的元素中, 而不只是在[ \<sharedListeners >](sharedlisteners-element.md)中定义的侦听器的名称。 `<filter>`</span><span class="sxs-lookup"><span data-stu-id="7b537-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="7b537-135">如果侦听器是在[ \<sharedListeners >](sharedlisteners-element.md)中定义的, 则必须在该元素中定义该侦听器的筛选器。</span><span class="sxs-lookup"><span data-stu-id="7b537-135">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="7b537-136">此元素可在计算机配置文件 (Machine.config) 和应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="7b537-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b537-137">示例</span><span class="sxs-lookup"><span data-stu-id="7b537-137">Example</span></span>  
 <span data-ttu-id="7b537-138">下面的示例演示`<filter>`如何使用元素将筛选器添加到跟踪的`Listeners`集合中`console`的侦听器, 并将筛选器事件级别指定为`Error`。</span><span class="sxs-lookup"><span data-stu-id="7b537-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7b537-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="7b537-139">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="7b537-140">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="7b537-140">Trace and Debug Settings Schema</span></span>](index.md)
