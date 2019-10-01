---
title: <source> 的 @no__t <listeners> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 4a11308278f755ec8271477352d91d8797d105c5
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699487"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="39aa6-102">\<remove > 元素，用于 2source @no__t 的 \<listeners ></span><span class="sxs-lookup"><span data-stu-id="39aa6-102">\<remove> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="39aa6-103">从跟踪源的 `Listeners` 集合中删除侦听器。</span><span class="sxs-lookup"><span data-stu-id="39aa6-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  
  
[<span data-ttu-id="39aa6-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="39aa6-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="39aa6-105">&nbsp; @ no__t-1[ **\<system >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="39aa6-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="39aa6-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<sources >** ](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="39aa6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="39aa6-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<source >** ](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="39aa6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="39aa6-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0listeners >** ](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="39aa6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>  
<span data-ttu-id="39aa6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<remove>**</span><span class="sxs-lookup"><span data-stu-id="39aa6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39aa6-110">语法</span><span class="sxs-lookup"><span data-stu-id="39aa6-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39aa6-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="39aa6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="39aa6-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="39aa6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39aa6-113">特性</span><span class="sxs-lookup"><span data-stu-id="39aa6-113">Attributes</span></span>  
  
|<span data-ttu-id="39aa6-114">特性</span><span class="sxs-lookup"><span data-stu-id="39aa6-114">Attribute</span></span>|<span data-ttu-id="39aa6-115">描述</span><span class="sxs-lookup"><span data-stu-id="39aa6-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="39aa6-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="39aa6-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="39aa6-117">要从 @no__t 集合中删除的侦听器的名称。</span><span class="sxs-lookup"><span data-stu-id="39aa6-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="39aa6-118">子元素</span><span class="sxs-lookup"><span data-stu-id="39aa6-118">Child Elements</span></span>  
 <span data-ttu-id="39aa6-119">无。</span><span class="sxs-lookup"><span data-stu-id="39aa6-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="39aa6-120">父元素</span><span class="sxs-lookup"><span data-stu-id="39aa6-120">Parent Elements</span></span>  
  
|<span data-ttu-id="39aa6-121">元素</span><span class="sxs-lookup"><span data-stu-id="39aa6-121">Element</span></span>|<span data-ttu-id="39aa6-122">描述</span><span class="sxs-lookup"><span data-stu-id="39aa6-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="39aa6-123">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="39aa6-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="39aa6-124">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="39aa6-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="39aa6-125">包含用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="39aa6-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="39aa6-126">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="39aa6-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="39aa6-127">指定用于收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="39aa6-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39aa6-128">备注</span><span class="sxs-lookup"><span data-stu-id="39aa6-128">Remarks</span></span>  
 <span data-ttu-id="39aa6-129">@No__t 0 元素从跟踪源的 @no__t 集合中删除指定的侦听器。</span><span class="sxs-lookup"><span data-stu-id="39aa6-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="39aa6-130">可以通过对 @no__t 实例的 <xref:System.Diagnostics.TraceSource.Listeners%2A> 属性调用 <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> 方法，以编程方式从跟踪源的 @no__t 集合中删除元素。</span><span class="sxs-lookup"><span data-stu-id="39aa6-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="39aa6-131">此元素可在计算机配置文件（Machine.config）和应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="39aa6-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39aa6-132">示例</span><span class="sxs-lookup"><span data-stu-id="39aa6-132">Example</span></span>  
 <span data-ttu-id="39aa6-133">下面的示例演示了如何使用 `<remove>` 元素，然后再使用 `<add>` 元素将侦听器 `console` 添加到跟踪源 `TraceSourceApp` 的 @no__t 集合。</span><span class="sxs-lookup"><span data-stu-id="39aa6-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="39aa6-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="39aa6-134">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="39aa6-135">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="39aa6-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="39aa6-136">\<clear></span><span class="sxs-lookup"><span data-stu-id="39aa6-136">\<clear></span></span>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="39aa6-137">跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="39aa6-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
