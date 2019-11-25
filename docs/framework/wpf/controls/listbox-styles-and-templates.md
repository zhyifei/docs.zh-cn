---
title: ListBox 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], ListBox
- templates [WPF], ListBox
- states [WPF], ListBox
- ControlTemplate [WPF], ListBox
- parts [WPF], ListBox
- ListBox [WPF], styles and templates
ms.assetid: fc5764cb-c27b-495b-88d4-d969a8213ccb
ms.openlocfilehash: cb7043a21020193a4b2a2569ec610f311834a698
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283745"
---
# <a name="listbox-styles-and-templates"></a><span data-ttu-id="769b8-102">ListBox 样式和模板</span><span class="sxs-lookup"><span data-stu-id="769b8-102">ListBox Styles and Templates</span></span>
<span data-ttu-id="769b8-103">本主题介绍 <xref:System.Windows.Controls.ListBox> 控件的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="769b8-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="769b8-104">您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。</span><span class="sxs-lookup"><span data-stu-id="769b8-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="769b8-105">有关详细信息，请参阅为[控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)。</span><span class="sxs-lookup"><span data-stu-id="769b8-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="listbox-parts"></a><span data-ttu-id="769b8-106">ListBox 部件</span><span class="sxs-lookup"><span data-stu-id="769b8-106">ListBox Parts</span></span>  
 <span data-ttu-id="769b8-107"><xref:System.Windows.Controls.ListBox> 控件没有任何命名部分。</span><span class="sxs-lookup"><span data-stu-id="769b8-107">The <xref:System.Windows.Controls.ListBox> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="769b8-108">为 <xref:System.Windows.Controls.ListBox>创建 <xref:System.Windows.Controls.ControlTemplate> 时，模板可能包含 <xref:System.Windows.Controls.ScrollViewer>中的 <xref:System.Windows.Controls.ItemsPresenter>。</span><span class="sxs-lookup"><span data-stu-id="769b8-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ListBox>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="769b8-109">（<xref:System.Windows.Controls.ItemsPresenter> 显示 <xref:System.Windows.Controls.ListBox>中的每一项; <xref:System.Windows.Controls.ScrollViewer> 允许在控件中滚动）。</span><span class="sxs-lookup"><span data-stu-id="769b8-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ListBox>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="769b8-110">如果 <xref:System.Windows.Controls.ItemsPresenter> 不是 <xref:System.Windows.Controls.ScrollViewer>的直接子级，则必须为 <xref:System.Windows.Controls.ItemsPresenter> 指定名称 `ItemsPresenter`。</span><span class="sxs-lookup"><span data-stu-id="769b8-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="listbox-states"></a><span data-ttu-id="769b8-111">ListBox 状态</span><span class="sxs-lookup"><span data-stu-id="769b8-111">ListBox States</span></span>  
 <span data-ttu-id="769b8-112">下表列出了 <xref:System.Windows.Controls.ListBox> 控件的可视状态。</span><span class="sxs-lookup"><span data-stu-id="769b8-112">The following table lists the visual states for the <xref:System.Windows.Controls.ListBox> control.</span></span>  
  
|<span data-ttu-id="769b8-113">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="769b8-113">VisualState Name</span></span>|<span data-ttu-id="769b8-114">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="769b8-114">VisualStateGroup Name</span></span>|<span data-ttu-id="769b8-115">描述</span><span class="sxs-lookup"><span data-stu-id="769b8-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="769b8-116">有效</span><span class="sxs-lookup"><span data-stu-id="769b8-116">Valid</span></span>|<span data-ttu-id="769b8-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="769b8-117">ValidationStates</span></span>|<span data-ttu-id="769b8-118">控件有效。</span><span class="sxs-lookup"><span data-stu-id="769b8-118">The control is valid.</span></span>|  
|<span data-ttu-id="769b8-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="769b8-119">InvalidFocused</span></span>|<span data-ttu-id="769b8-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="769b8-120">ValidationStates</span></span>|<span data-ttu-id="769b8-121">控件无效，但具有焦点。</span><span class="sxs-lookup"><span data-stu-id="769b8-121">The control is not valid and has focus.</span></span>|  
|<span data-ttu-id="769b8-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="769b8-122">InvalidUnfocused</span></span>|<span data-ttu-id="769b8-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="769b8-123">ValidationStates</span></span>|<span data-ttu-id="769b8-124">控件无效，并且没有焦点。</span><span class="sxs-lookup"><span data-stu-id="769b8-124">The control is not valid and does not have focus.</span></span>|  
  
## <a name="listboxitem-parts"></a><span data-ttu-id="769b8-125">ListBoxItem 部件</span><span class="sxs-lookup"><span data-stu-id="769b8-125">ListBoxItem Parts</span></span>  
 <span data-ttu-id="769b8-126"><xref:System.Windows.Controls.ListBoxItem> 控件没有任何命名部分。</span><span class="sxs-lookup"><span data-stu-id="769b8-126">The <xref:System.Windows.Controls.ListBoxItem> control does not have any named parts.</span></span>  
  
## <a name="listboxitem-states"></a><span data-ttu-id="769b8-127">ListBoxItem 状态</span><span class="sxs-lookup"><span data-stu-id="769b8-127">ListBoxItem States</span></span>  
 <span data-ttu-id="769b8-128">下表列出了 <xref:System.Windows.Controls.ListBox> 控件的可视状态。</span><span class="sxs-lookup"><span data-stu-id="769b8-128">The following table lists the visual states for the <xref:System.Windows.Controls.ListBox> control.</span></span>  
  
