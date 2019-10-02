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
ms.openlocfilehash: 0ca35d9be5e1eaf36a2c9cae99efc2736ef3403d
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699208"
---
# <a name="sources-element"></a><span data-ttu-id="e3a19-102">\<sources > 元素</span><span class="sxs-lookup"><span data-stu-id="e3a19-102">\<sources> Element</span></span>
<span data-ttu-id="e3a19-103">指定启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="e3a19-103">Specifies trace sources that initiate tracing messages.</span></span>  
  
[<span data-ttu-id="e3a19-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="e3a19-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="e3a19-105">&nbsp; @ no__t-1[ **\<system >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="e3a19-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="e3a19-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t **\<sources >**</span><span class="sxs-lookup"><span data-stu-id="e3a19-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sources>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3a19-107">语法</span><span class="sxs-lookup"><span data-stu-id="e3a19-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3a19-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e3a19-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e3a19-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e3a19-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3a19-110">特性</span><span class="sxs-lookup"><span data-stu-id="e3a19-110">Attributes</span></span>  
 <span data-ttu-id="e3a19-111">无。</span><span class="sxs-lookup"><span data-stu-id="e3a19-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e3a19-112">子元素</span><span class="sxs-lookup"><span data-stu-id="e3a19-112">Child Elements</span></span>  
  
|<span data-ttu-id="e3a19-113">元素</span><span class="sxs-lookup"><span data-stu-id="e3a19-113">Element</span></span>|<span data-ttu-id="e3a19-114">描述</span><span class="sxs-lookup"><span data-stu-id="e3a19-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3a19-115">\<source></span><span class="sxs-lookup"><span data-stu-id="e3a19-115">\<source></span></span>](source-element.md)|<span data-ttu-id="e3a19-116">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="e3a19-116">Required element.</span></span><br /><br /> <span data-ttu-id="e3a19-117">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="e3a19-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e3a19-118">父元素</span><span class="sxs-lookup"><span data-stu-id="e3a19-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e3a19-119">元素</span><span class="sxs-lookup"><span data-stu-id="e3a19-119">Element</span></span>|<span data-ttu-id="e3a19-120">描述</span><span class="sxs-lookup"><span data-stu-id="e3a19-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e3a19-121">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="e3a19-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="e3a19-122">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="e3a19-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3a19-123">备注</span><span class="sxs-lookup"><span data-stu-id="e3a19-123">Remarks</span></span>  
 <span data-ttu-id="e3a19-124">此元素可在计算机配置文件（Machine.config）和应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="e3a19-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3a19-125">示例</span><span class="sxs-lookup"><span data-stu-id="e3a19-125">Example</span></span>  
 <span data-ttu-id="e3a19-126">下面的示例演示如何使用 `<sources>` 元素将跟踪源添加 @no__t，并设置名为 `sourceSwitch` 的源开关的级别。</span><span class="sxs-lookup"><span data-stu-id="e3a19-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="e3a19-127">添加了控制台跟踪侦听器，用于将跟踪信息写入控制台。</span><span class="sxs-lookup"><span data-stu-id="e3a19-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e3a19-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3a19-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- [<span data-ttu-id="e3a19-129">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="e3a19-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e3a19-130">\<source></span><span class="sxs-lookup"><span data-stu-id="e3a19-130">\<source></span></span>](source-element.md)
