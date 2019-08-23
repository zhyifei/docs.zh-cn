---
title: <clear><listeners>的元素<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 9816ba0f8e4ddd4c38537eb4e014a4240ff20407
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927168"
---
# <a name="clear-element-for-listeners-for-trace"></a><span data-ttu-id="da869-102">\<为\<跟踪 > 清除\<侦听器 > > 元素</span><span class="sxs-lookup"><span data-stu-id="da869-102">\<clear> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="da869-103">清除跟踪的 `Listeners` 集合。</span><span class="sxs-lookup"><span data-stu-id="da869-103">Clears the `Listeners` collection for trace.</span></span>  
  
 <span data-ttu-id="da869-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="da869-104">\<configuration></span></span>  
<span data-ttu-id="da869-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="da869-105">\<system.diagnostics></span></span>  
<span data-ttu-id="da869-106">\<trace></span><span class="sxs-lookup"><span data-stu-id="da869-106">\<trace></span></span>  
<span data-ttu-id="da869-107">\<侦听器 ></span><span class="sxs-lookup"><span data-stu-id="da869-107">\<listeners></span></span>  
<span data-ttu-id="da869-108">\<清除 ></span><span class="sxs-lookup"><span data-stu-id="da869-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da869-109">语法</span><span class="sxs-lookup"><span data-stu-id="da869-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da869-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="da869-110">Attributes and Elements</span></span>  
 <span data-ttu-id="da869-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="da869-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da869-112">特性</span><span class="sxs-lookup"><span data-stu-id="da869-112">Attributes</span></span>  
 <span data-ttu-id="da869-113">无。</span><span class="sxs-lookup"><span data-stu-id="da869-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="da869-114">子元素</span><span class="sxs-lookup"><span data-stu-id="da869-114">Child Elements</span></span>  
 <span data-ttu-id="da869-115">无。</span><span class="sxs-lookup"><span data-stu-id="da869-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="da869-116">父元素</span><span class="sxs-lookup"><span data-stu-id="da869-116">Parent Elements</span></span>  
  
|<span data-ttu-id="da869-117">元素</span><span class="sxs-lookup"><span data-stu-id="da869-117">Element</span></span>|<span data-ttu-id="da869-118">描述</span><span class="sxs-lookup"><span data-stu-id="da869-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="da869-119">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="da869-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="da869-120">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="da869-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="da869-121">包含用于收集、存储和路由跟踪消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="da869-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="da869-122">包含收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="da869-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="da869-123">侦听器将跟踪输出定向到适当的目标。</span><span class="sxs-lookup"><span data-stu-id="da869-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da869-124">备注</span><span class="sxs-lookup"><span data-stu-id="da869-124">Remarks</span></span>  
 <span data-ttu-id="da869-125">元素从跟踪的集合中移除所有侦听器。 `Listeners` `<clear>`</span><span class="sxs-lookup"><span data-stu-id="da869-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="da869-126">可以在`<clear>` `<add>`使用元素之前使用元素, 以确定集合中没有其他活动的侦听器。</span><span class="sxs-lookup"><span data-stu-id="da869-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="da869-127">您可以通过对`Listeners` <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType>属性(`System.Diagnostics.Trace.Listeners.Clear()`) 调用方法, 以编程方式清除该集合。</span><span class="sxs-lookup"><span data-stu-id="da869-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="da869-128">此元素可在计算机配置文件 (Machine.config) 和应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="da869-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da869-129"><xref:System.Diagnostics.DefaultTraceListener> <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>元素从`Listeners`集合中移除, 并更改、 、<xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>和<xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>方法的行为。 `<clear>`</span><span class="sxs-lookup"><span data-stu-id="da869-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="da869-130">通常调用`Fail`或方法会导致显示消息框。 `Assert`</span><span class="sxs-lookup"><span data-stu-id="da869-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="da869-131">但是, 如果<xref:System.Diagnostics.DefaultTraceListener>不`Listeners`在集合中, 则不会显示消息框。</span><span class="sxs-lookup"><span data-stu-id="da869-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da869-132">示例</span><span class="sxs-lookup"><span data-stu-id="da869-132">Example</span></span>  
 <span data-ttu-id="da869-133">下面的`<clear>`示例演示如何在`<add>`使用元素`Listeners`将侦听器`console`添加到用于 trace 的集合之前使用元素。</span><span class="sxs-lookup"><span data-stu-id="da869-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="da869-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="da869-134">See also</span></span>

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="da869-135">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="da869-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="da869-136">\<remove></span><span class="sxs-lookup"><span data-stu-id="da869-136">\<remove></span></span>](remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="da869-137">跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="da869-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
