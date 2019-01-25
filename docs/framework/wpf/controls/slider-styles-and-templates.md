---
title: Slider 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Slider
- states [WPF], Slider
- Slider [WPF], styles and templates
- styles [WPF], Slider
- templates [WPF], Slider
- ControlTemplate [WPF], Slider
ms.assetid: d89aa97b-075a-4752-9c41-9679df65c491
ms.openlocfilehash: 3b56b26716eb2ffc0a776085579c4d5df09e3ace
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596249"
---
# <a name="slider-styles-and-templates"></a><span data-ttu-id="13e42-102">Slider 样式和模板</span><span class="sxs-lookup"><span data-stu-id="13e42-102">Slider Styles and Templates</span></span>
<span data-ttu-id="13e42-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.Slider>控件。</span><span class="sxs-lookup"><span data-stu-id="13e42-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Slider> control.</span></span> <span data-ttu-id="13e42-104">可以修改默认<xref:System.Windows.Controls.ControlTemplate>为控件提供唯一外观。</span><span class="sxs-lookup"><span data-stu-id="13e42-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="13e42-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="13e42-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="slider-parts"></a><span data-ttu-id="13e42-106">滑块部分</span><span class="sxs-lookup"><span data-stu-id="13e42-106">Slider Parts</span></span>  
 <span data-ttu-id="13e42-107">下表列出了用于命名的部件<xref:System.Windows.Controls.Slider>控件。</span><span class="sxs-lookup"><span data-stu-id="13e42-107">The following table lists the named parts for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="13e42-108">部件</span><span class="sxs-lookup"><span data-stu-id="13e42-108">Part</span></span>|<span data-ttu-id="13e42-109">类型</span><span class="sxs-lookup"><span data-stu-id="13e42-109">Type</span></span>|<span data-ttu-id="13e42-110">描述</span><span class="sxs-lookup"><span data-stu-id="13e42-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="13e42-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="13e42-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="13e42-112">指示的位置的元素的容器<xref:System.Windows.Controls.Slider>。</span><span class="sxs-lookup"><span data-stu-id="13e42-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Slider>.</span></span>|  
|<span data-ttu-id="13e42-113">PART_SelectionRange</span><span class="sxs-lookup"><span data-stu-id="13e42-113">PART_SelectionRange</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="13e42-114">显示选择范围沿元素<xref:System.Windows.Controls.Slider>。</span><span class="sxs-lookup"><span data-stu-id="13e42-114">The element that displays a selection range along the <xref:System.Windows.Controls.Slider>.</span></span>  <span data-ttu-id="13e42-115">选择范围，可见才<xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A>属性是`true`。</span><span class="sxs-lookup"><span data-stu-id="13e42-115">The selection range is visible only if the <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> property is `true`.</span></span>|  
  
## <a name="slider-states"></a><span data-ttu-id="13e42-116">滑块状态</span><span class="sxs-lookup"><span data-stu-id="13e42-116">Slider States</span></span>  
 <span data-ttu-id="13e42-117">下表列出了的可视状态<xref:System.Windows.Controls.Slider>控件。</span><span class="sxs-lookup"><span data-stu-id="13e42-117">The following table lists the visual states for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="13e42-118">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="13e42-118">VisualState Name</span></span>|<span data-ttu-id="13e42-119">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="13e42-119">VisualStateGroup Name</span></span>|<span data-ttu-id="13e42-120">描述</span><span class="sxs-lookup"><span data-stu-id="13e42-120">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="13e42-121">普通</span><span class="sxs-lookup"><span data-stu-id="13e42-121">Normal</span></span>|<span data-ttu-id="13e42-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="13e42-122">CommonStates</span></span>|<span data-ttu-id="13e42-123">默认状态。</span><span class="sxs-lookup"><span data-stu-id="13e42-123">The default state.</span></span>|  
|<span data-ttu-id="13e42-124">MouseOver</span><span class="sxs-lookup"><span data-stu-id="13e42-124">MouseOver</span></span>|<span data-ttu-id="13e42-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="13e42-125">CommonStates</span></span>|<span data-ttu-id="13e42-126">鼠标指针悬停在控件上。</span><span class="sxs-lookup"><span data-stu-id="13e42-126">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="13e42-127">已禁用</span><span class="sxs-lookup"><span data-stu-id="13e42-127">Disabled</span></span>|<span data-ttu-id="13e42-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="13e42-128">CommonStates</span></span>|<span data-ttu-id="13e42-129">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="13e42-129">The control is disabled.</span></span>|  
|<span data-ttu-id="13e42-130">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="13e42-130">Focused</span></span>|<span data-ttu-id="13e42-131">FocusStates</span><span class="sxs-lookup"><span data-stu-id="13e42-131">FocusStates</span></span>|<span data-ttu-id="13e42-132">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="13e42-132">The control has focus.</span></span>|  
|<span data-ttu-id="13e42-133">失去焦点</span><span class="sxs-lookup"><span data-stu-id="13e42-133">Unfocused</span></span>|<span data-ttu-id="13e42-134">FocusStates</span><span class="sxs-lookup"><span data-stu-id="13e42-134">FocusStates</span></span>|<span data-ttu-id="13e42-135">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="13e42-135">The control does not have focus.</span></span>|  
|<span data-ttu-id="13e42-136">有效</span><span class="sxs-lookup"><span data-stu-id="13e42-136">Valid</span></span>|<span data-ttu-id="13e42-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="13e42-137">ValidationStates</span></span>|<span data-ttu-id="13e42-138">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`false`。</span><span class="sxs-lookup"><span data-stu-id="13e42-138">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="13e42-139">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="13e42-139">InvalidFocused</span></span>|<span data-ttu-id="13e42-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="13e42-140">ValidationStates</span></span>|<span data-ttu-id="13e42-141"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="13e42-141">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="13e42-142">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="13e42-142">InvalidUnfocused</span></span>|<span data-ttu-id="13e42-143">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="13e42-143">ValidationStates</span></span>|<span data-ttu-id="13e42-144"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="13e42-144">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="slider-controltemplate-example"></a><span data-ttu-id="13e42-145">滑块 ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="13e42-145">Slider ControlTemplate Example</span></span>  
 <span data-ttu-id="13e42-146">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Slider>控件。</span><span class="sxs-lookup"><span data-stu-id="13e42-146">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Slider](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#slider)]  
  
 <span data-ttu-id="13e42-147">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="13e42-147">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="13e42-148">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="13e42-148">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13e42-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="13e42-149">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="13e42-150">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="13e42-150">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- [<span data-ttu-id="13e42-151">控件自定义</span><span class="sxs-lookup"><span data-stu-id="13e42-151">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)
- [<span data-ttu-id="13e42-152">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="13e42-152">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [<span data-ttu-id="13e42-153">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="13e42-153">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
