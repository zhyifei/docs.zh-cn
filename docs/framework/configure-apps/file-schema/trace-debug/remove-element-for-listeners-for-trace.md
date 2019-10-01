---
title: <trace> 的 @no__t <listeners> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: 56d1e56514aed98d5f3b9f7363e461af6ac68a8c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697221"
---
# <a name="remove-element-for-listeners-for-trace"></a><span data-ttu-id="b9461-102">\<remove > 元素，用于 2trace @no__t 的 \<listeners ></span><span class="sxs-lookup"><span data-stu-id="b9461-102">\<remove> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="b9461-103">从**侦听器**集合中删除侦听器。</span><span class="sxs-lookup"><span data-stu-id="b9461-103">Removes a listener from the **Listeners** collection.</span></span>  
  
[<span data-ttu-id="b9461-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="b9461-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="b9461-105">&nbsp; @ no__t-1[ **\<system >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="b9461-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="b9461-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<trace >** ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="b9461-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>  
<span data-ttu-id="b9461-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<listeners >** ](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="b9461-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>  
<span data-ttu-id="b9461-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<remove >**</span><span class="sxs-lookup"><span data-stu-id="b9461-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9461-109">语法</span><span class="sxs-lookup"><span data-stu-id="b9461-109">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b9461-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b9461-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b9461-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b9461-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b9461-112">特性</span><span class="sxs-lookup"><span data-stu-id="b9461-112">Attributes</span></span>  
  
|<span data-ttu-id="b9461-113">特性</span><span class="sxs-lookup"><span data-stu-id="b9461-113">Attribute</span></span>|<span data-ttu-id="b9461-114">描述</span><span class="sxs-lookup"><span data-stu-id="b9461-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b9461-115">**name**</span><span class="sxs-lookup"><span data-stu-id="b9461-115">**name**</span></span>|<span data-ttu-id="b9461-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="b9461-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="b9461-117">要从**侦听器**集合中删除的侦听器的名称。</span><span class="sxs-lookup"><span data-stu-id="b9461-117">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b9461-118">子元素</span><span class="sxs-lookup"><span data-stu-id="b9461-118">Child Elements</span></span>  
 <span data-ttu-id="b9461-119">无。</span><span class="sxs-lookup"><span data-stu-id="b9461-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b9461-120">父元素</span><span class="sxs-lookup"><span data-stu-id="b9461-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b9461-121">元素</span><span class="sxs-lookup"><span data-stu-id="b9461-121">Element</span></span>|<span data-ttu-id="b9461-122">描述</span><span class="sxs-lookup"><span data-stu-id="b9461-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b9461-123">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="b9461-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="b9461-124">指定用于收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="b9461-124">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="b9461-125">侦听器将跟踪输出定向到适当的目标。</span><span class="sxs-lookup"><span data-stu-id="b9461-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b9461-126">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="b9461-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="b9461-127">配置 ASP.NET 跟踪服务。</span><span class="sxs-lookup"><span data-stu-id="b9461-127">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9461-128">备注</span><span class="sxs-lookup"><span data-stu-id="b9461-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b9461-129">从 @no__t 集合中删除 @no__t 0 会改变 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>、<xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>、@no__t、@no__t 和方法的行为。</span><span class="sxs-lookup"><span data-stu-id="b9461-129">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="b9461-130">调用 @no__t 0 或 @no__t 方法通常会导致显示消息框，但如果 <xref:System.Diagnostics.DefaultTraceListener> 不在 @no__t 集合中，则不会显示消息框。</span><span class="sxs-lookup"><span data-stu-id="b9461-130">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9461-131">示例</span><span class="sxs-lookup"><span data-stu-id="b9461-131">Example</span></span>  
 <span data-ttu-id="b9461-132">下面的示例演示如何从跟踪**侦听器**集合中删除默认的跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="b9461-132">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b9461-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9461-133">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="b9461-134">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="b9461-134">Trace and Debug Settings Schema</span></span>](index.md)
