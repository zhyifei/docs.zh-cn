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
ms.openlocfilehash: afd0e955698dfc7ff3d5c843dd8db10f648265b8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254660"
---
# <a name="switches-element"></a><span data-ttu-id="d185c-102">\<开关 > 元素</span><span class="sxs-lookup"><span data-stu-id="d185c-102">\<switches> Element</span></span>
<span data-ttu-id="d185c-103">包含跟踪开关和对该跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="d185c-103">Contains trace switches and the level where the trace switches are set.</span></span>  
  
 <span data-ttu-id="d185c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d185c-104">\<configuration></span></span>  
<span data-ttu-id="d185c-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="d185c-105">\<system.diagnostics></span></span>  
<span data-ttu-id="d185c-106">\<switches></span><span class="sxs-lookup"><span data-stu-id="d185c-106">\<switches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d185c-107">语法</span><span class="sxs-lookup"><span data-stu-id="d185c-107">Syntax</span></span>  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d185c-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d185c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d185c-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d185c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d185c-110">特性</span><span class="sxs-lookup"><span data-stu-id="d185c-110">Attributes</span></span>  
 <span data-ttu-id="d185c-111">无。</span><span class="sxs-lookup"><span data-stu-id="d185c-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d185c-112">子元素</span><span class="sxs-lookup"><span data-stu-id="d185c-112">Child Elements</span></span>  
  
|<span data-ttu-id="d185c-113">元素</span><span class="sxs-lookup"><span data-stu-id="d185c-113">Element</span></span>|<span data-ttu-id="d185c-114">描述</span><span class="sxs-lookup"><span data-stu-id="d185c-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d185c-115">\<add></span><span class="sxs-lookup"><span data-stu-id="d185c-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|<span data-ttu-id="d185c-116">指定对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="d185c-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d185c-117">父元素</span><span class="sxs-lookup"><span data-stu-id="d185c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d185c-118">元素</span><span class="sxs-lookup"><span data-stu-id="d185c-118">Element</span></span>|<span data-ttu-id="d185c-119">描述</span><span class="sxs-lookup"><span data-stu-id="d185c-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d185c-120">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="d185c-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="d185c-121">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="d185c-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d185c-122">备注</span><span class="sxs-lookup"><span data-stu-id="d185c-122">Remarks</span></span>  
 <span data-ttu-id="d185c-123">可以通过将它放在配置文件更改跟踪开关的级别。</span><span class="sxs-lookup"><span data-stu-id="d185c-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="d185c-124">如果该切换<xref:System.Diagnostics.BooleanSwitch>，您可以将其打开和关闭。</span><span class="sxs-lookup"><span data-stu-id="d185c-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="d185c-125">如果该切换<xref:System.Diagnostics.TraceSwitch>，可以将不同级别分配给该代码以指定类型的跟踪或调试消息的应用程序输出。</span><span class="sxs-lookup"><span data-stu-id="d185c-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d185c-126">示例</span><span class="sxs-lookup"><span data-stu-id="d185c-126">Example</span></span>  
 <span data-ttu-id="d185c-127">下面的示例演示如何使用**\<切换 >** 元素中设置`General`跟踪切换到<xref:System.Diagnostics.TraceLevel>级别，并启用`Data`布尔型跟踪开关。</span><span class="sxs-lookup"><span data-stu-id="d185c-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d185c-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="d185c-128">See also</span></span>
- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="d185c-129">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="d185c-129">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
