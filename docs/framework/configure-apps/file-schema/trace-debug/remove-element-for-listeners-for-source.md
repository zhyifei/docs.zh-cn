---
title: <remove>用于<listeners><source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 657e6db2af9b99b3bbf03afc6aab02c58a830f2d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153330"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="1eaa0-102">\<删除>源\<>的侦听\<器>元素</span><span class="sxs-lookup"><span data-stu-id="1eaa0-102">\<remove> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="1eaa0-103">从跟踪源的 `Listeners` 集合中删除侦听器。</span><span class="sxs-lookup"><span data-stu-id="1eaa0-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="1eaa0-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1eaa0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1eaa0-105">&nbsp;&nbsp;[**\<系统.诊断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="1eaa0-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="1eaa0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<来源>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="1eaa0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="1eaa0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<源>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="1eaa0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="1eaa0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<听众>**](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="1eaa0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="1eaa0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<删除>**</span><span class="sxs-lookup"><span data-stu-id="1eaa0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="1eaa0-110">语法</span><span class="sxs-lookup"><span data-stu-id="1eaa0-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1eaa0-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1eaa0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1eaa0-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1eaa0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1eaa0-113">属性</span><span class="sxs-lookup"><span data-stu-id="1eaa0-113">Attributes</span></span>  
  
|<span data-ttu-id="1eaa0-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="1eaa0-114">Attribute</span></span>|<span data-ttu-id="1eaa0-115">说明</span><span class="sxs-lookup"><span data-stu-id="1eaa0-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="1eaa0-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="1eaa0-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="1eaa0-117">要从`Listeners`集合中删除的侦听器的名称。</span><span class="sxs-lookup"><span data-stu-id="1eaa0-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1eaa0-118">子元素</span><span class="sxs-lookup"><span data-stu-id="1eaa0-118">Child Elements</span></span>  
 <span data-ttu-id="1eaa0-119">无。</span><span class="sxs-lookup"><span data-stu-id="1eaa0-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1eaa0-120">父元素</span><span class="sxs-lookup"><span data-stu-id="1eaa0-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1eaa0-121">元素</span><span class="sxs-lookup"><span data-stu-id="1eaa0-121">Element</span></span>|<span data-ttu-id="1eaa0-122">说明</span><span class="sxs-lookup"><span data-stu-id="1eaa0-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1eaa0-123">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="1eaa0-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="1eaa0-124">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="1eaa0-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="1eaa0-125">包含用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="1eaa0-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="1eaa0-126">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="1eaa0-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="1eaa0-127">指定收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="1eaa0-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1eaa0-128">备注</span><span class="sxs-lookup"><span data-stu-id="1eaa0-128">Remarks</span></span>  
 <span data-ttu-id="1eaa0-129">该`<remove>`元素从跟踪源的集合中删除`Listeners`指定的侦听器。</span><span class="sxs-lookup"><span data-stu-id="1eaa0-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="1eaa0-130">`Listeners`您可以通过调用<xref:System.Diagnostics.TraceListenerCollection.Remove%2A><xref:System.Diagnostics.TraceSource>实例<xref:System.Diagnostics.TraceSource.Listeners%2A>属性上的方法，以编程方式从跟踪源的集合中删除元素。</span><span class="sxs-lookup"><span data-stu-id="1eaa0-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="1eaa0-131">此元素可用于计算机配置文件 （Machine.config） 和应用程序配置文件。</span><span class="sxs-lookup"><span data-stu-id="1eaa0-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1eaa0-132">示例</span><span class="sxs-lookup"><span data-stu-id="1eaa0-132">Example</span></span>  
 <span data-ttu-id="1eaa0-133">下面的`<remove>`示例演示如何在使用`<add>`元素将侦听器`console`添加到跟踪源`Listeners``TraceSourceApp`的集合之前使用 元素。</span><span class="sxs-lookup"><span data-stu-id="1eaa0-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"
         switchType="System.Diagnostics.SourceSwitch" >  
         <listeners>  
           <remove name="Default"/>  
           <add name="console"
             type="System.Diagnostics.ConsoleTraceListener" />  
         </listeners>  
      </source>  
    </sources>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="1eaa0-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1eaa0-134">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="1eaa0-135">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="1eaa0-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="1eaa0-136">\<明确></span><span class="sxs-lookup"><span data-stu-id="1eaa0-136">\<clear></span></span>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="1eaa0-137">跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="1eaa0-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
