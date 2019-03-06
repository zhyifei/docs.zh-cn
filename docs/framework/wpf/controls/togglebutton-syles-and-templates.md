---
title: ToggleButton 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
ms.openlocfilehash: fd8d1986bf5c9b5f42a4c8146a89682f4a96b75e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376177"
---
# <a name="togglebutton-syles-and-templates"></a><span data-ttu-id="18d63-102">ToggleButton 样式和模板</span><span class="sxs-lookup"><span data-stu-id="18d63-102">ToggleButton Syles and Templates</span></span>
<span data-ttu-id="18d63-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.Primitives.ToggleButton>控件。</span><span class="sxs-lookup"><span data-stu-id="18d63-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span> <span data-ttu-id="18d63-104">可以修改默认<xref:System.Windows.Controls.ControlTemplate>为控件提供唯一外观。</span><span class="sxs-lookup"><span data-stu-id="18d63-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="18d63-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="18d63-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="togglebutton-parts"></a><span data-ttu-id="18d63-106">切换按钮部件</span><span class="sxs-lookup"><span data-stu-id="18d63-106">ToggleButton Parts</span></span>  
 <span data-ttu-id="18d63-107"><xref:System.Windows.Controls.Primitives.ToggleButton>控件没有任何命名的部件。</span><span class="sxs-lookup"><span data-stu-id="18d63-107">The <xref:System.Windows.Controls.Primitives.ToggleButton> control does not have any named parts.</span></span>  
  
## <a name="togglebutton-states"></a><span data-ttu-id="18d63-108">切换按钮状态</span><span class="sxs-lookup"><span data-stu-id="18d63-108">ToggleButton States</span></span>  
 <span data-ttu-id="18d63-109">下表列出了的可视状态<xref:System.Windows.Controls.Primitives.ToggleButton>控件。</span><span class="sxs-lookup"><span data-stu-id="18d63-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>  
  
|<span data-ttu-id="18d63-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="18d63-110">VisualState Name</span></span>|<span data-ttu-id="18d63-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="18d63-111">VisualStateGroup Name</span></span>|<span data-ttu-id="18d63-112">描述</span><span class="sxs-lookup"><span data-stu-id="18d63-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="18d63-113">普通</span><span class="sxs-lookup"><span data-stu-id="18d63-113">Normal</span></span>|<span data-ttu-id="18d63-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="18d63-114">CommonStates</span></span>|<span data-ttu-id="18d63-115">默认状态。</span><span class="sxs-lookup"><span data-stu-id="18d63-115">The default state.</span></span>|  
|<span data-ttu-id="18d63-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="18d63-116">MouseOver</span></span>|<span data-ttu-id="18d63-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="18d63-117">CommonStates</span></span>|<span data-ttu-id="18d63-118">鼠标指针悬停在控件上方。</span><span class="sxs-lookup"><span data-stu-id="18d63-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="18d63-119">已按下</span><span class="sxs-lookup"><span data-stu-id="18d63-119">Pressed</span></span>|<span data-ttu-id="18d63-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="18d63-120">CommonStates</span></span>|<span data-ttu-id="18d63-121">已按下控件。</span><span class="sxs-lookup"><span data-stu-id="18d63-121">The control is pressed.</span></span>|  
|<span data-ttu-id="18d63-122">已禁用</span><span class="sxs-lookup"><span data-stu-id="18d63-122">Disabled</span></span>|<span data-ttu-id="18d63-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="18d63-123">CommonStates</span></span>|<span data-ttu-id="18d63-124">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="18d63-124">The control is disabled.</span></span>|  
|<span data-ttu-id="18d63-125">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="18d63-125">Focused</span></span>|<span data-ttu-id="18d63-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="18d63-126">FocusStates</span></span>|<span data-ttu-id="18d63-127">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="18d63-127">The control has focus.</span></span>|  
|<span data-ttu-id="18d63-128">失去焦点</span><span class="sxs-lookup"><span data-stu-id="18d63-128">Unfocused</span></span>|<span data-ttu-id="18d63-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="18d63-129">FocusStates</span></span>|<span data-ttu-id="18d63-130">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="18d63-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="18d63-131">已选中</span><span class="sxs-lookup"><span data-stu-id="18d63-131">Checked</span></span>|<span data-ttu-id="18d63-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="18d63-132">CheckStates</span></span>|<span data-ttu-id="18d63-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 为 `true`。</span><span class="sxs-lookup"><span data-stu-id="18d63-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|  
|<span data-ttu-id="18d63-134">未选中状态</span><span class="sxs-lookup"><span data-stu-id="18d63-134">Unchecked</span></span>|<span data-ttu-id="18d63-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="18d63-135">CheckStates</span></span>|<span data-ttu-id="18d63-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 为 `false`。</span><span class="sxs-lookup"><span data-stu-id="18d63-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|  
|<span data-ttu-id="18d63-137">不确定</span><span class="sxs-lookup"><span data-stu-id="18d63-137">Indeterminate</span></span>|<span data-ttu-id="18d63-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="18d63-138">CheckStates</span></span>|<span data-ttu-id="18d63-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> 是`true`，并<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>是`null`。</span><span class="sxs-lookup"><span data-stu-id="18d63-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="18d63-140">有效</span><span class="sxs-lookup"><span data-stu-id="18d63-140">Valid</span></span>|<span data-ttu-id="18d63-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="18d63-141">ValidationStates</span></span>|<span data-ttu-id="18d63-142">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`false`。</span><span class="sxs-lookup"><span data-stu-id="18d63-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="18d63-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="18d63-143">InvalidFocused</span></span>|<span data-ttu-id="18d63-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="18d63-144">ValidationStates</span></span>|<span data-ttu-id="18d63-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="18d63-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="18d63-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="18d63-146">InvalidUnfocused</span></span>|<span data-ttu-id="18d63-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="18d63-147">ValidationStates</span></span>|<span data-ttu-id="18d63-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="18d63-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="18d63-149">如果您的控件模板中不存在的不确定的可视状态，未选中状态的可视状态将用作默认可视状态。</span><span class="sxs-lookup"><span data-stu-id="18d63-149">If the Indeterminate visual state does not exist in your control template, then the Unchecked visual state will be used as default visual state.</span></span>  
  
## <a name="togglebutton-controltemplate-example"></a><span data-ttu-id="18d63-150">切换按钮 ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="18d63-150">ToggleButton ControlTemplate Example</span></span>  
 <span data-ttu-id="18d63-151">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Primitives.ToggleButton>控件。</span><span class="sxs-lookup"><span data-stu-id="18d63-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]  
  
 <span data-ttu-id="18d63-152">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="18d63-152">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="18d63-153">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="18d63-153">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18d63-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="18d63-154">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="18d63-155">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="18d63-155">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="18d63-156">控件自定义</span><span class="sxs-lookup"><span data-stu-id="18d63-156">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="18d63-157">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="18d63-157">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="18d63-158">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="18d63-158">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
