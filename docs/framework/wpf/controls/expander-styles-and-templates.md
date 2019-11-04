---
title: Expander 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], Expander
- ControlTemplate [WPF], Expander
- templates [WPF], Expander
- Expander [WPF], styles and templates
- states [WPF], Expander
- parts [WPF], Expander
ms.assetid: da2e5a1c-5230-4c21-98a5-59c7895facd7
ms.openlocfilehash: 26989474f264161be12bcc14fed614fdc7f775b6
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460329"
---
# <a name="expander-styles-and-templates"></a><span data-ttu-id="7c880-102">Expander 样式和模板</span><span class="sxs-lookup"><span data-stu-id="7c880-102">Expander Styles and Templates</span></span>
<span data-ttu-id="7c880-103">本主题介绍 <xref:System.Windows.Controls.Expander> 控件的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="7c880-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Expander> control.</span></span> <span data-ttu-id="7c880-104">您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。</span><span class="sxs-lookup"><span data-stu-id="7c880-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="7c880-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="7c880-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="expander-parts"></a><span data-ttu-id="7c880-106">扩展器部分</span><span class="sxs-lookup"><span data-stu-id="7c880-106">Expander Parts</span></span>  
 <span data-ttu-id="7c880-107"><xref:System.Windows.Controls.Expander> 控件没有任何命名部分。</span><span class="sxs-lookup"><span data-stu-id="7c880-107">The <xref:System.Windows.Controls.Expander> control does not have any named parts.</span></span>  
  
## <a name="expander-states"></a><span data-ttu-id="7c880-108">扩展器状态</span><span class="sxs-lookup"><span data-stu-id="7c880-108">Expander States</span></span>  
 <span data-ttu-id="7c880-109">下表列出了 <xref:System.Windows.Controls.Expander> 控件的可视状态。</span><span class="sxs-lookup"><span data-stu-id="7c880-109">The following table lists the visual states for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
