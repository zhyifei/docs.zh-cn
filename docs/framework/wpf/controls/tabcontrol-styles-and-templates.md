---
title: "TabControl 样式和模板"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ControlTemplate [WPF], TabControl
- TabControl [WPF], styles and templates [WPF]
- parts [WPF], TabControl
- styles [WPF], TabControl
- states [WPF], TabControl
- templates [WPF], TabControl
ms.assetid: f6b19a30-f10e-4fa1-96ce-f17a54092ab6
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 054d744c9c15f73ef99f9e9df3a775831b1fe148
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="tabcontrol-styles-and-templates"></a><span data-ttu-id="08b07-102">TabControl 样式和模板</span><span class="sxs-lookup"><span data-stu-id="08b07-102">TabControl Styles and Templates</span></span>
<span data-ttu-id="08b07-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.TabControl>控件。</span><span class="sxs-lookup"><span data-stu-id="08b07-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.TabControl> control.</span></span> <span data-ttu-id="08b07-104">你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。</span><span class="sxs-lookup"><span data-stu-id="08b07-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="08b07-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="08b07-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="tabcontrol-parts"></a><span data-ttu-id="08b07-106">TabControl 部件</span><span class="sxs-lookup"><span data-stu-id="08b07-106">TabControl Parts</span></span>  
 <span data-ttu-id="08b07-107">下表列出的命名的部件<xref:System.Windows.Controls.TabControl>控件。</span><span class="sxs-lookup"><span data-stu-id="08b07-107">The following table lists the named parts for the <xref:System.Windows.Controls.TabControl> control.</span></span>  
  
|<span data-ttu-id="08b07-108">部件</span><span class="sxs-lookup"><span data-stu-id="08b07-108">Part</span></span>|<span data-ttu-id="08b07-109">类型</span><span class="sxs-lookup"><span data-stu-id="08b07-109">Type</span></span>|<span data-ttu-id="08b07-110">描述</span><span class="sxs-lookup"><span data-stu-id="08b07-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="08b07-111">PART_SelectedContentHost</span><span class="sxs-lookup"><span data-stu-id="08b07-111">PART_SelectedContentHost</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="08b07-112">显示当前所选的内容的对象<xref:System.Windows.Controls.TabItem>。</span><span class="sxs-lookup"><span data-stu-id="08b07-112">The object that shows the content of the currently selected <xref:System.Windows.Controls.TabItem>.</span></span>|  
  
 <span data-ttu-id="08b07-113">当你创建<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.TabControl>，你的模板可能包含<xref:System.Windows.Controls.ItemsPresenter>内<xref:System.Windows.Controls.ScrollViewer>。</span><span class="sxs-lookup"><span data-stu-id="08b07-113">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.TabControl>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="08b07-114">(<xref:System.Windows.Controls.ItemsPresenter>显示中的每一项<xref:System.Windows.Controls.TabControl>;<xref:System.Windows.Controls.ScrollViewer>使控件内滚动)。</span><span class="sxs-lookup"><span data-stu-id="08b07-114">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.TabControl>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="08b07-115">如果<xref:System.Windows.Controls.ItemsPresenter>不的直接子级<xref:System.Windows.Controls.ScrollViewer>，您必须为指定<xref:System.Windows.Controls.ItemsPresenter>名称， `ItemsPresenter`。</span><span class="sxs-lookup"><span data-stu-id="08b07-115">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="tabcontrol-states"></a><span data-ttu-id="08b07-116">TabControl 状态</span><span class="sxs-lookup"><span data-stu-id="08b07-116">TabControl States</span></span>  
 <span data-ttu-id="08b07-117">下表列出的可视状态<xref:System.Windows.Controls.TabControl>控件。</span><span class="sxs-lookup"><span data-stu-id="08b07-117">The following table lists the visual states for the <xref:System.Windows.Controls.TabControl> control.</span></span>  
  
|<span data-ttu-id="08b07-118">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="08b07-118">VisualState Name</span></span>|<span data-ttu-id="08b07-119">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="08b07-119">VisualStateGroup Name</span></span>|<span data-ttu-id="08b07-120">描述</span><span class="sxs-lookup"><span data-stu-id="08b07-120">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="08b07-121">普通</span><span class="sxs-lookup"><span data-stu-id="08b07-121">Normal</span></span>|<span data-ttu-id="08b07-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="08b07-122">CommonStates</span></span>|<span data-ttu-id="08b07-123">默认状态。</span><span class="sxs-lookup"><span data-stu-id="08b07-123">The default state.</span></span>|  
|<span data-ttu-id="08b07-124">已禁用</span><span class="sxs-lookup"><span data-stu-id="08b07-124">Disabled</span></span>|<span data-ttu-id="08b07-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="08b07-125">CommonStates</span></span>|<span data-ttu-id="08b07-126">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="08b07-126">The control is disabled.</span></span>|  
|<span data-ttu-id="08b07-127">有效</span><span class="sxs-lookup"><span data-stu-id="08b07-127">Valid</span></span>|<span data-ttu-id="08b07-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="08b07-128">ValidationStates</span></span>|<span data-ttu-id="08b07-129">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="08b07-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="08b07-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="08b07-130">InvalidFocused</span></span>|<span data-ttu-id="08b07-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="08b07-131">ValidationStates</span></span>|<span data-ttu-id="08b07-132"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="08b07-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="08b07-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="08b07-133">InvalidUnfocused</span></span>|<span data-ttu-id="08b07-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="08b07-134">ValidationStates</span></span>|<span data-ttu-id="08b07-135"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="08b07-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="tabitem-parts"></a><span data-ttu-id="08b07-136">TabItem 部件</span><span class="sxs-lookup"><span data-stu-id="08b07-136">TabItem Parts</span></span>  
 <span data-ttu-id="08b07-137"><xref:System.Windows.Controls.TabItem>控件不具有任何已命名的部件。</span><span class="sxs-lookup"><span data-stu-id="08b07-137">The <xref:System.Windows.Controls.TabItem> control does not have any named parts.</span></span>  
  
