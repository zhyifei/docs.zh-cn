---
title: RepeatButton 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatButton [WPF], styles and templates
- styles [WPF], RepeatButton
- templates [WPF], RepeatButton
- parts [WPF], RepeatButton
- ControlTemplate [WPF], RepeatButton
- states [WPF], RepeatButton
ms.assetid: fd340743-f44f-4990-9077-085301469670
ms.openlocfilehash: 9c6a8ad0a954d244fb693e25965ab52dda114068
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459846"
---
# <a name="repeatbutton-styles-and-templates"></a><span data-ttu-id="c070b-102">RepeatButton 样式和模板</span><span class="sxs-lookup"><span data-stu-id="c070b-102">RepeatButton Styles and Templates</span></span>

<span data-ttu-id="c070b-103">本主题介绍 <xref:System.Windows.Controls.Primitives.RepeatButton> 控件的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="c070b-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span> <span data-ttu-id="c070b-104">您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。</span><span class="sxs-lookup"><span data-stu-id="c070b-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="c070b-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="c070b-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="repeatbutton-parts"></a><span data-ttu-id="c070b-106">RepeatButton 部件</span><span class="sxs-lookup"><span data-stu-id="c070b-106">RepeatButton Parts</span></span>

<span data-ttu-id="c070b-107"><xref:System.Windows.Controls.Primitives.RepeatButton> 控件没有任何命名部分。</span><span class="sxs-lookup"><span data-stu-id="c070b-107">The <xref:System.Windows.Controls.Primitives.RepeatButton> control does not have any named parts.</span></span>

## <a name="repeatbutton-states"></a><span data-ttu-id="c070b-108">RepeatButton 状态</span><span class="sxs-lookup"><span data-stu-id="c070b-108">RepeatButton States</span></span>

<span data-ttu-id="c070b-109">下表列出了 <xref:System.Windows.Controls.Primitives.RepeatButton> 控件的可视状态。</span><span class="sxs-lookup"><span data-stu-id="c070b-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

|<span data-ttu-id="c070b-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="c070b-110">VisualState Name</span></span>|<span data-ttu-id="c070b-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="c070b-111">VisualStateGroup Name</span></span>|<span data-ttu-id="c070b-112">描述</span><span class="sxs-lookup"><span data-stu-id="c070b-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="c070b-113">普通</span><span class="sxs-lookup"><span data-stu-id="c070b-113">Normal</span></span>|<span data-ttu-id="c070b-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c070b-114">CommonStates</span></span>|<span data-ttu-id="c070b-115">默认状态。</span><span class="sxs-lookup"><span data-stu-id="c070b-115">The default state.</span></span>|
|<span data-ttu-id="c070b-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="c070b-116">MouseOver</span></span>|<span data-ttu-id="c070b-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c070b-117">CommonStates</span></span>|<span data-ttu-id="c070b-118">鼠标指针悬停在控件上。</span><span class="sxs-lookup"><span data-stu-id="c070b-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="c070b-119">已按下</span><span class="sxs-lookup"><span data-stu-id="c070b-119">Pressed</span></span>|<span data-ttu-id="c070b-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c070b-120">CommonStates</span></span>|<span data-ttu-id="c070b-121">已按下控件。</span><span class="sxs-lookup"><span data-stu-id="c070b-121">The control is pressed.</span></span>|
|<span data-ttu-id="c070b-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="c070b-122">Disabled</span></span>|<span data-ttu-id="c070b-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c070b-123">CommonStates</span></span>|<span data-ttu-id="c070b-124">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="c070b-124">The control is disabled.</span></span>|
|<span data-ttu-id="c070b-125">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="c070b-125">Focused</span></span>|<span data-ttu-id="c070b-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="c070b-126">FocusStates</span></span>|<span data-ttu-id="c070b-127">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="c070b-127">The control has focus.</span></span>|
|<span data-ttu-id="c070b-128">失去焦点</span><span class="sxs-lookup"><span data-stu-id="c070b-128">Unfocused</span></span>|<span data-ttu-id="c070b-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="c070b-129">FocusStates</span></span>|<span data-ttu-id="c070b-130">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="c070b-130">The control does not have focus.</span></span>|
|<span data-ttu-id="c070b-131">有效</span><span class="sxs-lookup"><span data-stu-id="c070b-131">Valid</span></span>|<span data-ttu-id="c070b-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c070b-132">ValidationStates</span></span>|<span data-ttu-id="c070b-133">控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。</span><span class="sxs-lookup"><span data-stu-id="c070b-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="c070b-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="c070b-134">InvalidFocused</span></span>|<span data-ttu-id="c070b-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c070b-135">ValidationStates</span></span>|<span data-ttu-id="c070b-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。</span><span class="sxs-lookup"><span data-stu-id="c070b-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="c070b-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="c070b-137">InvalidUnfocused</span></span>|<span data-ttu-id="c070b-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c070b-138">ValidationStates</span></span>|<span data-ttu-id="c070b-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="c070b-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="repeatbutton-controltemplate-example"></a><span data-ttu-id="c070b-140">RepeatButton System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="c070b-140">RepeatButton ControlTemplate Example</span></span>

<span data-ttu-id="c070b-141">下面的示例演示如何为 <xref:System.Windows.Controls.Primitives.RepeatButton> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。</span><span class="sxs-lookup"><span data-stu-id="c070b-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#RepeatButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#repeatbutton)]

<span data-ttu-id="c070b-142">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="c070b-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="c070b-143">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="c070b-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="c070b-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="c070b-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="c070b-145">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="c070b-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="c070b-146">控件自定义</span><span class="sxs-lookup"><span data-stu-id="c070b-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="c070b-147">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="c070b-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="c070b-148">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="c070b-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
