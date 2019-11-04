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
ms.openlocfilehash: 64764d43191d30c191c5d6519982b16cfc86d26e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460953"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="ac820-102">Button 样式和模板</span><span class="sxs-lookup"><span data-stu-id="ac820-102">Button Styles and Templates</span></span>
<span data-ttu-id="ac820-103">本主题介绍 <xref:System.Windows.Controls.Button> 控件的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="ac820-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="ac820-104">您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。</span><span class="sxs-lookup"><span data-stu-id="ac820-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="ac820-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="ac820-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="ac820-106">Button 部分</span><span class="sxs-lookup"><span data-stu-id="ac820-106">Button Parts</span></span>  
 <span data-ttu-id="ac820-107"><xref:System.Windows.Controls.Button> 控件没有任何命名部分。</span><span class="sxs-lookup"><span data-stu-id="ac820-107">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="ac820-108">按钮状态</span><span class="sxs-lookup"><span data-stu-id="ac820-108">Button States</span></span>  
 <span data-ttu-id="ac820-109">下表列出了 <xref:System.Windows.Controls.Button> 控件的可视状态。</span><span class="sxs-lookup"><span data-stu-id="ac820-109">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="ac820-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="ac820-110">VisualState Name</span></span>|<span data-ttu-id="ac820-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="ac820-111">VisualStateGroup Name</span></span>|<span data-ttu-id="ac820-112">描述</span><span class="sxs-lookup"><span data-stu-id="ac820-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ac820-113">普通</span><span class="sxs-lookup"><span data-stu-id="ac820-113">Normal</span></span>|<span data-ttu-id="ac820-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ac820-114">CommonStates</span></span>|<span data-ttu-id="ac820-115">默认状态。</span><span class="sxs-lookup"><span data-stu-id="ac820-115">The default state.</span></span>|  
|<span data-ttu-id="ac820-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="ac820-116">MouseOver</span></span>|<span data-ttu-id="ac820-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ac820-117">CommonStates</span></span>|<span data-ttu-id="ac820-118">鼠标指针悬停在控件上。</span><span class="sxs-lookup"><span data-stu-id="ac820-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="ac820-119">已按下</span><span class="sxs-lookup"><span data-stu-id="ac820-119">Pressed</span></span>|<span data-ttu-id="ac820-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ac820-120">CommonStates</span></span>|<span data-ttu-id="ac820-121">已按下控件。</span><span class="sxs-lookup"><span data-stu-id="ac820-121">The control is pressed.</span></span>|  
|<span data-ttu-id="ac820-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="ac820-122">Disabled</span></span>|<span data-ttu-id="ac820-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ac820-123">CommonStates</span></span>|<span data-ttu-id="ac820-124">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="ac820-124">The control is disabled.</span></span>|  
|<span data-ttu-id="ac820-125">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="ac820-125">Focused</span></span>|<span data-ttu-id="ac820-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ac820-126">FocusStates</span></span>|<span data-ttu-id="ac820-127">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="ac820-127">The control has focus.</span></span>|  
|<span data-ttu-id="ac820-128">失去焦点</span><span class="sxs-lookup"><span data-stu-id="ac820-128">Unfocused</span></span>|<span data-ttu-id="ac820-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ac820-129">FocusStates</span></span>|<span data-ttu-id="ac820-130">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="ac820-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="ac820-131">有效</span><span class="sxs-lookup"><span data-stu-id="ac820-131">Valid</span></span>|<span data-ttu-id="ac820-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ac820-132">ValidationStates</span></span>|<span data-ttu-id="ac820-133">控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。</span><span class="sxs-lookup"><span data-stu-id="ac820-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="ac820-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="ac820-134">InvalidFocused</span></span>|<span data-ttu-id="ac820-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ac820-135">ValidationStates</span></span>|<span data-ttu-id="ac820-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 并且控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="ac820-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="ac820-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="ac820-137">InvalidUnfocused</span></span>|<span data-ttu-id="ac820-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ac820-138">ValidationStates</span></span>|<span data-ttu-id="ac820-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 的，该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="ac820-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="ac820-140">按钮 System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="ac820-140">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="ac820-141">下面的示例演示如何为 <xref:System.Windows.Controls.Button> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。</span><span class="sxs-lookup"><span data-stu-id="ac820-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="ac820-142">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="ac820-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="ac820-143">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="ac820-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac820-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="ac820-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="ac820-145">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="ac820-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="ac820-146">控件自定义</span><span class="sxs-lookup"><span data-stu-id="ac820-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="ac820-147">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="ac820-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="ac820-148">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="ac820-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
