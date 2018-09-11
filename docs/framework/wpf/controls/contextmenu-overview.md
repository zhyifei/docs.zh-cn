---
title: ContextMenu 概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ContextMenu
- ContextMenu controls [WPF], about ContextMenu controls
ms.assetid: 16909c42-799a-4561-91e0-7d69dcfeea91
ms.openlocfilehash: 54fd823594fba4500f35ed1d69720a3309e54a36
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44277281"
---
# <a name="contextmenu-overview"></a><span data-ttu-id="1c919-102">ContextMenu 概述</span><span class="sxs-lookup"><span data-stu-id="1c919-102">ContextMenu Overview</span></span>
<span data-ttu-id="1c919-103"><xref:System.Windows.Controls.ContextMenu>类表示使用特定于上下文的公开功能的元素<xref:System.Windows.Controls.Menu>。</span><span class="sxs-lookup"><span data-stu-id="1c919-103">The <xref:System.Windows.Controls.ContextMenu> class represents the element that exposes functionality by using a context-specific <xref:System.Windows.Controls.Menu>.</span></span> <span data-ttu-id="1c919-104">通常情况下，用户公开<xref:System.Windows.Controls.ContextMenu>在[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]通过右键单击鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="1c919-104">Typically, a user exposes the <xref:System.Windows.Controls.ContextMenu> in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] by right-clicking the mouse button.</span></span> <span data-ttu-id="1c919-105">本主题介绍<xref:System.Windows.Controls.ContextMenu>元素，并提供有关如何使用中的示例[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]和代码。</span><span class="sxs-lookup"><span data-stu-id="1c919-105">This topic introduces the <xref:System.Windows.Controls.ContextMenu> element and provides examples of how to use it in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] and code.</span></span>  
  
  
  
<a name="contextmenu_control"></a>   
## <a name="contextmenu-control"></a><span data-ttu-id="1c919-106">ContextMenu 控件</span><span class="sxs-lookup"><span data-stu-id="1c919-106">ContextMenu Control</span></span>  
 <span data-ttu-id="1c919-107">一个<xref:System.Windows.Controls.ContextMenu>附加到特定控件。</span><span class="sxs-lookup"><span data-stu-id="1c919-107">A <xref:System.Windows.Controls.ContextMenu> is attached to a specific control.</span></span> <span data-ttu-id="1c919-108"><xref:System.Windows.Controls.ContextMenu>元素使您能够为用户提供的项的指定命令或关联的选项与特定控件，例如，列表<xref:System.Windows.Controls.Button>。</span><span class="sxs-lookup"><span data-stu-id="1c919-108">The <xref:System.Windows.Controls.ContextMenu> element enables you to present users with a list of items that specify commands or options that are associated with a particular control, for example, a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="1c919-109">用户通过右键单击控件来显示菜单。</span><span class="sxs-lookup"><span data-stu-id="1c919-109">Users right-click the control to make the menu appear.</span></span> <span data-ttu-id="1c919-110">通常情况下，单击<xref:System.Windows.Controls.MenuItem>打开子菜单或导致应用程序执行某个命令。</span><span class="sxs-lookup"><span data-stu-id="1c919-110">Typically, clicking a <xref:System.Windows.Controls.MenuItem> opens a submenu or causes an application to carry out a command.</span></span>  
  