## <a name="tabitem-states"></a><span data-ttu-id="08b07-138">TabItem 状态</span><span class="sxs-lookup"><span data-stu-id="08b07-138">TabItem States</span></span>  
 <span data-ttu-id="08b07-139">下表列出的可视状态<xref:System.Windows.Controls.TabItem>控件。</span><span class="sxs-lookup"><span data-stu-id="08b07-139">The following table lists the visual states for the <xref:System.Windows.Controls.TabItem> control.</span></span>  
  
|<span data-ttu-id="08b07-140">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="08b07-140">VisualState Name</span></span>|<span data-ttu-id="08b07-141">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="08b07-141">VisualStateGroup Name</span></span>|<span data-ttu-id="08b07-142">描述</span><span class="sxs-lookup"><span data-stu-id="08b07-142">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="08b07-143">普通</span><span class="sxs-lookup"><span data-stu-id="08b07-143">Normal</span></span>|<span data-ttu-id="08b07-144">CommonStates</span><span class="sxs-lookup"><span data-stu-id="08b07-144">CommonStates</span></span>|<span data-ttu-id="08b07-145">默认状态。</span><span class="sxs-lookup"><span data-stu-id="08b07-145">The default state.</span></span>|  
|<span data-ttu-id="08b07-146">MouseOver</span><span class="sxs-lookup"><span data-stu-id="08b07-146">MouseOver</span></span>|<span data-ttu-id="08b07-147">CommonStates</span><span class="sxs-lookup"><span data-stu-id="08b07-147">CommonStates</span></span>|<span data-ttu-id="08b07-148">鼠标指针悬停在控件上。</span><span class="sxs-lookup"><span data-stu-id="08b07-148">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="08b07-149">已禁用</span><span class="sxs-lookup"><span data-stu-id="08b07-149">Disabled</span></span>|<span data-ttu-id="08b07-150">CommonStates</span><span class="sxs-lookup"><span data-stu-id="08b07-150">CommonStates</span></span>|<span data-ttu-id="08b07-151">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="08b07-151">The control is disabled.</span></span>|  
|<span data-ttu-id="08b07-152">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="08b07-152">Focused</span></span>|<span data-ttu-id="08b07-153">FocusStates</span><span class="sxs-lookup"><span data-stu-id="08b07-153">FocusStates</span></span>|<span data-ttu-id="08b07-154">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="08b07-154">The control has focus.</span></span>|  
|<span data-ttu-id="08b07-155">失去焦点</span><span class="sxs-lookup"><span data-stu-id="08b07-155">Unfocused</span></span>|<span data-ttu-id="08b07-156">FocusStates</span><span class="sxs-lookup"><span data-stu-id="08b07-156">FocusStates</span></span>|<span data-ttu-id="08b07-157">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="08b07-157">The control does not have focus.</span></span>|  
|<span data-ttu-id="08b07-158">已选定</span><span class="sxs-lookup"><span data-stu-id="08b07-158">Selected</span></span>|<span data-ttu-id="08b07-159">SelectionStates</span><span class="sxs-lookup"><span data-stu-id="08b07-159">SelectionStates</span></span>|<span data-ttu-id="08b07-160">控件被选定。</span><span class="sxs-lookup"><span data-stu-id="08b07-160">The control is selected.</span></span>|  
|<span data-ttu-id="08b07-161">未选定</span><span class="sxs-lookup"><span data-stu-id="08b07-161">Unselected</span></span>|<span data-ttu-id="08b07-162">SelectionStates</span><span class="sxs-lookup"><span data-stu-id="08b07-162">SelectionStates</span></span>|<span data-ttu-id="08b07-163">不选中控件。</span><span class="sxs-lookup"><span data-stu-id="08b07-163">The control is not selected.</span></span>|  
|<span data-ttu-id="08b07-164">有效</span><span class="sxs-lookup"><span data-stu-id="08b07-164">Valid</span></span>|<span data-ttu-id="08b07-165">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="08b07-165">ValidationStates</span></span>|<span data-ttu-id="08b07-166">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="08b07-166">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="08b07-167">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="08b07-167">InvalidFocused</span></span>|<span data-ttu-id="08b07-168">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="08b07-168">ValidationStates</span></span>|<span data-ttu-id="08b07-169"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="08b07-169">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="08b07-170">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="08b07-170">InvalidUnfocused</span></span>|<span data-ttu-id="08b07-171">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="08b07-171">ValidationStates</span></span>|<span data-ttu-id="08b07-172"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="08b07-172">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="tabcontrol-controltemplate-example"></a><span data-ttu-id="08b07-173">TabControl ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="08b07-173">TabControl ControlTemplate Example</span></span>  
 <span data-ttu-id="08b07-174">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.TabControl>和<xref:System.Windows.Controls.TabItem>控件。</span><span class="sxs-lookup"><span data-stu-id="08b07-174">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TabControl> and <xref:System.Windows.Controls.TabItem> controls.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TabControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tabcontrol.xaml#tabcontrol)]  
  
 <span data-ttu-id="08b07-175">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="08b07-175">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="08b07-176">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](http://go.microsoft.com/fwlink/?LinkID=160041)。</span><span class="sxs-lookup"><span data-stu-id="08b07-176">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08b07-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08b07-177">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="08b07-178">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="08b07-178">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="08b07-179">控件自定义</span><span class="sxs-lookup"><span data-stu-id="08b07-179">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="08b07-180">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="08b07-180">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="08b07-181">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="08b07-181">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
