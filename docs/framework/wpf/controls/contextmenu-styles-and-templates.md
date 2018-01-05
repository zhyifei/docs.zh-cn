---
title: "ContextMenu 样式和模板"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- templates [WPF], ContextMenu
- parts [WPF], ContextMenu
- ContextMenu [WPF], styles and templates
- styles [WPF], ContextMenu
- ControlTemplate [WPF], ContextMenu
- states [WPF], ContextMenu
ms.assetid: 342d1f17-c406-4f94-8f55-867c5f3ea511
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fbe7bdc39ed8b7cf342e7e3d2d3c9a3824a8b819
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="contextmenu-styles-and-templates"></a><span data-ttu-id="6bffc-102">ContextMenu 样式和模板</span><span class="sxs-lookup"><span data-stu-id="6bffc-102">ContextMenu Styles and Templates</span></span>
<span data-ttu-id="6bffc-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.ContextMenu>控件。</span><span class="sxs-lookup"><span data-stu-id="6bffc-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ContextMenu> control.</span></span> <span data-ttu-id="6bffc-104">你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。</span><span class="sxs-lookup"><span data-stu-id="6bffc-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="6bffc-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="6bffc-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="contextmenu-parts"></a><span data-ttu-id="6bffc-106">ContextMenu 部件</span><span class="sxs-lookup"><span data-stu-id="6bffc-106">ContextMenu Parts</span></span>  
 <span data-ttu-id="6bffc-107"><xref:System.Windows.Controls.ContextMenu>控件不具有任何已命名的部件。</span><span class="sxs-lookup"><span data-stu-id="6bffc-107">The <xref:System.Windows.Controls.ContextMenu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="6bffc-108">当你创建<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.ContextMenu>，你的模板可能包含<xref:System.Windows.Controls.ItemsPresenter>内<xref:System.Windows.Controls.ScrollViewer>。</span><span class="sxs-lookup"><span data-stu-id="6bffc-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ContextMenu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="6bffc-109">(<xref:System.Windows.Controls.ItemsPresenter>显示中的每一项<xref:System.Windows.Controls.ContextMenu>;<xref:System.Windows.Controls.ScrollViewer>使控件内滚动)。</span><span class="sxs-lookup"><span data-stu-id="6bffc-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ContextMenu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="6bffc-110">如果<xref:System.Windows.Controls.ItemsPresenter>不的直接子级<xref:System.Windows.Controls.ScrollViewer>，您必须为指定<xref:System.Windows.Controls.ItemsPresenter>名称， `ItemsPresenter`。</span><span class="sxs-lookup"><span data-stu-id="6bffc-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="contextmenu-states"></a><span data-ttu-id="6bffc-111">ContextMenu 状态</span><span class="sxs-lookup"><span data-stu-id="6bffc-111">ContextMenu States</span></span>  
 <span data-ttu-id="6bffc-112">下表列出的可视状态<xref:System.Windows.Controls.ContextMenu>控件。</span><span class="sxs-lookup"><span data-stu-id="6bffc-112">The following table lists the visual states for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
|<span data-ttu-id="6bffc-113">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="6bffc-113">VisualState Name</span></span>|<span data-ttu-id="6bffc-114">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="6bffc-114">VisualStateGroup Name</span></span>|<span data-ttu-id="6bffc-115">描述</span><span class="sxs-lookup"><span data-stu-id="6bffc-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="6bffc-116">有效</span><span class="sxs-lookup"><span data-stu-id="6bffc-116">Valid</span></span>|<span data-ttu-id="6bffc-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6bffc-117">ValidationStates</span></span>|<span data-ttu-id="6bffc-118">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="6bffc-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="6bffc-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="6bffc-119">InvalidFocused</span></span>|<span data-ttu-id="6bffc-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6bffc-120">ValidationStates</span></span>|<span data-ttu-id="6bffc-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="6bffc-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="6bffc-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="6bffc-122">InvalidUnfocused</span></span>|<span data-ttu-id="6bffc-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6bffc-123">ValidationStates</span></span>|<span data-ttu-id="6bffc-124"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="6bffc-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="contextmenu-controltemplate-example"></a><span data-ttu-id="6bffc-125">ContextMenu ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="6bffc-125">ContextMenu ControlTemplate Example</span></span>  
 <span data-ttu-id="6bffc-126">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.ContextMenu>控件。</span><span class="sxs-lookup"><span data-stu-id="6bffc-126">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <span data-ttu-id="6bffc-127"><xref:System.Windows.Controls.ControlTemplate>使用以下资源。</span><span class="sxs-lookup"><span data-stu-id="6bffc-127">The <xref:System.Windows.Controls.ControlTemplate> uses the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="6bffc-128">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](http://go.microsoft.com/fwlink/?LinkID=160041)。</span><span class="sxs-lookup"><span data-stu-id="6bffc-128">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bffc-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="6bffc-129">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="6bffc-130">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="6bffc-130">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="6bffc-131">控件自定义</span><span class="sxs-lookup"><span data-stu-id="6bffc-131">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="6bffc-132">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="6bffc-132">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="6bffc-133">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="6bffc-133">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
