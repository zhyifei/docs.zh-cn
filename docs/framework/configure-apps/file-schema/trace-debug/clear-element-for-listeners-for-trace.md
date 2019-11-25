---
title: <trace> 的 <listeners> 的 <clear> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 049b8e7ed17633c0f34b062915afaf719927dad6
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088919"
---
# <a name="clear-element-for-listeners-for-trace"></a><span data-ttu-id="90ff3-102">\<清除 \<跟踪的 \<侦听器 > > 元素 ></span><span class="sxs-lookup"><span data-stu-id="90ff3-102">\<clear> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="90ff3-103">清除跟踪的 `Listeners` 集合。</span><span class="sxs-lookup"><span data-stu-id="90ff3-103">Clears the `Listeners` collection for trace.</span></span>  

<span data-ttu-id="90ff3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="90ff3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="90ff3-105">&nbsp;&nbsp;[ **\<的 >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="90ff3-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="90ff3-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="90ff3-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="90ff3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**侦听器**](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="90ff3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="90ff3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="90ff3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="90ff3-109">语法</span><span class="sxs-lookup"><span data-stu-id="90ff3-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90ff3-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="90ff3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="90ff3-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="90ff3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90ff3-112">特性</span><span class="sxs-lookup"><span data-stu-id="90ff3-112">Attributes</span></span>  
 <span data-ttu-id="90ff3-113">无。</span><span class="sxs-lookup"><span data-stu-id="90ff3-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="90ff3-114">子元素</span><span class="sxs-lookup"><span data-stu-id="90ff3-114">Child Elements</span></span>  
 <span data-ttu-id="90ff3-115">无。</span><span class="sxs-lookup"><span data-stu-id="90ff3-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="90ff3-116">父元素</span><span class="sxs-lookup"><span data-stu-id="90ff3-116">Parent Elements</span></span>  
  
|<span data-ttu-id="90ff3-117">元素</span><span class="sxs-lookup"><span data-stu-id="90ff3-117">Element</span></span>|<span data-ttu-id="90ff3-118">描述</span><span class="sxs-lookup"><span data-stu-id="90ff3-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="90ff3-119">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="90ff3-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="90ff3-120">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="90ff3-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="90ff3-121">包含用于收集、存储和路由跟踪消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="90ff3-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="90ff3-122">包含收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="90ff3-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="90ff3-123">侦听器将跟踪输出定向到适当的目标。</span><span class="sxs-lookup"><span data-stu-id="90ff3-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90ff3-124">备注</span><span class="sxs-lookup"><span data-stu-id="90ff3-124">Remarks</span></span>  
 <span data-ttu-id="90ff3-125">`<clear>` 元素从跟踪的 `Listeners` 集合中删除所有侦听器。</span><span class="sxs-lookup"><span data-stu-id="90ff3-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="90ff3-126">在使用 `<add>` 元素之前，可以使用 `<clear>` 元素，以确定集合中没有其他活动侦听器。</span><span class="sxs-lookup"><span data-stu-id="90ff3-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="90ff3-127">您可以通过在 <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> 属性（`System.Diagnostics.Trace.Listeners.Clear()`）上调用 <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> 方法，以编程方式清除 `Listeners` 收集。</span><span class="sxs-lookup"><span data-stu-id="90ff3-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="90ff3-128">此元素可在计算机配置文件（Machine.config）和应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="90ff3-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="90ff3-129">`<clear>` 元素从 `Listeners` 集合中删除 <xref:System.Diagnostics.DefaultTraceListener>，从而更改 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>、<xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>、<xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>和 <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> 方法的行为。</span><span class="sxs-lookup"><span data-stu-id="90ff3-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="90ff3-130">通常调用 `Assert` 或 `Fail` 方法会导致显示消息框。</span><span class="sxs-lookup"><span data-stu-id="90ff3-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="90ff3-131">但是，如果 <xref:System.Diagnostics.DefaultTraceListener> 不在 `Listeners` 集合中，则不会显示消息框。</span><span class="sxs-lookup"><span data-stu-id="90ff3-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90ff3-132">示例</span><span class="sxs-lookup"><span data-stu-id="90ff3-132">Example</span></span>  
 <span data-ttu-id="90ff3-133">下面的示例演示如何使用 `<clear>` 元素，然后再使用 `<add>` 元素将侦听器 `console` 添加到跟踪的 `Listeners` 集合。</span><span class="sxs-lookup"><span data-stu-id="90ff3-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="90ff3-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="90ff3-134">See also</span></span>

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="90ff3-135">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="90ff3-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="90ff3-136">\<remove></span><span class="sxs-lookup"><span data-stu-id="90ff3-136">\<remove></span></span>](remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="90ff3-137">跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="90ff3-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
