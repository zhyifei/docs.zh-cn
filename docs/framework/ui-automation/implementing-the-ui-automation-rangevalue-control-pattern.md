---
title: 实现 UI 自动化 RangeValue 控件模式
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Range Value
- Range Value control pattern
- UI Automation, Range Value control pattern
ms.assetid: 225feaa4-918e-418b-938e-7389338d0a69
ms.openlocfilehash: bb486dc210bc2d03be6400e9fe5c80b2a7c1de8e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64659872"
---
# <a name="implementing-the-ui-automation-rangevalue-control-pattern"></a><span data-ttu-id="d09f6-102">实现 UI 自动化 RangeValue 控件模式</span><span class="sxs-lookup"><span data-stu-id="d09f6-102">Implementing the UI Automation RangeValue Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="d09f6-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="d09f6-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d09f6-104">有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API:UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="d09f6-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="d09f6-105">本主题介绍了实现 <xref:System.Windows.Automation.Provider.IRangeValueProvider>的准则和约定，包括有关事件和属性的信息。</span><span class="sxs-lookup"><span data-stu-id="d09f6-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IRangeValueProvider>, including information about events and properties.</span></span> <span data-ttu-id="d09f6-106">本主题的结尾列出了指向其他参考资料的链接。</span><span class="sxs-lookup"><span data-stu-id="d09f6-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="d09f6-107"><xref:System.Windows.Automation.RangeValuePattern> 控件模式用于支持可被设置为范围内的某个值的控件。</span><span class="sxs-lookup"><span data-stu-id="d09f6-107">The <xref:System.Windows.Automation.RangeValuePattern> control pattern is used to support controls that can be set to a value within a range.</span></span> <span data-ttu-id="d09f6-108">有关实现此控件模式的控件示例，请参阅 [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="d09f6-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="d09f6-109">实现准则和约定</span><span class="sxs-lookup"><span data-stu-id="d09f6-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="d09f6-110">在实现 Range Value 控件模式时，请注意以下准则和约定：</span><span class="sxs-lookup"><span data-stu-id="d09f6-110">When implementing the Range Value control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="d09f6-111">控件允许基于区域设置或用户首选项来校准支持的属性。</span><span class="sxs-lookup"><span data-stu-id="d09f6-111">Controls allow recalibration of their supported properties based upon locale or user preference.</span></span> <span data-ttu-id="d09f6-112">这样的一个示例是温度计控件，它可被设置为以华氏或摄氏显示温度。</span><span class="sxs-lookup"><span data-stu-id="d09f6-112">An example of this is a thermometer control that can be set to display the temperature in Fahrenheit or Celsius.</span></span>  
  
- <span data-ttu-id="d09f6-113">具有不明确范围值的控件（如进度栏或滑块）应对这些值进行规范化。</span><span class="sxs-lookup"><span data-stu-id="d09f6-113">Controls that have ambiguous range values, such as progress bars or sliders, should have those values normalized.</span></span>  
  
 <span data-ttu-id="d09f6-114">![进度栏。](../../../docs/framework/ui-automation/media/uia-rangevaluepattern-progress-bar.PNG "UIA_RangeValuePattern_Progress_Bar")</span><span class="sxs-lookup"><span data-stu-id="d09f6-114">![Progress bar.](../../../docs/framework/ui-automation/media/uia-rangevaluepattern-progress-bar.PNG "UIA_RangeValuePattern_Progress_Bar")</span></span>  
<span data-ttu-id="d09f6-115">进度栏的示例，其中值为整数类型，最小和最大属性值分别被规范化为 0 和 100</span><span class="sxs-lookup"><span data-stu-id="d09f6-115">Example of a Progress Bar Where Value Is of Type Integer and Minimum and Maximum Property Values Are Normalized to 0 and 100, Respectively</span></span>  
  
<a name="Required_Members_for_the_IRangeValueProvider"></a>   
## <a name="required-members-for-irangevalueprovider"></a><span data-ttu-id="d09f6-116">IRangeValueProvider 必需的成员</span><span class="sxs-lookup"><span data-stu-id="d09f6-116">Required Members for IRangeValueProvider</span></span>  
  
