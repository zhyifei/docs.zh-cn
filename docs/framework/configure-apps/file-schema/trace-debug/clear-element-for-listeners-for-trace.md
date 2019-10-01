---
title: <trace> 的 @no__t <listeners> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 0361580724351f8f42d058d5e20354e3335bac2f
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699371"
---
# <a name="clear-element-for-listeners-for-trace"></a><span data-ttu-id="b8b72-102">\<clear > 元素，用于 2trace @no__t 的 \<listeners ></span><span class="sxs-lookup"><span data-stu-id="b8b72-102">\<clear> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="b8b72-103">清除跟踪的 `Listeners` 集合。</span><span class="sxs-lookup"><span data-stu-id="b8b72-103">Clears the `Listeners` collection for trace.</span></span>  
  
[<span data-ttu-id="b8b72-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="b8b72-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="b8b72-105">&nbsp; @ no__t-1[ **\<system >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="b8b72-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="b8b72-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<trace >** ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="b8b72-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>  
<span data-ttu-id="b8b72-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<listeners >** ](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="b8b72-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>  
<span data-ttu-id="b8b72-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="b8b72-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8b72-109">语法</span><span class="sxs-lookup"><span data-stu-id="b8b72-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8b72-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b8b72-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b8b72-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b8b72-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8b72-112">特性</span><span class="sxs-lookup"><span data-stu-id="b8b72-112">Attributes</span></span>  
 <span data-ttu-id="b8b72-113">无。</span><span class="sxs-lookup"><span data-stu-id="b8b72-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b8b72-114">子元素</span><span class="sxs-lookup"><span data-stu-id="b8b72-114">Child Elements</span></span>  
 <span data-ttu-id="b8b72-115">无。</span><span class="sxs-lookup"><span data-stu-id="b8b72-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b8b72-116">父元素</span><span class="sxs-lookup"><span data-stu-id="b8b72-116">Parent Elements</span></span>  
  
|<span data-ttu-id="b8b72-117">元素</span><span class="sxs-lookup"><span data-stu-id="b8b72-117">Element</span></span>|<span data-ttu-id="b8b72-118">描述</span><span class="sxs-lookup"><span data-stu-id="b8b72-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b8b72-119">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="b8b72-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b8b72-120">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="b8b72-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="b8b72-121">包含用于收集、存储和路由跟踪消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="b8b72-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="b8b72-122">包含收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="b8b72-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="b8b72-123">侦听器将跟踪输出定向到适当的目标。</span><span class="sxs-lookup"><span data-stu-id="b8b72-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8b72-124">备注</span><span class="sxs-lookup"><span data-stu-id="b8b72-124">Remarks</span></span>  
 <span data-ttu-id="b8b72-125">@No__t-0 元素从 trace 的 @no__t 集合中删除所有侦听器。</span><span class="sxs-lookup"><span data-stu-id="b8b72-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="b8b72-126">你可以使用 `<clear>` 元素，然后才能使用 @no__t 元素，以确定集合中没有其他活动的侦听器。</span><span class="sxs-lookup"><span data-stu-id="b8b72-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="b8b72-127">可以通过在 <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> 属性（`System.Diagnostics.Trace.Listeners.Clear()`）上调用 <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> 方法，以编程方式清除 `Listeners` 收集。</span><span class="sxs-lookup"><span data-stu-id="b8b72-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="b8b72-128">此元素可在计算机配置文件（Machine.config）和应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="b8b72-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b8b72-129">@No__t-0 元素从 `Listeners` 集合中删除 <xref:System.Diagnostics.DefaultTraceListener>，改变 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>、@no__t、@no__t 和 @no__t 方法的行为。</span><span class="sxs-lookup"><span data-stu-id="b8b72-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="b8b72-130">调用 @no__t 0 或 @no__t 方法通常会导致显示消息框。</span><span class="sxs-lookup"><span data-stu-id="b8b72-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="b8b72-131">但是，如果 <xref:System.Diagnostics.DefaultTraceListener> 不在 @no__t 集合中，则不会显示消息框。</span><span class="sxs-lookup"><span data-stu-id="b8b72-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8b72-132">示例</span><span class="sxs-lookup"><span data-stu-id="b8b72-132">Example</span></span>  
 <span data-ttu-id="b8b72-133">下面的示例演示如何使用 `<clear>` 元素，然后再使用 @no__t，将侦听器 `console` 添加到 trace 的 @no__t 集合。</span><span class="sxs-lookup"><span data-stu-id="b8b72-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b8b72-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="b8b72-134">See also</span></span>

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="b8b72-135">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="b8b72-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b8b72-136">\<remove></span><span class="sxs-lookup"><span data-stu-id="b8b72-136">\<remove></span></span>](remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="b8b72-137">跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="b8b72-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
