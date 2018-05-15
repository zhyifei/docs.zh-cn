---
title: '&lt;删除&gt;元素&lt;侦听器&gt;为&lt;跟踪&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 11f4b648ac1ffc614f18a3686eb2b6508a272980
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltremovegt-element-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="0520c-102">&lt;删除&gt;元素&lt;侦听器&gt;为&lt;跟踪&gt;</span><span class="sxs-lookup"><span data-stu-id="0520c-102">&lt;remove&gt; Element for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="0520c-103">删除从侦听器**侦听器**集合。</span><span class="sxs-lookup"><span data-stu-id="0520c-103">Removes a listener from the **Listeners** collection.</span></span>  
  
 <span data-ttu-id="0520c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0520c-104">\<configuration></span></span>  
<span data-ttu-id="0520c-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="0520c-105">\<system.diagnostics></span></span>  
<span data-ttu-id="0520c-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="0520c-106">\<trace></span></span>  
<span data-ttu-id="0520c-107">\<侦听器 ></span><span class="sxs-lookup"><span data-stu-id="0520c-107">\<listeners></span></span>  
<span data-ttu-id="0520c-108">\<remove></span><span class="sxs-lookup"><span data-stu-id="0520c-108">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0520c-109">语法</span><span class="sxs-lookup"><span data-stu-id="0520c-109">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0520c-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0520c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0520c-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0520c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0520c-112">特性</span><span class="sxs-lookup"><span data-stu-id="0520c-112">Attributes</span></span>  
  
|<span data-ttu-id="0520c-113">特性</span><span class="sxs-lookup"><span data-stu-id="0520c-113">Attribute</span></span>|<span data-ttu-id="0520c-114">描述</span><span class="sxs-lookup"><span data-stu-id="0520c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0520c-115">**name**</span><span class="sxs-lookup"><span data-stu-id="0520c-115">**name**</span></span>|<span data-ttu-id="0520c-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="0520c-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="0520c-117">从删除的侦听器名称**侦听器**集合。</span><span class="sxs-lookup"><span data-stu-id="0520c-117">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0520c-118">子元素</span><span class="sxs-lookup"><span data-stu-id="0520c-118">Child Elements</span></span>  
 <span data-ttu-id="0520c-119">无。</span><span class="sxs-lookup"><span data-stu-id="0520c-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0520c-120">父元素</span><span class="sxs-lookup"><span data-stu-id="0520c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="0520c-121">元素</span><span class="sxs-lookup"><span data-stu-id="0520c-121">Element</span></span>|<span data-ttu-id="0520c-122">描述</span><span class="sxs-lookup"><span data-stu-id="0520c-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0520c-123">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="0520c-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="0520c-124">指定收集，侦听器存储区，并将消息路由。</span><span class="sxs-lookup"><span data-stu-id="0520c-124">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="0520c-125">侦听器将跟踪输出定向到适当的目标。</span><span class="sxs-lookup"><span data-stu-id="0520c-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="0520c-126">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="0520c-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="0520c-127">配置 ASP.NET 跟踪服务。</span><span class="sxs-lookup"><span data-stu-id="0520c-127">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0520c-128">备注</span><span class="sxs-lookup"><span data-stu-id="0520c-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0520c-129">删除<xref:System.Diagnostics.DefaultTraceListener>从`Listeners`集合会更改的行为<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>， <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>， <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>，和<xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="0520c-129">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="0520c-130">调用`Assert`或`Fail`方法通常会导致显示一个消息框，但如果不显示消息框<xref:System.Diagnostics.DefaultTraceListener>不在`Listeners`集合。</span><span class="sxs-lookup"><span data-stu-id="0520c-130">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0520c-131">示例</span><span class="sxs-lookup"><span data-stu-id="0520c-131">Example</span></span>  
 <span data-ttu-id="0520c-132">下面的示例演示如何从跟踪中删除默认跟踪侦听器**侦听器**集合。</span><span class="sxs-lookup"><span data-stu-id="0520c-132">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0520c-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="0520c-133">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 [<span data-ttu-id="0520c-134">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="0520c-134">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
