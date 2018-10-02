---
title: '&lt;源&gt;元素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sources
helpviewer_keywords:
- sources element
- trace sources
- <sources> element
ms.assetid: c727b2e2-423a-4463-a223-013f40ff16a3
author: mcleblanc
ms.author: markl
ms.openlocfilehash: a9c5c5529e349eca2ba089ed6fb71da4bd48430a
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2018
ms.locfileid: "48033241"
---
# <a name="ltsourcesgt-element"></a><span data-ttu-id="4c037-102">&lt;源&gt;元素</span><span class="sxs-lookup"><span data-stu-id="4c037-102">&lt;sources&gt; Element</span></span>
<span data-ttu-id="4c037-103">指定启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="4c037-103">Specifies trace sources that initiate tracing messages.</span></span>  
  
 <span data-ttu-id="4c037-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4c037-104">\<configuration></span></span>  
<span data-ttu-id="4c037-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="4c037-105">\<system.diagnostics></span></span>  
<span data-ttu-id="4c037-106">\<源 ></span><span class="sxs-lookup"><span data-stu-id="4c037-106">\<sources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c037-107">语法</span><span class="sxs-lookup"><span data-stu-id="4c037-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c037-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4c037-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4c037-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4c037-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c037-110">特性</span><span class="sxs-lookup"><span data-stu-id="4c037-110">Attributes</span></span>  
 <span data-ttu-id="4c037-111">无。</span><span class="sxs-lookup"><span data-stu-id="4c037-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4c037-112">子元素</span><span class="sxs-lookup"><span data-stu-id="4c037-112">Child Elements</span></span>  
  
|<span data-ttu-id="4c037-113">元素</span><span class="sxs-lookup"><span data-stu-id="4c037-113">Element</span></span>|<span data-ttu-id="4c037-114">描述</span><span class="sxs-lookup"><span data-stu-id="4c037-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c037-115">\<source></span><span class="sxs-lookup"><span data-stu-id="4c037-115">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)|<span data-ttu-id="4c037-116">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="4c037-116">Required element.</span></span><br /><br /> <span data-ttu-id="4c037-117">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="4c037-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4c037-118">父元素</span><span class="sxs-lookup"><span data-stu-id="4c037-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4c037-119">元素</span><span class="sxs-lookup"><span data-stu-id="4c037-119">Element</span></span>|<span data-ttu-id="4c037-120">描述</span><span class="sxs-lookup"><span data-stu-id="4c037-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4c037-121">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="4c037-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="4c037-122">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="4c037-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c037-123">备注</span><span class="sxs-lookup"><span data-stu-id="4c037-123">Remarks</span></span>  
 <span data-ttu-id="4c037-124">计算机配置文件 (Machine.config) 和应用程序配置文件中，可以使用此元素。</span><span class="sxs-lookup"><span data-stu-id="4c037-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c037-125">示例</span><span class="sxs-lookup"><span data-stu-id="4c037-125">Example</span></span>  
 <span data-ttu-id="4c037-126">下面的示例演示如何使用`<sources>`要添加的跟踪源元素`mySource`，并设置源开关的级别命名为`sourceSwitch`。</span><span class="sxs-lookup"><span data-stu-id="4c037-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="4c037-127">控制台跟踪侦听器添加的跟踪信息写入控制台。</span><span class="sxs-lookup"><span data-stu-id="4c037-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4c037-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="4c037-128">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.ConsoleTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 <xref:System.Diagnostics.XmlWriterTraceListener>  
 [<span data-ttu-id="4c037-129">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="4c037-129">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="4c037-130">\<source></span><span class="sxs-lookup"><span data-stu-id="4c037-130">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)
