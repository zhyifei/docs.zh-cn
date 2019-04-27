---
title: <NetFx40_PInvokeStackResilience> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 725bd715f6e70dff08929e58d588a3d8561d5011
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674059"
---
# <a name="netfx40pinvokestackresilience-element"></a><span data-ttu-id="e554e-102">\<NetFx40_PInvokeStackResilience > 元素</span><span class="sxs-lookup"><span data-stu-id="e554e-102">\<NetFx40_PInvokeStackResilience> Element</span></span>
<span data-ttu-id="e554e-103">指定运行时是否以减慢托管和非托管代码之间的转换速度为代价，在运行时自动修复不正确的平台调用声明。</span><span class="sxs-lookup"><span data-stu-id="e554e-103">Specifies whether the runtime automatically fixes incorrect platform invoke declarations at run time, at the cost of slower transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="e554e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e554e-104">\<configuration></span></span>  
<span data-ttu-id="e554e-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="e554e-105">\<runtime></span></span>  
<span data-ttu-id="e554e-106"><NetFx40_PInvokeStackResilience></span><span class="sxs-lookup"><span data-stu-id="e554e-106"><NetFx40_PInvokeStackResilience></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e554e-107">语法</span><span class="sxs-lookup"><span data-stu-id="e554e-107">Syntax</span></span>  
  
