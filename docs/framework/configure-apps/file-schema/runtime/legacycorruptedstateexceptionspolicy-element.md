---
title: <legacyCorruptedStateExceptionsPolicy> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d8733e11aba30ebea30fc71a5350f76dfd041eb4
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456417"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a><span data-ttu-id="3e51f-102">\<legacyCorruptedStateExceptionsPolicy > 元素</span><span class="sxs-lookup"><span data-stu-id="3e51f-102">\<legacyCorruptedStateExceptionsPolicy> Element</span></span>
<span data-ttu-id="3e51f-103">指定公共语言运行时是否允许托管的代码捕获访问冲突和其他损坏的状态异常。</span><span class="sxs-lookup"><span data-stu-id="3e51f-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
 <span data-ttu-id="3e51f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3e51f-104">\<configuration></span></span>  
<span data-ttu-id="3e51f-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="3e51f-105">\<runtime></span></span>  
<span data-ttu-id="3e51f-106">\<legacyCorruptedStateExceptionsPolicy></span><span class="sxs-lookup"><span data-stu-id="3e51f-106">\<legacyCorruptedStateExceptionsPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e51f-107">语法</span><span class="sxs-lookup"><span data-stu-id="3e51f-107">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3e51f-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3e51f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3e51f-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3e51f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3e51f-110">特性</span><span class="sxs-lookup"><span data-stu-id="3e51f-110">Attributes</span></span>  
  
|<span data-ttu-id="3e51f-111">特性</span><span class="sxs-lookup"><span data-stu-id="3e51f-111">Attribute</span></span>|<span data-ttu-id="3e51f-112">描述</span><span class="sxs-lookup"><span data-stu-id="3e51f-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="3e51f-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="3e51f-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="3e51f-114">指定应用程序将捕获损坏状态异常失败，例如，访问冲突。</span><span class="sxs-lookup"><span data-stu-id="3e51f-114">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="3e51f-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="3e51f-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="3e51f-116">值</span><span class="sxs-lookup"><span data-stu-id="3e51f-116">Value</span></span>|<span data-ttu-id="3e51f-117">描述</span><span class="sxs-lookup"><span data-stu-id="3e51f-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="3e51f-118">应用程序将不会捕获损坏状态异常失败，例如，访问冲突。</span><span class="sxs-lookup"><span data-stu-id="3e51f-118">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="3e51f-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="3e51f-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="3e51f-120">应用程序将捕获损坏状态异常失败，例如，访问冲突。</span><span class="sxs-lookup"><span data-stu-id="3e51f-120">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3e51f-121">子元素</span><span class="sxs-lookup"><span data-stu-id="3e51f-121">Child Elements</span></span>  
 <span data-ttu-id="3e51f-122">无。</span><span class="sxs-lookup"><span data-stu-id="3e51f-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3e51f-123">父元素</span><span class="sxs-lookup"><span data-stu-id="3e51f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3e51f-124">元素</span><span class="sxs-lookup"><span data-stu-id="3e51f-124">Element</span></span>|<span data-ttu-id="3e51f-125">描述</span><span class="sxs-lookup"><span data-stu-id="3e51f-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3e51f-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="3e51f-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3e51f-127">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="3e51f-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e51f-128">备注</span><span class="sxs-lookup"><span data-stu-id="3e51f-128">Remarks</span></span>  
 <span data-ttu-id="3e51f-129">在.NET Framework 版本 3.5 及更早版本中，公共语言运行时允许托管的代码来捕获损坏的进程状态已引发的异常。</span><span class="sxs-lookup"><span data-stu-id="3e51f-129">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="3e51f-130">访问冲突是异常的这种类型的示例。</span><span class="sxs-lookup"><span data-stu-id="3e51f-130">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="3e51f-131">从开始[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]的托管代码不能再捕获这些类型中的异常的`catch`块。</span><span class="sxs-lookup"><span data-stu-id="3e51f-131">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="3e51f-132">但是，您可以覆盖此更改并维护两种方式损坏的状态异常的处理：</span><span class="sxs-lookup"><span data-stu-id="3e51f-132">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
- <span data-ttu-id="3e51f-133">设置`<legacyCorruptedStateExceptionsPolicy>`元素的`enabled`属性为`true`。</span><span class="sxs-lookup"><span data-stu-id="3e51f-133">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="3e51f-134">此配置设置适用，并会影响所有方法。</span><span class="sxs-lookup"><span data-stu-id="3e51f-134">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="3e51f-135">或</span><span class="sxs-lookup"><span data-stu-id="3e51f-135">-or-</span></span>  
  
- <span data-ttu-id="3e51f-136">将应用<xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType>属性包含异常的方法为`catch`块。</span><span class="sxs-lookup"><span data-stu-id="3e51f-136">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="3e51f-137">此配置元素是仅适用于.NET Framework 4 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="3e51f-137">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e51f-138">示例</span><span class="sxs-lookup"><span data-stu-id="3e51f-138">Example</span></span>  
 <span data-ttu-id="3e51f-139">下面的示例演示如何指定应用程序应恢复为.NET Framework 4 之前, 的行为和捕获所有损坏状态异常失败。</span><span class="sxs-lookup"><span data-stu-id="3e51f-139">The following example shows how to specify that the application should revert to the behavior before the .NET Framework 4, and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3e51f-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e51f-140">See also</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [<span data-ttu-id="3e51f-141">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="3e51f-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="3e51f-142">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="3e51f-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
