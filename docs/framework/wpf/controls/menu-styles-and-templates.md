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
ms.openlocfilehash: 979ed7292a0f6582753305d1a7704c48aa751003
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460219"
---
# <a name="menu-styles-and-templates"></a><span data-ttu-id="3e520-102">Menu 样式和模板</span><span class="sxs-lookup"><span data-stu-id="3e520-102">Menu Styles and Templates</span></span>
<span data-ttu-id="3e520-103">本主题介绍 <xref:System.Windows.Controls.Menu> 控件的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="3e520-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Menu> control.</span></span> <span data-ttu-id="3e520-104">您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。</span><span class="sxs-lookup"><span data-stu-id="3e520-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="3e520-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="3e520-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="menu-parts"></a><span data-ttu-id="3e520-106">菜单部件</span><span class="sxs-lookup"><span data-stu-id="3e520-106">Menu Parts</span></span>  
 <span data-ttu-id="3e520-107"><xref:System.Windows.Controls.Menu> 控件没有任何命名部分。</span><span class="sxs-lookup"><span data-stu-id="3e520-107">The <xref:System.Windows.Controls.Menu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="3e520-108">为 <xref:System.Windows.Controls.Menu>创建 <xref:System.Windows.Controls.ControlTemplate> 时，模板可能包含 <xref:System.Windows.Controls.ScrollViewer>中的 <xref:System.Windows.Controls.ItemsPresenter>。</span><span class="sxs-lookup"><span data-stu-id="3e520-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.Menu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="3e520-109">（<xref:System.Windows.Controls.ItemsPresenter> 显示 <xref:System.Windows.Controls.Menu>中的每一项; <xref:System.Windows.Controls.ScrollViewer> 允许在控件中滚动）。</span><span class="sxs-lookup"><span data-stu-id="3e520-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.Menu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="3e520-110">如果 <xref:System.Windows.Controls.ItemsPresenter> 不是 <xref:System.Windows.Controls.ScrollViewer>的直接子级，则必须为 <xref:System.Windows.Controls.ItemsPresenter> 指定名称 `ItemsPresenter`。</span><span class="sxs-lookup"><span data-stu-id="3e520-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menu-states"></a><span data-ttu-id="3e520-111">菜单状态</span><span class="sxs-lookup"><span data-stu-id="3e520-111">Menu States</span></span>  
 <span data-ttu-id="3e520-112">下表列出了 <xref:System.Windows.Controls.Menu> 控件的可视状态。</span><span class="sxs-lookup"><span data-stu-id="3e520-112">The following table lists the visual states for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="3e520-113">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="3e520-113">VisualState Name</span></span>|<span data-ttu-id="3e520-114">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="3e520-114">VisualStateGroup Name</span></span>|<span data-ttu-id="3e520-115">描述</span><span class="sxs-lookup"><span data-stu-id="3e520-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="3e520-116">有效</span><span class="sxs-lookup"><span data-stu-id="3e520-116">Valid</span></span>|<span data-ttu-id="3e520-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3e520-117">ValidationStates</span></span>|<span data-ttu-id="3e520-118">控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。</span><span class="sxs-lookup"><span data-stu-id="3e520-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="3e520-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="3e520-119">InvalidFocused</span></span>|<span data-ttu-id="3e520-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3e520-120">ValidationStates</span></span>|<span data-ttu-id="3e520-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。</span><span class="sxs-lookup"><span data-stu-id="3e520-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="3e520-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="3e520-122">InvalidUnfocused</span></span>|<span data-ttu-id="3e520-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3e520-123">ValidationStates</span></span>|<span data-ttu-id="3e520-124"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="3e520-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menuitem-parts"></a><span data-ttu-id="3e520-125">MenuItem 部分</span><span class="sxs-lookup"><span data-stu-id="3e520-125">MenuItem Parts</span></span>  
 <span data-ttu-id="3e520-126">下表列出了 <xref:System.Windows.Controls.Menu> 控件的已命名部分。</span><span class="sxs-lookup"><span data-stu-id="3e520-126">The following table lists the named parts for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="3e520-127">部件</span><span class="sxs-lookup"><span data-stu-id="3e520-127">Part</span></span>|<span data-ttu-id="3e520-128">键入</span><span class="sxs-lookup"><span data-stu-id="3e520-128">Type</span></span>|<span data-ttu-id="3e520-129">描述</span><span class="sxs-lookup"><span data-stu-id="3e520-129">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="3e520-130">PART_Popup</span><span class="sxs-lookup"><span data-stu-id="3e520-130">PART_Popup</span></span>|<xref:System.Windows.Controls.Primitives.Popup>|<span data-ttu-id="3e520-131">子菜单的区域。</span><span class="sxs-lookup"><span data-stu-id="3e520-131">The area for the submenu.</span></span>|  
  
 <span data-ttu-id="3e520-132">为 <xref:System.Windows.Controls.MenuItem>创建 <xref:System.Windows.Controls.ControlTemplate> 时，模板可能包含 <xref:System.Windows.Controls.ScrollViewer>中的 <xref:System.Windows.Controls.ItemsPresenter>。</span><span class="sxs-lookup"><span data-stu-id="3e520-132">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.MenuItem>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="3e520-133">（<xref:System.Windows.Controls.ItemsPresenter> 显示 <xref:System.Windows.Controls.MenuItem>中的每一项; <xref:System.Windows.Controls.ScrollViewer> 允许在控件中滚动）。</span><span class="sxs-lookup"><span data-stu-id="3e520-133">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.MenuItem>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="3e520-134">如果 <xref:System.Windows.Controls.ItemsPresenter> 不是 <xref:System.Windows.Controls.ScrollViewer>的直接子级，则必须为 <xref:System.Windows.Controls.ItemsPresenter> 指定名称 `ItemsPresenter`。</span><span class="sxs-lookup"><span data-stu-id="3e520-134">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menuitem-states"></a><span data-ttu-id="3e520-135">MenuItem 状态</span><span class="sxs-lookup"><span data-stu-id="3e520-135">MenuItem States</span></span>  
 <span data-ttu-id="3e520-136">下表列出了 <xref:System.Windows.Controls.MenuItem> 控件的可视状态。</span><span class="sxs-lookup"><span data-stu-id="3e520-136">The following table lists the visual states for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
