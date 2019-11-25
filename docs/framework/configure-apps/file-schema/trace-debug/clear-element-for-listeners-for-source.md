---
title: <source> 的 <listeners> 的 <clear> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 4567f236397435e89371ca4c80730ff964fddd21
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088935"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="5e592-102">\<清除 \<源的 \<侦听器 > > 元素 ></span><span class="sxs-lookup"><span data-stu-id="5e592-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="5e592-103">清除跟踪源的 `Listeners` 集合。</span><span class="sxs-lookup"><span data-stu-id="5e592-103">Clears the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="5e592-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5e592-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5e592-105">&nbsp;&nbsp;[ **\<的 >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="5e592-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="5e592-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](sources-element.md) ></span><span class="sxs-lookup"><span data-stu-id="5e592-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="5e592-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **&nbsp;&nbsp;\<** ](source-element.md) ></span><span class="sxs-lookup"><span data-stu-id="5e592-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="5e592-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**侦听器 >** ](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="5e592-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="5e592-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<清除 >**</span><span class="sxs-lookup"><span data-stu-id="5e592-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="5e592-110">语法</span><span class="sxs-lookup"><span data-stu-id="5e592-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5e592-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5e592-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5e592-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5e592-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5e592-113">特性</span><span class="sxs-lookup"><span data-stu-id="5e592-113">Attributes</span></span>  
 <span data-ttu-id="5e592-114">无。</span><span class="sxs-lookup"><span data-stu-id="5e592-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5e592-115">子元素</span><span class="sxs-lookup"><span data-stu-id="5e592-115">Child Elements</span></span>  
 <span data-ttu-id="5e592-116">无。</span><span class="sxs-lookup"><span data-stu-id="5e592-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5e592-117">父元素</span><span class="sxs-lookup"><span data-stu-id="5e592-117">Parent Elements</span></span>  
  
|<span data-ttu-id="5e592-118">元素</span><span class="sxs-lookup"><span data-stu-id="5e592-118">Element</span></span>|<span data-ttu-id="5e592-119">描述</span><span class="sxs-lookup"><span data-stu-id="5e592-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5e592-120">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="5e592-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="5e592-121">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="5e592-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="5e592-122">包含用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="5e592-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="5e592-123">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="5e592-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="5e592-124">指定用于收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="5e592-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e592-125">备注</span><span class="sxs-lookup"><span data-stu-id="5e592-125">Remarks</span></span>  
 <span data-ttu-id="5e592-126">`<clear>` 元素将从跟踪源（包括 <xref:System.Diagnostics.DefaultTraceListener>）的 `Listeners` 集合中删除所有侦听器。</span><span class="sxs-lookup"><span data-stu-id="5e592-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="5e592-127">在使用 `<add>` 元素之前，可以使用 `<clear>` 元素，以确定集合中没有其他活动侦听器。</span><span class="sxs-lookup"><span data-stu-id="5e592-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="5e592-128">配置文件</span><span class="sxs-lookup"><span data-stu-id="5e592-128">Configuration File</span></span>  
 <span data-ttu-id="5e592-129">此元素可在计算机配置文件（Machine.config）和应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="5e592-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e592-130">示例</span><span class="sxs-lookup"><span data-stu-id="5e592-130">Example</span></span>  
 <span data-ttu-id="5e592-131">下面的示例演示如何使用 `<clear>` 元素，然后再使用 `<add>` 元素向跟踪源 `Listeners` 的 `TraceSourceApp`集合添加侦听器 `console` 和 `textListener`。</span><span class="sxs-lookup"><span data-stu-id="5e592-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5e592-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="5e592-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="5e592-133">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="5e592-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5e592-134">跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="5e592-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
