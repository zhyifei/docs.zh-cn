---
title: '&lt;断言&gt;元素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assert
helpviewer_keywords:
- <assert> element
- assert element
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
author: mcleblanc
ms.author: markl
ms.openlocfilehash: b15e569ff6e42298c0a1de02f77ab7c302c70d86
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48266138"
---
# <a name="ltassertgt-element"></a><span data-ttu-id="6d352-102">&lt;断言&gt;元素</span><span class="sxs-lookup"><span data-stu-id="6d352-102">&lt;assert&gt; Element</span></span>
<span data-ttu-id="6d352-103">指定调用 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> 方法时是否显示消息框；另外指定要写入消息的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="6d352-103">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>  
  
 <span data-ttu-id="6d352-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6d352-104">\<configuration></span></span>  
<span data-ttu-id="6d352-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="6d352-105">\<system.diagnostics></span></span>  
<span data-ttu-id="6d352-106">\<断言 ></span><span class="sxs-lookup"><span data-stu-id="6d352-106">\<assert></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d352-107">语法</span><span class="sxs-lookup"><span data-stu-id="6d352-107">Syntax</span></span>  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6d352-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6d352-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6d352-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6d352-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6d352-110">特性</span><span class="sxs-lookup"><span data-stu-id="6d352-110">Attributes</span></span>  
  
|<span data-ttu-id="6d352-111">特性</span><span class="sxs-lookup"><span data-stu-id="6d352-111">Attribute</span></span>|<span data-ttu-id="6d352-112">描述</span><span class="sxs-lookup"><span data-stu-id="6d352-112">Description</span></span>|  
|---------------|-----------------|  
|`assertuienabled`|<span data-ttu-id="6d352-113">可选特性。</span><span class="sxs-lookup"><span data-stu-id="6d352-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="6d352-114">指定是否显示消息框何时**Debug.Assert**方法的计算结果为**false**。</span><span class="sxs-lookup"><span data-stu-id="6d352-114">Specifies whether to display a message box when the **Debug.Assert** method evaluates to **false**.</span></span>|  
|`logfilename`|<span data-ttu-id="6d352-115">可选特性。</span><span class="sxs-lookup"><span data-stu-id="6d352-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="6d352-116">指定要将消息写到如果的文件的名称**Debug.Assert**的计算结果为**false**。</span><span class="sxs-lookup"><span data-stu-id="6d352-116">Specifies the name of the file to write the message to if **Debug.Assert** evaluates to **false**.</span></span>|  
  
## <a name="assertuienabled-attribute"></a><span data-ttu-id="6d352-117">assertuienabled 属性</span><span class="sxs-lookup"><span data-stu-id="6d352-117">assertuienabled Attribute</span></span>  
  
|<span data-ttu-id="6d352-118">“值”</span><span class="sxs-lookup"><span data-stu-id="6d352-118">Value</span></span>|<span data-ttu-id="6d352-119">描述</span><span class="sxs-lookup"><span data-stu-id="6d352-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="6d352-120">显示消息框。</span><span class="sxs-lookup"><span data-stu-id="6d352-120">Displays the message box.</span></span> <span data-ttu-id="6d352-121">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="6d352-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="6d352-122">不显示消息框。</span><span class="sxs-lookup"><span data-stu-id="6d352-122">Does not display the message box.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6d352-123">子元素</span><span class="sxs-lookup"><span data-stu-id="6d352-123">Child Elements</span></span>  
 <span data-ttu-id="6d352-124">无。</span><span class="sxs-lookup"><span data-stu-id="6d352-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6d352-125">父元素</span><span class="sxs-lookup"><span data-stu-id="6d352-125">Parent Elements</span></span>  
  
|<span data-ttu-id="6d352-126">元素</span><span class="sxs-lookup"><span data-stu-id="6d352-126">Element</span></span>|<span data-ttu-id="6d352-127">描述</span><span class="sxs-lookup"><span data-stu-id="6d352-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6d352-128">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="6d352-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="6d352-129">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="6d352-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d352-130">备注</span><span class="sxs-lookup"><span data-stu-id="6d352-130">Remarks</span></span>  
 <span data-ttu-id="6d352-131">在这两个属性 **\<assert >** 元素是可选的。</span><span class="sxs-lookup"><span data-stu-id="6d352-131">Both attributes in the **\<assert>** element are optional.</span></span> <span data-ttu-id="6d352-132">您可以禁用消息框，而无需指定要将消息写入的文件，也可以指定要写入消息时保留启用的消息框的文件。</span><span class="sxs-lookup"><span data-stu-id="6d352-132">You can disable message boxes without specifying a file to write the messages to, or you can specify a file to write messages to while leaving message boxes enabled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d352-133">示例</span><span class="sxs-lookup"><span data-stu-id="6d352-133">Example</span></span>  
 <span data-ttu-id="6d352-134">下面的示例演示如何在调用时禁用显示消息框**Debug.Assert**并将消息写入`c:\log.txt`。</span><span class="sxs-lookup"><span data-stu-id="6d352-134">The following example shows how to disable displaying message boxes when you call **Debug.Assert** and write the messages to `c:\log.txt`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6d352-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="6d352-135">See Also</span></span>  
 <xref:System.Diagnostics.Debug>  
 [<span data-ttu-id="6d352-136">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="6d352-136">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
