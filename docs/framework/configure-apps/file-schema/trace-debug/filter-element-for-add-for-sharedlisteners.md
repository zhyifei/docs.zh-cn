---
title: <sharedListeners> 的 @no__t <add> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter
helpviewer_keywords:
- filter element for <add> for <sharedListeners>
- initializeData attribute
- <filter> element for <add> for <sharedListeners>
- filters, trace listeners
- trace listeners, filters
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
ms.openlocfilehash: 4e92f80e9f6069b5fa70501e13a55d5a6fe95e7a
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697327"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a><span data-ttu-id="7217d-102">\<filter > 元素，用于 2sharedListeners @no__t 的 \<add ></span><span class="sxs-lookup"><span data-stu-id="7217d-102">\<filter> Element for \<add> for \<sharedListeners></span></span>
<span data-ttu-id="7217d-103">将筛选器添加到 `sharedListeners` 集合中的侦听器。</span><span class="sxs-lookup"><span data-stu-id="7217d-103">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  
  
[<span data-ttu-id="7217d-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="7217d-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="7217d-105">&nbsp; @ no__t-1[ **\<system >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="7217d-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="7217d-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<sharedListeners >** ](sharedlisteners-element.md)</span><span class="sxs-lookup"><span data-stu-id="7217d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)</span></span>  
<span data-ttu-id="7217d-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<add >** ](add-element-for-sharedlisteners.md)</span><span class="sxs-lookup"><span data-stu-id="7217d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-sharedlisteners.md)</span></span>  
<span data-ttu-id="7217d-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<filter >**</span><span class="sxs-lookup"><span data-stu-id="7217d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7217d-109">语法</span><span class="sxs-lookup"><span data-stu-id="7217d-109">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7217d-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7217d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7217d-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7217d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7217d-112">特性</span><span class="sxs-lookup"><span data-stu-id="7217d-112">Attributes</span></span>  
  
|<span data-ttu-id="7217d-113">特性</span><span class="sxs-lookup"><span data-stu-id="7217d-113">Attribute</span></span>|<span data-ttu-id="7217d-114">描述</span><span class="sxs-lookup"><span data-stu-id="7217d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7217d-115">**type**</span><span class="sxs-lookup"><span data-stu-id="7217d-115">**type**</span></span>|<span data-ttu-id="7217d-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="7217d-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="7217d-117">指定筛选器的类型。</span><span class="sxs-lookup"><span data-stu-id="7217d-117">Specifies the type of the filter.</span></span> <span data-ttu-id="7217d-118">只能使用该类型的完整名称（格式为 <xref:System.Type.FullName%2A?displayProperty=nameWithType> 属性），也可以使用包含程序集信息的完全限定的类型名称（采用 @no__t 的格式）。</span><span class="sxs-lookup"><span data-stu-id="7217d-118">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="7217d-119">有关创建完全限定类型名称的信息，请参阅[指定完全限定的类型](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)名称。</span><span class="sxs-lookup"><span data-stu-id="7217d-119">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="7217d-120">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="7217d-120">**initializeData**</span></span>|<span data-ttu-id="7217d-121">可选特性。</span><span class="sxs-lookup"><span data-stu-id="7217d-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="7217d-122">传递到指定类的构造函数的字符串。</span><span class="sxs-lookup"><span data-stu-id="7217d-122">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7217d-123">子元素</span><span class="sxs-lookup"><span data-stu-id="7217d-123">Child Elements</span></span>  
 <span data-ttu-id="7217d-124">无。</span><span class="sxs-lookup"><span data-stu-id="7217d-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7217d-125">父元素</span><span class="sxs-lookup"><span data-stu-id="7217d-125">Parent Elements</span></span>  
  
|<span data-ttu-id="7217d-126">元素</span><span class="sxs-lookup"><span data-stu-id="7217d-126">Element</span></span>|<span data-ttu-id="7217d-127">描述</span><span class="sxs-lookup"><span data-stu-id="7217d-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7217d-128">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="7217d-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="7217d-129">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="7217d-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="7217d-130">任何源或跟踪元素都可以引用的侦听器的集合。</span><span class="sxs-lookup"><span data-stu-id="7217d-130">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="7217d-131">将侦听器添加到**sharedListeners**集合。</span><span class="sxs-lookup"><span data-stu-id="7217d-131">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7217d-132">备注</span><span class="sxs-lookup"><span data-stu-id="7217d-132">Remarks</span></span>  
 <span data-ttu-id="7217d-133">如果侦听器是在 @no__t 1 元素的 `<add>` 元素中定义的，则应在作为 `<add>` 元素的子元素的 `<filter>` 元素中定义该侦听器的筛选器。</span><span class="sxs-lookup"><span data-stu-id="7217d-133">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="7217d-134">此元素可在计算机配置文件（Machine.config）和应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="7217d-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7217d-135">示例</span><span class="sxs-lookup"><span data-stu-id="7217d-135">Example</span></span>  
 <span data-ttu-id="7217d-136">下面的示例演示如何使用 `<filter>` 元素向 `sharedListeners` 集合中的跟踪侦听器 @no__t 添加筛选器。</span><span class="sxs-lookup"><span data-stu-id="7217d-136">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"   
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"   
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7217d-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="7217d-137">See also</span></span>

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="7217d-138">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="7217d-138">Trace and Debug Settings Schema</span></span>](index.md)
