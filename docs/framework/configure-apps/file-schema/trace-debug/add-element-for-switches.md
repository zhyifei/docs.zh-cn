---
title: '&lt;添加&gt;元素&lt;开关&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add
helpviewer_keywords:
- <add> element for <switches>
- add element for <switches>
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e0dc425327f6577606e1205a23fdaffcc39f6e01
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747449"
---
# <a name="ltaddgt-element-for-ltswitchesgt"></a><span data-ttu-id="7c1cc-102">&lt;添加&gt;元素&lt;开关&gt;</span><span class="sxs-lookup"><span data-stu-id="7c1cc-102">&lt;add&gt; Element for &lt;switches&gt;</span></span>
<span data-ttu-id="7c1cc-103">指定对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="7c1cc-103">Specifies the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="7c1cc-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7c1cc-104">\<configuration></span></span>  
<span data-ttu-id="7c1cc-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="7c1cc-105">\<system.diagnostics></span></span>  
<span data-ttu-id="7c1cc-106">\<交换机 ></span><span class="sxs-lookup"><span data-stu-id="7c1cc-106">\<switches></span></span>  
<span data-ttu-id="7c1cc-107">\<add></span><span class="sxs-lookup"><span data-stu-id="7c1cc-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c1cc-108">语法</span><span class="sxs-lookup"><span data-stu-id="7c1cc-108">Syntax</span></span>  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7c1cc-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7c1cc-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7c1cc-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7c1cc-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7c1cc-111">特性</span><span class="sxs-lookup"><span data-stu-id="7c1cc-111">Attributes</span></span>  
  
|<span data-ttu-id="7c1cc-112">特性</span><span class="sxs-lookup"><span data-stu-id="7c1cc-112">Attribute</span></span>|<span data-ttu-id="7c1cc-113">描述</span><span class="sxs-lookup"><span data-stu-id="7c1cc-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7c1cc-114">**name**</span><span class="sxs-lookup"><span data-stu-id="7c1cc-114">**name**</span></span>|<span data-ttu-id="7c1cc-115">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="7c1cc-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="7c1cc-116">指定的交换机的名称。</span><span class="sxs-lookup"><span data-stu-id="7c1cc-116">Specifies the name of the switch.</span></span> <span data-ttu-id="7c1cc-117">此属性的值对应于*displayName*传递切换构造函数的参数。</span><span class="sxs-lookup"><span data-stu-id="7c1cc-117">The value of this attribute corresponds to the *displayName* parameter that is passed to switch constructor.</span></span>|  
|<span data-ttu-id="7c1cc-118">**value**</span><span class="sxs-lookup"><span data-stu-id="7c1cc-118">**value**</span></span>|<span data-ttu-id="7c1cc-119">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="7c1cc-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="7c1cc-120">指定开关的级别。</span><span class="sxs-lookup"><span data-stu-id="7c1cc-120">Specifies the level of the switch.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7c1cc-121">子元素</span><span class="sxs-lookup"><span data-stu-id="7c1cc-121">Child Elements</span></span>  
 <span data-ttu-id="7c1cc-122">无。</span><span class="sxs-lookup"><span data-stu-id="7c1cc-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7c1cc-123">父元素</span><span class="sxs-lookup"><span data-stu-id="7c1cc-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7c1cc-124">元素</span><span class="sxs-lookup"><span data-stu-id="7c1cc-124">Element</span></span>|<span data-ttu-id="7c1cc-125">描述</span><span class="sxs-lookup"><span data-stu-id="7c1cc-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7c1cc-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="7c1cc-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`switches`|<span data-ttu-id="7c1cc-127">包含跟踪开关和对该跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="7c1cc-127">Contains trace switches and the level where the trace switches are set.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="7c1cc-128">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="7c1cc-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c1cc-129">备注</span><span class="sxs-lookup"><span data-stu-id="7c1cc-129">Remarks</span></span>  
 <span data-ttu-id="7c1cc-130">可以通过将它放在配置文件来更改跟踪开关的级别。</span><span class="sxs-lookup"><span data-stu-id="7c1cc-130">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="7c1cc-131">如果开关已<xref:System.Diagnostics.BooleanSwitch>，你可以将其打开和关闭。</span><span class="sxs-lookup"><span data-stu-id="7c1cc-131">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="7c1cc-132">如果开关已<xref:System.Diagnostics.TraceSwitch>，可以将不同级别分配到它，以指定类型的跟踪或调试消息的应用程序输出。</span><span class="sxs-lookup"><span data-stu-id="7c1cc-132">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c1cc-133">示例</span><span class="sxs-lookup"><span data-stu-id="7c1cc-133">Example</span></span>  
 <span data-ttu-id="7c1cc-134">下面的示例演示如何使用**\<添加 >** 元素中设置`General`跟踪切换到<xref:System.Diagnostics.TraceLevel>级别，并启用`Data`布尔型跟踪开关。</span><span class="sxs-lookup"><span data-stu-id="7c1cc-134">The following example shows how to use the **\<add>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7c1cc-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="7c1cc-135">See Also</span></span>  
 <xref:System.Diagnostics.Switch>  
 <xref:System.Diagnostics.TraceSwitch>  
 <xref:System.Diagnostics.BooleanSwitch>  
 [<span data-ttu-id="7c1cc-136">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="7c1cc-136">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
