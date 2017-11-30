---
title: "ListView 样式和模板"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], ListView
- states [WPF], ListView
- ControlTemplate [WPF], ListView
- styles [WPF], ListView
- ListView [WPF], styles and templates
- templates [WPF], ListView
ms.assetid: d2387356-2171-4785-822a-7247e024b4ee
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ccd597aa6d517bb3a7dda347c26c0eaf731a278f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="listview-styles-and-templates"></a><span data-ttu-id="a9dc9-102">ListView 样式和模板</span><span class="sxs-lookup"><span data-stu-id="a9dc9-102">ListView Styles and Templates</span></span>
<span data-ttu-id="a9dc9-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="a9dc9-104">你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a9dc9-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="listview-parts"></a><span data-ttu-id="a9dc9-106">ListView 部件</span><span class="sxs-lookup"><span data-stu-id="a9dc9-106">ListView Parts</span></span>  
 <span data-ttu-id="a9dc9-107"><xref:System.Windows.Controls.ListView>控件不具有任何已命名的部件。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-107">The <xref:System.Windows.Controls.ListView> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="a9dc9-108">当你创建<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.ListView>，你的模板可能包含<xref:System.Windows.Controls.ItemsPresenter>内<xref:System.Windows.Controls.ScrollViewer>。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ListView>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="a9dc9-109">(<xref:System.Windows.Controls.ItemsPresenter>显示中的每一项<xref:System.Windows.Controls.ListView>;<xref:System.Windows.Controls.ScrollViewer>使控件内滚动)。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ListView>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="a9dc9-110">如果<xref:System.Windows.Controls.ItemsPresenter>不的直接子级<xref:System.Windows.Controls.ScrollViewer>，您必须为指定<xref:System.Windows.Controls.ItemsPresenter>名称， `ItemsPresenter`。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="listview-states"></a><span data-ttu-id="a9dc9-111">ListView 状态</span><span class="sxs-lookup"><span data-stu-id="a9dc9-111">ListView States</span></span>  
 <span data-ttu-id="a9dc9-112">下表列出的可视状态<xref:System.Windows.Controls.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-112">The following table lists the visual states for the <xref:System.Windows.Controls.ListView> control.</span></span>  
  
|<span data-ttu-id="a9dc9-113">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="a9dc9-113">VisualState Name</span></span>|<span data-ttu-id="a9dc9-114">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="a9dc9-114">VisualStateGroup Name</span></span>|<span data-ttu-id="a9dc9-115">描述</span><span class="sxs-lookup"><span data-stu-id="a9dc9-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a9dc9-116">有效</span><span class="sxs-lookup"><span data-stu-id="a9dc9-116">Valid</span></span>|<span data-ttu-id="a9dc9-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a9dc9-117">ValidationStates</span></span>|<span data-ttu-id="a9dc9-118">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a9dc9-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a9dc9-119">InvalidFocused</span></span>|<span data-ttu-id="a9dc9-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a9dc9-120">ValidationStates</span></span>|<span data-ttu-id="a9dc9-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="a9dc9-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a9dc9-122">InvalidUnfocused</span></span>|<span data-ttu-id="a9dc9-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a9dc9-123">ValidationStates</span></span>|<span data-ttu-id="a9dc9-124"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="listviewitem-parts"></a><span data-ttu-id="a9dc9-125">列表视图项部分</span><span class="sxs-lookup"><span data-stu-id="a9dc9-125">ListViewItem Parts</span></span>  
 <span data-ttu-id="a9dc9-126"><xref:System.Windows.Controls.ListViewItem>控件不具有任何已命名的部件。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-126">The <xref:System.Windows.Controls.ListViewItem> control does not have any named parts.</span></span>  
  
## <a name="listviewitem-states"></a><span data-ttu-id="a9dc9-127">列表视图项状态</span><span class="sxs-lookup"><span data-stu-id="a9dc9-127">ListViewItem States</span></span>  
 <span data-ttu-id="a9dc9-128">下表列出的状态<xref:System.Windows.Controls.ListViewItem>控件。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-128">The following table lists the states for the <xref:System.Windows.Controls.ListViewItem> control.</span></span>  
  
