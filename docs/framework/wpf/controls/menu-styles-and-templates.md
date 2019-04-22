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
ms.openlocfilehash: 6818be4ac92dbdd7de0c6c6fa65109e21eadc2f5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59094198"
---
# <a name="menu-styles-and-templates"></a><span data-ttu-id="e9cde-102">Menu 样式和模板</span><span class="sxs-lookup"><span data-stu-id="e9cde-102">Menu Styles and Templates</span></span>
<span data-ttu-id="e9cde-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.Menu>控件。</span><span class="sxs-lookup"><span data-stu-id="e9cde-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Menu> control.</span></span> <span data-ttu-id="e9cde-104">可以修改默认<xref:System.Windows.Controls.ControlTemplate>为控件提供唯一外观。</span><span class="sxs-lookup"><span data-stu-id="e9cde-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="e9cde-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="e9cde-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="menu-parts"></a><span data-ttu-id="e9cde-106">菜单部分</span><span class="sxs-lookup"><span data-stu-id="e9cde-106">Menu Parts</span></span>  
 <span data-ttu-id="e9cde-107"><xref:System.Windows.Controls.Menu>控件没有任何命名的部件。</span><span class="sxs-lookup"><span data-stu-id="e9cde-107">The <xref:System.Windows.Controls.Menu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="e9cde-108">当您创建<xref:System.Windows.Controls.ControlTemplate>有关<xref:System.Windows.Controls.Menu>，模板可能包含<xref:System.Windows.Controls.ItemsPresenter>内<xref:System.Windows.Controls.ScrollViewer>。</span><span class="sxs-lookup"><span data-stu-id="e9cde-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.Menu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="e9cde-109">(<xref:System.Windows.Controls.ItemsPresenter>显示在每个项<xref:System.Windows.Controls.Menu>;<xref:System.Windows.Controls.ScrollViewer>控件内实现滚动)。</span><span class="sxs-lookup"><span data-stu-id="e9cde-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.Menu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="e9cde-110">如果<xref:System.Windows.Controls.ItemsPresenter>不是直接子级<xref:System.Windows.Controls.ScrollViewer>，必须授予<xref:System.Windows.Controls.ItemsPresenter>名称， `ItemsPresenter`。</span><span class="sxs-lookup"><span data-stu-id="e9cde-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menu-states"></a><span data-ttu-id="e9cde-111">菜单状态</span><span class="sxs-lookup"><span data-stu-id="e9cde-111">Menu States</span></span>  
 <span data-ttu-id="e9cde-112">下表列出了的可视状态<xref:System.Windows.Controls.Menu>控件。</span><span class="sxs-lookup"><span data-stu-id="e9cde-112">The following table lists the visual states for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="e9cde-113">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="e9cde-113">VisualState Name</span></span>|<span data-ttu-id="e9cde-114">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="e9cde-114">VisualStateGroup Name</span></span>|<span data-ttu-id="e9cde-115">描述</span><span class="sxs-lookup"><span data-stu-id="e9cde-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e9cde-116">有效</span><span class="sxs-lookup"><span data-stu-id="e9cde-116">Valid</span></span>|<span data-ttu-id="e9cde-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e9cde-117">ValidationStates</span></span>|<span data-ttu-id="e9cde-118">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`false`。</span><span class="sxs-lookup"><span data-stu-id="e9cde-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="e9cde-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="e9cde-119">InvalidFocused</span></span>|<span data-ttu-id="e9cde-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e9cde-120">ValidationStates</span></span>|<span data-ttu-id="e9cde-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="e9cde-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="e9cde-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="e9cde-122">InvalidUnfocused</span></span>|<span data-ttu-id="e9cde-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e9cde-123">ValidationStates</span></span>|<span data-ttu-id="e9cde-124"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="e9cde-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menuitem-parts"></a><span data-ttu-id="e9cde-125">菜单项部分</span><span class="sxs-lookup"><span data-stu-id="e9cde-125">MenuItem Parts</span></span>  
 <span data-ttu-id="e9cde-126">下表列出了用于命名的部件<xref:System.Windows.Controls.Menu>控件。</span><span class="sxs-lookup"><span data-stu-id="e9cde-126">The following table lists the named parts for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="e9cde-127">部件</span><span class="sxs-lookup"><span data-stu-id="e9cde-127">Part</span></span>|<span data-ttu-id="e9cde-128">类型</span><span class="sxs-lookup"><span data-stu-id="e9cde-128">Type</span></span>|<span data-ttu-id="e9cde-129">描述</span><span class="sxs-lookup"><span data-stu-id="e9cde-129">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e9cde-130">PART_Popup</span><span class="sxs-lookup"><span data-stu-id="e9cde-130">PART_Popup</span></span>|<xref:System.Windows.Controls.Primitives.Popup>|<span data-ttu-id="e9cde-131">用于子菜单的区域。</span><span class="sxs-lookup"><span data-stu-id="e9cde-131">The area for the submenu.</span></span>|  
  
 <span data-ttu-id="e9cde-132">当您创建<xref:System.Windows.Controls.ControlTemplate>有关<xref:System.Windows.Controls.MenuItem>，模板可能包含<xref:System.Windows.Controls.ItemsPresenter>内<xref:System.Windows.Controls.ScrollViewer>。</span><span class="sxs-lookup"><span data-stu-id="e9cde-132">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.MenuItem>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="e9cde-133">(<xref:System.Windows.Controls.ItemsPresenter>显示在每个项<xref:System.Windows.Controls.MenuItem>;<xref:System.Windows.Controls.ScrollViewer>控件内实现滚动)。</span><span class="sxs-lookup"><span data-stu-id="e9cde-133">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.MenuItem>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="e9cde-134">如果<xref:System.Windows.Controls.ItemsPresenter>不是直接子级<xref:System.Windows.Controls.ScrollViewer>，必须授予<xref:System.Windows.Controls.ItemsPresenter>名称， `ItemsPresenter`。</span><span class="sxs-lookup"><span data-stu-id="e9cde-134">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menuitem-states"></a><span data-ttu-id="e9cde-135">菜单项状态</span><span class="sxs-lookup"><span data-stu-id="e9cde-135">MenuItem States</span></span>  
 <span data-ttu-id="e9cde-136">下表列出了的可视状态<xref:System.Windows.Controls.MenuItem>控件。</span><span class="sxs-lookup"><span data-stu-id="e9cde-136">The following table lists the visual states for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
