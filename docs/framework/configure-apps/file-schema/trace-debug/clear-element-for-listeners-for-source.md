---
title: <clear> 元素<listeners>为 <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 63d3bb272fcdbee2c59b0569c85f8183cdac8666
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158348"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="1c055-102">\<清除 > 元素\<侦听器 > 为\<源 ></span><span class="sxs-lookup"><span data-stu-id="1c055-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="1c055-103">清除跟踪源的 `Listeners` 集合。</span><span class="sxs-lookup"><span data-stu-id="1c055-103">Clears the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="1c055-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1c055-104">\<configuration></span></span>  
<span data-ttu-id="1c055-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="1c055-105">\<system.diagnostics></span></span>  
<span data-ttu-id="1c055-106">\<sources></span><span class="sxs-lookup"><span data-stu-id="1c055-106">\<sources></span></span>  
<span data-ttu-id="1c055-107">\<source></span><span class="sxs-lookup"><span data-stu-id="1c055-107">\<source></span></span>  
<span data-ttu-id="1c055-108">\<listeners></span><span class="sxs-lookup"><span data-stu-id="1c055-108">\<listeners></span></span>  
<span data-ttu-id="1c055-109">\<clear></span><span class="sxs-lookup"><span data-stu-id="1c055-109">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c055-110">语法</span><span class="sxs-lookup"><span data-stu-id="1c055-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c055-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1c055-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1c055-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1c055-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c055-113">特性</span><span class="sxs-lookup"><span data-stu-id="1c055-113">Attributes</span></span>  
 <span data-ttu-id="1c055-114">无。</span><span class="sxs-lookup"><span data-stu-id="1c055-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1c055-115">子元素</span><span class="sxs-lookup"><span data-stu-id="1c055-115">Child Elements</span></span>  
 <span data-ttu-id="1c055-116">无。</span><span class="sxs-lookup"><span data-stu-id="1c055-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1c055-117">父元素</span><span class="sxs-lookup"><span data-stu-id="1c055-117">Parent Elements</span></span>  
  
|<span data-ttu-id="1c055-118">元素</span><span class="sxs-lookup"><span data-stu-id="1c055-118">Element</span></span>|<span data-ttu-id="1c055-119">描述</span><span class="sxs-lookup"><span data-stu-id="1c055-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1c055-120">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="1c055-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="1c055-121">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="1c055-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="1c055-122">包含用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="1c055-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="1c055-123">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="1c055-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="1c055-124">指定侦听器，用于收集、 存储和路由消息。</span><span class="sxs-lookup"><span data-stu-id="1c055-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c055-125">备注</span><span class="sxs-lookup"><span data-stu-id="1c055-125">Remarks</span></span>  
 <span data-ttu-id="1c055-126">`<clear>`元素中移除所有侦听器`Listeners`集合跟踪源，包括<xref:System.Diagnostics.DefaultTraceListener>。</span><span class="sxs-lookup"><span data-stu-id="1c055-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="1c055-127">可以使用`<clear>`元素之前使用`<add>`元素为特定集合中没有任何其他活动的侦听器。</span><span class="sxs-lookup"><span data-stu-id="1c055-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="1c055-128">配置文件</span><span class="sxs-lookup"><span data-stu-id="1c055-128">Configuration File</span></span>  
 <span data-ttu-id="1c055-129">计算机配置文件 (Machine.config) 和应用程序配置文件中，可以使用此元素。</span><span class="sxs-lookup"><span data-stu-id="1c055-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c055-130">示例</span><span class="sxs-lookup"><span data-stu-id="1c055-130">Example</span></span>  
 <span data-ttu-id="1c055-131">下面的示例演示如何使用`<clear>`之前使用的元素`<add>`元素添加侦听器`console`并`textListener`到`Listeners`跟踪源集合`TraceSourceApp`。</span><span class="sxs-lookup"><span data-stu-id="1c055-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
       <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <clear/>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"   
        type="System.Diagnostics.TextWriterTraceListener"   
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="1c055-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c055-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="1c055-133">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="1c055-133">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="1c055-134">跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="1c055-134">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
