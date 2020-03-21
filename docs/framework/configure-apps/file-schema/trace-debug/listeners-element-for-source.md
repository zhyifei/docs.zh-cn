---
title: <source> 的 <listeners> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
ms.openlocfilehash: 0eee325e01b41a15a19e4f40f479596f9d70f73b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153407"
---
# <a name="listeners-element-for-source"></a><span data-ttu-id="ccc73-102">\<源>的侦\<听器>元素</span><span class="sxs-lookup"><span data-stu-id="ccc73-102">\<listeners> Element for \<source></span></span>
<span data-ttu-id="ccc73-103">添加或删除 集合中的<xref:System.Diagnostics.TraceSource.Listeners%2A>侦听器。 <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ccc73-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="ccc73-104">侦听器将跟踪输出定向到适当的目标，如日志、窗口或文本文件。</span><span class="sxs-lookup"><span data-stu-id="ccc73-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
[<span data-ttu-id="ccc73-105">**\<配置>**</span><span class="sxs-lookup"><span data-stu-id="ccc73-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="ccc73-106">&nbsp;&nbsp;[**\<系统.诊断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="ccc73-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="ccc73-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<来源>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="ccc73-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="ccc73-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<源>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="ccc73-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="ccc73-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<听众>**</span><span class="sxs-lookup"><span data-stu-id="ccc73-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccc73-110">语法</span><span class="sxs-lookup"><span data-stu-id="ccc73-110">Syntax</span></span>  
  
```xml  
<listeners>
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ccc73-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ccc73-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ccc73-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ccc73-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ccc73-113">属性</span><span class="sxs-lookup"><span data-stu-id="ccc73-113">Attributes</span></span>  
 <span data-ttu-id="ccc73-114">无。</span><span class="sxs-lookup"><span data-stu-id="ccc73-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ccc73-115">子元素</span><span class="sxs-lookup"><span data-stu-id="ccc73-115">Child Elements</span></span>  
  
|<span data-ttu-id="ccc73-116">元素</span><span class="sxs-lookup"><span data-stu-id="ccc73-116">Element</span></span>|<span data-ttu-id="ccc73-117">说明</span><span class="sxs-lookup"><span data-stu-id="ccc73-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ccc73-118">\<添加></span><span class="sxs-lookup"><span data-stu-id="ccc73-118">\<add></span></span>](add-element-for-listeners-for-source.md)|<span data-ttu-id="ccc73-119">将侦听器添加到 `Listeners` 集合中。</span><span class="sxs-lookup"><span data-stu-id="ccc73-119">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="ccc73-120">\<删除></span><span class="sxs-lookup"><span data-stu-id="ccc73-120">\<remove></span></span>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="ccc73-121">从`Listeners`集合中删除侦听器。</span><span class="sxs-lookup"><span data-stu-id="ccc73-121">Removes a listener from the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="ccc73-122">\<明确></span><span class="sxs-lookup"><span data-stu-id="ccc73-122">\<clear></span></span>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="ccc73-123">清除跟踪源的 `Listeners` 集合。</span><span class="sxs-lookup"><span data-stu-id="ccc73-123">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ccc73-124">父元素</span><span class="sxs-lookup"><span data-stu-id="ccc73-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ccc73-125">元素</span><span class="sxs-lookup"><span data-stu-id="ccc73-125">Element</span></span>|<span data-ttu-id="ccc73-126">说明</span><span class="sxs-lookup"><span data-stu-id="ccc73-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ccc73-127">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="ccc73-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="ccc73-128">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="ccc73-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="ccc73-129">包含用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="ccc73-129">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="ccc73-130">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="ccc73-130">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ccc73-131">备注</span><span class="sxs-lookup"><span data-stu-id="ccc73-131">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="ccc73-132">配置文件</span><span class="sxs-lookup"><span data-stu-id="ccc73-132">Configuration File</span></span>  
 <span data-ttu-id="ccc73-133">此元素可用于计算机配置文件 （Machine.config） 和应用程序配置文件。</span><span class="sxs-lookup"><span data-stu-id="ccc73-133">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ccc73-134">示例</span><span class="sxs-lookup"><span data-stu-id="ccc73-134">Example</span></span>  
 <span data-ttu-id="ccc73-135">下面的示例演示如何使用 元素`<listeners>`向`mySource`源添加控制台跟踪侦听器并删除默认跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="ccc73-135">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"
            type="System.Diagnostics.ConsoleTraceListener">  
            <filter type="System.Diagnostics.EventTypeFilter"
              initializeData="Error"/>  
          </add>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ccc73-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ccc73-136">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="ccc73-137">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="ccc73-137">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ccc73-138">跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="ccc73-138">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