|<span data-ttu-id="769b8-129">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="769b8-129">VisualState Name</span></span>|<span data-ttu-id="769b8-130">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="769b8-130">VisualStateGroup Name</span></span>|<span data-ttu-id="769b8-131">描述</span><span class="sxs-lookup"><span data-stu-id="769b8-131">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="769b8-132">一般</span><span class="sxs-lookup"><span data-stu-id="769b8-132">Normal</span></span>|<span data-ttu-id="769b8-133">CommonStates</span><span class="sxs-lookup"><span data-stu-id="769b8-133">CommonStates</span></span>|<span data-ttu-id="769b8-134">默认状态。</span><span class="sxs-lookup"><span data-stu-id="769b8-134">The default state.</span></span>|  
|<span data-ttu-id="769b8-135">MouseOver</span><span class="sxs-lookup"><span data-stu-id="769b8-135">MouseOver</span></span>|<span data-ttu-id="769b8-136">CommonStates</span><span class="sxs-lookup"><span data-stu-id="769b8-136">CommonStates</span></span>|<span data-ttu-id="769b8-137">鼠标指针悬停在控件上。</span><span class="sxs-lookup"><span data-stu-id="769b8-137">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="769b8-138">Disabled</span><span class="sxs-lookup"><span data-stu-id="769b8-138">Disabled</span></span>|<span data-ttu-id="769b8-139">CommonStates</span><span class="sxs-lookup"><span data-stu-id="769b8-139">CommonStates</span></span>|<span data-ttu-id="769b8-140">该项已禁用。</span><span class="sxs-lookup"><span data-stu-id="769b8-140">The item is disabled.</span></span>|  
|<span data-ttu-id="769b8-141">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="769b8-141">Focused</span></span>|<span data-ttu-id="769b8-142">FocusStates</span><span class="sxs-lookup"><span data-stu-id="769b8-142">FocusStates</span></span>|<span data-ttu-id="769b8-143">该项有焦点。</span><span class="sxs-lookup"><span data-stu-id="769b8-143">The item has focus.</span></span>|  
|<span data-ttu-id="769b8-144">失去焦点</span><span class="sxs-lookup"><span data-stu-id="769b8-144">Unfocused</span></span>|<span data-ttu-id="769b8-145">FocusStates</span><span class="sxs-lookup"><span data-stu-id="769b8-145">FocusStates</span></span>|<span data-ttu-id="769b8-146">该项没有焦点。</span><span class="sxs-lookup"><span data-stu-id="769b8-146">The item does not have focus.</span></span>|  
|<span data-ttu-id="769b8-147">未选定</span><span class="sxs-lookup"><span data-stu-id="769b8-147">Unselected</span></span>|<span data-ttu-id="769b8-148">SelectionStates</span><span class="sxs-lookup"><span data-stu-id="769b8-148">SelectionStates</span></span>|<span data-ttu-id="769b8-149">未选定该项。</span><span class="sxs-lookup"><span data-stu-id="769b8-149">The item is not selected.</span></span>|  
|<span data-ttu-id="769b8-150">已选定</span><span class="sxs-lookup"><span data-stu-id="769b8-150">Selected</span></span>|<span data-ttu-id="769b8-151">SelectionStates</span><span class="sxs-lookup"><span data-stu-id="769b8-151">SelectionStates</span></span>|<span data-ttu-id="769b8-152">该项当前已选定。</span><span class="sxs-lookup"><span data-stu-id="769b8-152">The item is currentlyplate selected.</span></span>|  
|<span data-ttu-id="769b8-153">SelectedUnfocused</span><span class="sxs-lookup"><span data-stu-id="769b8-153">SelectedUnfocused</span></span>|<span data-ttu-id="769b8-154">SelectionStates</span><span class="sxs-lookup"><span data-stu-id="769b8-154">SelectionStates</span></span>|<span data-ttu-id="769b8-155">该项已选定，但没有焦点。</span><span class="sxs-lookup"><span data-stu-id="769b8-155">The item is selected, but does not have focus.</span></span>|  
|<span data-ttu-id="769b8-156">有效</span><span class="sxs-lookup"><span data-stu-id="769b8-156">Valid</span></span>|<span data-ttu-id="769b8-157">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="769b8-157">ValidationStates</span></span>|<span data-ttu-id="769b8-158">控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。</span><span class="sxs-lookup"><span data-stu-id="769b8-158">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="769b8-159">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="769b8-159">InvalidFocused</span></span>|<span data-ttu-id="769b8-160">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="769b8-160">ValidationStates</span></span>|<span data-ttu-id="769b8-161"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。</span><span class="sxs-lookup"><span data-stu-id="769b8-161">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="769b8-162">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="769b8-162">InvalidUnfocused</span></span>|<span data-ttu-id="769b8-163">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="769b8-163">ValidationStates</span></span>|<span data-ttu-id="769b8-164"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="769b8-164">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="listbox-controltemplate-example"></a><span data-ttu-id="769b8-165">ListBox ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="769b8-165">ListBox ControlTemplate Example</span></span>  
 <span data-ttu-id="769b8-166">下面的示例演示如何为 <xref:System.Windows.Controls.ListBox> 和 <xref:System.Windows.Controls.ListBoxItem> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。</span><span class="sxs-lookup"><span data-stu-id="769b8-166">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ListBox> and <xref:System.Windows.Controls.ListBoxItem> controls.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ListBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/listbox.xaml#listbox)]  
  
 <span data-ttu-id="769b8-167">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="769b8-167">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="769b8-168">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="769b8-168">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="769b8-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="769b8-169">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="769b8-170">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="769b8-170">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="769b8-171">控件自定义</span><span class="sxs-lookup"><span data-stu-id="769b8-171">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="769b8-172">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="769b8-172">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="769b8-173">为控件创建模板</span><span class="sxs-lookup"><span data-stu-id="769b8-173">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
