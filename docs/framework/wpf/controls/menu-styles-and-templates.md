---
title: Menu 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], Menu
- ControlTemplate [WPF], Menu
- Menu [WPF], styles and templates
- states [WPF], Menu
- templates [WPF], Menu
- parts [WPF], Menu
ms.assetid: b89da183-9b87-42c6-ac53-731a42c7b09e
ms.openlocfilehash: b7148f4148f6f141b44899c2c14d0b0028cb6795
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="menu-styles-and-templates"></a><span data-ttu-id="53fb3-102">Menu 样式和模板</span><span class="sxs-lookup"><span data-stu-id="53fb3-102">Menu Styles and Templates</span></span>
<span data-ttu-id="53fb3-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.Menu>控件。</span><span class="sxs-lookup"><span data-stu-id="53fb3-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Menu> control.</span></span> <span data-ttu-id="53fb3-104">你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。</span><span class="sxs-lookup"><span data-stu-id="53fb3-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="53fb3-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="53fb3-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="menu-parts"></a><span data-ttu-id="53fb3-106">菜单部分</span><span class="sxs-lookup"><span data-stu-id="53fb3-106">Menu Parts</span></span>  
 <span data-ttu-id="53fb3-107"><xref:System.Windows.Controls.Menu>控件不具有任何已命名的部件。</span><span class="sxs-lookup"><span data-stu-id="53fb3-107">The <xref:System.Windows.Controls.Menu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="53fb3-108">当你创建<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Menu>，你的模板可能包含<xref:System.Windows.Controls.ItemsPresenter>内<xref:System.Windows.Controls.ScrollViewer>。</span><span class="sxs-lookup"><span data-stu-id="53fb3-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.Menu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="53fb3-109">(<xref:System.Windows.Controls.ItemsPresenter>显示中的每一项<xref:System.Windows.Controls.Menu>;<xref:System.Windows.Controls.ScrollViewer>使控件内滚动)。</span><span class="sxs-lookup"><span data-stu-id="53fb3-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.Menu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="53fb3-110">如果<xref:System.Windows.Controls.ItemsPresenter>不的直接子级<xref:System.Windows.Controls.ScrollViewer>，您必须为指定<xref:System.Windows.Controls.ItemsPresenter>名称， `ItemsPresenter`。</span><span class="sxs-lookup"><span data-stu-id="53fb3-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menu-states"></a><span data-ttu-id="53fb3-111">菜单状态</span><span class="sxs-lookup"><span data-stu-id="53fb3-111">Menu States</span></span>  
 <span data-ttu-id="53fb3-112">下表列出的可视状态<xref:System.Windows.Controls.Menu>控件。</span><span class="sxs-lookup"><span data-stu-id="53fb3-112">The following table lists the visual states for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="53fb3-113">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="53fb3-113">VisualState Name</span></span>|<span data-ttu-id="53fb3-114">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="53fb3-114">VisualStateGroup Name</span></span>|<span data-ttu-id="53fb3-115">描述</span><span class="sxs-lookup"><span data-stu-id="53fb3-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="53fb3-116">有效</span><span class="sxs-lookup"><span data-stu-id="53fb3-116">Valid</span></span>|<span data-ttu-id="53fb3-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="53fb3-117">ValidationStates</span></span>|<span data-ttu-id="53fb3-118">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="53fb3-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="53fb3-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="53fb3-119">InvalidFocused</span></span>|<span data-ttu-id="53fb3-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="53fb3-120">ValidationStates</span></span>|<span data-ttu-id="53fb3-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="53fb3-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="53fb3-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="53fb3-122">InvalidUnfocused</span></span>|<span data-ttu-id="53fb3-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="53fb3-123">ValidationStates</span></span>|<span data-ttu-id="53fb3-124"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="53fb3-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menuitem-parts"></a><span data-ttu-id="53fb3-125">MenuItem 部件</span><span class="sxs-lookup"><span data-stu-id="53fb3-125">MenuItem Parts</span></span>  
 <span data-ttu-id="53fb3-126">下表列出的命名的部件<xref:System.Windows.Controls.Menu>控件。</span><span class="sxs-lookup"><span data-stu-id="53fb3-126">The following table lists the named parts for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="53fb3-127">部件</span><span class="sxs-lookup"><span data-stu-id="53fb3-127">Part</span></span>|<span data-ttu-id="53fb3-128">类型</span><span class="sxs-lookup"><span data-stu-id="53fb3-128">Type</span></span>|<span data-ttu-id="53fb3-129">描述</span><span class="sxs-lookup"><span data-stu-id="53fb3-129">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="53fb3-130">PART_Popup</span><span class="sxs-lookup"><span data-stu-id="53fb3-130">PART_Popup</span></span>|<xref:System.Windows.Controls.Primitives.Popup>|<span data-ttu-id="53fb3-131">子菜单的区域。</span><span class="sxs-lookup"><span data-stu-id="53fb3-131">The area for the submenu.</span></span>|  
  
 <span data-ttu-id="53fb3-132">当你创建<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.MenuItem>，你的模板可能包含<xref:System.Windows.Controls.ItemsPresenter>内<xref:System.Windows.Controls.ScrollViewer>。</span><span class="sxs-lookup"><span data-stu-id="53fb3-132">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.MenuItem>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="53fb3-133">(<xref:System.Windows.Controls.ItemsPresenter>显示中的每一项<xref:System.Windows.Controls.MenuItem>;<xref:System.Windows.Controls.ScrollViewer>使控件内滚动)。</span><span class="sxs-lookup"><span data-stu-id="53fb3-133">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.MenuItem>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="53fb3-134">如果<xref:System.Windows.Controls.ItemsPresenter>不的直接子级<xref:System.Windows.Controls.ScrollViewer>，您必须为指定<xref:System.Windows.Controls.ItemsPresenter>名称， `ItemsPresenter`。</span><span class="sxs-lookup"><span data-stu-id="53fb3-134">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menuitem-states"></a><span data-ttu-id="53fb3-135">MenuItem 状态</span><span class="sxs-lookup"><span data-stu-id="53fb3-135">MenuItem States</span></span>  
 <span data-ttu-id="53fb3-136">下表列出的可视状态<xref:System.Windows.Controls.MenuItem>控件。</span><span class="sxs-lookup"><span data-stu-id="53fb3-136">The following table lists the visual states for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
