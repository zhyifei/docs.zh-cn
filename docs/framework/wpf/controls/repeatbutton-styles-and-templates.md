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
ms.openlocfilehash: 86f212326bc707e4b07b8cab8d9a95d4f6ef8920
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053309"
---
# <a name="repeatbutton-styles-and-templates"></a><span data-ttu-id="fd9a3-102">RepeatButton 样式和模板</span><span class="sxs-lookup"><span data-stu-id="fd9a3-102">RepeatButton Styles and Templates</span></span>

<span data-ttu-id="fd9a3-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.Primitives.RepeatButton>控件。</span><span class="sxs-lookup"><span data-stu-id="fd9a3-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span> <span data-ttu-id="fd9a3-104">可以修改默认<xref:System.Windows.Controls.ControlTemplate>为控件提供唯一外观。</span><span class="sxs-lookup"><span data-stu-id="fd9a3-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="fd9a3-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="fd9a3-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="repeatbutton-parts"></a><span data-ttu-id="fd9a3-106">RepeatButton 部件</span><span class="sxs-lookup"><span data-stu-id="fd9a3-106">RepeatButton Parts</span></span>

<span data-ttu-id="fd9a3-107"><xref:System.Windows.Controls.Primitives.RepeatButton>控件没有任何命名的部件。</span><span class="sxs-lookup"><span data-stu-id="fd9a3-107">The <xref:System.Windows.Controls.Primitives.RepeatButton> control does not have any named parts.</span></span>

## <a name="repeatbutton-states"></a><span data-ttu-id="fd9a3-108">RepeatButton 状态</span><span class="sxs-lookup"><span data-stu-id="fd9a3-108">RepeatButton States</span></span>

<span data-ttu-id="fd9a3-109">下表列出了的可视状态<xref:System.Windows.Controls.Primitives.RepeatButton>控件。</span><span class="sxs-lookup"><span data-stu-id="fd9a3-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

|<span data-ttu-id="fd9a3-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="fd9a3-110">VisualState Name</span></span>|<span data-ttu-id="fd9a3-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="fd9a3-111">VisualStateGroup Name</span></span>|<span data-ttu-id="fd9a3-112">描述</span><span class="sxs-lookup"><span data-stu-id="fd9a3-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="fd9a3-113">普通</span><span class="sxs-lookup"><span data-stu-id="fd9a3-113">Normal</span></span>|<span data-ttu-id="fd9a3-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fd9a3-114">CommonStates</span></span>|<span data-ttu-id="fd9a3-115">默认状态。</span><span class="sxs-lookup"><span data-stu-id="fd9a3-115">The default state.</span></span>|
|<span data-ttu-id="fd9a3-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="fd9a3-116">MouseOver</span></span>|<span data-ttu-id="fd9a3-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fd9a3-117">CommonStates</span></span>|<span data-ttu-id="fd9a3-118">鼠标指针悬停在控件上方。</span><span class="sxs-lookup"><span data-stu-id="fd9a3-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="fd9a3-119">已按下</span><span class="sxs-lookup"><span data-stu-id="fd9a3-119">Pressed</span></span>|<span data-ttu-id="fd9a3-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fd9a3-120">CommonStates</span></span>|<span data-ttu-id="fd9a3-121">已按下控件。</span><span class="sxs-lookup"><span data-stu-id="fd9a3-121">The control is pressed.</span></span>|
|<span data-ttu-id="fd9a3-122">已禁用</span><span class="sxs-lookup"><span data-stu-id="fd9a3-122">Disabled</span></span>|<span data-ttu-id="fd9a3-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fd9a3-123">CommonStates</span></span>|<span data-ttu-id="fd9a3-124">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="fd9a3-124">The control is disabled.</span></span>|
|<span data-ttu-id="fd9a3-125">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="fd9a3-125">Focused</span></span>|<span data-ttu-id="fd9a3-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="fd9a3-126">FocusStates</span></span>|<span data-ttu-id="fd9a3-127">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="fd9a3-127">The control has focus.</span></span>|
|<span data-ttu-id="fd9a3-128">失去焦点</span><span class="sxs-lookup"><span data-stu-id="fd9a3-128">Unfocused</span></span>|<span data-ttu-id="fd9a3-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="fd9a3-129">FocusStates</span></span>|<span data-ttu-id="fd9a3-130">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="fd9a3-130">The control does not have focus.</span></span>|
|<span data-ttu-id="fd9a3-131">有效</span><span class="sxs-lookup"><span data-stu-id="fd9a3-131">Valid</span></span>|<span data-ttu-id="fd9a3-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fd9a3-132">ValidationStates</span></span>|<span data-ttu-id="fd9a3-133">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`false`。</span><span class="sxs-lookup"><span data-stu-id="fd9a3-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="fd9a3-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="fd9a3-134">InvalidFocused</span></span>|<span data-ttu-id="fd9a3-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fd9a3-135">ValidationStates</span></span>|<span data-ttu-id="fd9a3-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="fd9a3-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="fd9a3-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="fd9a3-137">InvalidUnfocused</span></span>|<span data-ttu-id="fd9a3-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fd9a3-138">ValidationStates</span></span>|<span data-ttu-id="fd9a3-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="fd9a3-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="repeatbutton-controltemplate-example"></a><span data-ttu-id="fd9a3-140">RepeatButton ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="fd9a3-140">RepeatButton ControlTemplate Example</span></span>

<span data-ttu-id="fd9a3-141">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Primitives.RepeatButton>控件。</span><span class="sxs-lookup"><span data-stu-id="fd9a3-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#RepeatButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#repeatbutton)]

<span data-ttu-id="fd9a3-142">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="fd9a3-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="fd9a3-143">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="fd9a3-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="fd9a3-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd9a3-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="fd9a3-145">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="fd9a3-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="fd9a3-146">控件自定义</span><span class="sxs-lookup"><span data-stu-id="fd9a3-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="fd9a3-147">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="fd9a3-147">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="fd9a3-148">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="fd9a3-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
