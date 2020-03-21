---
title: <source> 元素
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: 417722ce2f3865350158413307495e3ab435d386
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153290"
---
# <a name="source-element"></a><span data-ttu-id="28ee1-102">\<源>元素</span><span class="sxs-lookup"><span data-stu-id="28ee1-102">\<source> Element</span></span>
<span data-ttu-id="28ee1-103">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="28ee1-103">Specifies a trace source that initiates tracing messages.</span></span>  

<span data-ttu-id="28ee1-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="28ee1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="28ee1-105">&nbsp;&nbsp;[**\<系统.诊断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="28ee1-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="28ee1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<来源>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="28ee1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="28ee1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<源>**</span><span class="sxs-lookup"><span data-stu-id="28ee1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<source>**</span></span>

## <a name="syntax"></a><span data-ttu-id="28ee1-108">语法</span><span class="sxs-lookup"><span data-stu-id="28ee1-108">Syntax</span></span>  
  
```xml  
<source>
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28ee1-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="28ee1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="28ee1-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="28ee1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28ee1-111">属性</span><span class="sxs-lookup"><span data-stu-id="28ee1-111">Attributes</span></span>  
  
|<span data-ttu-id="28ee1-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="28ee1-112">Attribute</span></span>|<span data-ttu-id="28ee1-113">说明</span><span class="sxs-lookup"><span data-stu-id="28ee1-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="28ee1-114">可选特性。</span><span class="sxs-lookup"><span data-stu-id="28ee1-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="28ee1-115">指定跟踪源的名称。</span><span class="sxs-lookup"><span data-stu-id="28ee1-115">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="28ee1-116">可选特性。</span><span class="sxs-lookup"><span data-stu-id="28ee1-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="28ee1-117">指定应用程序中跟踪开关实例的名称。</span><span class="sxs-lookup"><span data-stu-id="28ee1-117">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="28ee1-118">如果在`<switches>`元素中未标识交换机，则值指定交换机的级别。</span><span class="sxs-lookup"><span data-stu-id="28ee1-118">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="28ee1-119">可选特性。</span><span class="sxs-lookup"><span data-stu-id="28ee1-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="28ee1-120">指定跟踪开关的类型。</span><span class="sxs-lookup"><span data-stu-id="28ee1-120">Specifies the type of the trace switch.</span></span> <span data-ttu-id="28ee1-121">如果存在，则类型必须是有效的类名称，不能为空字符串。</span><span class="sxs-lookup"><span data-stu-id="28ee1-121">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="28ee1-122">可选特性。</span><span class="sxs-lookup"><span data-stu-id="28ee1-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="28ee1-123">指定由该跟踪源的方法标识的<xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A>特定于跟踪源的属性的值。</span><span class="sxs-lookup"><span data-stu-id="28ee1-123">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28ee1-124">子元素</span><span class="sxs-lookup"><span data-stu-id="28ee1-124">Child Elements</span></span>  
  
|<span data-ttu-id="28ee1-125">元素</span><span class="sxs-lookup"><span data-stu-id="28ee1-125">Element</span></span>|<span data-ttu-id="28ee1-126">说明</span><span class="sxs-lookup"><span data-stu-id="28ee1-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28ee1-127">\<听众></span><span class="sxs-lookup"><span data-stu-id="28ee1-127">\<listeners></span></span>](listeners-element-for-source.md)|<span data-ttu-id="28ee1-128">包含收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="28ee1-128">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="28ee1-129">父元素</span><span class="sxs-lookup"><span data-stu-id="28ee1-129">Parent Elements</span></span>  
  
|<span data-ttu-id="28ee1-130">元素</span><span class="sxs-lookup"><span data-stu-id="28ee1-130">Element</span></span>|<span data-ttu-id="28ee1-131">说明</span><span class="sxs-lookup"><span data-stu-id="28ee1-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="28ee1-132">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="28ee1-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="28ee1-133">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="28ee1-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="28ee1-134">包含用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="28ee1-134">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28ee1-135">备注</span><span class="sxs-lookup"><span data-stu-id="28ee1-135">Remarks</span></span>  
 <span data-ttu-id="28ee1-136">此元素可用于计算机配置文件 （Machine.config） 和应用程序配置文件。</span><span class="sxs-lookup"><span data-stu-id="28ee1-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28ee1-137">示例</span><span class="sxs-lookup"><span data-stu-id="28ee1-137">Example</span></span>  
 <span data-ttu-id="28ee1-138">下面的示例演示如何使用 元素`<source>`添加跟踪源`mySource`，并为名为 的`sourceSwitch`源交换机设置级别。</span><span class="sxs-lookup"><span data-stu-id="28ee1-138">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="28ee1-139">添加了将跟踪信息写入控制台的控制台跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="28ee1-139">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch" switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter" initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
        <switches>  
           <add name="sourceSwitch" value="Warning" />  
        </switches>
  </system.diagnostics>
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="28ee1-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28ee1-140">See also</span></span>

- [<span data-ttu-id="28ee1-141">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="28ee1-141">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="28ee1-142">跟踪开关</span><span class="sxs-lookup"><span data-stu-id="28ee1-142">Trace Switches</span></span>](../../../debug-trace-profile/trace-switches.md)
