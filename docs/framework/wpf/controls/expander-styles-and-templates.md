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
ms.openlocfilehash: c5f805c251d3f6b256035e568798cd6d252ea9a4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911725"
---
# <a name="expander-styles-and-templates"></a><span data-ttu-id="4215c-102">Expander 样式和模板</span><span class="sxs-lookup"><span data-stu-id="4215c-102">Expander Styles and Templates</span></span>
<span data-ttu-id="4215c-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.Expander>控件。</span><span class="sxs-lookup"><span data-stu-id="4215c-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Expander> control.</span></span> <span data-ttu-id="4215c-104">可以修改默认<xref:System.Windows.Controls.ControlTemplate>为控件提供唯一外观。</span><span class="sxs-lookup"><span data-stu-id="4215c-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="4215c-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="4215c-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="expander-parts"></a><span data-ttu-id="4215c-106">扩展器部分</span><span class="sxs-lookup"><span data-stu-id="4215c-106">Expander Parts</span></span>  
 <span data-ttu-id="4215c-107"><xref:System.Windows.Controls.Expander>控件没有任何命名的部件。</span><span class="sxs-lookup"><span data-stu-id="4215c-107">The <xref:System.Windows.Controls.Expander> control does not have any named parts.</span></span>  
  
## <a name="expander-states"></a><span data-ttu-id="4215c-108">扩展器状态</span><span class="sxs-lookup"><span data-stu-id="4215c-108">Expander States</span></span>  
 <span data-ttu-id="4215c-109">下表列出了的可视状态<xref:System.Windows.Controls.Expander>控件。</span><span class="sxs-lookup"><span data-stu-id="4215c-109">The following table lists the visual states for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
