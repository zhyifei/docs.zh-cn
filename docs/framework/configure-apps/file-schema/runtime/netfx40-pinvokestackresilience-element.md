---
title: <NetFx40_PInvokeStackResilience> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf97cc1ec544c7cf640c43b1b45760fca8cffe89
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663554"
---
# <a name="netfx40_pinvokestackresilience-element"></a><span data-ttu-id="abf36-102">\<NetFx40_PInvokeStackResilience > 元素</span><span class="sxs-lookup"><span data-stu-id="abf36-102">\<NetFx40_PInvokeStackResilience> Element</span></span>

<span data-ttu-id="abf36-103">指定运行时是否以减慢托管和非托管代码之间的转换速度为代价，在运行时自动修复不正确的平台调用声明。</span><span class="sxs-lookup"><span data-stu-id="abf36-103">Specifies whether the runtime automatically fixes incorrect platform invoke declarations at run time, at the cost of slower transitions between managed and unmanaged code.</span></span>

<span data-ttu-id="abf36-104">\<配置 > </span><span class="sxs-lookup"><span data-stu-id="abf36-104">\<configuration></span></span>\
<span data-ttu-id="abf36-105">\<运行时 > </span><span class="sxs-lookup"><span data-stu-id="abf36-105">\<runtime></span></span>\
<span data-ttu-id="abf36-106">\<NetFx40_PInvokeStackResilience></span><span class="sxs-lookup"><span data-stu-id="abf36-106">\<NetFx40_PInvokeStackResilience></span></span>

## <a name="syntax"></a><span data-ttu-id="abf36-107">语法</span><span class="sxs-lookup"><span data-stu-id="abf36-107">Syntax</span></span>

