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
ms.openlocfilehash: e055dcbd557f9b90eb2fe99ad15a05b6f229fd28
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805921"
---
# <a name="togglebutton-styles-and-templates"></a><span data-ttu-id="e2ce1-102">ToggleButton 样式和模板</span><span class="sxs-lookup"><span data-stu-id="e2ce1-102">ToggleButton Styles and Templates</span></span>

<span data-ttu-id="e2ce1-103">本主题介绍控件的<xref:System.Windows.Controls.Primitives.ToggleButton>样式和模板。</span><span class="sxs-lookup"><span data-stu-id="e2ce1-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span> <span data-ttu-id="e2ce1-104">您可以修改默认值<xref:System.Windows.Controls.ControlTemplate>，为控件提供唯一的外观。</span><span class="sxs-lookup"><span data-stu-id="e2ce1-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="e2ce1-105">有关详细信息，请参阅为[控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)。</span><span class="sxs-lookup"><span data-stu-id="e2ce1-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>

## <a name="togglebutton-parts"></a><span data-ttu-id="e2ce1-106">切换按钮零件</span><span class="sxs-lookup"><span data-stu-id="e2ce1-106">ToggleButton Parts</span></span>

<span data-ttu-id="e2ce1-107">该<xref:System.Windows.Controls.Primitives.ToggleButton>控件没有任何命名部件。</span><span class="sxs-lookup"><span data-stu-id="e2ce1-107">The <xref:System.Windows.Controls.Primitives.ToggleButton> control does not have any named parts.</span></span>

## <a name="togglebutton-states"></a><span data-ttu-id="e2ce1-108">切换按钮状态</span><span class="sxs-lookup"><span data-stu-id="e2ce1-108">ToggleButton States</span></span>

<span data-ttu-id="e2ce1-109">下表列出了控件的<xref:System.Windows.Controls.Primitives.ToggleButton>可视状态。</span><span class="sxs-lookup"><span data-stu-id="e2ce1-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

