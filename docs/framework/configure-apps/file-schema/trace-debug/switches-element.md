---
title: <switches> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches
- http://schemas.microsoft.com/.NetConfiguration/v2.0#switches
helpviewer_keywords:
- <switches> element
- switches element
- trace switches, <switches> element
ms.assetid: 4cf36786-b89a-40e2-a0f1-86bb9b783343
ms.openlocfilehash: 15cc9680d7a20341eb5d1d1df302c1e034e70e02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153225"
---
# <a name="switches-element"></a><span data-ttu-id="34572-102">\<切换>元素</span><span class="sxs-lookup"><span data-stu-id="34572-102">\<switches> Element</span></span>
<span data-ttu-id="34572-103">包含跟踪开关和对该跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="34572-103">Contains trace switches and the level where the trace switches are set.</span></span>  

<span data-ttu-id="34572-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="34572-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="34572-105">&nbsp;&nbsp;[**\<系统.诊断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="34572-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="34572-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<开关>**</span><span class="sxs-lookup"><span data-stu-id="34572-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<switches>**</span></span>

## <a name="syntax"></a><span data-ttu-id="34572-107">语法</span><span class="sxs-lookup"><span data-stu-id="34572-107">Syntax</span></span>  
  
```xml  
      <switches>
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34572-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="34572-108">Attributes and Elements</span></span>  
 <span data-ttu-id="34572-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="34572-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34572-110">属性</span><span class="sxs-lookup"><span data-stu-id="34572-110">Attributes</span></span>  
 <span data-ttu-id="34572-111">无。</span><span class="sxs-lookup"><span data-stu-id="34572-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="34572-112">子元素</span><span class="sxs-lookup"><span data-stu-id="34572-112">Child Elements</span></span>  
  
|<span data-ttu-id="34572-113">元素</span><span class="sxs-lookup"><span data-stu-id="34572-113">Element</span></span>|<span data-ttu-id="34572-114">说明</span><span class="sxs-lookup"><span data-stu-id="34572-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34572-115">\<添加></span><span class="sxs-lookup"><span data-stu-id="34572-115">\<add></span></span>](add-element-for-switches.md)|<span data-ttu-id="34572-116">指定对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="34572-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="34572-117">父元素</span><span class="sxs-lookup"><span data-stu-id="34572-117">Parent Elements</span></span>  
  
|<span data-ttu-id="34572-118">元素</span><span class="sxs-lookup"><span data-stu-id="34572-118">Element</span></span>|<span data-ttu-id="34572-119">说明</span><span class="sxs-lookup"><span data-stu-id="34572-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="34572-120">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="34572-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="34572-121">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="34572-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34572-122">备注</span><span class="sxs-lookup"><span data-stu-id="34572-122">Remarks</span></span>  
 <span data-ttu-id="34572-123">通过将跟踪开关放入配置文件中，可以更改跟踪开关的级别。</span><span class="sxs-lookup"><span data-stu-id="34572-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="34572-124">如果开关为 ，<xref:System.Diagnostics.BooleanSwitch>则可以打开和关闭开关。</span><span class="sxs-lookup"><span data-stu-id="34572-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="34572-125">如果交换机为 ，<xref:System.Diagnostics.TraceSwitch>则可以为其分配不同级别以指定应用程序输出的跟踪类型或调试消息。</span><span class="sxs-lookup"><span data-stu-id="34572-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34572-126">示例</span><span class="sxs-lookup"><span data-stu-id="34572-126">Example</span></span>  
 <span data-ttu-id="34572-127">下面的示例演示如何使用**\<开关>** 元素将`General`跟踪开关设置为<xref:System.Diagnostics.TraceLevel>级别，并启用`Data`布尔跟踪开关。</span><span class="sxs-lookup"><span data-stu-id="34572-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="34572-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34572-128">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="34572-129">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="34572-129">Trace and Debug Settings Schema</span></span>](index.md)