```xml
<NetFx40_PInvokeStackResilience  enabled="1|0"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="abf36-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="abf36-108">Attributes and Elements</span></span>

<span data-ttu-id="abf36-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="abf36-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="abf36-110">特性</span><span class="sxs-lookup"><span data-stu-id="abf36-110">Attributes</span></span>

|<span data-ttu-id="abf36-111">特性</span><span class="sxs-lookup"><span data-stu-id="abf36-111">Attribute</span></span>|<span data-ttu-id="abf36-112">描述</span><span class="sxs-lookup"><span data-stu-id="abf36-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="abf36-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="abf36-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="abf36-114">指定运行时是否检测到不正确的平台调用声明, 并在运行时在32位平台上自动修复堆栈。</span><span class="sxs-lookup"><span data-stu-id="abf36-114">Specifies whether the runtime detects incorrect platform invoke declarations and automatically fixes the stack at run time on 32-bit platforms.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="abf36-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="abf36-115">enabled Attribute</span></span>

|<span data-ttu-id="abf36-116">值</span><span class="sxs-lookup"><span data-stu-id="abf36-116">Value</span></span>|<span data-ttu-id="abf36-117">描述</span><span class="sxs-lookup"><span data-stu-id="abf36-117">Description</span></span>|
|-----------|-----------------|
|`0`|<span data-ttu-id="abf36-118">运行时使用 .NET Framework 4 中引入的更快互操作封送处理体系结构, 该体系结构不会检测并修复不正确的平台调用声明。</span><span class="sxs-lookup"><span data-stu-id="abf36-118">The runtime uses the faster interop marshaling architecture introduced in the .NET Framework 4, which does not detect and fix incorrect platform invoke declarations.</span></span> <span data-ttu-id="abf36-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="abf36-119">This is the default.</span></span>|
|`1`|<span data-ttu-id="abf36-120">运行时使用检测并修复不正确的平台调用声明的慢速转换。</span><span class="sxs-lookup"><span data-stu-id="abf36-120">The runtime uses slower transitions that detect and fix incorrect platform invoke declarations.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="abf36-121">子元素</span><span class="sxs-lookup"><span data-stu-id="abf36-121">Child Elements</span></span>

<span data-ttu-id="abf36-122">无。</span><span class="sxs-lookup"><span data-stu-id="abf36-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="abf36-123">父元素</span><span class="sxs-lookup"><span data-stu-id="abf36-123">Parent Elements</span></span>

|<span data-ttu-id="abf36-124">元素</span><span class="sxs-lookup"><span data-stu-id="abf36-124">Element</span></span>|<span data-ttu-id="abf36-125">描述</span><span class="sxs-lookup"><span data-stu-id="abf36-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="abf36-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="abf36-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="abf36-127">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="abf36-127">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="abf36-128">备注</span><span class="sxs-lookup"><span data-stu-id="abf36-128">Remarks</span></span>

<span data-ttu-id="abf36-129">此元素使您能够以更快的互操作封送处理为依据不正确的平台调用声明来处理运行时复原。</span><span class="sxs-lookup"><span data-stu-id="abf36-129">This element enables you to trade faster interop marshaling for run-time resilience against incorrect platform invoke declarations.</span></span>

<span data-ttu-id="abf36-130">从 .NET Framework 4 开始, 简化的互操作封送处理体系结构可为从托管代码到非托管代码的转换提供显著的性能改进。</span><span class="sxs-lookup"><span data-stu-id="abf36-130">Starting with the .NET Framework 4, a streamlined interop marshaling architecture provides a significant performance improvement for transitions from managed code to unmanaged code.</span></span> <span data-ttu-id="abf36-131">在 .NET Framework 的早期版本中, 封送层在32位平台上检测到不正确的平台调用声明, 并自动修复堆栈。</span><span class="sxs-lookup"><span data-stu-id="abf36-131">In earlier versions of the .NET Framework, the marshaling layer detected incorrect platform invoke declarations on 32-bit platforms and automatically fixed the stack.</span></span> <span data-ttu-id="abf36-132">新的封送处理体系结构消除了此步骤。</span><span class="sxs-lookup"><span data-stu-id="abf36-132">The new marshaling architecture eliminates this step.</span></span> <span data-ttu-id="abf36-133">因此, 转换速度非常快, 但不正确的平台调用声明可能导致程序失败。</span><span class="sxs-lookup"><span data-stu-id="abf36-133">As a result, transitions are very fast, but an incorrect platform invoke declaration can cause a program failure.</span></span>

<span data-ttu-id="abf36-134">为了便于在开发期间检测到不正确的声明, Visual Studio 调试体验也得到了改进。</span><span class="sxs-lookup"><span data-stu-id="abf36-134">To make it easy to detect incorrect declarations during development, the Visual Studio debugging experience has been improved.</span></span> <span data-ttu-id="abf36-135">当应用程序在附加调试器中运行时, [pInvokeStackImbalance](../../../debug-trace-profile/pinvokestackimbalance-mda.md)托管调试助手 (MDA) 将通知您不正确的平台调用声明。</span><span class="sxs-lookup"><span data-stu-id="abf36-135">The [pInvokeStackImbalance](../../../debug-trace-profile/pinvokestackimbalance-mda.md) managed debugging assistant (MDA) notifies you of incorrect platform invoke declarations when your application is running with the debugger attached.</span></span>

<span data-ttu-id="abf36-136">若要解决您的应用程序使用无法重新编译的组件, 并且具有不正确的平台调用声明的情况, `NetFx40_PInvokeStackResilience`可以使用元素。</span><span class="sxs-lookup"><span data-stu-id="abf36-136">To address scenarios where your application uses components that you cannot recompile, and that have incorrect platform invoke declarations, you can use the `NetFx40_PInvokeStackResilience` element.</span></span> <span data-ttu-id="abf36-137">将此元素添加到应用程序配置文件`enabled="1"`中, 并将其 "导入" 到兼容模式, 并且具有较早版本的 .NET Framework 的行为, 代价是慢于转换。</span><span class="sxs-lookup"><span data-stu-id="abf36-137">Adding this element to your application configuration file with `enabled="1"` opts into a compatibility mode with the behavior of earlier versions of the .NET Framework, at the cost of slower transitions.</span></span> <span data-ttu-id="abf36-138">已针对早期版本的 .NET Framework 编译的程序集会自动选择进入此兼容模式, 并且不需要此元素。</span><span class="sxs-lookup"><span data-stu-id="abf36-138">Assemblies that have been compiled against earlier versions of the .NET Framework are automatically opted into this compatibility mode, and do not need this element.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="abf36-139">配置文件</span><span class="sxs-lookup"><span data-stu-id="abf36-139">Configuration File</span></span>

<span data-ttu-id="abf36-140">此元素只能在应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="abf36-140">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="abf36-141">示例</span><span class="sxs-lookup"><span data-stu-id="abf36-141">Example</span></span>

<span data-ttu-id="abf36-142">下面的示例演示如何针对应用程序的不正确的平台调用声明提高复原能力, 降低了托管和非托管代码之间的转换速度。</span><span class="sxs-lookup"><span data-stu-id="abf36-142">The following example shows how to opt into increased resilience against incorrect platform invoke declarations for an application, at the cost of slower transitions between managed and unmanaged code.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_PInvokeStackResilience enabled="1"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="abf36-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="abf36-143">See also</span></span>

- [<span data-ttu-id="abf36-144">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="abf36-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="abf36-145">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="abf36-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="abf36-146">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="abf36-146">pInvokeStackImbalance</span></span>](../../../debug-trace-profile/pinvokestackimbalance-mda.md)