|<span data-ttu-id="a9dc9-129">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="a9dc9-129">VisualState Name</span></span>|<span data-ttu-id="a9dc9-130">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="a9dc9-130">VisualStateGroup Name</span></span>|<span data-ttu-id="a9dc9-131">描述</span><span class="sxs-lookup"><span data-stu-id="a9dc9-131">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a9dc9-132">普通</span><span class="sxs-lookup"><span data-stu-id="a9dc9-132">Normal</span></span>|<span data-ttu-id="a9dc9-133">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a9dc9-133">CommonStates</span></span>|<span data-ttu-id="a9dc9-134">默认状态。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-134">The default state.</span></span>|  
|<span data-ttu-id="a9dc9-135">已禁用</span><span class="sxs-lookup"><span data-stu-id="a9dc9-135">Disabled</span></span>|<span data-ttu-id="a9dc9-136">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a9dc9-136">CommonStates</span></span>|<span data-ttu-id="a9dc9-137">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-137">The control is disabled.</span></span>|  
|<span data-ttu-id="a9dc9-138">MouseOver</span><span class="sxs-lookup"><span data-stu-id="a9dc9-138">MouseOver</span></span>|<span data-ttu-id="a9dc9-139">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a9dc9-139">CommonStates</span></span>|<span data-ttu-id="a9dc9-140">鼠标指针位于<xref:System.Windows.Controls.ComboBox>控件。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-140">The mouse pointer is over the <xref:System.Windows.Controls.ComboBox> control.</span></span>|  
|<span data-ttu-id="a9dc9-141">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="a9dc9-141">Focused</span></span>|<span data-ttu-id="a9dc9-142">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a9dc9-142">FocusStates</span></span>|<span data-ttu-id="a9dc9-143">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-143">The control has focus.</span></span>|  
|<span data-ttu-id="a9dc9-144">失去焦点</span><span class="sxs-lookup"><span data-stu-id="a9dc9-144">Unfocused</span></span>|<span data-ttu-id="a9dc9-145">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a9dc9-145">FocusStates</span></span>|<span data-ttu-id="a9dc9-146">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-146">The control does not have focus.</span></span>|  
|<span data-ttu-id="a9dc9-147">已选定</span><span class="sxs-lookup"><span data-stu-id="a9dc9-147">Selected</span></span>|<span data-ttu-id="a9dc9-148">SelectionStates</span><span class="sxs-lookup"><span data-stu-id="a9dc9-148">SelectionStates</span></span>|<span data-ttu-id="a9dc9-149">当前选择项。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-149">The item is currently selected.</span></span>|  
|<span data-ttu-id="a9dc9-150">未选定</span><span class="sxs-lookup"><span data-stu-id="a9dc9-150">Unselected</span></span>|<span data-ttu-id="a9dc9-151">SelectionStates</span><span class="sxs-lookup"><span data-stu-id="a9dc9-151">SelectionStates</span></span>|<span data-ttu-id="a9dc9-152">未选定该项。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-152">The item is not selected.</span></span>|  
|<span data-ttu-id="a9dc9-153">SelectedUnfocused</span><span class="sxs-lookup"><span data-stu-id="a9dc9-153">SelectedUnfocused</span></span>|<span data-ttu-id="a9dc9-154">SelectionStates</span><span class="sxs-lookup"><span data-stu-id="a9dc9-154">SelectionStates</span></span>|<span data-ttu-id="a9dc9-155">该项已选定，但没有焦点。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-155">The item is selected, but does not have focus.</span></span>|  
|<span data-ttu-id="a9dc9-156">有效</span><span class="sxs-lookup"><span data-stu-id="a9dc9-156">Valid</span></span>|<span data-ttu-id="a9dc9-157">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a9dc9-157">ValidationStates</span></span>|<span data-ttu-id="a9dc9-158">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-158">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a9dc9-159">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a9dc9-159">InvalidFocused</span></span>|<span data-ttu-id="a9dc9-160">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a9dc9-160">ValidationStates</span></span>|<span data-ttu-id="a9dc9-161"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-161">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="a9dc9-162">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a9dc9-162">InvalidUnfocused</span></span>|<span data-ttu-id="a9dc9-163">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a9dc9-163">ValidationStates</span></span>|<span data-ttu-id="a9dc9-164"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-164">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="listview-controltemplate-examples"></a><span data-ttu-id="a9dc9-165">ListView ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="a9dc9-165">ListView ControlTemplate Examples</span></span>  
 <span data-ttu-id="a9dc9-166">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.ListView>控件和其关联的类型。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-166">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ListView> control and its associated types.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ListView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/listview.xaml#listview)]  
  
 <span data-ttu-id="a9dc9-167"><xref:System.Windows.Controls.ControlTemplate>示例使用一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-167">The <xref:System.Windows.Controls.ControlTemplate> examples use one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a9dc9-168">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](http://go.microsoft.com/fwlink/?LinkID=160041)。</span><span class="sxs-lookup"><span data-stu-id="a9dc9-168">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9dc9-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9dc9-169">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="a9dc9-170">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="a9dc9-170">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="a9dc9-171">控件自定义</span><span class="sxs-lookup"><span data-stu-id="a9dc9-171">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="a9dc9-172">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="a9dc9-172">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="a9dc9-173">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="a9dc9-173">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
