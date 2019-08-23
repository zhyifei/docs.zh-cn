---
title: <remove><listeners>的元素<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: 0c5c9efb8a22d26ea5d4467f9628af5935d6dbad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920477"
---
# <a name="remove-element-for-listeners-for-trace"></a><span data-ttu-id="40206-102">\<删除\< \<跟踪的侦听器 > > 元素 ></span><span class="sxs-lookup"><span data-stu-id="40206-102">\<remove> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="40206-103">从**侦听器**集合中删除侦听器。</span><span class="sxs-lookup"><span data-stu-id="40206-103">Removes a listener from the **Listeners** collection.</span></span>  
  
 <span data-ttu-id="40206-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="40206-104">\<configuration></span></span>  
<span data-ttu-id="40206-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="40206-105">\<system.diagnostics></span></span>  
<span data-ttu-id="40206-106">\<trace></span><span class="sxs-lookup"><span data-stu-id="40206-106">\<trace></span></span>  
<span data-ttu-id="40206-107">\<侦听器 ></span><span class="sxs-lookup"><span data-stu-id="40206-107">\<listeners></span></span>  
<span data-ttu-id="40206-108">\<remove></span><span class="sxs-lookup"><span data-stu-id="40206-108">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40206-109">语法</span><span class="sxs-lookup"><span data-stu-id="40206-109">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40206-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="40206-110">Attributes and Elements</span></span>  
 <span data-ttu-id="40206-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="40206-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40206-112">特性</span><span class="sxs-lookup"><span data-stu-id="40206-112">Attributes</span></span>  
  
|<span data-ttu-id="40206-113">特性</span><span class="sxs-lookup"><span data-stu-id="40206-113">Attribute</span></span>|<span data-ttu-id="40206-114">描述</span><span class="sxs-lookup"><span data-stu-id="40206-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="40206-115">**名称**</span><span class="sxs-lookup"><span data-stu-id="40206-115">**name**</span></span>|<span data-ttu-id="40206-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="40206-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="40206-117">要从**侦听器**集合中删除的侦听器的名称。</span><span class="sxs-lookup"><span data-stu-id="40206-117">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40206-118">子元素</span><span class="sxs-lookup"><span data-stu-id="40206-118">Child Elements</span></span>  
 <span data-ttu-id="40206-119">无。</span><span class="sxs-lookup"><span data-stu-id="40206-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40206-120">父元素</span><span class="sxs-lookup"><span data-stu-id="40206-120">Parent Elements</span></span>  
  
|<span data-ttu-id="40206-121">元素</span><span class="sxs-lookup"><span data-stu-id="40206-121">Element</span></span>|<span data-ttu-id="40206-122">描述</span><span class="sxs-lookup"><span data-stu-id="40206-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="40206-123">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="40206-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="40206-124">指定用于收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="40206-124">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="40206-125">侦听器将跟踪输出定向到适当的目标。</span><span class="sxs-lookup"><span data-stu-id="40206-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="40206-126">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="40206-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="40206-127">配置 ASP.NET 跟踪服务。</span><span class="sxs-lookup"><span data-stu-id="40206-127">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40206-128">备注</span><span class="sxs-lookup"><span data-stu-id="40206-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="40206-129"><xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>从集合中移除会改变、 、<xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>和<xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>方法的行为。 <xref:System.Diagnostics.DefaultTraceListener> `Listeners`</span><span class="sxs-lookup"><span data-stu-id="40206-129">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="40206-130">通常, 调用`Fail`或方法 <xref:System.Diagnostics.DefaultTraceListener>会导致显示消息框, 但是, 如果不在`Listeners`集合中, 则不会显示消息框。 `Assert`</span><span class="sxs-lookup"><span data-stu-id="40206-130">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40206-131">示例</span><span class="sxs-lookup"><span data-stu-id="40206-131">Example</span></span>  
 <span data-ttu-id="40206-132">下面的示例演示如何从跟踪**侦听器**集合中删除默认的跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="40206-132">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="40206-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="40206-133">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="40206-134">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="40206-134">Trace and Debug Settings Schema</span></span>](index.md)
