---
title: "&lt;legacyCorruptedStateExceptionsPolicy&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f09d6cf256e072d01f3cfc79987aa4d240f96235
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltlegacycorruptedstateexceptionspolicygt-element"></a><span data-ttu-id="faf85-102">&lt;legacyCorruptedStateExceptionsPolicy&gt;元素</span><span class="sxs-lookup"><span data-stu-id="faf85-102">&lt;legacyCorruptedStateExceptionsPolicy&gt; Element</span></span>
<span data-ttu-id="faf85-103">指定公共语言运行时是否允许托管的代码获取访问冲突和其他损坏的状态异常。</span><span class="sxs-lookup"><span data-stu-id="faf85-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
 <span data-ttu-id="faf85-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="faf85-104">\<configuration></span></span>  
<span data-ttu-id="faf85-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="faf85-105">\<runtime></span></span>  
<span data-ttu-id="faf85-106">\<legacyCorruptedStateExceptionsPolicy ></span><span class="sxs-lookup"><span data-stu-id="faf85-106">\<legacyCorruptedStateExceptionsPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faf85-107">语法</span><span class="sxs-lookup"><span data-stu-id="faf85-107">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="faf85-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="faf85-108">Attributes and Elements</span></span>  
 <span data-ttu-id="faf85-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="faf85-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="faf85-110">特性</span><span class="sxs-lookup"><span data-stu-id="faf85-110">Attributes</span></span>  
  
|<span data-ttu-id="faf85-111">特性</span><span class="sxs-lookup"><span data-stu-id="faf85-111">Attribute</span></span>|<span data-ttu-id="faf85-112">描述</span><span class="sxs-lookup"><span data-stu-id="faf85-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="faf85-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="faf85-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="faf85-114">指定应用程序将捕获损坏状态异常失败，例如访问冲突。</span><span class="sxs-lookup"><span data-stu-id="faf85-114">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="faf85-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="faf85-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="faf85-116">值</span><span class="sxs-lookup"><span data-stu-id="faf85-116">Value</span></span>|<span data-ttu-id="faf85-117">描述</span><span class="sxs-lookup"><span data-stu-id="faf85-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="faf85-118">应用程序将不会捕获损坏状态异常失败，例如访问冲突。</span><span class="sxs-lookup"><span data-stu-id="faf85-118">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="faf85-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="faf85-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="faf85-120">应用程序将捕获损坏状态异常失败，例如访问冲突。</span><span class="sxs-lookup"><span data-stu-id="faf85-120">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="faf85-121">子元素</span><span class="sxs-lookup"><span data-stu-id="faf85-121">Child Elements</span></span>  
 <span data-ttu-id="faf85-122">无。</span><span class="sxs-lookup"><span data-stu-id="faf85-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="faf85-123">父元素</span><span class="sxs-lookup"><span data-stu-id="faf85-123">Parent Elements</span></span>  
  
|<span data-ttu-id="faf85-124">元素</span><span class="sxs-lookup"><span data-stu-id="faf85-124">Element</span></span>|<span data-ttu-id="faf85-125">说明</span><span class="sxs-lookup"><span data-stu-id="faf85-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="faf85-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="faf85-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="faf85-127">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="faf85-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="faf85-128">备注</span><span class="sxs-lookup"><span data-stu-id="faf85-128">Remarks</span></span>  
 <span data-ttu-id="faf85-129">在.NET Framework 版本 3.5 及更早版本中，公共语言运行时允许托管的代码，若要捕捉由损坏的进程状态引发的异常。</span><span class="sxs-lookup"><span data-stu-id="faf85-129">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="faf85-130">访问冲突是这种异常的示例。</span><span class="sxs-lookup"><span data-stu-id="faf85-130">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="faf85-131">从开始[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]，托管代码将不再捕获这些类型中的异常的`catch`块。</span><span class="sxs-lookup"><span data-stu-id="faf85-131">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="faf85-132">但是，你可以重写此更改和维护的两种方式的损坏的状态异常的处理方式：</span><span class="sxs-lookup"><span data-stu-id="faf85-132">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
-   <span data-ttu-id="faf85-133">设置`<legacyCorruptedStateExceptionsPolicy>`元素的`enabled`属性设为`true`。</span><span class="sxs-lookup"><span data-stu-id="faf85-133">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="faf85-134">此配置设置是适用，并且会影响所有方法。</span><span class="sxs-lookup"><span data-stu-id="faf85-134">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="faf85-135">- 或 -</span><span class="sxs-lookup"><span data-stu-id="faf85-135">-or-</span></span>  
  
-   <span data-ttu-id="faf85-136">应用<xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType>属性设为包含异常的方法`catch`块。</span><span class="sxs-lookup"><span data-stu-id="faf85-136">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="faf85-137">此配置元素可仅用于[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]及更高版本。</span><span class="sxs-lookup"><span data-stu-id="faf85-137">This configuration element is available only in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="faf85-138">示例</span><span class="sxs-lookup"><span data-stu-id="faf85-138">Example</span></span>  
 <span data-ttu-id="faf85-139">下面的示例演示如何指定应用程序应恢复到之前的行为[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]，并捕获所有损坏状态异常失败。</span><span class="sxs-lookup"><span data-stu-id="faf85-139">The following example shows how to specify that the application should revert to the behavior before the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="faf85-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="faf85-140">See Also</span></span>  
 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>  
 [<span data-ttu-id="faf85-141">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="faf85-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="faf85-142">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="faf85-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