|<span data-ttu-id="e9cde-137">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="e9cde-137">VisualState Name</span></span>|<span data-ttu-id="e9cde-138">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="e9cde-138">VisualStateGroup Name</span></span>|<span data-ttu-id="e9cde-139">描述</span><span class="sxs-lookup"><span data-stu-id="e9cde-139">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e9cde-140">有效</span><span class="sxs-lookup"><span data-stu-id="e9cde-140">Valid</span></span>|<span data-ttu-id="e9cde-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e9cde-141">ValidationStates</span></span>|<span data-ttu-id="e9cde-142">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`false`。</span><span class="sxs-lookup"><span data-stu-id="e9cde-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="e9cde-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="e9cde-143">InvalidFocused</span></span>|<span data-ttu-id="e9cde-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e9cde-144">ValidationStates</span></span>|<span data-ttu-id="e9cde-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="e9cde-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="e9cde-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="e9cde-146">InvalidUnfocused</span></span>|<span data-ttu-id="e9cde-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e9cde-147">ValidationStates</span></span>|<span data-ttu-id="e9cde-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="e9cde-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menu-and-menuitem-controltemplate-example"></a><span data-ttu-id="e9cde-149">菜单和菜单项 ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="e9cde-149">Menu and MenuItem ControlTemplate Example</span></span>  
 <span data-ttu-id="e9cde-150">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Menu>控件。</span><span class="sxs-lookup"><span data-stu-id="e9cde-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Menu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menu)]  
  
 <span data-ttu-id="e9cde-151">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.MenuItem>控件。</span><span class="sxs-lookup"><span data-stu-id="e9cde-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuItem](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuitem)]  
  
 <span data-ttu-id="e9cde-152">下面的示例定义`MenuScrollViewer`，会在上一示例中使用。</span><span class="sxs-lookup"><span data-stu-id="e9cde-152">The following example defines the `MenuScrollViewer`, which is used in the previous example.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuscrollviewer)]  
  
 <span data-ttu-id="e9cde-153"><xref:System.Windows.Controls.ControlTemplate>示例使用一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="e9cde-153">The <xref:System.Windows.Controls.ControlTemplate> examples use one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="e9cde-154">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="e9cde-154">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9cde-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9cde-155">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="e9cde-156">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="e9cde-156">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="e9cde-157">控件自定义</span><span class="sxs-lookup"><span data-stu-id="e9cde-157">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="e9cde-158">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="e9cde-158">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="e9cde-159">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="e9cde-159">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
