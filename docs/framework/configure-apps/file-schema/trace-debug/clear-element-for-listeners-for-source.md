---
title: <source> 的 @no__t <listeners> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 05c20040ef59f4dee6b15bbe0b0369281b532754
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697196"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="a40dd-102">\<clear > 元素，用于 2source @no__t 的 \<listeners ></span><span class="sxs-lookup"><span data-stu-id="a40dd-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="a40dd-103">清除跟踪源的 `Listeners` 集合。</span><span class="sxs-lookup"><span data-stu-id="a40dd-103">Clears the `Listeners` collection for a trace source.</span></span>  
  
[<span data-ttu-id="a40dd-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="a40dd-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="a40dd-105">&nbsp; @ no__t-1[ **\<system >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="a40dd-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="a40dd-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<sources >** ](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="a40dd-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="a40dd-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<source >** ](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="a40dd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="a40dd-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0listeners >** ](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="a40dd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>  
<span data-ttu-id="a40dd-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<clear>**</span><span class="sxs-lookup"><span data-stu-id="a40dd-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a40dd-110">语法</span><span class="sxs-lookup"><span data-stu-id="a40dd-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a40dd-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a40dd-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a40dd-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a40dd-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a40dd-113">特性</span><span class="sxs-lookup"><span data-stu-id="a40dd-113">Attributes</span></span>  
 <span data-ttu-id="a40dd-114">无。</span><span class="sxs-lookup"><span data-stu-id="a40dd-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a40dd-115">子元素</span><span class="sxs-lookup"><span data-stu-id="a40dd-115">Child Elements</span></span>  
 <span data-ttu-id="a40dd-116">无。</span><span class="sxs-lookup"><span data-stu-id="a40dd-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a40dd-117">父元素</span><span class="sxs-lookup"><span data-stu-id="a40dd-117">Parent Elements</span></span>  
  
|<span data-ttu-id="a40dd-118">元素</span><span class="sxs-lookup"><span data-stu-id="a40dd-118">Element</span></span>|<span data-ttu-id="a40dd-119">描述</span><span class="sxs-lookup"><span data-stu-id="a40dd-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a40dd-120">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="a40dd-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="a40dd-121">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="a40dd-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="a40dd-122">包含用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="a40dd-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="a40dd-123">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="a40dd-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="a40dd-124">指定用于收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="a40dd-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a40dd-125">备注</span><span class="sxs-lookup"><span data-stu-id="a40dd-125">Remarks</span></span>  
 <span data-ttu-id="a40dd-126">@No__t 0 元素从跟踪源的 @no__t 集合（包括 <xref:System.Diagnostics.DefaultTraceListener>）中删除所有侦听器。</span><span class="sxs-lookup"><span data-stu-id="a40dd-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="a40dd-127">你可以使用 `<clear>` 元素，然后才能使用 @no__t 元素，以确定集合中没有其他活动的侦听器。</span><span class="sxs-lookup"><span data-stu-id="a40dd-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="a40dd-128">配置文件</span><span class="sxs-lookup"><span data-stu-id="a40dd-128">Configuration File</span></span>  
 <span data-ttu-id="a40dd-129">此元素可在计算机配置文件（Machine.config）和应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="a40dd-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a40dd-130">示例</span><span class="sxs-lookup"><span data-stu-id="a40dd-130">Example</span></span>  
 <span data-ttu-id="a40dd-131">下面的示例演示了如何使用 `<clear>` 元素，然后再使用 `<add>` 元素将侦听器添加到 @no__t 的跟踪源的 @no__t 集合 `console` 和 @no__t。</span><span class="sxs-lookup"><span data-stu-id="a40dd-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a40dd-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="a40dd-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="a40dd-133">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="a40dd-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a40dd-134">跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="a40dd-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