|<span data-ttu-id="53fb3-137">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="53fb3-137">VisualState Name</span></span>|<span data-ttu-id="53fb3-138">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="53fb3-138">VisualStateGroup Name</span></span>|<span data-ttu-id="53fb3-139">描述</span><span class="sxs-lookup"><span data-stu-id="53fb3-139">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="53fb3-140">有效</span><span class="sxs-lookup"><span data-stu-id="53fb3-140">Valid</span></span>|<span data-ttu-id="53fb3-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="53fb3-141">ValidationStates</span></span>|<span data-ttu-id="53fb3-142">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="53fb3-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="53fb3-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="53fb3-143">InvalidFocused</span></span>|<span data-ttu-id="53fb3-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="53fb3-144">ValidationStates</span></span>|<span data-ttu-id="53fb3-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="53fb3-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="53fb3-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="53fb3-146">InvalidUnfocused</span></span>|<span data-ttu-id="53fb3-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="53fb3-147">ValidationStates</span></span>|<span data-ttu-id="53fb3-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="53fb3-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menu-and-menuitem-controltemplate-example"></a><span data-ttu-id="53fb3-149">菜单和 MenuItem ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="53fb3-149">Menu and MenuItem ControlTemplate Example</span></span>  
 <span data-ttu-id="53fb3-150">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Menu>控件。</span><span class="sxs-lookup"><span data-stu-id="53fb3-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Menu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menu)]  
  
 <span data-ttu-id="53fb3-151">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.MenuItem>控件。</span><span class="sxs-lookup"><span data-stu-id="53fb3-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuItem](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuitem)]  
  
 <span data-ttu-id="53fb3-152">下面的示例定义`MenuScrollViewer`，用于在前面的示例。</span><span class="sxs-lookup"><span data-stu-id="53fb3-152">The following example defines the `MenuScrollViewer`, which is used in the previous example.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuScrollViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuscrollviewer)]  
  
 <span data-ttu-id="53fb3-153"><xref:System.Windows.Controls.ControlTemplate>示例使用一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="53fb3-153">The <xref:System.Windows.Controls.ControlTemplate> examples use one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="53fb3-154">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](http://go.microsoft.com/fwlink/?LinkID=160041)。</span><span class="sxs-lookup"><span data-stu-id="53fb3-154">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53fb3-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="53fb3-155">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="53fb3-156">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="53fb3-156">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="53fb3-157">控件自定义</span><span class="sxs-lookup"><span data-stu-id="53fb3-157">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="53fb3-158">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="53fb3-158">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="53fb3-159">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="53fb3-159">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