|<span data-ttu-id="4215c-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="4215c-110">VisualState Name</span></span>|<span data-ttu-id="4215c-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="4215c-111">VisualStateGroup Name</span></span>|<span data-ttu-id="4215c-112">描述</span><span class="sxs-lookup"><span data-stu-id="4215c-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="4215c-113">普通</span><span class="sxs-lookup"><span data-stu-id="4215c-113">Normal</span></span>|<span data-ttu-id="4215c-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4215c-114">CommonStates</span></span>|<span data-ttu-id="4215c-115">默认状态。</span><span class="sxs-lookup"><span data-stu-id="4215c-115">The default state.</span></span>|  
|<span data-ttu-id="4215c-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="4215c-116">MouseOver</span></span>|<span data-ttu-id="4215c-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4215c-117">CommonStates</span></span>|<span data-ttu-id="4215c-118">鼠标指针悬停在控件上。</span><span class="sxs-lookup"><span data-stu-id="4215c-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="4215c-119">已禁用</span><span class="sxs-lookup"><span data-stu-id="4215c-119">Disabled</span></span>|<span data-ttu-id="4215c-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4215c-120">CommonStates</span></span>|<span data-ttu-id="4215c-121">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="4215c-121">The control is disabled.</span></span>|  
|<span data-ttu-id="4215c-122">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="4215c-122">Focused</span></span>|<span data-ttu-id="4215c-123">FocusStates</span><span class="sxs-lookup"><span data-stu-id="4215c-123">FocusStates</span></span>|<span data-ttu-id="4215c-124">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="4215c-124">The control has focus.</span></span>|  
|<span data-ttu-id="4215c-125">失去焦点</span><span class="sxs-lookup"><span data-stu-id="4215c-125">Unfocused</span></span>|<span data-ttu-id="4215c-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="4215c-126">FocusStates</span></span>|<span data-ttu-id="4215c-127">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="4215c-127">The control does not have focus.</span></span>|  
|<span data-ttu-id="4215c-128">展开</span><span class="sxs-lookup"><span data-stu-id="4215c-128">Expanded</span></span>|<span data-ttu-id="4215c-129">ExpansionStates</span><span class="sxs-lookup"><span data-stu-id="4215c-129">ExpansionStates</span></span>|<span data-ttu-id="4215c-130">展开控件。</span><span class="sxs-lookup"><span data-stu-id="4215c-130">The control is expanded.</span></span>|  
|<span data-ttu-id="4215c-131">Collapsed</span><span class="sxs-lookup"><span data-stu-id="4215c-131">Collapsed</span></span>|<span data-ttu-id="4215c-132">ExpansionStates</span><span class="sxs-lookup"><span data-stu-id="4215c-132">ExpansionStates</span></span>|<span data-ttu-id="4215c-133">不展开控件。</span><span class="sxs-lookup"><span data-stu-id="4215c-133">The control is not expanded.</span></span>|  
|<span data-ttu-id="4215c-134">ExpandDown</span><span class="sxs-lookup"><span data-stu-id="4215c-134">ExpandDown</span></span>|<span data-ttu-id="4215c-135">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="4215c-135">ExpandDirectionStates</span></span>|<span data-ttu-id="4215c-136">控件向下展开。</span><span class="sxs-lookup"><span data-stu-id="4215c-136">The control expands down.</span></span>|  
|<span data-ttu-id="4215c-137">ExpandUp</span><span class="sxs-lookup"><span data-stu-id="4215c-137">ExpandUp</span></span>|<span data-ttu-id="4215c-138">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="4215c-138">ExpandDirectionStates</span></span>|<span data-ttu-id="4215c-139">控件向上扩展。</span><span class="sxs-lookup"><span data-stu-id="4215c-139">The control expands up.</span></span>|  
|<span data-ttu-id="4215c-140">ExpandLeft</span><span class="sxs-lookup"><span data-stu-id="4215c-140">ExpandLeft</span></span>|<span data-ttu-id="4215c-141">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="4215c-141">ExpandDirectionStates</span></span>|<span data-ttu-id="4215c-142">控件向左展开。</span><span class="sxs-lookup"><span data-stu-id="4215c-142">The control expands left.</span></span>|  
|<span data-ttu-id="4215c-143">ExpandRight</span><span class="sxs-lookup"><span data-stu-id="4215c-143">ExpandRight</span></span>|<span data-ttu-id="4215c-144">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="4215c-144">ExpandDirectionStates</span></span>|<span data-ttu-id="4215c-145">控件向右展开。</span><span class="sxs-lookup"><span data-stu-id="4215c-145">The control expands right.</span></span>|  
|<span data-ttu-id="4215c-146">有效</span><span class="sxs-lookup"><span data-stu-id="4215c-146">Valid</span></span>|<span data-ttu-id="4215c-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4215c-147">ValidationStates</span></span>|<span data-ttu-id="4215c-148">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`false`。</span><span class="sxs-lookup"><span data-stu-id="4215c-148">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="4215c-149">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="4215c-149">InvalidFocused</span></span>|<span data-ttu-id="4215c-150">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4215c-150">ValidationStates</span></span>|<span data-ttu-id="4215c-151"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="4215c-151">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="4215c-152">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="4215c-152">InvalidUnfocused</span></span>|<span data-ttu-id="4215c-153">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4215c-153">ValidationStates</span></span>|<span data-ttu-id="4215c-154"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="4215c-154">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="expander-controltemplate-example"></a><span data-ttu-id="4215c-155">扩展器 ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="4215c-155">Expander ControlTemplate Example</span></span>  
 <span data-ttu-id="4215c-156">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Expander>控件。</span><span class="sxs-lookup"><span data-stu-id="4215c-156">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Expander](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/expander.xaml#expander)]  
  
 <span data-ttu-id="4215c-157">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="4215c-157">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="4215c-158">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="4215c-158">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4215c-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="4215c-159">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="4215c-160">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="4215c-160">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="4215c-161">控件自定义</span><span class="sxs-lookup"><span data-stu-id="4215c-161">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="4215c-162">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="4215c-162">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="4215c-163">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="4215c-163">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
