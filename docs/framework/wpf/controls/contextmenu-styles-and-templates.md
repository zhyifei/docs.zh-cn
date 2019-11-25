---
title: ContextMenu 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], ContextMenu
- parts [WPF], ContextMenu
- ContextMenu [WPF], styles and templates
- styles [WPF], ContextMenu
- ControlTemplate [WPF], ContextMenu
- states [WPF], ContextMenu
ms.assetid: 342d1f17-c406-4f94-8f55-867c5f3ea511
ms.openlocfilehash: fa192e20ea84e96c9f85ff84e16c63b7f56c8a98
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283543"
---
# <a name="contextmenu-styles-and-templates"></a><span data-ttu-id="545b1-102">ContextMenu 样式和模板</span><span class="sxs-lookup"><span data-stu-id="545b1-102">ContextMenu Styles and Templates</span></span>
<span data-ttu-id="545b1-103">本主题介绍 <xref:System.Windows.Controls.ContextMenu> 控件的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="545b1-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ContextMenu> control.</span></span> <span data-ttu-id="545b1-104">您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。</span><span class="sxs-lookup"><span data-stu-id="545b1-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="545b1-105">有关详细信息，请参阅为[控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)。</span><span class="sxs-lookup"><span data-stu-id="545b1-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="contextmenu-parts"></a><span data-ttu-id="545b1-106">ContextMenu 部件</span><span class="sxs-lookup"><span data-stu-id="545b1-106">ContextMenu Parts</span></span>  
 <span data-ttu-id="545b1-107"><xref:System.Windows.Controls.ContextMenu> 控件没有任何命名部分。</span><span class="sxs-lookup"><span data-stu-id="545b1-107">The <xref:System.Windows.Controls.ContextMenu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="545b1-108">为 <xref:System.Windows.Controls.ContextMenu>创建 <xref:System.Windows.Controls.ControlTemplate> 时，模板可能包含 <xref:System.Windows.Controls.ScrollViewer>中的 <xref:System.Windows.Controls.ItemsPresenter>。</span><span class="sxs-lookup"><span data-stu-id="545b1-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ContextMenu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="545b1-109">（<xref:System.Windows.Controls.ItemsPresenter> 显示 <xref:System.Windows.Controls.ContextMenu>中的每一项; <xref:System.Windows.Controls.ScrollViewer> 允许在控件中滚动）。</span><span class="sxs-lookup"><span data-stu-id="545b1-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ContextMenu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="545b1-110">如果 <xref:System.Windows.Controls.ItemsPresenter> 不是 <xref:System.Windows.Controls.ScrollViewer>的直接子级，则必须为 <xref:System.Windows.Controls.ItemsPresenter> 指定名称 `ItemsPresenter`。</span><span class="sxs-lookup"><span data-stu-id="545b1-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="contextmenu-states"></a><span data-ttu-id="545b1-111">ContextMenu 状态</span><span class="sxs-lookup"><span data-stu-id="545b1-111">ContextMenu States</span></span>  
 <span data-ttu-id="545b1-112">下表列出了 <xref:System.Windows.Controls.ContextMenu> 控件的可视状态。</span><span class="sxs-lookup"><span data-stu-id="545b1-112">The following table lists the visual states for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
|<span data-ttu-id="545b1-113">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="545b1-113">VisualState Name</span></span>|<span data-ttu-id="545b1-114">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="545b1-114">VisualStateGroup Name</span></span>|<span data-ttu-id="545b1-115">描述</span><span class="sxs-lookup"><span data-stu-id="545b1-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="545b1-116">有效</span><span class="sxs-lookup"><span data-stu-id="545b1-116">Valid</span></span>|<span data-ttu-id="545b1-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="545b1-117">ValidationStates</span></span>|<span data-ttu-id="545b1-118">控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。</span><span class="sxs-lookup"><span data-stu-id="545b1-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="545b1-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="545b1-119">InvalidFocused</span></span>|<span data-ttu-id="545b1-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="545b1-120">ValidationStates</span></span>|<span data-ttu-id="545b1-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。</span><span class="sxs-lookup"><span data-stu-id="545b1-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="545b1-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="545b1-122">InvalidUnfocused</span></span>|<span data-ttu-id="545b1-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="545b1-123">ValidationStates</span></span>|<span data-ttu-id="545b1-124"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="545b1-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="contextmenu-controltemplate-example"></a><span data-ttu-id="545b1-125">ContextMenu System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="545b1-125">ContextMenu ControlTemplate Example</span></span>  
 <span data-ttu-id="545b1-126">下面的示例演示如何为 <xref:System.Windows.Controls.ContextMenu> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。</span><span class="sxs-lookup"><span data-stu-id="545b1-126">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <span data-ttu-id="545b1-127"><xref:System.Windows.Controls.ControlTemplate> 使用以下资源。</span><span class="sxs-lookup"><span data-stu-id="545b1-127">The <xref:System.Windows.Controls.ControlTemplate> uses the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="545b1-128">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="545b1-128">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="545b1-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="545b1-129">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="545b1-130">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="545b1-130">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="545b1-131">控件自定义</span><span class="sxs-lookup"><span data-stu-id="545b1-131">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="545b1-132">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="545b1-132">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="545b1-133">为控件创建模板</span><span class="sxs-lookup"><span data-stu-id="545b1-133">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
