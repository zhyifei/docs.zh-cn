---
title: RadioButton 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], RadioButton
- RadioButton [WPF], styles and templates
- ControlTemplate [WPF], RadioButton
- states [WPF], RadioButton
- templates [WPF], RadioButton
- parts [WPF], RadioButton
ms.assetid: 9acf93f7-dd2f-4010-8ce0-1edd81c52ae2
ms.openlocfilehash: 2d732dc6620cd06c99bdbaedfa5be474477d4917
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283438"
---
# <a name="radiobutton-styles-and-templates"></a><span data-ttu-id="8d04b-102">RadioButton 样式和模板</span><span class="sxs-lookup"><span data-stu-id="8d04b-102">RadioButton Styles and Templates</span></span>
<span data-ttu-id="8d04b-103">本主题介绍 <xref:System.Windows.Controls.RadioButton> 控件的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="8d04b-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.RadioButton> control.</span></span> <span data-ttu-id="8d04b-104">您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。</span><span class="sxs-lookup"><span data-stu-id="8d04b-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="8d04b-105">有关详细信息，请参阅为[控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)。</span><span class="sxs-lookup"><span data-stu-id="8d04b-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="radiobutton-parts"></a><span data-ttu-id="8d04b-106">单选按钮部件</span><span class="sxs-lookup"><span data-stu-id="8d04b-106">RadioButton Parts</span></span>  
 <span data-ttu-id="8d04b-107"><xref:System.Windows.Controls.RadioButton> 控件没有任何命名部分。</span><span class="sxs-lookup"><span data-stu-id="8d04b-107">The <xref:System.Windows.Controls.RadioButton> control does not have any named parts.</span></span>  
  
## <a name="radiobutton-states"></a><span data-ttu-id="8d04b-108">单选按钮状态</span><span class="sxs-lookup"><span data-stu-id="8d04b-108">RadioButton States</span></span>  
 <span data-ttu-id="8d04b-109">下表列出了 <xref:System.Windows.Controls.RadioButton> 控件的可视状态。</span><span class="sxs-lookup"><span data-stu-id="8d04b-109">The following table lists the visual states for the <xref:System.Windows.Controls.RadioButton> control.</span></span>  
  
|<span data-ttu-id="8d04b-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="8d04b-110">VisualState Name</span></span>|<span data-ttu-id="8d04b-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="8d04b-111">VisualStateGroup Name</span></span>|<span data-ttu-id="8d04b-112">说明</span><span class="sxs-lookup"><span data-stu-id="8d04b-112">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="8d04b-113">正常</span><span class="sxs-lookup"><span data-stu-id="8d04b-113">Normal</span></span>|<span data-ttu-id="8d04b-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="8d04b-114">CommonStates</span></span>|<span data-ttu-id="8d04b-115">默认状态。</span><span class="sxs-lookup"><span data-stu-id="8d04b-115">The default state.</span></span>|  
|<span data-ttu-id="8d04b-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="8d04b-116">MouseOver</span></span>|<span data-ttu-id="8d04b-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="8d04b-117">CommonStates</span></span>|<span data-ttu-id="8d04b-118">鼠标指针悬停在控件上。</span><span class="sxs-lookup"><span data-stu-id="8d04b-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="8d04b-119">已按下</span><span class="sxs-lookup"><span data-stu-id="8d04b-119">Pressed</span></span>|<span data-ttu-id="8d04b-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="8d04b-120">CommonStates</span></span>|<span data-ttu-id="8d04b-121">已按下控件。</span><span class="sxs-lookup"><span data-stu-id="8d04b-121">The control is pressed.</span></span>|  
|<span data-ttu-id="8d04b-122">已禁用</span><span class="sxs-lookup"><span data-stu-id="8d04b-122">Disabled</span></span>|<span data-ttu-id="8d04b-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="8d04b-123">CommonStates</span></span>|<span data-ttu-id="8d04b-124">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="8d04b-124">The control is disabled.</span></span>|  
|<span data-ttu-id="8d04b-125">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="8d04b-125">Focused</span></span>|<span data-ttu-id="8d04b-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="8d04b-126">FocusStates</span></span>|<span data-ttu-id="8d04b-127">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="8d04b-127">The control has focus.</span></span>|  
|<span data-ttu-id="8d04b-128">失去焦点</span><span class="sxs-lookup"><span data-stu-id="8d04b-128">Unfocused</span></span>|<span data-ttu-id="8d04b-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="8d04b-129">FocusStates</span></span>|<span data-ttu-id="8d04b-130">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="8d04b-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="8d04b-131">已选中</span><span class="sxs-lookup"><span data-stu-id="8d04b-131">Checked</span></span>|<span data-ttu-id="8d04b-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="8d04b-132">CheckStates</span></span>|<span data-ttu-id="8d04b-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 为 `true`。</span><span class="sxs-lookup"><span data-stu-id="8d04b-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|  
|<span data-ttu-id="8d04b-134">无</span><span class="sxs-lookup"><span data-stu-id="8d04b-134">Unchecked</span></span>|<span data-ttu-id="8d04b-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="8d04b-135">CheckStates</span></span>|<span data-ttu-id="8d04b-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 为 `false`。</span><span class="sxs-lookup"><span data-stu-id="8d04b-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|  
|<span data-ttu-id="8d04b-137">尚</span><span class="sxs-lookup"><span data-stu-id="8d04b-137">Indeterminate</span></span>|<span data-ttu-id="8d04b-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="8d04b-138">CheckStates</span></span>|<span data-ttu-id="8d04b-139">`true`<xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A>，<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> `null`。</span><span class="sxs-lookup"><span data-stu-id="8d04b-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="8d04b-140">有效</span><span class="sxs-lookup"><span data-stu-id="8d04b-140">Valid</span></span>|<span data-ttu-id="8d04b-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8d04b-141">ValidationStates</span></span>|<span data-ttu-id="8d04b-142">控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。</span><span class="sxs-lookup"><span data-stu-id="8d04b-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="8d04b-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="8d04b-143">InvalidFocused</span></span>|<span data-ttu-id="8d04b-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8d04b-144">ValidationStates</span></span>|<span data-ttu-id="8d04b-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。</span><span class="sxs-lookup"><span data-stu-id="8d04b-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="8d04b-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="8d04b-146">InvalidUnfocused</span></span>|<span data-ttu-id="8d04b-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8d04b-147">ValidationStates</span></span>|<span data-ttu-id="8d04b-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="8d04b-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="radiobutton-controltemplate-example"></a><span data-ttu-id="8d04b-149">单选按钮 System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="8d04b-149">RadioButton ControlTemplate Example</span></span>  
 <span data-ttu-id="8d04b-150">下面的示例演示如何为 <xref:System.Windows.Controls.RadioButton> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。</span><span class="sxs-lookup"><span data-stu-id="8d04b-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.RadioButton> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#RadioButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/radiobutton.xaml#radiobutton)]  
  
 <span data-ttu-id="8d04b-151">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="8d04b-151">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="8d04b-152">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="8d04b-152">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d04b-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d04b-153">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="8d04b-154">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="8d04b-154">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="8d04b-155">控件自定义</span><span class="sxs-lookup"><span data-stu-id="8d04b-155">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="8d04b-156">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="8d04b-156">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="8d04b-157">为控件创建模板</span><span class="sxs-lookup"><span data-stu-id="8d04b-157">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
