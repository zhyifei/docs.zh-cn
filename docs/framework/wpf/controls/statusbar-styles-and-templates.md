---
title: StatusBar 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], StatusBar
- styles [WPF], StatusBar
- templates [WPF], StatusBar
- states [WPF], StatusBar
- parts [WPF], StatusBar
- StatusBar [WPF], styles and templates
ms.assetid: 9f5e1c25-81eb-4756-a0ac-d9e1fbe33ee2
ms.openlocfilehash: 11fa3ab6edd62f0b5484d9ccf76c101d04be353c
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2018
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="2dda9-102">StatusBar 样式和模板</span><span class="sxs-lookup"><span data-stu-id="2dda9-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="2dda9-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.Primitives.StatusBar>控件。</span><span class="sxs-lookup"><span data-stu-id="2dda9-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="2dda9-104">你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。</span><span class="sxs-lookup"><span data-stu-id="2dda9-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="2dda9-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="2dda9-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="2dda9-106">StatusBar 部件</span><span class="sxs-lookup"><span data-stu-id="2dda9-106">StatusBar Parts</span></span>  
 <span data-ttu-id="2dda9-107"><xref:System.Windows.Controls.Primitives.StatusBar>控件不具有任何已命名的部件。</span><span class="sxs-lookup"><span data-stu-id="2dda9-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="2dda9-108">StatusBar 状态</span><span class="sxs-lookup"><span data-stu-id="2dda9-108">StatusBar States</span></span>  
 <span data-ttu-id="2dda9-109">下表列出的可视状态<xref:System.Windows.Controls.Primitives.StatusBar>控件。</span><span class="sxs-lookup"><span data-stu-id="2dda9-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="2dda9-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="2dda9-110">VisualState Name</span></span>|<span data-ttu-id="2dda9-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="2dda9-111">VisualStateGroup Name</span></span>|<span data-ttu-id="2dda9-112">描述</span><span class="sxs-lookup"><span data-stu-id="2dda9-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="2dda9-113">有效</span><span class="sxs-lookup"><span data-stu-id="2dda9-113">Valid</span></span>|<span data-ttu-id="2dda9-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2dda9-114">ValidationStates</span></span>|<span data-ttu-id="2dda9-115">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="2dda9-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="2dda9-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="2dda9-116">InvalidFocused</span></span>|<span data-ttu-id="2dda9-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2dda9-117">ValidationStates</span></span>|<span data-ttu-id="2dda9-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="2dda9-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="2dda9-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="2dda9-119">InvalidUnfocused</span></span>|<span data-ttu-id="2dda9-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2dda9-120">ValidationStates</span></span>|<span data-ttu-id="2dda9-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="2dda9-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="2dda9-122">StatusBarItem 部件</span><span class="sxs-lookup"><span data-stu-id="2dda9-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="2dda9-123"><xref:System.Windows.Controls.Primitives.StatusBarItem>控件不具有任何已命名的部件。</span><span class="sxs-lookup"><span data-stu-id="2dda9-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="2dda9-124">StatusBar 状态</span><span class="sxs-lookup"><span data-stu-id="2dda9-124">StatusBar States</span></span>  
 <span data-ttu-id="2dda9-125">下表列出的可视状态<xref:System.Windows.Controls.Primitives.StatusBarItem>控件。</span><span class="sxs-lookup"><span data-stu-id="2dda9-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="2dda9-126">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="2dda9-126">VisualState Name</span></span>|<span data-ttu-id="2dda9-127">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="2dda9-127">VisualStateGroup Name</span></span>|<span data-ttu-id="2dda9-128">描述</span><span class="sxs-lookup"><span data-stu-id="2dda9-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="2dda9-129">有效</span><span class="sxs-lookup"><span data-stu-id="2dda9-129">Valid</span></span>|<span data-ttu-id="2dda9-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2dda9-130">ValidationStates</span></span>|<span data-ttu-id="2dda9-131">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="2dda9-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="2dda9-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="2dda9-132">InvalidFocused</span></span>|<span data-ttu-id="2dda9-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2dda9-133">ValidationStates</span></span>|<span data-ttu-id="2dda9-134"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="2dda9-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="2dda9-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="2dda9-135">InvalidUnfocused</span></span>|<span data-ttu-id="2dda9-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2dda9-136">ValidationStates</span></span>|<span data-ttu-id="2dda9-137"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="2dda9-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="2dda9-138">StatusBar ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="2dda9-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="2dda9-139">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Primitives.StatusBar>控件。</span><span class="sxs-lookup"><span data-stu-id="2dda9-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="2dda9-140"><xref:System.Windows.Controls.ControlTemplate>使用一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="2dda9-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="2dda9-141">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="2dda9-141">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dda9-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="2dda9-142">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="2dda9-143">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="2dda9-143">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="2dda9-144">控件自定义</span><span class="sxs-lookup"><span data-stu-id="2dda9-144">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="2dda9-145">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="2dda9-145">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="2dda9-146">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="2dda9-146">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
