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
ms.openlocfilehash: c161f842192396101dcc6850f3b3da328958eac3
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697089"
---
# <a name="switches-element"></a><span data-ttu-id="d8b82-102">\<switches > 元素</span><span class="sxs-lookup"><span data-stu-id="d8b82-102">\<switches> Element</span></span>
<span data-ttu-id="d8b82-103">包含跟踪开关和对该跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="d8b82-103">Contains trace switches and the level where the trace switches are set.</span></span>  
  
[<span data-ttu-id="d8b82-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="d8b82-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="d8b82-105">&nbsp; @ no__t-1[ **\<system >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="d8b82-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="d8b82-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t **\<switches >**</span><span class="sxs-lookup"><span data-stu-id="d8b82-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<switches>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8b82-107">语法</span><span class="sxs-lookup"><span data-stu-id="d8b82-107">Syntax</span></span>  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8b82-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d8b82-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d8b82-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d8b82-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8b82-110">特性</span><span class="sxs-lookup"><span data-stu-id="d8b82-110">Attributes</span></span>  
 <span data-ttu-id="d8b82-111">无。</span><span class="sxs-lookup"><span data-stu-id="d8b82-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d8b82-112">子元素</span><span class="sxs-lookup"><span data-stu-id="d8b82-112">Child Elements</span></span>  
  
|<span data-ttu-id="d8b82-113">元素</span><span class="sxs-lookup"><span data-stu-id="d8b82-113">Element</span></span>|<span data-ttu-id="d8b82-114">描述</span><span class="sxs-lookup"><span data-stu-id="d8b82-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8b82-115">\<add></span><span class="sxs-lookup"><span data-stu-id="d8b82-115">\<add></span></span>](add-element-for-switches.md)|<span data-ttu-id="d8b82-116">指定对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="d8b82-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d8b82-117">父元素</span><span class="sxs-lookup"><span data-stu-id="d8b82-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d8b82-118">元素</span><span class="sxs-lookup"><span data-stu-id="d8b82-118">Element</span></span>|<span data-ttu-id="d8b82-119">描述</span><span class="sxs-lookup"><span data-stu-id="d8b82-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d8b82-120">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="d8b82-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="d8b82-121">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="d8b82-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8b82-122">备注</span><span class="sxs-lookup"><span data-stu-id="d8b82-122">Remarks</span></span>  
 <span data-ttu-id="d8b82-123">可以通过将跟踪开关置于配置文件中来更改其级别。</span><span class="sxs-lookup"><span data-stu-id="d8b82-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="d8b82-124">如果开关是 @no__t 0，则可以将其打开或关闭。</span><span class="sxs-lookup"><span data-stu-id="d8b82-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="d8b82-125">如果开关是 @no__t 0，则可以为其分配不同的级别，以指定应用程序输出的跟踪或调试消息的类型。</span><span class="sxs-lookup"><span data-stu-id="d8b82-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8b82-126">示例</span><span class="sxs-lookup"><span data-stu-id="d8b82-126">Example</span></span>  
 <span data-ttu-id="d8b82-127">下面的示例演示如何使用 **\<切换>** 元素中设置`General`跟踪切换到<xref:System.Diagnostics.TraceLevel>级别，并启用`Data`布尔型跟踪开关。</span><span class="sxs-lookup"><span data-stu-id="d8b82-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d8b82-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8b82-128">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="d8b82-129">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="d8b82-129">Trace and Debug Settings Schema</span></span>](index.md)
 