|<span data-ttu-id="e2ce1-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="e2ce1-110">VisualState Name</span></span>|<span data-ttu-id="e2ce1-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="e2ce1-111">VisualStateGroup Name</span></span>|<span data-ttu-id="e2ce1-112">说明</span><span class="sxs-lookup"><span data-stu-id="e2ce1-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="e2ce1-113">一般</span><span class="sxs-lookup"><span data-stu-id="e2ce1-113">Normal</span></span>|<span data-ttu-id="e2ce1-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="e2ce1-114">CommonStates</span></span>|<span data-ttu-id="e2ce1-115">默认状态。</span><span class="sxs-lookup"><span data-stu-id="e2ce1-115">The default state.</span></span>|
|<span data-ttu-id="e2ce1-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="e2ce1-116">MouseOver</span></span>|<span data-ttu-id="e2ce1-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="e2ce1-117">CommonStates</span></span>|<span data-ttu-id="e2ce1-118">鼠标指针悬停在控件上方。</span><span class="sxs-lookup"><span data-stu-id="e2ce1-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="e2ce1-119">已按下</span><span class="sxs-lookup"><span data-stu-id="e2ce1-119">Pressed</span></span>|<span data-ttu-id="e2ce1-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="e2ce1-120">CommonStates</span></span>|<span data-ttu-id="e2ce1-121">已按下控件。</span><span class="sxs-lookup"><span data-stu-id="e2ce1-121">The control is pressed.</span></span>|
|<span data-ttu-id="e2ce1-122">已禁用</span><span class="sxs-lookup"><span data-stu-id="e2ce1-122">Disabled</span></span>|<span data-ttu-id="e2ce1-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="e2ce1-123">CommonStates</span></span>|<span data-ttu-id="e2ce1-124">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="e2ce1-124">The control is disabled.</span></span>|
|<span data-ttu-id="e2ce1-125">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="e2ce1-125">Focused</span></span>|<span data-ttu-id="e2ce1-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="e2ce1-126">FocusStates</span></span>|<span data-ttu-id="e2ce1-127">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="e2ce1-127">The control has focus.</span></span>|
|<span data-ttu-id="e2ce1-128">失去焦点</span><span class="sxs-lookup"><span data-stu-id="e2ce1-128">Unfocused</span></span>|<span data-ttu-id="e2ce1-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="e2ce1-129">FocusStates</span></span>|<span data-ttu-id="e2ce1-130">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="e2ce1-130">The control does not have focus.</span></span>|
|<span data-ttu-id="e2ce1-131">已选中</span><span class="sxs-lookup"><span data-stu-id="e2ce1-131">Checked</span></span>|<span data-ttu-id="e2ce1-132">检查状态</span><span class="sxs-lookup"><span data-stu-id="e2ce1-132">CheckStates</span></span>|<span data-ttu-id="e2ce1-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 为 `true`。</span><span class="sxs-lookup"><span data-stu-id="e2ce1-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|
|<span data-ttu-id="e2ce1-134">未选中</span><span class="sxs-lookup"><span data-stu-id="e2ce1-134">Unchecked</span></span>|<span data-ttu-id="e2ce1-135">检查状态</span><span class="sxs-lookup"><span data-stu-id="e2ce1-135">CheckStates</span></span>|<span data-ttu-id="e2ce1-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 为 `false`。</span><span class="sxs-lookup"><span data-stu-id="e2ce1-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|
|<span data-ttu-id="e2ce1-137">定</span><span class="sxs-lookup"><span data-stu-id="e2ce1-137">Indeterminate</span></span>|<span data-ttu-id="e2ce1-138">检查状态</span><span class="sxs-lookup"><span data-stu-id="e2ce1-138">CheckStates</span></span>|<span data-ttu-id="e2ce1-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> 为 `true` 且 <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 为 `null`。</span><span class="sxs-lookup"><span data-stu-id="e2ce1-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|
|<span data-ttu-id="e2ce1-140">有效</span><span class="sxs-lookup"><span data-stu-id="e2ce1-140">Valid</span></span>|<span data-ttu-id="e2ce1-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e2ce1-141">ValidationStates</span></span>|<span data-ttu-id="e2ce1-142">控件使用 类<xref:System.Windows.Controls.Validation>，<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性为`false`。</span><span class="sxs-lookup"><span data-stu-id="e2ce1-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="e2ce1-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="e2ce1-143">InvalidFocused</span></span>|<span data-ttu-id="e2ce1-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e2ce1-144">ValidationStates</span></span>|<span data-ttu-id="e2ce1-145">附加<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>属性是`true`，控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="e2ce1-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|
|<span data-ttu-id="e2ce1-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="e2ce1-146">InvalidUnfocused</span></span>|<span data-ttu-id="e2ce1-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e2ce1-147">ValidationStates</span></span>|<span data-ttu-id="e2ce1-148">附加<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>属性为`true`，控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="e2ce1-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|

> [!NOTE]
> <span data-ttu-id="e2ce1-149">如果控件模板中不存在不确定的可视状态，则"未选中的可视状态"将用作默认可视状态。</span><span class="sxs-lookup"><span data-stu-id="e2ce1-149">If the Indeterminate visual state does not exist in your control template, then the Unchecked visual state will be used as default visual state.</span></span>

## <a name="togglebutton-controltemplate-example"></a><span data-ttu-id="e2ce1-150">切换按钮控制模板示例</span><span class="sxs-lookup"><span data-stu-id="e2ce1-150">ToggleButton ControlTemplate Example</span></span>

<span data-ttu-id="e2ce1-151">下面的示例演示如何为<xref:System.Windows.Controls.ControlTemplate><xref:System.Windows.Controls.Primitives.ToggleButton>控件定义 。</span><span class="sxs-lookup"><span data-stu-id="e2ce1-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

<span data-ttu-id="e2ce1-152">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="e2ce1-152">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="e2ce1-153">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="e2ce1-153">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="e2ce1-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e2ce1-154">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="e2ce1-155">Control 样式和模板</span><span class="sxs-lookup"><span data-stu-id="e2ce1-155">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="e2ce1-156">控件自定义</span><span class="sxs-lookup"><span data-stu-id="e2ce1-156">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="e2ce1-157">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="e2ce1-157">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="e2ce1-158">为控件创建模板</span><span class="sxs-lookup"><span data-stu-id="e2ce1-158">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
