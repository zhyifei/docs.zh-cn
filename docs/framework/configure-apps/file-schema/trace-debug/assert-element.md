---
title: <assert> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assert
helpviewer_keywords:
- <assert> element
- assert element
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
ms.openlocfilehash: 30ec24aefcf8c4d1e110238a2c60a958eded5545
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699388"
---
# <a name="assert-element"></a><span data-ttu-id="32378-102">\<assert > 元素</span><span class="sxs-lookup"><span data-stu-id="32378-102">\<assert> Element</span></span>
<span data-ttu-id="32378-103">指定调用 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> 方法时是否显示消息框；另外指定要写入消息的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="32378-103">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>  
  
[<span data-ttu-id="32378-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="32378-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="32378-105">&nbsp; @ no__t-1[ **\<system >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="32378-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="32378-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t **\<assert >**</span><span class="sxs-lookup"><span data-stu-id="32378-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<assert>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32378-107">语法</span><span class="sxs-lookup"><span data-stu-id="32378-107">Syntax</span></span>  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32378-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="32378-108">Attributes and Elements</span></span>  
 <span data-ttu-id="32378-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="32378-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32378-110">特性</span><span class="sxs-lookup"><span data-stu-id="32378-110">Attributes</span></span>  
  
|<span data-ttu-id="32378-111">特性</span><span class="sxs-lookup"><span data-stu-id="32378-111">Attribute</span></span>|<span data-ttu-id="32378-112">描述</span><span class="sxs-lookup"><span data-stu-id="32378-112">Description</span></span>|  
|---------------|-----------------|  
|`assertuienabled`|<span data-ttu-id="32378-113">可选特性。</span><span class="sxs-lookup"><span data-stu-id="32378-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="32378-114">指定在**Debug 断言**方法的计算结果为**false**时是否显示消息框。</span><span class="sxs-lookup"><span data-stu-id="32378-114">Specifies whether to display a message box when the **Debug.Assert** method evaluates to **false**.</span></span>|  
|`logfilename`|<span data-ttu-id="32378-115">可选特性。</span><span class="sxs-lookup"><span data-stu-id="32378-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="32378-116">指定如果**debug.exe**的计算结果为**false**，则为要将消息写入到的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="32378-116">Specifies the name of the file to write the message to if **Debug.Assert** evaluates to **false**.</span></span>|  
  
## <a name="assertuienabled-attribute"></a><span data-ttu-id="32378-117">assertuienabled 特性</span><span class="sxs-lookup"><span data-stu-id="32378-117">assertuienabled Attribute</span></span>  
  
|<span data-ttu-id="32378-118">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="32378-118">Value</span></span>|<span data-ttu-id="32378-119">描述</span><span class="sxs-lookup"><span data-stu-id="32378-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="32378-120">显示消息框。</span><span class="sxs-lookup"><span data-stu-id="32378-120">Displays the message box.</span></span> <span data-ttu-id="32378-121">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="32378-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="32378-122">不显示消息框。</span><span class="sxs-lookup"><span data-stu-id="32378-122">Does not display the message box.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="32378-123">子元素</span><span class="sxs-lookup"><span data-stu-id="32378-123">Child Elements</span></span>  
 <span data-ttu-id="32378-124">无。</span><span class="sxs-lookup"><span data-stu-id="32378-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="32378-125">父元素</span><span class="sxs-lookup"><span data-stu-id="32378-125">Parent Elements</span></span>  
  
|<span data-ttu-id="32378-126">元素</span><span class="sxs-lookup"><span data-stu-id="32378-126">Element</span></span>|<span data-ttu-id="32378-127">描述</span><span class="sxs-lookup"><span data-stu-id="32378-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="32378-128">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="32378-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="32378-129">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="32378-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32378-130">备注</span><span class="sxs-lookup"><span data-stu-id="32378-130">Remarks</span></span>  
 <span data-ttu-id="32378-131">**@No__t-1assert >** 元素中的两个特性都是可选的。</span><span class="sxs-lookup"><span data-stu-id="32378-131">Both attributes in the **\<assert>** element are optional.</span></span> <span data-ttu-id="32378-132">您可以禁用消息框而不指定要向其中写入消息的文件，也可以指定在使消息框处于启用状态时要将消息写入到的文件。</span><span class="sxs-lookup"><span data-stu-id="32378-132">You can disable message boxes without specifying a file to write the messages to, or you can specify a file to write messages to while leaving message boxes enabled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32378-133">示例</span><span class="sxs-lookup"><span data-stu-id="32378-133">Example</span></span>  
 <span data-ttu-id="32378-134">下面的示例演示了如何在调用**Debug. 断言**并将消息写入 `c:\log.txt` 时禁用显示消息框。</span><span class="sxs-lookup"><span data-stu-id="32378-134">The following example shows how to disable displaying message boxes when you call **Debug.Assert** and write the messages to `c:\log.txt`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="32378-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="32378-135">See also</span></span>

- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="32378-136">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="32378-136">Trace and Debug Settings Schema</span></span>](index.md)
