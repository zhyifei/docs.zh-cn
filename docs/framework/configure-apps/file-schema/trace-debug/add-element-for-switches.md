---
title: <switches> 的 <add> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add
helpviewer_keywords:
- <add> element for <switches>
- add element for <switches>
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
ms.openlocfilehash: d7500620aed1165ff365fee8529230ba252dbc4b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673805"
---
# <a name="add-element-for-switches"></a><span data-ttu-id="3eac0-102">\<添加 > 元素\<开关 ></span><span class="sxs-lookup"><span data-stu-id="3eac0-102">\<add> Element for \<switches></span></span>
<span data-ttu-id="3eac0-103">指定对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="3eac0-103">Specifies the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="3eac0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3eac0-104">\<configuration></span></span>  
<span data-ttu-id="3eac0-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="3eac0-105">\<system.diagnostics></span></span>  
<span data-ttu-id="3eac0-106">\<switches></span><span class="sxs-lookup"><span data-stu-id="3eac0-106">\<switches></span></span>  
<span data-ttu-id="3eac0-107">\<add></span><span class="sxs-lookup"><span data-stu-id="3eac0-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eac0-108">语法</span><span class="sxs-lookup"><span data-stu-id="3eac0-108">Syntax</span></span>  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3eac0-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3eac0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3eac0-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3eac0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3eac0-111">特性</span><span class="sxs-lookup"><span data-stu-id="3eac0-111">Attributes</span></span>  
  
|<span data-ttu-id="3eac0-112">特性</span><span class="sxs-lookup"><span data-stu-id="3eac0-112">Attribute</span></span>|<span data-ttu-id="3eac0-113">描述</span><span class="sxs-lookup"><span data-stu-id="3eac0-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3eac0-114">**name**</span><span class="sxs-lookup"><span data-stu-id="3eac0-114">**name**</span></span>|<span data-ttu-id="3eac0-115">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="3eac0-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="3eac0-116">指定的交换机的名称。</span><span class="sxs-lookup"><span data-stu-id="3eac0-116">Specifies the name of the switch.</span></span> <span data-ttu-id="3eac0-117">此属性的值对应于*displayName*传递切换构造函数的参数。</span><span class="sxs-lookup"><span data-stu-id="3eac0-117">The value of this attribute corresponds to the *displayName* parameter that is passed to switch constructor.</span></span>|  
|<span data-ttu-id="3eac0-118">**值**</span><span class="sxs-lookup"><span data-stu-id="3eac0-118">**value**</span></span>|<span data-ttu-id="3eac0-119">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="3eac0-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="3eac0-120">指定此开关的级别。</span><span class="sxs-lookup"><span data-stu-id="3eac0-120">Specifies the level of the switch.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3eac0-121">子元素</span><span class="sxs-lookup"><span data-stu-id="3eac0-121">Child Elements</span></span>  
 <span data-ttu-id="3eac0-122">无。</span><span class="sxs-lookup"><span data-stu-id="3eac0-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3eac0-123">父元素</span><span class="sxs-lookup"><span data-stu-id="3eac0-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3eac0-124">元素</span><span class="sxs-lookup"><span data-stu-id="3eac0-124">Element</span></span>|<span data-ttu-id="3eac0-125">描述</span><span class="sxs-lookup"><span data-stu-id="3eac0-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3eac0-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="3eac0-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`switches`|<span data-ttu-id="3eac0-127">包含跟踪开关和对该跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="3eac0-127">Contains trace switches and the level where the trace switches are set.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="3eac0-128">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="3eac0-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3eac0-129">备注</span><span class="sxs-lookup"><span data-stu-id="3eac0-129">Remarks</span></span>  
 <span data-ttu-id="3eac0-130">可以通过将它放在配置文件更改跟踪开关的级别。</span><span class="sxs-lookup"><span data-stu-id="3eac0-130">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="3eac0-131">如果该切换<xref:System.Diagnostics.BooleanSwitch>，您可以将其打开和关闭。</span><span class="sxs-lookup"><span data-stu-id="3eac0-131">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="3eac0-132">如果该切换<xref:System.Diagnostics.TraceSwitch>，可以将不同级别分配给该代码以指定类型的跟踪或调试消息的应用程序输出。</span><span class="sxs-lookup"><span data-stu-id="3eac0-132">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3eac0-133">示例</span><span class="sxs-lookup"><span data-stu-id="3eac0-133">Example</span></span>  
 <span data-ttu-id="3eac0-134">下面的示例演示如何使用 **\<添加>** 元素中设置`General`跟踪切换到<xref:System.Diagnostics.TraceLevel>级别，并启用`Data`布尔型跟踪开关。</span><span class="sxs-lookup"><span data-stu-id="3eac0-134">The following example shows how to use the **\<add>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3eac0-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="3eac0-135">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="3eac0-136">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="3eac0-136">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