|<span data-ttu-id="7c880-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="7c880-110">VisualState Name</span></span>|<span data-ttu-id="7c880-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="7c880-111">VisualStateGroup Name</span></span>|<span data-ttu-id="7c880-112">描述</span><span class="sxs-lookup"><span data-stu-id="7c880-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="7c880-113">普通</span><span class="sxs-lookup"><span data-stu-id="7c880-113">Normal</span></span>|<span data-ttu-id="7c880-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="7c880-114">CommonStates</span></span>|<span data-ttu-id="7c880-115">默认状态。</span><span class="sxs-lookup"><span data-stu-id="7c880-115">The default state.</span></span>|  
|<span data-ttu-id="7c880-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="7c880-116">MouseOver</span></span>|<span data-ttu-id="7c880-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="7c880-117">CommonStates</span></span>|<span data-ttu-id="7c880-118">鼠标指针悬停在控件上。</span><span class="sxs-lookup"><span data-stu-id="7c880-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="7c880-119">Disabled</span><span class="sxs-lookup"><span data-stu-id="7c880-119">Disabled</span></span>|<span data-ttu-id="7c880-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="7c880-120">CommonStates</span></span>|<span data-ttu-id="7c880-121">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="7c880-121">The control is disabled.</span></span>|  
|<span data-ttu-id="7c880-122">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="7c880-122">Focused</span></span>|<span data-ttu-id="7c880-123">FocusStates</span><span class="sxs-lookup"><span data-stu-id="7c880-123">FocusStates</span></span>|<span data-ttu-id="7c880-124">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="7c880-124">The control has focus.</span></span>|  
|<span data-ttu-id="7c880-125">失去焦点</span><span class="sxs-lookup"><span data-stu-id="7c880-125">Unfocused</span></span>|<span data-ttu-id="7c880-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="7c880-126">FocusStates</span></span>|<span data-ttu-id="7c880-127">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="7c880-127">The control does not have focus.</span></span>|  
|<span data-ttu-id="7c880-128">展开</span><span class="sxs-lookup"><span data-stu-id="7c880-128">Expanded</span></span>|<span data-ttu-id="7c880-129">ExpansionStates</span><span class="sxs-lookup"><span data-stu-id="7c880-129">ExpansionStates</span></span>|<span data-ttu-id="7c880-130">控件已展开。</span><span class="sxs-lookup"><span data-stu-id="7c880-130">The control is expanded.</span></span>|  
|<span data-ttu-id="7c880-131">Collapsed</span><span class="sxs-lookup"><span data-stu-id="7c880-131">Collapsed</span></span>|<span data-ttu-id="7c880-132">ExpansionStates</span><span class="sxs-lookup"><span data-stu-id="7c880-132">ExpansionStates</span></span>|<span data-ttu-id="7c880-133">控件未展开。</span><span class="sxs-lookup"><span data-stu-id="7c880-133">The control is not expanded.</span></span>|  
|<span data-ttu-id="7c880-134">ExpandDown</span><span class="sxs-lookup"><span data-stu-id="7c880-134">ExpandDown</span></span>|<span data-ttu-id="7c880-135">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="7c880-135">ExpandDirectionStates</span></span>|<span data-ttu-id="7c880-136">控件向下扩展。</span><span class="sxs-lookup"><span data-stu-id="7c880-136">The control expands down.</span></span>|  
|<span data-ttu-id="7c880-137">ExpandUp</span><span class="sxs-lookup"><span data-stu-id="7c880-137">ExpandUp</span></span>|<span data-ttu-id="7c880-138">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="7c880-138">ExpandDirectionStates</span></span>|<span data-ttu-id="7c880-139">控件展开。</span><span class="sxs-lookup"><span data-stu-id="7c880-139">The control expands up.</span></span>|  
|<span data-ttu-id="7c880-140">ExpandLeft</span><span class="sxs-lookup"><span data-stu-id="7c880-140">ExpandLeft</span></span>|<span data-ttu-id="7c880-141">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="7c880-141">ExpandDirectionStates</span></span>|<span data-ttu-id="7c880-142">控件向左扩展。</span><span class="sxs-lookup"><span data-stu-id="7c880-142">The control expands left.</span></span>|  
|<span data-ttu-id="7c880-143">ExpandRight</span><span class="sxs-lookup"><span data-stu-id="7c880-143">ExpandRight</span></span>|<span data-ttu-id="7c880-144">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="7c880-144">ExpandDirectionStates</span></span>|<span data-ttu-id="7c880-145">控件向右展开。</span><span class="sxs-lookup"><span data-stu-id="7c880-145">The control expands right.</span></span>|  
|<span data-ttu-id="7c880-146">有效</span><span class="sxs-lookup"><span data-stu-id="7c880-146">Valid</span></span>|<span data-ttu-id="7c880-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7c880-147">ValidationStates</span></span>|<span data-ttu-id="7c880-148">控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。</span><span class="sxs-lookup"><span data-stu-id="7c880-148">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="7c880-149">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="7c880-149">InvalidFocused</span></span>|<span data-ttu-id="7c880-150">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7c880-150">ValidationStates</span></span>|<span data-ttu-id="7c880-151"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。</span><span class="sxs-lookup"><span data-stu-id="7c880-151">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="7c880-152">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="7c880-152">InvalidUnfocused</span></span>|<span data-ttu-id="7c880-153">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7c880-153">ValidationStates</span></span>|<span data-ttu-id="7c880-154"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="7c880-154">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="expander-controltemplate-example"></a><span data-ttu-id="7c880-155">扩展器 System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="7c880-155">Expander ControlTemplate Example</span></span>  
 <span data-ttu-id="7c880-156">下面的示例演示如何为 <xref:System.Windows.Controls.Expander> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。</span><span class="sxs-lookup"><span data-stu-id="7c880-156">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Expander](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/expander.xaml#expander)]  
  
 <span data-ttu-id="7c880-157">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="7c880-157">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="7c880-158">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="7c880-158">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c880-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="7c880-159">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="7c880-160">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="7c880-160">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="7c880-161">控件自定义</span><span class="sxs-lookup"><span data-stu-id="7c880-161">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="7c880-162">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="7c880-162">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="7c880-163">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="7c880-163">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