<a name="creating_contextmenus"></a>   
## <a name="creating-contextmenus"></a><span data-ttu-id="1c919-111">创建 ContextMenus</span><span class="sxs-lookup"><span data-stu-id="1c919-111">Creating ContextMenus</span></span>  
 <span data-ttu-id="1c919-112">以下示例演示如何创建<xref:System.Windows.Controls.ContextMenu>具有子菜单。</span><span class="sxs-lookup"><span data-stu-id="1c919-112">The following examples show how to create a <xref:System.Windows.Controls.ContextMenu> with submenus.</span></span> <span data-ttu-id="1c919-113"><xref:System.Windows.Controls.ContextMenu>控件附加到按钮控件。</span><span class="sxs-lookup"><span data-stu-id="1c919-113">The <xref:System.Windows.Controls.ContextMenu> controls are attached to button controls.</span></span>  
  
 [!code-xaml[ContextMenu#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>   
## <a name="applying-styles-to-a-contextmenu"></a><span data-ttu-id="1c919-114">将样式应用于 ContextMenu</span><span class="sxs-lookup"><span data-stu-id="1c919-114">Applying Styles to a ContextMenu</span></span>  
 <span data-ttu-id="1c919-115">通过使用控件<xref:System.Windows.Style>，可以显著改变外观和行为<xref:System.Windows.Controls.ContextMenu>而无需编写自定义控件。</span><span class="sxs-lookup"><span data-stu-id="1c919-115">By using a control <xref:System.Windows.Style>, you can dramatically change the appearance and behavior of a <xref:System.Windows.Controls.ContextMenu> without writing a custom control.</span></span> <span data-ttu-id="1c919-116">除了设置可视化属性以外，还可以将样式应用于控件的各个部分。</span><span class="sxs-lookup"><span data-stu-id="1c919-116">In addition to setting visual properties, you can also apply styles to parts of a control.</span></span> <span data-ttu-id="1c919-117">例如，可以使用属性，来更改控件的部件的行为或可添加其他部分，或更改其布局<xref:System.Windows.Controls.ContextMenu>。</span><span class="sxs-lookup"><span data-stu-id="1c919-117">For example, you can change the behavior of parts of the control by using properties, or you can add parts to, or change the layout of, a <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="1c919-118">下面的示例演示几种方法添加到样式<xref:System.Windows.Controls.ContextMenu>控件。</span><span class="sxs-lookup"><span data-stu-id="1c919-118">The following examples show several ways to add styles to <xref:System.Windows.Controls.ContextMenu> controls.</span></span>  
  
 <span data-ttu-id="1c919-119">第一个示例定义一个名为 `SimpleSysResources` 的样式，它演示如何在样式中使用当前的系统设置。</span><span class="sxs-lookup"><span data-stu-id="1c919-119">The first example defines a style called `SimpleSysResources`, which shows how to use the current system settings in your style.</span></span> <span data-ttu-id="1c919-120">该示例将分配<xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A>作为<xref:System.Windows.Controls.Control.Background%2A>颜色和<xref:System.Windows.SystemColors.MenuTextBrushKey%2A>作为<xref:System.Windows.Controls.Control.Foreground%2A>的颜色<xref:System.Windows.Controls.ContextMenu>。</span><span class="sxs-lookup"><span data-stu-id="1c919-120">The example assigns <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> as the <xref:System.Windows.Controls.Control.Background%2A> color and <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> as the <xref:System.Windows.Controls.Control.Foreground%2A> color of the <xref:System.Windows.Controls.ContextMenu>.</span></span>  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=   
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=   
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 <span data-ttu-id="1c919-121">下面的示例使用<xref:System.Windows.Trigger>要更改的外观元素<xref:System.Windows.Controls.Menu>响应，则将引发的事件<xref:System.Windows.Controls.ContextMenu>。</span><span class="sxs-lookup"><span data-stu-id="1c919-121">The following example uses the <xref:System.Windows.Trigger> element to change the appearance of a <xref:System.Windows.Controls.Menu> in response to events that are raised on the <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="1c919-122">当用户将鼠标移到菜单的外观<xref:System.Windows.Controls.ContextMenu>项更改。</span><span class="sxs-lookup"><span data-stu-id="1c919-122">When a user moves the mouse over the menu, the appearance of the <xref:System.Windows.Controls.ContextMenu> items changes.</span></span>  
  
```xaml  
<Style x:Key="Triggers" TargetType="{x:Type MenuItem}">  
  <Style.Triggers>  
    <Trigger Property="MenuItem.IsMouseOver" Value="true">  
      <Setter Property = "FontSize" Value="16"/>  
      <Setter Property = "FontStyle" Value="Italic"/>  
      <Setter Property = "Foreground" Value="Red"/>  
    </Trigger>  
  </Style.Triggers>  
</Style>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1c919-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c919-123">See Also</span></span>  
 <xref:System.Windows.Controls.ContextMenu>  
 <xref:System.Windows.Style>  
 <xref:System.Windows.Controls.Menu>  
 <xref:System.Windows.Controls.MenuItem>  
 [<span data-ttu-id="1c919-124">ContextMenu</span><span class="sxs-lookup"><span data-stu-id="1c919-124">ContextMenu</span></span>](../../../../docs/framework/wpf/controls/contextmenu.md)  
 [<span data-ttu-id="1c919-125">ContextMenu 样式和模板</span><span class="sxs-lookup"><span data-stu-id="1c919-125">ContextMenu Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/contextmenu-styles-and-templates.md)  
 [<span data-ttu-id="1c919-126">WPF 控件库示例</span><span class="sxs-lookup"><span data-stu-id="1c919-126">WPF Controls Gallery Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160053)
