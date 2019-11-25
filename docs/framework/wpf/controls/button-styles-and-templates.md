---
title: Button 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
ms.openlocfilehash: ef9f85848ebdda9dc4ae15d0f54847eacd46e24d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283585"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="57a84-102">Button 样式和模板</span><span class="sxs-lookup"><span data-stu-id="57a84-102">Button Styles and Templates</span></span>
<span data-ttu-id="57a84-103">本主题介绍 <xref:System.Windows.Controls.Button> 控件的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="57a84-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="57a84-104">您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。</span><span class="sxs-lookup"><span data-stu-id="57a84-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="57a84-105">有关详细信息，请参阅为[控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)。</span><span class="sxs-lookup"><span data-stu-id="57a84-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="57a84-106">Button 部分</span><span class="sxs-lookup"><span data-stu-id="57a84-106">Button Parts</span></span>  
 <span data-ttu-id="57a84-107"><xref:System.Windows.Controls.Button> 控件没有任何命名部分。</span><span class="sxs-lookup"><span data-stu-id="57a84-107">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="57a84-108">按钮状态</span><span class="sxs-lookup"><span data-stu-id="57a84-108">Button States</span></span>  
 <span data-ttu-id="57a84-109">下表列出了 <xref:System.Windows.Controls.Button> 控件的可视状态。</span><span class="sxs-lookup"><span data-stu-id="57a84-109">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="57a84-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="57a84-110">VisualState Name</span></span>|<span data-ttu-id="57a84-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="57a84-111">VisualStateGroup Name</span></span>|<span data-ttu-id="57a84-112">描述</span><span class="sxs-lookup"><span data-stu-id="57a84-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="57a84-113">一般</span><span class="sxs-lookup"><span data-stu-id="57a84-113">Normal</span></span>|<span data-ttu-id="57a84-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="57a84-114">CommonStates</span></span>|<span data-ttu-id="57a84-115">默认状态。</span><span class="sxs-lookup"><span data-stu-id="57a84-115">The default state.</span></span>|  
|<span data-ttu-id="57a84-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="57a84-116">MouseOver</span></span>|<span data-ttu-id="57a84-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="57a84-117">CommonStates</span></span>|<span data-ttu-id="57a84-118">鼠标指针悬停在控件上。</span><span class="sxs-lookup"><span data-stu-id="57a84-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="57a84-119">已按下</span><span class="sxs-lookup"><span data-stu-id="57a84-119">Pressed</span></span>|<span data-ttu-id="57a84-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="57a84-120">CommonStates</span></span>|<span data-ttu-id="57a84-121">已按下控件。</span><span class="sxs-lookup"><span data-stu-id="57a84-121">The control is pressed.</span></span>|  
|<span data-ttu-id="57a84-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="57a84-122">Disabled</span></span>|<span data-ttu-id="57a84-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="57a84-123">CommonStates</span></span>|<span data-ttu-id="57a84-124">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="57a84-124">The control is disabled.</span></span>|  
|<span data-ttu-id="57a84-125">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="57a84-125">Focused</span></span>|<span data-ttu-id="57a84-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="57a84-126">FocusStates</span></span>|<span data-ttu-id="57a84-127">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="57a84-127">The control has focus.</span></span>|  
|<span data-ttu-id="57a84-128">失去焦点</span><span class="sxs-lookup"><span data-stu-id="57a84-128">Unfocused</span></span>|<span data-ttu-id="57a84-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="57a84-129">FocusStates</span></span>|<span data-ttu-id="57a84-130">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="57a84-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="57a84-131">有效</span><span class="sxs-lookup"><span data-stu-id="57a84-131">Valid</span></span>|<span data-ttu-id="57a84-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="57a84-132">ValidationStates</span></span>|<span data-ttu-id="57a84-133">控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。</span><span class="sxs-lookup"><span data-stu-id="57a84-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="57a84-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="57a84-134">InvalidFocused</span></span>|<span data-ttu-id="57a84-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="57a84-135">ValidationStates</span></span>|<span data-ttu-id="57a84-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 并且控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="57a84-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="57a84-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="57a84-137">InvalidUnfocused</span></span>|<span data-ttu-id="57a84-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="57a84-138">ValidationStates</span></span>|<span data-ttu-id="57a84-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 的，该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="57a84-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="57a84-140">按钮 System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="57a84-140">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="57a84-141">下面的示例演示如何为 <xref:System.Windows.Controls.Button> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。</span><span class="sxs-lookup"><span data-stu-id="57a84-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="57a84-142">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="57a84-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="57a84-143">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="57a84-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57a84-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57a84-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="57a84-145">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="57a84-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="57a84-146">控件自定义</span><span class="sxs-lookup"><span data-stu-id="57a84-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="57a84-147">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="57a84-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="57a84-148">为控件创建模板</span><span class="sxs-lookup"><span data-stu-id="57a84-148">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