|<span data-ttu-id="d09f6-117">必需的成员</span><span class="sxs-lookup"><span data-stu-id="d09f6-117">Required member</span></span>|<span data-ttu-id="d09f6-118">成员类型</span><span class="sxs-lookup"><span data-stu-id="d09f6-118">Member type</span></span>|<span data-ttu-id="d09f6-119">说明</span><span class="sxs-lookup"><span data-stu-id="d09f6-119">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.RangeValuePattern.IsReadOnlyProperty>|<span data-ttu-id="d09f6-120">属性</span><span class="sxs-lookup"><span data-stu-id="d09f6-120">Property</span></span>|<span data-ttu-id="d09f6-121">None</span><span class="sxs-lookup"><span data-stu-id="d09f6-121">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.ValueProperty>|<span data-ttu-id="d09f6-122">属性</span><span class="sxs-lookup"><span data-stu-id="d09f6-122">Property</span></span>|<span data-ttu-id="d09f6-123">None</span><span class="sxs-lookup"><span data-stu-id="d09f6-123">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.LargeChangeProperty>|<span data-ttu-id="d09f6-124">属性</span><span class="sxs-lookup"><span data-stu-id="d09f6-124">Property</span></span>|<span data-ttu-id="d09f6-125">None</span><span class="sxs-lookup"><span data-stu-id="d09f6-125">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.SmallChangeProperty>|<span data-ttu-id="d09f6-126">属性</span><span class="sxs-lookup"><span data-stu-id="d09f6-126">Property</span></span>|<span data-ttu-id="d09f6-127">None</span><span class="sxs-lookup"><span data-stu-id="d09f6-127">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.MaximumProperty>|<span data-ttu-id="d09f6-128">属性</span><span class="sxs-lookup"><span data-stu-id="d09f6-128">Property</span></span>|<span data-ttu-id="d09f6-129">None</span><span class="sxs-lookup"><span data-stu-id="d09f6-129">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.MinimumProperty>|<span data-ttu-id="d09f6-130">属性</span><span class="sxs-lookup"><span data-stu-id="d09f6-130">Property</span></span>|<span data-ttu-id="d09f6-131">None</span><span class="sxs-lookup"><span data-stu-id="d09f6-131">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.SetValue%2A>|<span data-ttu-id="d09f6-132">方法</span><span class="sxs-lookup"><span data-stu-id="d09f6-132">Methods</span></span>|<span data-ttu-id="d09f6-133">None</span><span class="sxs-lookup"><span data-stu-id="d09f6-133">None</span></span>|  
  
 <span data-ttu-id="d09f6-134">没有与此控件模式关联的事件。</span><span class="sxs-lookup"><span data-stu-id="d09f6-134">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="d09f6-135">Exceptions</span><span class="sxs-lookup"><span data-stu-id="d09f6-135">Exceptions</span></span>  
 <span data-ttu-id="d09f6-136">提供程序必须引发以下异常。</span><span class="sxs-lookup"><span data-stu-id="d09f6-136">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="d09f6-137">异常类型</span><span class="sxs-lookup"><span data-stu-id="d09f6-137">Exception type</span></span>|<span data-ttu-id="d09f6-138">条件</span><span class="sxs-lookup"><span data-stu-id="d09f6-138">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentOutOfRangeException>|<span data-ttu-id="d09f6-139">使用一个大于<xref:System.Windows.Automation.RangeValuePattern.SetValue%2A> 或小于 <xref:System.Windows.Automation.RangeValuePattern.MaximumProperty> 的值调用 <xref:System.Windows.Automation.RangeValuePattern.MinimumProperty>。</span><span class="sxs-lookup"><span data-stu-id="d09f6-139"><xref:System.Windows.Automation.RangeValuePattern.SetValue%2A> is called with a value that is either greater than <xref:System.Windows.Automation.RangeValuePattern.MaximumProperty> or less than <xref:System.Windows.Automation.RangeValuePattern.MinimumProperty>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d09f6-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="d09f6-140">See also</span></span>

- [<span data-ttu-id="d09f6-141">UI 自动化控件模式概述</span><span class="sxs-lookup"><span data-stu-id="d09f6-141">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="d09f6-142">在 UI 自动化提供程序中支持控件模式</span><span class="sxs-lookup"><span data-stu-id="d09f6-142">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="d09f6-143">客户端的 UI 自动化控件模式</span><span class="sxs-lookup"><span data-stu-id="d09f6-143">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="d09f6-144">UI 自动化树概述</span><span class="sxs-lookup"><span data-stu-id="d09f6-144">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [<span data-ttu-id="d09f6-145">在 UI 自动化中使用缓存</span><span class="sxs-lookup"><span data-stu-id="d09f6-145">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
