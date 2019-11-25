---
title: <trace> 的 <listeners> 的 <remove> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: f06973ec30d5061e4a200d6bf7e68adcf6302018
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088837"
---
# <a name="remove-element-for-listeners-for-trace"></a><span data-ttu-id="c3260-102">\<删除 \<跟踪的 \<侦听器 > > 元素 ></span><span class="sxs-lookup"><span data-stu-id="c3260-102">\<remove> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="c3260-103">从**侦听器**集合中删除侦听器。</span><span class="sxs-lookup"><span data-stu-id="c3260-103">Removes a listener from the **Listeners** collection.</span></span>  

<span data-ttu-id="c3260-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c3260-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c3260-105">&nbsp;&nbsp;[ **\<的 >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="c3260-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="c3260-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="c3260-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="c3260-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**侦听器**](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="c3260-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="c3260-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<删除 >**</span><span class="sxs-lookup"><span data-stu-id="c3260-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="c3260-109">语法</span><span class="sxs-lookup"><span data-stu-id="c3260-109">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3260-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c3260-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c3260-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c3260-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c3260-112">特性</span><span class="sxs-lookup"><span data-stu-id="c3260-112">Attributes</span></span>  
  
|<span data-ttu-id="c3260-113">特性</span><span class="sxs-lookup"><span data-stu-id="c3260-113">Attribute</span></span>|<span data-ttu-id="c3260-114">描述</span><span class="sxs-lookup"><span data-stu-id="c3260-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c3260-115">**name**</span><span class="sxs-lookup"><span data-stu-id="c3260-115">**name**</span></span>|<span data-ttu-id="c3260-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="c3260-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="c3260-117">要从**侦听器**集合中删除的侦听器的名称。</span><span class="sxs-lookup"><span data-stu-id="c3260-117">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c3260-118">子元素</span><span class="sxs-lookup"><span data-stu-id="c3260-118">Child Elements</span></span>  
 <span data-ttu-id="c3260-119">无。</span><span class="sxs-lookup"><span data-stu-id="c3260-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c3260-120">父元素</span><span class="sxs-lookup"><span data-stu-id="c3260-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c3260-121">元素</span><span class="sxs-lookup"><span data-stu-id="c3260-121">Element</span></span>|<span data-ttu-id="c3260-122">描述</span><span class="sxs-lookup"><span data-stu-id="c3260-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c3260-123">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="c3260-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="c3260-124">指定用于收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="c3260-124">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="c3260-125">侦听器将跟踪输出定向到适当的目标。</span><span class="sxs-lookup"><span data-stu-id="c3260-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="c3260-126">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="c3260-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="c3260-127">配置 ASP.NET 跟踪服务。</span><span class="sxs-lookup"><span data-stu-id="c3260-127">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3260-128">备注</span><span class="sxs-lookup"><span data-stu-id="c3260-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c3260-129">从 `Listeners` 集合中删除 <xref:System.Diagnostics.DefaultTraceListener> 会改变 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>、<xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>、<xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>和 <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> 方法的行为。</span><span class="sxs-lookup"><span data-stu-id="c3260-129">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="c3260-130">通常调用 `Assert` 或 `Fail` 方法会导致显示消息框，但如果 <xref:System.Diagnostics.DefaultTraceListener> 不在 `Listeners` 集合中，则不会显示消息框。</span><span class="sxs-lookup"><span data-stu-id="c3260-130">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3260-131">示例</span><span class="sxs-lookup"><span data-stu-id="c3260-131">Example</span></span>  
 <span data-ttu-id="c3260-132">下面的示例演示如何从跟踪**侦听器**集合中删除默认的跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="c3260-132">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <remove name="Default" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c3260-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="c3260-133">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="c3260-134">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="c3260-134">Trace and Debug Settings Schema</span></span>](index.md)
