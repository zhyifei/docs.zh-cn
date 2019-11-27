---
title: PasswordBox 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], PasswordBox
- templates [WPF], PasswordBox
- ControlTemplate [WPF], PasswordBox
- states [WPF], PasswordBox
- PasswordBox [WPF], styles and templates
- parts [WPF], PasswordBox
ms.assetid: deb52107-959f-4a60-b303-d21a0a933060
ms.openlocfilehash: 4ba90182468466773644c7375059f0cc01675b33
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283466"
---
# <a name="passwordbox-styles-and-templates"></a><span data-ttu-id="fb262-102">PasswordBox 样式和模板</span><span class="sxs-lookup"><span data-stu-id="fb262-102">PasswordBox Styles and Templates</span></span>

<span data-ttu-id="fb262-103">本主题介绍 <xref:System.Windows.Controls.PasswordBox> 控件的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="fb262-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.PasswordBox> control.</span></span> <span data-ttu-id="fb262-104">您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。</span><span class="sxs-lookup"><span data-stu-id="fb262-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="fb262-105">有关详细信息，请参阅为[控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)。</span><span class="sxs-lookup"><span data-stu-id="fb262-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>

## <a name="passwordbox-parts"></a><span data-ttu-id="fb262-106">PasswordBox 部件</span><span class="sxs-lookup"><span data-stu-id="fb262-106">PasswordBox Parts</span></span>

<span data-ttu-id="fb262-107">下表列出了 <xref:System.Windows.Controls.PasswordBox> 控件的已命名部分。</span><span class="sxs-lookup"><span data-stu-id="fb262-107">The following table lists the named parts for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="fb262-108">部件</span><span class="sxs-lookup"><span data-stu-id="fb262-108">Part</span></span>|<span data-ttu-id="fb262-109">类型</span><span class="sxs-lookup"><span data-stu-id="fb262-109">Type</span></span>|<span data-ttu-id="fb262-110">说明</span><span class="sxs-lookup"><span data-stu-id="fb262-110">Description</span></span>|
|-|-|-|
|<span data-ttu-id="fb262-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="fb262-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="fb262-112">可包含 <xref:System.Windows.FrameworkElement>的可视元素。</span><span class="sxs-lookup"><span data-stu-id="fb262-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="fb262-113"><xref:System.Windows.Controls.PasswordBox> 的文本显示在此元素中。</span><span class="sxs-lookup"><span data-stu-id="fb262-113">The text of the <xref:System.Windows.Controls.PasswordBox> is displayed in this element.</span></span>|

## <a name="passwordbox-states"></a><span data-ttu-id="fb262-114">PasswordBox 状态</span><span class="sxs-lookup"><span data-stu-id="fb262-114">PasswordBox States</span></span>

<span data-ttu-id="fb262-115">下表列出了 <xref:System.Windows.Controls.PasswordBox> 控件的可视状态。</span><span class="sxs-lookup"><span data-stu-id="fb262-115">The following table lists the visual states for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="fb262-116">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="fb262-116">VisualState Name</span></span>|<span data-ttu-id="fb262-117">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="fb262-117">VisualStateGroup Name</span></span>|<span data-ttu-id="fb262-118">说明</span><span class="sxs-lookup"><span data-stu-id="fb262-118">Description</span></span>|
|-|-|-|
|<span data-ttu-id="fb262-119">正常</span><span class="sxs-lookup"><span data-stu-id="fb262-119">Normal</span></span>|<span data-ttu-id="fb262-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fb262-120">CommonStates</span></span>|<span data-ttu-id="fb262-121">默认状态。</span><span class="sxs-lookup"><span data-stu-id="fb262-121">The default state.</span></span>|
|<span data-ttu-id="fb262-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="fb262-122">MouseOver</span></span>|<span data-ttu-id="fb262-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fb262-123">CommonStates</span></span>|<span data-ttu-id="fb262-124">鼠标指针悬停在控件上。</span><span class="sxs-lookup"><span data-stu-id="fb262-124">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="fb262-125">已禁用</span><span class="sxs-lookup"><span data-stu-id="fb262-125">Disabled</span></span>|<span data-ttu-id="fb262-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fb262-126">CommonStates</span></span>|<span data-ttu-id="fb262-127">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="fb262-127">The control is disabled.</span></span>|
|<span data-ttu-id="fb262-128">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="fb262-128">Focused</span></span>|<span data-ttu-id="fb262-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="fb262-129">FocusStates</span></span>|<span data-ttu-id="fb262-130">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="fb262-130">The control has focus.</span></span>|
|<span data-ttu-id="fb262-131">失去焦点</span><span class="sxs-lookup"><span data-stu-id="fb262-131">Unfocused</span></span>|<span data-ttu-id="fb262-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="fb262-132">FocusStates</span></span>|<span data-ttu-id="fb262-133">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="fb262-133">The control does not have focus.</span></span>|
|<span data-ttu-id="fb262-134">有效</span><span class="sxs-lookup"><span data-stu-id="fb262-134">Valid</span></span>|<span data-ttu-id="fb262-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fb262-135">ValidationStates</span></span>|<span data-ttu-id="fb262-136">控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。</span><span class="sxs-lookup"><span data-stu-id="fb262-136">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="fb262-137">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="fb262-137">InvalidFocused</span></span>|<span data-ttu-id="fb262-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fb262-138">ValidationStates</span></span>|<span data-ttu-id="fb262-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。</span><span class="sxs-lookup"><span data-stu-id="fb262-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="fb262-140">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="fb262-140">InvalidUnfocused</span></span>|<span data-ttu-id="fb262-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fb262-141">ValidationStates</span></span>|<span data-ttu-id="fb262-142"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="fb262-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="passwordbox-controltemplate-example"></a><span data-ttu-id="fb262-143">PasswordBox System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="fb262-143">PasswordBox ControlTemplate Example</span></span>

<span data-ttu-id="fb262-144">下面的示例演示如何为 <xref:System.Windows.Controls.PasswordBox> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。</span><span class="sxs-lookup"><span data-stu-id="fb262-144">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

[!code-xaml[ControlTemplateExamples#PasswordBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]

<span data-ttu-id="fb262-145">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="fb262-145">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="fb262-146">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="fb262-146">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="fb262-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb262-147">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="fb262-148">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="fb262-148">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="fb262-149">控件自定义</span><span class="sxs-lookup"><span data-stu-id="fb262-149">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="fb262-150">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="fb262-150">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="fb262-151">为控件创建模板</span><span class="sxs-lookup"><span data-stu-id="fb262-151">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
