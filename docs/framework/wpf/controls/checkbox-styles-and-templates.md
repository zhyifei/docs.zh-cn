---
title: CheckBox 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], CheckBox
- templates [WPF], CheckBox
- parts [WPF], CheckBox
- ControlTemplate [WPF], CheckBox
- CheckBox [WPF], styles and templates
- styles [WPF], CheckBox
ms.assetid: bfdaec96-d101-4d3d-864d-c27e6b621d03
ms.openlocfilehash: b3f417a676b141a4a6dbccfe51bf5b7abe669198
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120050"
---
# <a name="checkbox-styles-and-templates"></a><span data-ttu-id="763f5-102">CheckBox 样式和模板</span><span class="sxs-lookup"><span data-stu-id="763f5-102">CheckBox Styles and Templates</span></span>
<span data-ttu-id="763f5-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.CheckBox>控件。</span><span class="sxs-lookup"><span data-stu-id="763f5-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.CheckBox> control.</span></span> <span data-ttu-id="763f5-104">可以修改默认<xref:System.Windows.Controls.ControlTemplate>为控件提供唯一外观。</span><span class="sxs-lookup"><span data-stu-id="763f5-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="763f5-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="763f5-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="checkbox-parts"></a><span data-ttu-id="763f5-106">复选框部分</span><span class="sxs-lookup"><span data-stu-id="763f5-106">CheckBox Parts</span></span>  
 <span data-ttu-id="763f5-107"><xref:System.Windows.Controls.CheckBox>控件没有任何命名的部件。</span><span class="sxs-lookup"><span data-stu-id="763f5-107">The <xref:System.Windows.Controls.CheckBox> control does not have any named parts.</span></span>  
  
## <a name="checkbox-states"></a><span data-ttu-id="763f5-108">复选框状态</span><span class="sxs-lookup"><span data-stu-id="763f5-108">CheckBox States</span></span>  
 <span data-ttu-id="763f5-109">下表列出了的可视状态<xref:System.Windows.Controls.CheckBox>控件。</span><span class="sxs-lookup"><span data-stu-id="763f5-109">The following table lists the visual states for the <xref:System.Windows.Controls.CheckBox> control.</span></span>  
  
|<span data-ttu-id="763f5-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="763f5-110">VisualState Name</span></span>|<span data-ttu-id="763f5-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="763f5-111">VisualStateGroup Name</span></span>|<span data-ttu-id="763f5-112">描述</span><span class="sxs-lookup"><span data-stu-id="763f5-112">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="763f5-113">普通</span><span class="sxs-lookup"><span data-stu-id="763f5-113">Normal</span></span>|<span data-ttu-id="763f5-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="763f5-114">CommonStates</span></span>|<span data-ttu-id="763f5-115">默认状态。</span><span class="sxs-lookup"><span data-stu-id="763f5-115">The default state.</span></span>|  
|<span data-ttu-id="763f5-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="763f5-116">MouseOver</span></span>|<span data-ttu-id="763f5-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="763f5-117">CommonStates</span></span>|<span data-ttu-id="763f5-118">鼠标指针悬停在控件上方。</span><span class="sxs-lookup"><span data-stu-id="763f5-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="763f5-119">已按下</span><span class="sxs-lookup"><span data-stu-id="763f5-119">Pressed</span></span>|<span data-ttu-id="763f5-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="763f5-120">CommonStates</span></span>|<span data-ttu-id="763f5-121">已按下控件。</span><span class="sxs-lookup"><span data-stu-id="763f5-121">The control is pressed.</span></span>|  
|<span data-ttu-id="763f5-122">已禁用</span><span class="sxs-lookup"><span data-stu-id="763f5-122">Disabled</span></span>|<span data-ttu-id="763f5-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="763f5-123">CommonStates</span></span>|<span data-ttu-id="763f5-124">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="763f5-124">The control is disabled.</span></span>|  
|<span data-ttu-id="763f5-125">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="763f5-125">Focused</span></span>|<span data-ttu-id="763f5-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="763f5-126">FocusStates</span></span>|<span data-ttu-id="763f5-127">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="763f5-127">The control has focus.</span></span>|  
|<span data-ttu-id="763f5-128">失去焦点</span><span class="sxs-lookup"><span data-stu-id="763f5-128">Unfocused</span></span>|<span data-ttu-id="763f5-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="763f5-129">FocusStates</span></span>|<span data-ttu-id="763f5-130">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="763f5-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="763f5-131">已选中</span><span class="sxs-lookup"><span data-stu-id="763f5-131">Checked</span></span>|<span data-ttu-id="763f5-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="763f5-132">CheckStates</span></span>|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> <span data-ttu-id="763f5-133">是`true`。</span><span class="sxs-lookup"><span data-stu-id="763f5-133">is `true`.</span></span>|  
|<span data-ttu-id="763f5-134">未选中状态</span><span class="sxs-lookup"><span data-stu-id="763f5-134">Unchecked</span></span>|<span data-ttu-id="763f5-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="763f5-135">CheckStates</span></span>|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> <span data-ttu-id="763f5-136">是`false`。</span><span class="sxs-lookup"><span data-stu-id="763f5-136">is `false`.</span></span>|  
|<span data-ttu-id="763f5-137">不确定</span><span class="sxs-lookup"><span data-stu-id="763f5-137">Indeterminate</span></span>|<span data-ttu-id="763f5-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="763f5-138">CheckStates</span></span>|<xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> <span data-ttu-id="763f5-139">是`true`，并<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>是`null`。</span><span class="sxs-lookup"><span data-stu-id="763f5-139">is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="763f5-140">有效</span><span class="sxs-lookup"><span data-stu-id="763f5-140">Valid</span></span>|<span data-ttu-id="763f5-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="763f5-141">ValidationStates</span></span>|<span data-ttu-id="763f5-142">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`false`。</span><span class="sxs-lookup"><span data-stu-id="763f5-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="763f5-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="763f5-143">InvalidUnfocused</span></span>|<span data-ttu-id="763f5-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="763f5-144">ValidationStates</span></span>|<span data-ttu-id="763f5-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="763f5-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="763f5-146">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="763f5-146">InvalidFocused</span></span>|<span data-ttu-id="763f5-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="763f5-147">ValidationStates</span></span>|<span data-ttu-id="763f5-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="763f5-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="checkbox-controltemplate-example"></a><span data-ttu-id="763f5-149">复选框 ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="763f5-149">CheckBox ControlTemplate Example</span></span>  
 <span data-ttu-id="763f5-150">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.CheckBox>控件。</span><span class="sxs-lookup"><span data-stu-id="763f5-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.CheckBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#CheckBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/checkbox.xaml#checkbox)]  
  
 <span data-ttu-id="763f5-151">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="763f5-151">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="763f5-152">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="763f5-152">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="763f5-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="763f5-153">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="763f5-154">Control 样式和模板</span><span class="sxs-lookup"><span data-stu-id="763f5-154">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="763f5-155">控件自定义</span><span class="sxs-lookup"><span data-stu-id="763f5-155">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="763f5-156">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="763f5-156">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="763f5-157">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="763f5-157">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
