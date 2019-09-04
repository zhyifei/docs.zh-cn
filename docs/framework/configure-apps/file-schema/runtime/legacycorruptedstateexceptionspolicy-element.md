---
title: <legacyCorruptedStateExceptionsPolicy> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6566437d899b768cda1bab74bb1310deb7aa74db
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252506"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a><span data-ttu-id="63bc7-102">\<legacyCorruptedStateExceptionsPolicy > 元素</span><span class="sxs-lookup"><span data-stu-id="63bc7-102">\<legacyCorruptedStateExceptionsPolicy> Element</span></span>
<span data-ttu-id="63bc7-103">指定公共语言运行时是否允许托管代码捕获访问冲突和其他损坏状态异常。</span><span class="sxs-lookup"><span data-stu-id="63bc7-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
<span data-ttu-id="63bc7-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="63bc7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="63bc7-105">&nbsp;&nbsp;[ **\<运行时 >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="63bc7-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="63bc7-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<legacyCorruptedStateExceptionsPolicy>**</span><span class="sxs-lookup"><span data-stu-id="63bc7-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyCorruptedStateExceptionsPolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63bc7-107">语法</span><span class="sxs-lookup"><span data-stu-id="63bc7-107">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63bc7-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="63bc7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="63bc7-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="63bc7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63bc7-110">特性</span><span class="sxs-lookup"><span data-stu-id="63bc7-110">Attributes</span></span>  
  
|<span data-ttu-id="63bc7-111">特性</span><span class="sxs-lookup"><span data-stu-id="63bc7-111">Attribute</span></span>|<span data-ttu-id="63bc7-112">描述</span><span class="sxs-lookup"><span data-stu-id="63bc7-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="63bc7-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="63bc7-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="63bc7-114">指定应用程序将捕获损坏状态异常故障，例如访问冲突。</span><span class="sxs-lookup"><span data-stu-id="63bc7-114">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="63bc7-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="63bc7-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="63bc7-116">值</span><span class="sxs-lookup"><span data-stu-id="63bc7-116">Value</span></span>|<span data-ttu-id="63bc7-117">描述</span><span class="sxs-lookup"><span data-stu-id="63bc7-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="63bc7-118">应用程序不会捕获损坏状态异常故障，例如访问冲突。</span><span class="sxs-lookup"><span data-stu-id="63bc7-118">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="63bc7-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="63bc7-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="63bc7-120">应用程序将捕获损坏状态异常故障，例如访问冲突。</span><span class="sxs-lookup"><span data-stu-id="63bc7-120">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="63bc7-121">子元素</span><span class="sxs-lookup"><span data-stu-id="63bc7-121">Child Elements</span></span>  
 <span data-ttu-id="63bc7-122">无。</span><span class="sxs-lookup"><span data-stu-id="63bc7-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="63bc7-123">父元素</span><span class="sxs-lookup"><span data-stu-id="63bc7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="63bc7-124">元素</span><span class="sxs-lookup"><span data-stu-id="63bc7-124">Element</span></span>|<span data-ttu-id="63bc7-125">描述</span><span class="sxs-lookup"><span data-stu-id="63bc7-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="63bc7-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="63bc7-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="63bc7-127">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="63bc7-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63bc7-128">备注</span><span class="sxs-lookup"><span data-stu-id="63bc7-128">Remarks</span></span>  
 <span data-ttu-id="63bc7-129">在 .NET Framework 版本3.5 及更早版本中，公共语言运行时允许托管代码捕获由损坏的进程状态引发的异常。</span><span class="sxs-lookup"><span data-stu-id="63bc7-129">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="63bc7-130">访问冲突就是这种类型的异常的一个示例。</span><span class="sxs-lookup"><span data-stu-id="63bc7-130">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="63bc7-131">从 .NET Framework 4 开始，托管代码不再在块中`catch`捕获这些类型的异常。</span><span class="sxs-lookup"><span data-stu-id="63bc7-131">Starting with the .NET Framework 4, managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="63bc7-132">不过，你可以通过两种方式重写此更改并保持对损坏状态异常的处理：</span><span class="sxs-lookup"><span data-stu-id="63bc7-132">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
- <span data-ttu-id="63bc7-133">将元素的`enabled`属性设置为`true`。 `<legacyCorruptedStateExceptionsPolicy>`</span><span class="sxs-lookup"><span data-stu-id="63bc7-133">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="63bc7-134">此配置设置将应用 processwide 并影响所有方法。</span><span class="sxs-lookup"><span data-stu-id="63bc7-134">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="63bc7-135">或</span><span class="sxs-lookup"><span data-stu-id="63bc7-135">-or-</span></span>  
  
- <span data-ttu-id="63bc7-136">将特性应用于包含异常`catch`块的方法。 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="63bc7-136">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="63bc7-137">此配置元素仅在 .NET Framework 4 及更高版本中可用。</span><span class="sxs-lookup"><span data-stu-id="63bc7-137">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63bc7-138">示例</span><span class="sxs-lookup"><span data-stu-id="63bc7-138">Example</span></span>  
 <span data-ttu-id="63bc7-139">下面的示例演示如何指定应用程序应恢复到 .NET Framework 4 之前的行为，并捕获所有损坏状态异常错误。</span><span class="sxs-lookup"><span data-stu-id="63bc7-139">The following example shows how to specify that the application should revert to the behavior before the .NET Framework 4, and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="63bc7-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="63bc7-140">See also</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [<span data-ttu-id="63bc7-141">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="63bc7-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="63bc7-142">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="63bc7-142">Configuration File Schema</span></span>](../index.md)
