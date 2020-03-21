---
title: <clear>用于<listeners><source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 7f9ddd93d27c3619119702c82c9e8752dab1af7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153576"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="6ea63-102">\<为\<侦听器>\<源>清除>元素</span><span class="sxs-lookup"><span data-stu-id="6ea63-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="6ea63-103">清除跟踪源的 `Listeners` 集合。</span><span class="sxs-lookup"><span data-stu-id="6ea63-103">Clears the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="6ea63-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6ea63-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6ea63-105">&nbsp;&nbsp;[**\<系统.诊断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="6ea63-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="6ea63-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<来源>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="6ea63-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="6ea63-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<源>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="6ea63-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="6ea63-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<听众>**](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="6ea63-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="6ea63-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<明确>**</span><span class="sxs-lookup"><span data-stu-id="6ea63-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="6ea63-110">语法</span><span class="sxs-lookup"><span data-stu-id="6ea63-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ea63-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6ea63-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6ea63-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6ea63-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ea63-113">属性</span><span class="sxs-lookup"><span data-stu-id="6ea63-113">Attributes</span></span>  
 <span data-ttu-id="6ea63-114">无。</span><span class="sxs-lookup"><span data-stu-id="6ea63-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6ea63-115">子元素</span><span class="sxs-lookup"><span data-stu-id="6ea63-115">Child Elements</span></span>  
 <span data-ttu-id="6ea63-116">无。</span><span class="sxs-lookup"><span data-stu-id="6ea63-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6ea63-117">父元素</span><span class="sxs-lookup"><span data-stu-id="6ea63-117">Parent Elements</span></span>  
  
|<span data-ttu-id="6ea63-118">元素</span><span class="sxs-lookup"><span data-stu-id="6ea63-118">Element</span></span>|<span data-ttu-id="6ea63-119">说明</span><span class="sxs-lookup"><span data-stu-id="6ea63-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6ea63-120">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="6ea63-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="6ea63-121">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="6ea63-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="6ea63-122">包含用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="6ea63-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="6ea63-123">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="6ea63-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="6ea63-124">指定收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="6ea63-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ea63-125">备注</span><span class="sxs-lookup"><span data-stu-id="6ea63-125">Remarks</span></span>  
 <span data-ttu-id="6ea63-126">该`<clear>`元素从跟踪源（包括`Listeners`）<xref:System.Diagnostics.DefaultTraceListener>的集合中删除所有侦听器。</span><span class="sxs-lookup"><span data-stu-id="6ea63-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="6ea63-127">在使用 元素`<clear>`之前，`<add>`可以使用 该元素来确定集合中没有其他活动侦听器。</span><span class="sxs-lookup"><span data-stu-id="6ea63-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="6ea63-128">配置文件</span><span class="sxs-lookup"><span data-stu-id="6ea63-128">Configuration File</span></span>  
 <span data-ttu-id="6ea63-129">此元素可用于计算机配置文件 （Machine.config） 和应用程序配置文件。</span><span class="sxs-lookup"><span data-stu-id="6ea63-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ea63-130">示例</span><span class="sxs-lookup"><span data-stu-id="6ea63-130">Example</span></span>  
 <span data-ttu-id="6ea63-131">下面的示例演示如何`<clear>`在使用`<add>`元素将侦听器`console`和`textListener`跟踪源`Listeners``TraceSourceApp`的集合之前使用元素。</span><span class="sxs-lookup"><span data-stu-id="6ea63-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6ea63-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ea63-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="6ea63-133">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="6ea63-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6ea63-134">跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="6ea63-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