```xml  
<NetFx40_PInvokeStackResilience  enabled="1|0"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e554e-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e554e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e554e-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e554e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e554e-110">特性</span><span class="sxs-lookup"><span data-stu-id="e554e-110">Attributes</span></span>  
  
|<span data-ttu-id="e554e-111">特性</span><span class="sxs-lookup"><span data-stu-id="e554e-111">Attribute</span></span>|<span data-ttu-id="e554e-112">描述</span><span class="sxs-lookup"><span data-stu-id="e554e-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="e554e-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="e554e-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="e554e-114">指定是否在运行时检测到不正确的平台调用声明和 32 位平台上，将自动修复在运行时堆栈。</span><span class="sxs-lookup"><span data-stu-id="e554e-114">Specifies whether the runtime detects incorrect platform invoke declarations and automatically fixes the stack at run time on 32-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="e554e-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="e554e-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="e554e-116">“值”</span><span class="sxs-lookup"><span data-stu-id="e554e-116">Value</span></span>|<span data-ttu-id="e554e-117">描述</span><span class="sxs-lookup"><span data-stu-id="e554e-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="e554e-118">运行时使用的更快的互操作封送处理体系结构中引入[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]，这不会检测和修复不正确的平台调用声明。</span><span class="sxs-lookup"><span data-stu-id="e554e-118">The runtime uses the faster interop marshaling architecture introduced in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], which does not detect and fix incorrect platform invoke declarations.</span></span> <span data-ttu-id="e554e-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="e554e-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="e554e-120">运行时使用的转换速度的检测和修复不正确的平台调用声明。</span><span class="sxs-lookup"><span data-stu-id="e554e-120">The runtime uses slower transitions that detect and fix incorrect platform invoke declarations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e554e-121">子元素</span><span class="sxs-lookup"><span data-stu-id="e554e-121">Child Elements</span></span>  
 <span data-ttu-id="e554e-122">无。</span><span class="sxs-lookup"><span data-stu-id="e554e-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e554e-123">父元素</span><span class="sxs-lookup"><span data-stu-id="e554e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e554e-124">元素</span><span class="sxs-lookup"><span data-stu-id="e554e-124">Element</span></span>|<span data-ttu-id="e554e-125">描述</span><span class="sxs-lookup"><span data-stu-id="e554e-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e554e-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="e554e-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e554e-127">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="e554e-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e554e-128">备注</span><span class="sxs-lookup"><span data-stu-id="e554e-128">Remarks</span></span>  
 <span data-ttu-id="e554e-129">此元素可以交换更快地互操作封送处理运行时恢复能力对不正确的平台调用声明。</span><span class="sxs-lookup"><span data-stu-id="e554e-129">This element enables you to trade faster interop marshaling for run-time resilience against incorrect platform invoke declarations.</span></span>  
  
 <span data-ttu-id="e554e-130">从开始[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]，简化的互操作封送处理体系结构提供了从托管代码转换到非托管代码一显著的性能改进。</span><span class="sxs-lookup"><span data-stu-id="e554e-130">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], a streamlined interop marshaling architecture provides a significant performance improvement for transitions from managed code to unmanaged code.</span></span> <span data-ttu-id="e554e-131">在早期版本的.NET Framework，封送处理层检测到不正确的平台调用在 32 位平台上的声明，并自动修复堆栈。</span><span class="sxs-lookup"><span data-stu-id="e554e-131">In earlier versions of the .NET Framework, the marshaling layer detected incorrect platform invoke declarations on 32-bit platforms and automatically fixed the stack.</span></span> <span data-ttu-id="e554e-132">新的封送处理体系结构消除了此步骤。</span><span class="sxs-lookup"><span data-stu-id="e554e-132">The new marshaling architecture eliminates this step.</span></span> <span data-ttu-id="e554e-133">因此，转换速度非常快，但不正确的平台调用声明可能会导致程序失败。</span><span class="sxs-lookup"><span data-stu-id="e554e-133">As a result, transitions are very fast, but an incorrect platform invoke declaration can cause a program failure.</span></span>  
  
 <span data-ttu-id="e554e-134">为了更加轻松地在开发过程中检测不正确的声明，改进 Visual Studio 调试体验。</span><span class="sxs-lookup"><span data-stu-id="e554e-134">To make it easy to detect incorrect declarations during development, the Visual Studio debugging experience has been improved.</span></span> <span data-ttu-id="e554e-135">[PInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)托管调试助手 (MDA) 通知你的应用程序运行带有附加调试程序时，您不正确的平台调用声明。</span><span class="sxs-lookup"><span data-stu-id="e554e-135">The [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) managed debugging assistant (MDA) notifies you of incorrect platform invoke declarations when your application is running with the debugger attached.</span></span>  
  
 <span data-ttu-id="e554e-136">为应用程序使用组件，则不能重新编译，和，具有不正确的平台调用声明，您可以使用其中的解决情况`NetFx40_PInvokeStackResilience`元素。</span><span class="sxs-lookup"><span data-stu-id="e554e-136">To address scenarios where your application uses components that you cannot recompile, and that have incorrect platform invoke declarations, you can use the `NetFx40_PInvokeStackResilience` element.</span></span> <span data-ttu-id="e554e-137">将此元素添加到应用程序配置文件与`enabled="1"`opts 到与早期版本的.NET Framework 中，转换速度为代价的行为的兼容性模式。</span><span class="sxs-lookup"><span data-stu-id="e554e-137">Adding this element to your application configuration file with `enabled="1"` opts into a compatibility mode with the behavior of earlier versions of the .NET Framework, at the cost of slower transitions.</span></span> <span data-ttu-id="e554e-138">已针对.NET Framework 的早期版本编译的程序集自动选择加入此兼容性模式，并且不需要此元素。</span><span class="sxs-lookup"><span data-stu-id="e554e-138">Assemblies that have been compiled against earlier versions of the .NET Framework are automatically opted into this compatibility mode, and do not need this element.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="e554e-139">配置文件</span><span class="sxs-lookup"><span data-stu-id="e554e-139">Configuration File</span></span>  
 <span data-ttu-id="e554e-140">仅在应用程序配置文件中，可以使用此元素。</span><span class="sxs-lookup"><span data-stu-id="e554e-140">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e554e-141">示例</span><span class="sxs-lookup"><span data-stu-id="e554e-141">Example</span></span>  
 <span data-ttu-id="e554e-142">下面的示例演示如何对不正确的增强恢复能力选择使用平台调用声明应用程序之间的转换速度为代价托管和非托管代码。</span><span class="sxs-lookup"><span data-stu-id="e554e-142">The following example shows how to opt into increased resilience against incorrect platform invoke declarations for an application, at the cost of slower transitions between managed and unmanaged code.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_PInvokeStackResilience enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e554e-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="e554e-143">See also</span></span>

- [<span data-ttu-id="e554e-144">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="e554e-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="e554e-145">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="e554e-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="e554e-146">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="e554e-146">pInvokeStackImbalance</span></span>](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)
