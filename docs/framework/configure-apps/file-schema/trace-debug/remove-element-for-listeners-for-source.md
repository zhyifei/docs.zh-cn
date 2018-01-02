---
title: "&lt;删除&gt;元素&lt;侦听器&gt;为&lt;源&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
caps.latest.revision: "6"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: b983c5eb80f958098b6991970559d077b97a0759
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltremovegt-element-for-ltlistenersgt-for-ltsourcegt"></a><span data-ttu-id="684e5-102">&lt;删除&gt;元素&lt;侦听器&gt;为&lt;源&gt;</span><span class="sxs-lookup"><span data-stu-id="684e5-102">&lt;remove&gt; Element for &lt;listeners&gt; for &lt;source&gt;</span></span>
<span data-ttu-id="684e5-103">从跟踪源的 `Listeners` 集合中删除侦听器。</span><span class="sxs-lookup"><span data-stu-id="684e5-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="684e5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="684e5-104">\<configuration></span></span>  
<span data-ttu-id="684e5-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="684e5-105">\<system.diagnostics></span></span>  
<span data-ttu-id="684e5-106">\<源 ></span><span class="sxs-lookup"><span data-stu-id="684e5-106">\<sources></span></span>  
<span data-ttu-id="684e5-107">\<源 ></span><span class="sxs-lookup"><span data-stu-id="684e5-107">\<source></span></span>  
<span data-ttu-id="684e5-108">\<侦听器 ></span><span class="sxs-lookup"><span data-stu-id="684e5-108">\<listeners></span></span>  
<span data-ttu-id="684e5-109">\<删除 ></span><span class="sxs-lookup"><span data-stu-id="684e5-109">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="684e5-110">语法</span><span class="sxs-lookup"><span data-stu-id="684e5-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="684e5-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="684e5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="684e5-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="684e5-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="684e5-113">特性</span><span class="sxs-lookup"><span data-stu-id="684e5-113">Attributes</span></span>  
  
|<span data-ttu-id="684e5-114">特性</span><span class="sxs-lookup"><span data-stu-id="684e5-114">Attribute</span></span>|<span data-ttu-id="684e5-115">描述</span><span class="sxs-lookup"><span data-stu-id="684e5-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="684e5-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="684e5-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="684e5-117">从删除的侦听器名称`Listeners`集合。</span><span class="sxs-lookup"><span data-stu-id="684e5-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="684e5-118">子元素</span><span class="sxs-lookup"><span data-stu-id="684e5-118">Child Elements</span></span>  
 <span data-ttu-id="684e5-119">无。</span><span class="sxs-lookup"><span data-stu-id="684e5-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="684e5-120">父元素</span><span class="sxs-lookup"><span data-stu-id="684e5-120">Parent Elements</span></span>  
  
|<span data-ttu-id="684e5-121">元素</span><span class="sxs-lookup"><span data-stu-id="684e5-121">Element</span></span>|<span data-ttu-id="684e5-122">说明</span><span class="sxs-lookup"><span data-stu-id="684e5-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="684e5-123">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="684e5-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="684e5-124">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="684e5-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="684e5-125">包含用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="684e5-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="684e5-126">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="684e5-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="684e5-127">指定收集、 存储和将消息路由的侦听器。</span><span class="sxs-lookup"><span data-stu-id="684e5-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="684e5-128">备注</span><span class="sxs-lookup"><span data-stu-id="684e5-128">Remarks</span></span>  
 <span data-ttu-id="684e5-129">`<remove>`元素中移除指定的侦听器从`Listeners`跟踪源的集合。</span><span class="sxs-lookup"><span data-stu-id="684e5-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="684e5-130">你可以删除从元素`Listeners`以编程方式通过调用跟踪源集合<xref:System.Diagnostics.TraceListenerCollection.Remove%2A>方法<xref:System.Diagnostics.TraceSource.Listeners%2A>属性<xref:System.Diagnostics.TraceSource>实例。</span><span class="sxs-lookup"><span data-stu-id="684e5-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="684e5-131">计算机配置文件 (Machine.config) 和应用程序配置文件中，可以使用此元素。</span><span class="sxs-lookup"><span data-stu-id="684e5-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="684e5-132">示例</span><span class="sxs-lookup"><span data-stu-id="684e5-132">Example</span></span>  
 <span data-ttu-id="684e5-133">下面的示例演示如何使用`<remove>`元素之前使用`<add>`元素添加侦听器`console`到`Listeners`跟踪源集合`TraceSourceApp`。</span><span class="sxs-lookup"><span data-stu-id="684e5-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="684e5-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="684e5-134">See Also</span></span>  
 <xref:System.Diagnostics.TraceSource.Listeners%2A>  
 <xref:System.Diagnostics.TraceSource>  
 [<span data-ttu-id="684e5-135">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="684e5-135">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="684e5-136">\<clear></span><span class="sxs-lookup"><span data-stu-id="684e5-136">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)  
 [<span data-ttu-id="684e5-137">跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="684e5-137">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
