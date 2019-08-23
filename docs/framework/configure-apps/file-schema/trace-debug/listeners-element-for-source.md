---
title: <source> 的 <listeners> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
ms.openlocfilehash: 853bc94978218fd4d426e6070b3a36e20435cd6d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920490"
---
# <a name="listeners-element-for-source"></a><span data-ttu-id="bfc0f-102">\<源 > 的\<侦听器 > 元素</span><span class="sxs-lookup"><span data-stu-id="bfc0f-102">\<listeners> Element for \<source></span></span>
<span data-ttu-id="bfc0f-103">在的<xref:System.Diagnostics.TraceSource.Listeners%2A>集合<xref:System.Diagnostics.TraceSource>中添加或移除侦听器。</span><span class="sxs-lookup"><span data-stu-id="bfc0f-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="bfc0f-104">侦听器将跟踪输出定向到适当的目标, 如日志、窗口或文本文件。</span><span class="sxs-lookup"><span data-stu-id="bfc0f-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
 <span data-ttu-id="bfc0f-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bfc0f-105">\<configuration></span></span>  
<span data-ttu-id="bfc0f-106">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="bfc0f-106">\<system.diagnostics></span></span>  
<span data-ttu-id="bfc0f-107">\<源 ></span><span class="sxs-lookup"><span data-stu-id="bfc0f-107">\<sources></span></span>  
<span data-ttu-id="bfc0f-108">\<源 ></span><span class="sxs-lookup"><span data-stu-id="bfc0f-108">\<source></span></span>  
<span data-ttu-id="bfc0f-109">\<侦听器 > 元素</span><span class="sxs-lookup"><span data-stu-id="bfc0f-109">\<listeners> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfc0f-110">语法</span><span class="sxs-lookup"><span data-stu-id="bfc0f-110">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bfc0f-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="bfc0f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="bfc0f-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="bfc0f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bfc0f-113">特性</span><span class="sxs-lookup"><span data-stu-id="bfc0f-113">Attributes</span></span>  
 <span data-ttu-id="bfc0f-114">无。</span><span class="sxs-lookup"><span data-stu-id="bfc0f-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bfc0f-115">子元素</span><span class="sxs-lookup"><span data-stu-id="bfc0f-115">Child Elements</span></span>  
  
|<span data-ttu-id="bfc0f-116">元素</span><span class="sxs-lookup"><span data-stu-id="bfc0f-116">Element</span></span>|<span data-ttu-id="bfc0f-117">描述</span><span class="sxs-lookup"><span data-stu-id="bfc0f-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bfc0f-118">\<add></span><span class="sxs-lookup"><span data-stu-id="bfc0f-118">\<add></span></span>](add-element-for-listeners-for-source.md)|<span data-ttu-id="bfc0f-119">将侦听器添加到 `Listeners` 集合中。</span><span class="sxs-lookup"><span data-stu-id="bfc0f-119">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="bfc0f-120">\<remove></span><span class="sxs-lookup"><span data-stu-id="bfc0f-120">\<remove></span></span>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="bfc0f-121">从`Listeners`集合中移除侦听器。</span><span class="sxs-lookup"><span data-stu-id="bfc0f-121">Removes a listener from the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="bfc0f-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="bfc0f-122">\<clear></span></span>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="bfc0f-123">清除跟踪源的 `Listeners` 集合。</span><span class="sxs-lookup"><span data-stu-id="bfc0f-123">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bfc0f-124">父元素</span><span class="sxs-lookup"><span data-stu-id="bfc0f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="bfc0f-125">元素</span><span class="sxs-lookup"><span data-stu-id="bfc0f-125">Element</span></span>|<span data-ttu-id="bfc0f-126">描述</span><span class="sxs-lookup"><span data-stu-id="bfc0f-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bfc0f-127">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="bfc0f-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="bfc0f-128">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="bfc0f-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="bfc0f-129">包含用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="bfc0f-129">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="bfc0f-130">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="bfc0f-130">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfc0f-131">备注</span><span class="sxs-lookup"><span data-stu-id="bfc0f-131">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="bfc0f-132">配置文件</span><span class="sxs-lookup"><span data-stu-id="bfc0f-132">Configuration File</span></span>  
 <span data-ttu-id="bfc0f-133">此元素可在计算机配置文件 (Machine.config) 和应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="bfc0f-133">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfc0f-134">示例</span><span class="sxs-lookup"><span data-stu-id="bfc0f-134">Example</span></span>  
 <span data-ttu-id="bfc0f-135">下面的示例演示如何使用`<listeners>`元素将控制台跟踪侦听器添加`mySource`到源, 并删除默认的跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="bfc0f-135">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bfc0f-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="bfc0f-136">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="bfc0f-137">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="bfc0f-137">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="bfc0f-138">跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="bfc0f-138">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
