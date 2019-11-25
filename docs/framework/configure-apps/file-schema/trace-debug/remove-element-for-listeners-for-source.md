---
title: <source> 的 <listeners> 的 <remove> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 75db45d4e868ce88e030ec6a43c8bdaf788a1102
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088852"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="bdb93-102">\<删除 \<源的 \<侦听器 > > 元素 ></span><span class="sxs-lookup"><span data-stu-id="bdb93-102">\<remove> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="bdb93-103">从跟踪源的 `Listeners` 集合中删除侦听器。</span><span class="sxs-lookup"><span data-stu-id="bdb93-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="bdb93-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bdb93-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bdb93-105">&nbsp;&nbsp;[ **\<的 >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="bdb93-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="bdb93-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](sources-element.md) ></span><span class="sxs-lookup"><span data-stu-id="bdb93-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="bdb93-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **&nbsp;&nbsp;\<** ](source-element.md) ></span><span class="sxs-lookup"><span data-stu-id="bdb93-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="bdb93-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**侦听器 >** ](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="bdb93-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="bdb93-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<删除 >**</span><span class="sxs-lookup"><span data-stu-id="bdb93-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="bdb93-110">语法</span><span class="sxs-lookup"><span data-stu-id="bdb93-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bdb93-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="bdb93-111">Attributes and Elements</span></span>  
 <span data-ttu-id="bdb93-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="bdb93-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bdb93-113">特性</span><span class="sxs-lookup"><span data-stu-id="bdb93-113">Attributes</span></span>  
  
|<span data-ttu-id="bdb93-114">特性</span><span class="sxs-lookup"><span data-stu-id="bdb93-114">Attribute</span></span>|<span data-ttu-id="bdb93-115">描述</span><span class="sxs-lookup"><span data-stu-id="bdb93-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="bdb93-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="bdb93-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="bdb93-117">要从 `Listeners` 集合中删除的侦听器的名称。</span><span class="sxs-lookup"><span data-stu-id="bdb93-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bdb93-118">子元素</span><span class="sxs-lookup"><span data-stu-id="bdb93-118">Child Elements</span></span>  
 <span data-ttu-id="bdb93-119">无。</span><span class="sxs-lookup"><span data-stu-id="bdb93-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bdb93-120">父元素</span><span class="sxs-lookup"><span data-stu-id="bdb93-120">Parent Elements</span></span>  
  
|<span data-ttu-id="bdb93-121">元素</span><span class="sxs-lookup"><span data-stu-id="bdb93-121">Element</span></span>|<span data-ttu-id="bdb93-122">描述</span><span class="sxs-lookup"><span data-stu-id="bdb93-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bdb93-123">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="bdb93-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="bdb93-124">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="bdb93-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="bdb93-125">包含用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="bdb93-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="bdb93-126">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="bdb93-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="bdb93-127">指定用于收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="bdb93-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bdb93-128">备注</span><span class="sxs-lookup"><span data-stu-id="bdb93-128">Remarks</span></span>  
 <span data-ttu-id="bdb93-129">`<remove>` 元素从跟踪源的 `Listeners` 集合中删除指定的侦听器。</span><span class="sxs-lookup"><span data-stu-id="bdb93-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="bdb93-130">您可以通过对 <xref:System.Diagnostics.TraceSource> 实例的 <xref:System.Diagnostics.TraceSource.Listeners%2A> 属性调用 <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> 方法，以编程方式从跟踪源的 `Listeners` 集合中删除元素。</span><span class="sxs-lookup"><span data-stu-id="bdb93-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="bdb93-131">此元素可在计算机配置文件（Machine.config）和应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="bdb93-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bdb93-132">示例</span><span class="sxs-lookup"><span data-stu-id="bdb93-132">Example</span></span>  
 <span data-ttu-id="bdb93-133">下面的示例演示如何使用 `<remove>` 元素，然后再使用 `<add>` 元素将侦听器 `console` 添加到跟踪源 `TraceSourceApp`的 `Listeners` 集合。</span><span class="sxs-lookup"><span data-stu-id="bdb93-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bdb93-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="bdb93-134">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="bdb93-135">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="bdb93-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="bdb93-136">\<clear></span><span class="sxs-lookup"><span data-stu-id="bdb93-136">\<clear></span></span>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="bdb93-137">跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="bdb93-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
