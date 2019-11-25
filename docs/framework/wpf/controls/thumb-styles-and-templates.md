---
title: Thumb 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Thumb
- styles [WPF], Thumb
- templates [WPF], Thumb
- Thumb [WPF], styles and templates
- ControlTemplate [WPF], Thumb
- parts [WPF], Thumb
ms.assetid: 86a49235-62d9-414e-923e-53126e3f930a
ms.openlocfilehash: 0d0d88e3b527beacfa5f879027e696aa75b18147
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283685"
---
# <a name="thumb-styles-and-templates"></a><span data-ttu-id="54dbb-102">Thumb 样式和模板</span><span class="sxs-lookup"><span data-stu-id="54dbb-102">Thumb Styles and Templates</span></span>

<span data-ttu-id="54dbb-103">本主题介绍 <xref:System.Windows.Controls.Primitives.Thumb> 控件的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="54dbb-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="54dbb-104">您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。</span><span class="sxs-lookup"><span data-stu-id="54dbb-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="54dbb-105">有关详细信息，请参阅为[控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)。</span><span class="sxs-lookup"><span data-stu-id="54dbb-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>

## <a name="thumb-parts"></a><span data-ttu-id="54dbb-106">拇指部分</span><span class="sxs-lookup"><span data-stu-id="54dbb-106">Thumb Parts</span></span>

<span data-ttu-id="54dbb-107"><xref:System.Windows.Controls.Primitives.Thumb> 控件没有任何命名部分。</span><span class="sxs-lookup"><span data-stu-id="54dbb-107">The <xref:System.Windows.Controls.Primitives.Thumb> control does not have any named parts.</span></span>

## <a name="thumb-states"></a><span data-ttu-id="54dbb-108">缩略图状态</span><span class="sxs-lookup"><span data-stu-id="54dbb-108">Thumb States</span></span>

<span data-ttu-id="54dbb-109">下表列出了 <xref:System.Windows.Controls.Primitives.Thumb> 控件的可视状态。</span><span class="sxs-lookup"><span data-stu-id="54dbb-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>

|<span data-ttu-id="54dbb-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="54dbb-110">VisualState Name</span></span>|<span data-ttu-id="54dbb-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="54dbb-111">VisualStateGroup Name</span></span>|<span data-ttu-id="54dbb-112">描述</span><span class="sxs-lookup"><span data-stu-id="54dbb-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="54dbb-113">一般</span><span class="sxs-lookup"><span data-stu-id="54dbb-113">Normal</span></span>|<span data-ttu-id="54dbb-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="54dbb-114">CommonStates</span></span>|<span data-ttu-id="54dbb-115">默认状态。</span><span class="sxs-lookup"><span data-stu-id="54dbb-115">The default state.</span></span>|
|<span data-ttu-id="54dbb-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="54dbb-116">MouseOver</span></span>|<span data-ttu-id="54dbb-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="54dbb-117">CommonStates</span></span>|<span data-ttu-id="54dbb-118">鼠标指针悬停在控件上。</span><span class="sxs-lookup"><span data-stu-id="54dbb-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="54dbb-119">已按下</span><span class="sxs-lookup"><span data-stu-id="54dbb-119">Pressed</span></span>|<span data-ttu-id="54dbb-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="54dbb-120">CommonStates</span></span>|<span data-ttu-id="54dbb-121">已按下控件。</span><span class="sxs-lookup"><span data-stu-id="54dbb-121">The control is pressed.</span></span>|
|<span data-ttu-id="54dbb-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="54dbb-122">Disabled</span></span>|<span data-ttu-id="54dbb-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="54dbb-123">CommonStates</span></span>|<span data-ttu-id="54dbb-124">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="54dbb-124">The control is disabled.</span></span>|
|<span data-ttu-id="54dbb-125">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="54dbb-125">Focused</span></span>|<span data-ttu-id="54dbb-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="54dbb-126">FocusStates</span></span>|<span data-ttu-id="54dbb-127">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="54dbb-127">The control has focus.</span></span>|
|<span data-ttu-id="54dbb-128">失去焦点</span><span class="sxs-lookup"><span data-stu-id="54dbb-128">Unfocused</span></span>|<span data-ttu-id="54dbb-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="54dbb-129">FocusStates</span></span>|<span data-ttu-id="54dbb-130">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="54dbb-130">The control does not have focus.</span></span>|
|<span data-ttu-id="54dbb-131">有效</span><span class="sxs-lookup"><span data-stu-id="54dbb-131">Valid</span></span>|<span data-ttu-id="54dbb-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="54dbb-132">ValidationStates</span></span>|<span data-ttu-id="54dbb-133">控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。</span><span class="sxs-lookup"><span data-stu-id="54dbb-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="54dbb-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="54dbb-134">InvalidFocused</span></span>|<span data-ttu-id="54dbb-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="54dbb-135">ValidationStates</span></span>|<span data-ttu-id="54dbb-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。</span><span class="sxs-lookup"><span data-stu-id="54dbb-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="54dbb-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="54dbb-137">InvalidUnfocused</span></span>|<span data-ttu-id="54dbb-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="54dbb-138">ValidationStates</span></span>|<span data-ttu-id="54dbb-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="54dbb-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="thumb-controltemplate-example"></a><span data-ttu-id="54dbb-140">Thumb System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="54dbb-140">Thumb ControlTemplate Example</span></span>

<span data-ttu-id="54dbb-141">下面的示例演示如何为 <xref:System.Windows.Controls.Primitives.Thumb> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。</span><span class="sxs-lookup"><span data-stu-id="54dbb-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>

[!code-xaml[ControlTemplateExamples#Thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#thumb)]

<span data-ttu-id="54dbb-142">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="54dbb-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="54dbb-143">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="54dbb-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="54dbb-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54dbb-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="54dbb-145">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="54dbb-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="54dbb-146">控件自定义</span><span class="sxs-lookup"><span data-stu-id="54dbb-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="54dbb-147">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="54dbb-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="54dbb-148">为控件创建模板</span><span class="sxs-lookup"><span data-stu-id="54dbb-148">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
