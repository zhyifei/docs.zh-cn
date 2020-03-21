---
title: <clear>用于<listeners><trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 905dad8274fede80f4809ff3c7a014049f9df450
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153537"
---
# <a name="clear-element-for-listeners-for-trace"></a><span data-ttu-id="c0544-102">\<清除>元素，\<用于>跟踪\<>的侦听器</span><span class="sxs-lookup"><span data-stu-id="c0544-102">\<clear> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="c0544-103">清除跟踪的 `Listeners` 集合。</span><span class="sxs-lookup"><span data-stu-id="c0544-103">Clears the `Listeners` collection for trace.</span></span>  

<span data-ttu-id="c0544-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c0544-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c0544-105">&nbsp;&nbsp;[**\<系统.诊断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="c0544-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="c0544-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<跟踪>**](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="c0544-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="c0544-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<听众>**](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="c0544-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="c0544-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<明确>**</span><span class="sxs-lookup"><span data-stu-id="c0544-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="c0544-109">语法</span><span class="sxs-lookup"><span data-stu-id="c0544-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0544-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c0544-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c0544-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c0544-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0544-112">属性</span><span class="sxs-lookup"><span data-stu-id="c0544-112">Attributes</span></span>  
 <span data-ttu-id="c0544-113">无。</span><span class="sxs-lookup"><span data-stu-id="c0544-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c0544-114">子元素</span><span class="sxs-lookup"><span data-stu-id="c0544-114">Child Elements</span></span>  
 <span data-ttu-id="c0544-115">无。</span><span class="sxs-lookup"><span data-stu-id="c0544-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0544-116">父元素</span><span class="sxs-lookup"><span data-stu-id="c0544-116">Parent Elements</span></span>  
  
|<span data-ttu-id="c0544-117">元素</span><span class="sxs-lookup"><span data-stu-id="c0544-117">Element</span></span>|<span data-ttu-id="c0544-118">说明</span><span class="sxs-lookup"><span data-stu-id="c0544-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c0544-119">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="c0544-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="c0544-120">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="c0544-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="c0544-121">包含用于收集、存储和路由跟踪消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="c0544-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="c0544-122">包含收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="c0544-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="c0544-123">侦听器将跟踪输出定向到适当的目标。</span><span class="sxs-lookup"><span data-stu-id="c0544-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0544-124">备注</span><span class="sxs-lookup"><span data-stu-id="c0544-124">Remarks</span></span>  
 <span data-ttu-id="c0544-125">该`<clear>`元素从跟踪集合中删除`Listeners`所有侦听器。</span><span class="sxs-lookup"><span data-stu-id="c0544-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="c0544-126">在使用 元素`<clear>`之前，`<add>`可以使用 该元素来确定集合中没有其他活动侦听器。</span><span class="sxs-lookup"><span data-stu-id="c0544-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="c0544-127">您可以通过`Listeners`在<xref:System.Diagnostics.TraceListenerCollection.Clear%2A><xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType>属性上调用 方法 （）`System.Diagnostics.Trace.Listeners.Clear()`以编程方式清除集合。</span><span class="sxs-lookup"><span data-stu-id="c0544-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="c0544-128">此元素可用于计算机配置文件 （Machine.config） 和应用程序配置文件。</span><span class="sxs-lookup"><span data-stu-id="c0544-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c0544-129">元素`<clear>`从<xref:System.Diagnostics.DefaultTraceListener>`Listeners`集合中删除 ， 更改<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>、 、<xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>和<xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>方法的行为。</span><span class="sxs-lookup"><span data-stu-id="c0544-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="c0544-130">调用`Assert`或`Fail`方法通常会导致显示消息框。</span><span class="sxs-lookup"><span data-stu-id="c0544-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="c0544-131">但是，如果 不在<xref:System.Diagnostics.DefaultTraceListener>`Listeners`集合中，则不会显示消息框。</span><span class="sxs-lookup"><span data-stu-id="c0544-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0544-132">示例</span><span class="sxs-lookup"><span data-stu-id="c0544-132">Example</span></span>  
 <span data-ttu-id="c0544-133">下面的示例`<clear>`演示如何在使用`<add>`元素将侦听器`console`添加到跟踪`Listeners`集合之前使用元素。</span><span class="sxs-lookup"><span data-stu-id="c0544-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="c0544-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c0544-134">See also</span></span>

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="c0544-135">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="c0544-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c0544-136">\<删除></span><span class="sxs-lookup"><span data-stu-id="c0544-136">\<remove></span></span>](remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="c0544-137">跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="c0544-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
