---
title: <source> 的 <listeners> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
ms.openlocfilehash: d7641611e5d8257b49bc6a6abd0a2fadfde66e91
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697292"
---
# <a name="listeners-element-for-source"></a><span data-ttu-id="5dfbb-102">\<source 的 @no__t 0listeners > 元素 ></span><span class="sxs-lookup"><span data-stu-id="5dfbb-102">\<listeners> Element for \<source></span></span>
<span data-ttu-id="5dfbb-103">在 @no__t 的 @no__t 集合中添加或删除侦听器。</span><span class="sxs-lookup"><span data-stu-id="5dfbb-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="5dfbb-104">侦听器将跟踪输出定向到适当的目标，如日志、窗口或文本文件。</span><span class="sxs-lookup"><span data-stu-id="5dfbb-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
[<span data-ttu-id="5dfbb-105"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="5dfbb-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="5dfbb-106">&nbsp; @ no__t-1[ **\<system >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="5dfbb-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="5dfbb-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<sources >** ](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="5dfbb-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="5dfbb-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<source >** ](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="5dfbb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="5dfbb-109">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<listeners >**</span><span class="sxs-lookup"><span data-stu-id="5dfbb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dfbb-110">语法</span><span class="sxs-lookup"><span data-stu-id="5dfbb-110">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5dfbb-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5dfbb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5dfbb-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5dfbb-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5dfbb-113">特性</span><span class="sxs-lookup"><span data-stu-id="5dfbb-113">Attributes</span></span>  
 <span data-ttu-id="5dfbb-114">无。</span><span class="sxs-lookup"><span data-stu-id="5dfbb-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5dfbb-115">子元素</span><span class="sxs-lookup"><span data-stu-id="5dfbb-115">Child Elements</span></span>  
  
|<span data-ttu-id="5dfbb-116">元素</span><span class="sxs-lookup"><span data-stu-id="5dfbb-116">Element</span></span>|<span data-ttu-id="5dfbb-117">描述</span><span class="sxs-lookup"><span data-stu-id="5dfbb-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5dfbb-118">\<add></span><span class="sxs-lookup"><span data-stu-id="5dfbb-118">\<add></span></span>](add-element-for-listeners-for-source.md)|<span data-ttu-id="5dfbb-119">将侦听器添加到 `Listeners` 集合中。</span><span class="sxs-lookup"><span data-stu-id="5dfbb-119">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="5dfbb-120">\<remove></span><span class="sxs-lookup"><span data-stu-id="5dfbb-120">\<remove></span></span>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="5dfbb-121">从 @no__t 集合中删除侦听器。</span><span class="sxs-lookup"><span data-stu-id="5dfbb-121">Removes a listener from the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="5dfbb-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="5dfbb-122">\<clear></span></span>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="5dfbb-123">清除跟踪源的 `Listeners` 集合。</span><span class="sxs-lookup"><span data-stu-id="5dfbb-123">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5dfbb-124">父元素</span><span class="sxs-lookup"><span data-stu-id="5dfbb-124">Parent Elements</span></span>  
  
|<span data-ttu-id="5dfbb-125">元素</span><span class="sxs-lookup"><span data-stu-id="5dfbb-125">Element</span></span>|<span data-ttu-id="5dfbb-126">描述</span><span class="sxs-lookup"><span data-stu-id="5dfbb-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5dfbb-127">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="5dfbb-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="5dfbb-128">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="5dfbb-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="5dfbb-129">包含用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="5dfbb-129">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="5dfbb-130">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="5dfbb-130">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5dfbb-131">备注</span><span class="sxs-lookup"><span data-stu-id="5dfbb-131">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="5dfbb-132">配置文件</span><span class="sxs-lookup"><span data-stu-id="5dfbb-132">Configuration File</span></span>  
 <span data-ttu-id="5dfbb-133">此元素可在计算机配置文件（Machine.config）和应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="5dfbb-133">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5dfbb-134">示例</span><span class="sxs-lookup"><span data-stu-id="5dfbb-134">Example</span></span>  
 <span data-ttu-id="5dfbb-135">下面的示例演示如何使用 `<listeners>` 元素向 @no__t 源添加控制台跟踪侦听器，并删除默认的跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="5dfbb-135">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5dfbb-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="5dfbb-136">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="5dfbb-137">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="5dfbb-137">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5dfbb-138">跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="5dfbb-138">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
