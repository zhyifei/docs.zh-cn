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
ms.openlocfilehash: f533142d5ba202bd4aaf628487eaaa2a18a535d0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283388"
---
# <a name="slider-styles-and-templates"></a><span data-ttu-id="3b39f-102">Slider 样式和模板</span><span class="sxs-lookup"><span data-stu-id="3b39f-102">Slider Styles and Templates</span></span>
<span data-ttu-id="3b39f-103">本主题介绍 <xref:System.Windows.Controls.Slider> 控件的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="3b39f-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Slider> control.</span></span> <span data-ttu-id="3b39f-104">您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。</span><span class="sxs-lookup"><span data-stu-id="3b39f-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="3b39f-105">有关详细信息，请参阅为[控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)。</span><span class="sxs-lookup"><span data-stu-id="3b39f-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="slider-parts"></a><span data-ttu-id="3b39f-106">滑块部分</span><span class="sxs-lookup"><span data-stu-id="3b39f-106">Slider Parts</span></span>  
 <span data-ttu-id="3b39f-107">下表列出了 <xref:System.Windows.Controls.Slider> 控件的已命名部分。</span><span class="sxs-lookup"><span data-stu-id="3b39f-107">The following table lists the named parts for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="3b39f-108">部件</span><span class="sxs-lookup"><span data-stu-id="3b39f-108">Part</span></span>|<span data-ttu-id="3b39f-109">类型</span><span class="sxs-lookup"><span data-stu-id="3b39f-109">Type</span></span>|<span data-ttu-id="3b39f-110">说明</span><span class="sxs-lookup"><span data-stu-id="3b39f-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="3b39f-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="3b39f-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="3b39f-112">指示 <xref:System.Windows.Controls.Slider>位置的元素的容器。</span><span class="sxs-lookup"><span data-stu-id="3b39f-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Slider>.</span></span>|  
|<span data-ttu-id="3b39f-113">PART_SelectionRange</span><span class="sxs-lookup"><span data-stu-id="3b39f-113">PART_SelectionRange</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="3b39f-114">沿 <xref:System.Windows.Controls.Slider>显示选择范围的元素。</span><span class="sxs-lookup"><span data-stu-id="3b39f-114">The element that displays a selection range along the <xref:System.Windows.Controls.Slider>.</span></span>  <span data-ttu-id="3b39f-115">仅当 `true`<xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> 属性时，选择范围才可见。</span><span class="sxs-lookup"><span data-stu-id="3b39f-115">The selection range is visible only if the <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> property is `true`.</span></span>|  
  
## <a name="slider-states"></a><span data-ttu-id="3b39f-116">滑块状态</span><span class="sxs-lookup"><span data-stu-id="3b39f-116">Slider States</span></span>  
 <span data-ttu-id="3b39f-117">下表列出了 <xref:System.Windows.Controls.Slider> 控件的可视状态。</span><span class="sxs-lookup"><span data-stu-id="3b39f-117">The following table lists the visual states for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="3b39f-118">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="3b39f-118">VisualState Name</span></span>|<span data-ttu-id="3b39f-119">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="3b39f-119">VisualStateGroup Name</span></span>|<span data-ttu-id="3b39f-120">说明</span><span class="sxs-lookup"><span data-stu-id="3b39f-120">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="3b39f-121">正常</span><span class="sxs-lookup"><span data-stu-id="3b39f-121">Normal</span></span>|<span data-ttu-id="3b39f-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3b39f-122">CommonStates</span></span>|<span data-ttu-id="3b39f-123">默认状态。</span><span class="sxs-lookup"><span data-stu-id="3b39f-123">The default state.</span></span>|  
|<span data-ttu-id="3b39f-124">MouseOver</span><span class="sxs-lookup"><span data-stu-id="3b39f-124">MouseOver</span></span>|<span data-ttu-id="3b39f-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3b39f-125">CommonStates</span></span>|<span data-ttu-id="3b39f-126">鼠标指针悬停在控件上。</span><span class="sxs-lookup"><span data-stu-id="3b39f-126">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="3b39f-127">已禁用</span><span class="sxs-lookup"><span data-stu-id="3b39f-127">Disabled</span></span>|<span data-ttu-id="3b39f-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3b39f-128">CommonStates</span></span>|<span data-ttu-id="3b39f-129">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="3b39f-129">The control is disabled.</span></span>|  
|<span data-ttu-id="3b39f-130">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="3b39f-130">Focused</span></span>|<span data-ttu-id="3b39f-131">FocusStates</span><span class="sxs-lookup"><span data-stu-id="3b39f-131">FocusStates</span></span>|<span data-ttu-id="3b39f-132">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="3b39f-132">The control has focus.</span></span>|  
|<span data-ttu-id="3b39f-133">失去焦点</span><span class="sxs-lookup"><span data-stu-id="3b39f-133">Unfocused</span></span>|<span data-ttu-id="3b39f-134">FocusStates</span><span class="sxs-lookup"><span data-stu-id="3b39f-134">FocusStates</span></span>|<span data-ttu-id="3b39f-135">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="3b39f-135">The control does not have focus.</span></span>|  
|<span data-ttu-id="3b39f-136">有效</span><span class="sxs-lookup"><span data-stu-id="3b39f-136">Valid</span></span>|<span data-ttu-id="3b39f-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3b39f-137">ValidationStates</span></span>|<span data-ttu-id="3b39f-138">控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。</span><span class="sxs-lookup"><span data-stu-id="3b39f-138">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="3b39f-139">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="3b39f-139">InvalidFocused</span></span>|<span data-ttu-id="3b39f-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3b39f-140">ValidationStates</span></span>|<span data-ttu-id="3b39f-141"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。</span><span class="sxs-lookup"><span data-stu-id="3b39f-141">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="3b39f-142">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="3b39f-142">InvalidUnfocused</span></span>|<span data-ttu-id="3b39f-143">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3b39f-143">ValidationStates</span></span>|<span data-ttu-id="3b39f-144"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="3b39f-144">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="slider-controltemplate-example"></a><span data-ttu-id="3b39f-145">滑块 System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="3b39f-145">Slider ControlTemplate Example</span></span>  
 <span data-ttu-id="3b39f-146">下面的示例演示如何为 <xref:System.Windows.Controls.Slider> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。</span><span class="sxs-lookup"><span data-stu-id="3b39f-146">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Slider](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#slider)]  
  
 <span data-ttu-id="3b39f-147">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="3b39f-147">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="3b39f-148">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="3b39f-148">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b39f-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b39f-149">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="3b39f-150">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="3b39f-150">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="3b39f-151">控件自定义</span><span class="sxs-lookup"><span data-stu-id="3b39f-151">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="3b39f-152">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="3b39f-152">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="3b39f-153">为控件创建模板</span><span class="sxs-lookup"><span data-stu-id="3b39f-153">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
