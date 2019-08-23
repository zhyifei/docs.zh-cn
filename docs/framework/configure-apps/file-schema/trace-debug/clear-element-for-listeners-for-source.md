---
title: <clear><listeners>的元素<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 768d51a74b4c31d1250d2f5d6517f760f886e0a0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920563"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="d78b7-102">\<清除\< \<源 > 侦听器 > > 元素</span><span class="sxs-lookup"><span data-stu-id="d78b7-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="d78b7-103">清除跟踪源的 `Listeners` 集合。</span><span class="sxs-lookup"><span data-stu-id="d78b7-103">Clears the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="d78b7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d78b7-104">\<configuration></span></span>  
<span data-ttu-id="d78b7-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="d78b7-105">\<system.diagnostics></span></span>  
<span data-ttu-id="d78b7-106">\<源 ></span><span class="sxs-lookup"><span data-stu-id="d78b7-106">\<sources></span></span>  
<span data-ttu-id="d78b7-107">\<源 ></span><span class="sxs-lookup"><span data-stu-id="d78b7-107">\<source></span></span>  
<span data-ttu-id="d78b7-108">\<侦听器 ></span><span class="sxs-lookup"><span data-stu-id="d78b7-108">\<listeners></span></span>  
<span data-ttu-id="d78b7-109">\<清除 ></span><span class="sxs-lookup"><span data-stu-id="d78b7-109">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d78b7-110">语法</span><span class="sxs-lookup"><span data-stu-id="d78b7-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d78b7-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d78b7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d78b7-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d78b7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d78b7-113">特性</span><span class="sxs-lookup"><span data-stu-id="d78b7-113">Attributes</span></span>  
 <span data-ttu-id="d78b7-114">无。</span><span class="sxs-lookup"><span data-stu-id="d78b7-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d78b7-115">子元素</span><span class="sxs-lookup"><span data-stu-id="d78b7-115">Child Elements</span></span>  
 <span data-ttu-id="d78b7-116">无。</span><span class="sxs-lookup"><span data-stu-id="d78b7-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d78b7-117">父元素</span><span class="sxs-lookup"><span data-stu-id="d78b7-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d78b7-118">元素</span><span class="sxs-lookup"><span data-stu-id="d78b7-118">Element</span></span>|<span data-ttu-id="d78b7-119">描述</span><span class="sxs-lookup"><span data-stu-id="d78b7-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d78b7-120">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="d78b7-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="d78b7-121">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="d78b7-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="d78b7-122">包含用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="d78b7-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="d78b7-123">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="d78b7-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="d78b7-124">指定用于收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="d78b7-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d78b7-125">备注</span><span class="sxs-lookup"><span data-stu-id="d78b7-125">Remarks</span></span>  
 <span data-ttu-id="d78b7-126">元素从跟踪源的集合中移除所有侦听器,包括。<xref:System.Diagnostics.DefaultTraceListener> `Listeners` `<clear>`</span><span class="sxs-lookup"><span data-stu-id="d78b7-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="d78b7-127">可以在`<clear>` `<add>`使用元素之前使用元素, 以确定集合中没有其他活动的侦听器。</span><span class="sxs-lookup"><span data-stu-id="d78b7-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="d78b7-128">配置文件</span><span class="sxs-lookup"><span data-stu-id="d78b7-128">Configuration File</span></span>  
 <span data-ttu-id="d78b7-129">此元素可在计算机配置文件 (Machine.config) 和应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="d78b7-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d78b7-130">示例</span><span class="sxs-lookup"><span data-stu-id="d78b7-130">Example</span></span>  
 <span data-ttu-id="d78b7-131">下面的示例演示`<clear>`如何在`<add>`使用元素将侦听器`console`和`textListener` `Listeners`集合添加到跟踪源`TraceSourceApp`之前使用元素。</span><span class="sxs-lookup"><span data-stu-id="d78b7-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d78b7-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="d78b7-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="d78b7-133">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="d78b7-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d78b7-134">跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="d78b7-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
