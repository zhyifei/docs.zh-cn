---
title: <sources> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sources
helpviewer_keywords:
- sources element
- trace sources
- <sources> element
ms.assetid: c727b2e2-423a-4463-a223-013f40ff16a3
ms.openlocfilehash: 2a76816ee73f516b3c7544877a77531acaa8e09c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153264"
---
# <a name="sources-element"></a><span data-ttu-id="3801f-102">\<源>元素</span><span class="sxs-lookup"><span data-stu-id="3801f-102">\<sources> Element</span></span>
<span data-ttu-id="3801f-103">指定启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="3801f-103">Specifies trace sources that initiate tracing messages.</span></span>  

<span data-ttu-id="3801f-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3801f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3801f-105">&nbsp;&nbsp;[**\<系统.诊断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="3801f-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="3801f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<来源>**</span><span class="sxs-lookup"><span data-stu-id="3801f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sources>**</span></span>

## <a name="syntax"></a><span data-ttu-id="3801f-107">语法</span><span class="sxs-lookup"><span data-stu-id="3801f-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3801f-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3801f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3801f-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3801f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3801f-110">属性</span><span class="sxs-lookup"><span data-stu-id="3801f-110">Attributes</span></span>  
 <span data-ttu-id="3801f-111">无。</span><span class="sxs-lookup"><span data-stu-id="3801f-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3801f-112">子元素</span><span class="sxs-lookup"><span data-stu-id="3801f-112">Child Elements</span></span>  
  
|<span data-ttu-id="3801f-113">元素</span><span class="sxs-lookup"><span data-stu-id="3801f-113">Element</span></span>|<span data-ttu-id="3801f-114">说明</span><span class="sxs-lookup"><span data-stu-id="3801f-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3801f-115">\<源></span><span class="sxs-lookup"><span data-stu-id="3801f-115">\<source></span></span>](source-element.md)|<span data-ttu-id="3801f-116">必需元素。</span><span class="sxs-lookup"><span data-stu-id="3801f-116">Required element.</span></span><br /><br /> <span data-ttu-id="3801f-117">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="3801f-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3801f-118">父元素</span><span class="sxs-lookup"><span data-stu-id="3801f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="3801f-119">元素</span><span class="sxs-lookup"><span data-stu-id="3801f-119">Element</span></span>|<span data-ttu-id="3801f-120">说明</span><span class="sxs-lookup"><span data-stu-id="3801f-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3801f-121">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="3801f-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="3801f-122">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="3801f-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3801f-123">备注</span><span class="sxs-lookup"><span data-stu-id="3801f-123">Remarks</span></span>  
 <span data-ttu-id="3801f-124">此元素可用于计算机配置文件 （Machine.config） 和应用程序配置文件。</span><span class="sxs-lookup"><span data-stu-id="3801f-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3801f-125">示例</span><span class="sxs-lookup"><span data-stu-id="3801f-125">Example</span></span>  
 <span data-ttu-id="3801f-126">下面的示例演示如何使用 元素`<sources>`添加跟踪源`mySource`，并为名为 的`sourceSwitch`源交换机设置级别。</span><span class="sxs-lookup"><span data-stu-id="3801f-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="3801f-127">添加了将跟踪信息写入控制台的控制台跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="3801f-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <sources>  
         <source name="mySource" switchName="sourceSwitch"
            switchType="System.Diagnostics.SourceSwitch"  >  
            <listeners>  
               <add name="console"
                  type="System.Diagnostics.ConsoleTraceListener" >  
                  <filter type="System.Diagnostics.EventTypeFilter"
                     initializeData="Error" />  
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
  
## <a name="see-also"></a><span data-ttu-id="3801f-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3801f-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- [<span data-ttu-id="3801f-129">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="3801f-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3801f-130">\<源></span><span class="sxs-lookup"><span data-stu-id="3801f-130">\<source></span></span>](source-element.md)
