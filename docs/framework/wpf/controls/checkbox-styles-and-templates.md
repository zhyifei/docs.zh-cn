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
ms.openlocfilehash: b85e13b13c849e278a6535e09cd0dbaec396bf10
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460797"
---
# <a name="checkbox-styles-and-templates"></a><span data-ttu-id="2097d-102">CheckBox 样式和模板</span><span class="sxs-lookup"><span data-stu-id="2097d-102">CheckBox Styles and Templates</span></span>
<span data-ttu-id="2097d-103">本主题介绍 <xref:System.Windows.Controls.CheckBox> 控件的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="2097d-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.CheckBox> control.</span></span> <span data-ttu-id="2097d-104">您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。</span><span class="sxs-lookup"><span data-stu-id="2097d-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="2097d-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="2097d-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="checkbox-parts"></a><span data-ttu-id="2097d-106">CheckBox 部分</span><span class="sxs-lookup"><span data-stu-id="2097d-106">CheckBox Parts</span></span>  
 <span data-ttu-id="2097d-107"><xref:System.Windows.Controls.CheckBox> 控件没有任何命名部分。</span><span class="sxs-lookup"><span data-stu-id="2097d-107">The <xref:System.Windows.Controls.CheckBox> control does not have any named parts.</span></span>  
  
## <a name="checkbox-states"></a><span data-ttu-id="2097d-108">复选框状态</span><span class="sxs-lookup"><span data-stu-id="2097d-108">CheckBox States</span></span>  
 <span data-ttu-id="2097d-109">下表列出了 <xref:System.Windows.Controls.CheckBox> 控件的可视状态。</span><span class="sxs-lookup"><span data-stu-id="2097d-109">The following table lists the visual states for the <xref:System.Windows.Controls.CheckBox> control.</span></span>  
  
|<span data-ttu-id="2097d-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="2097d-110">VisualState Name</span></span>|<span data-ttu-id="2097d-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="2097d-111">VisualStateGroup Name</span></span>|<span data-ttu-id="2097d-112">描述</span><span class="sxs-lookup"><span data-stu-id="2097d-112">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="2097d-113">普通</span><span class="sxs-lookup"><span data-stu-id="2097d-113">Normal</span></span>|<span data-ttu-id="2097d-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="2097d-114">CommonStates</span></span>|<span data-ttu-id="2097d-115">默认状态。</span><span class="sxs-lookup"><span data-stu-id="2097d-115">The default state.</span></span>|  
|<span data-ttu-id="2097d-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="2097d-116">MouseOver</span></span>|<span data-ttu-id="2097d-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="2097d-117">CommonStates</span></span>|<span data-ttu-id="2097d-118">鼠标指针悬停在控件上。</span><span class="sxs-lookup"><span data-stu-id="2097d-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="2097d-119">已按下</span><span class="sxs-lookup"><span data-stu-id="2097d-119">Pressed</span></span>|<span data-ttu-id="2097d-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="2097d-120">CommonStates</span></span>|<span data-ttu-id="2097d-121">已按下控件。</span><span class="sxs-lookup"><span data-stu-id="2097d-121">The control is pressed.</span></span>|  
|<span data-ttu-id="2097d-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="2097d-122">Disabled</span></span>|<span data-ttu-id="2097d-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="2097d-123">CommonStates</span></span>|<span data-ttu-id="2097d-124">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="2097d-124">The control is disabled.</span></span>|  
|<span data-ttu-id="2097d-125">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="2097d-125">Focused</span></span>|<span data-ttu-id="2097d-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="2097d-126">FocusStates</span></span>|<span data-ttu-id="2097d-127">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="2097d-127">The control has focus.</span></span>|  
|<span data-ttu-id="2097d-128">失去焦点</span><span class="sxs-lookup"><span data-stu-id="2097d-128">Unfocused</span></span>|<span data-ttu-id="2097d-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="2097d-129">FocusStates</span></span>|<span data-ttu-id="2097d-130">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="2097d-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="2097d-131">已选中</span><span class="sxs-lookup"><span data-stu-id="2097d-131">Checked</span></span>|<span data-ttu-id="2097d-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="2097d-132">CheckStates</span></span>|<span data-ttu-id="2097d-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 为 `true`。</span><span class="sxs-lookup"><span data-stu-id="2097d-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|  
|<span data-ttu-id="2097d-134">无</span><span class="sxs-lookup"><span data-stu-id="2097d-134">Unchecked</span></span>|<span data-ttu-id="2097d-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="2097d-135">CheckStates</span></span>|<span data-ttu-id="2097d-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 为 `false`。</span><span class="sxs-lookup"><span data-stu-id="2097d-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|  
|<span data-ttu-id="2097d-137">尚</span><span class="sxs-lookup"><span data-stu-id="2097d-137">Indeterminate</span></span>|<span data-ttu-id="2097d-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="2097d-138">CheckStates</span></span>|<span data-ttu-id="2097d-139">`true`<xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A>，<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> `null`。</span><span class="sxs-lookup"><span data-stu-id="2097d-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="2097d-140">有效</span><span class="sxs-lookup"><span data-stu-id="2097d-140">Valid</span></span>|<span data-ttu-id="2097d-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2097d-141">ValidationStates</span></span>|<span data-ttu-id="2097d-142">控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。</span><span class="sxs-lookup"><span data-stu-id="2097d-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="2097d-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="2097d-143">InvalidUnfocused</span></span>|<span data-ttu-id="2097d-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2097d-144">ValidationStates</span></span>|<span data-ttu-id="2097d-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。</span><span class="sxs-lookup"><span data-stu-id="2097d-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="2097d-146">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="2097d-146">InvalidFocused</span></span>|<span data-ttu-id="2097d-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2097d-147">ValidationStates</span></span>|<span data-ttu-id="2097d-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="2097d-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="checkbox-controltemplate-example"></a><span data-ttu-id="2097d-149">CheckBox System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="2097d-149">CheckBox ControlTemplate Example</span></span>  
 <span data-ttu-id="2097d-150">下面的示例演示如何为 <xref:System.Windows.Controls.CheckBox> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。</span><span class="sxs-lookup"><span data-stu-id="2097d-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.CheckBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#CheckBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/checkbox.xaml#checkbox)]  
  
 <span data-ttu-id="2097d-151">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="2097d-151">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="2097d-152">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="2097d-152">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2097d-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="2097d-153">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="2097d-154">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="2097d-154">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="2097d-155">控件自定义</span><span class="sxs-lookup"><span data-stu-id="2097d-155">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="2097d-156">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="2097d-156">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="2097d-157">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="2097d-157">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