|<span data-ttu-id="3e520-137">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="3e520-137">VisualState Name</span></span>|<span data-ttu-id="3e520-138">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="3e520-138">VisualStateGroup Name</span></span>|<span data-ttu-id="3e520-139">描述</span><span class="sxs-lookup"><span data-stu-id="3e520-139">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="3e520-140">有效</span><span class="sxs-lookup"><span data-stu-id="3e520-140">Valid</span></span>|<span data-ttu-id="3e520-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3e520-141">ValidationStates</span></span>|<span data-ttu-id="3e520-142">控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。</span><span class="sxs-lookup"><span data-stu-id="3e520-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="3e520-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="3e520-143">InvalidFocused</span></span>|<span data-ttu-id="3e520-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3e520-144">ValidationStates</span></span>|<span data-ttu-id="3e520-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。</span><span class="sxs-lookup"><span data-stu-id="3e520-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="3e520-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="3e520-146">InvalidUnfocused</span></span>|<span data-ttu-id="3e520-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3e520-147">ValidationStates</span></span>|<span data-ttu-id="3e520-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="3e520-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menu-and-menuitem-controltemplate-example"></a><span data-ttu-id="3e520-149">Menu 和 MenuItem System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="3e520-149">Menu and MenuItem ControlTemplate Example</span></span>  
 <span data-ttu-id="3e520-150">下面的示例演示如何为 <xref:System.Windows.Controls.Menu> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。</span><span class="sxs-lookup"><span data-stu-id="3e520-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Menu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menu)]  
  
 <span data-ttu-id="3e520-151">下面的示例演示如何为 <xref:System.Windows.Controls.MenuItem> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。</span><span class="sxs-lookup"><span data-stu-id="3e520-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuItem](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuitem)]  
  
 <span data-ttu-id="3e520-152">下面的示例定义了在上一个示例中使用的 `MenuScrollViewer`。</span><span class="sxs-lookup"><span data-stu-id="3e520-152">The following example defines the `MenuScrollViewer`, which is used in the previous example.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuscrollviewer)]  
  
 <span data-ttu-id="3e520-153"><xref:System.Windows.Controls.ControlTemplate> 示例使用以下一个或多个资源。</span><span class="sxs-lookup"><span data-stu-id="3e520-153">The <xref:System.Windows.Controls.ControlTemplate> examples use one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="3e520-154">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="3e520-154">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e520-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e520-155">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="3e520-156">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="3e520-156">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="3e520-157">控件自定义</span><span class="sxs-lookup"><span data-stu-id="3e520-157">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="3e520-158">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="3e520-158">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="3e520-159">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="3e520-159">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
