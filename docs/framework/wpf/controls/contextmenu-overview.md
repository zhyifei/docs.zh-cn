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
ms.openlocfilehash: 4d2d8db0f614b5240705146dbe91432b96b46dd6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185915"
---
# <a name="contextmenu-overview"></a><span data-ttu-id="a254a-102">ContextMenu 概述</span><span class="sxs-lookup"><span data-stu-id="a254a-102">ContextMenu Overview</span></span>
<span data-ttu-id="a254a-103">类<xref:System.Windows.Controls.ContextMenu>表示使用特定于<xref:System.Windows.Controls.Menu>上下文的 公开功能的元素。</span><span class="sxs-lookup"><span data-stu-id="a254a-103">The <xref:System.Windows.Controls.ContextMenu> class represents the element that exposes functionality by using a context-specific <xref:System.Windows.Controls.Menu>.</span></span> <span data-ttu-id="a254a-104">通常，用户[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]通过右键单击<xref:System.Windows.Controls.ContextMenu>鼠标按钮来公开 中的。</span><span class="sxs-lookup"><span data-stu-id="a254a-104">Typically, a user exposes the <xref:System.Windows.Controls.ContextMenu> in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] by right-clicking the mouse button.</span></span> <span data-ttu-id="a254a-105">本主题介绍该<xref:System.Windows.Controls.ContextMenu>元素，并提供如何在 和 代码中使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]该元素的示例。</span><span class="sxs-lookup"><span data-stu-id="a254a-105">This topic introduces the <xref:System.Windows.Controls.ContextMenu> element and provides examples of how to use it in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] and code.</span></span>  

<a name="contextmenu_control"></a>
## <a name="contextmenu-control"></a><span data-ttu-id="a254a-106">ContextMenu 控件</span><span class="sxs-lookup"><span data-stu-id="a254a-106">ContextMenu Control</span></span>  
 <span data-ttu-id="a254a-107">附加到<xref:System.Windows.Controls.ContextMenu>特定控件。</span><span class="sxs-lookup"><span data-stu-id="a254a-107">A <xref:System.Windows.Controls.ContextMenu> is attached to a specific control.</span></span> <span data-ttu-id="a254a-108">该<xref:System.Windows.Controls.ContextMenu>元素使您能够向用户显示指定与特定控件关联的命令或选项的项列表，例如<xref:System.Windows.Controls.Button>。</span><span class="sxs-lookup"><span data-stu-id="a254a-108">The <xref:System.Windows.Controls.ContextMenu> element enables you to present users with a list of items that specify commands or options that are associated with a particular control, for example, a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="a254a-109">用户通过右键单击控件来显示菜单。</span><span class="sxs-lookup"><span data-stu-id="a254a-109">Users right-click the control to make the menu appear.</span></span> <span data-ttu-id="a254a-110">通常，单击<xref:System.Windows.Controls.MenuItem>将打开子菜单或导致应用程序执行命令。</span><span class="sxs-lookup"><span data-stu-id="a254a-110">Typically, clicking a <xref:System.Windows.Controls.MenuItem> opens a submenu or causes an application to carry out a command.</span></span>  
  
<a name="creating_contextmenus"></a>
## <a name="creating-contextmenus"></a><span data-ttu-id="a254a-111">创建 ContextMenus</span><span class="sxs-lookup"><span data-stu-id="a254a-111">Creating ContextMenus</span></span>  
 <span data-ttu-id="a254a-112">以下示例演示如何使用子菜单创建<xref:System.Windows.Controls.ContextMenu>。</span><span class="sxs-lookup"><span data-stu-id="a254a-112">The following examples show how to create a <xref:System.Windows.Controls.ContextMenu> with submenus.</span></span> <span data-ttu-id="a254a-113">控件<xref:System.Windows.Controls.ContextMenu>附加到按钮控件。</span><span class="sxs-lookup"><span data-stu-id="a254a-113">The <xref:System.Windows.Controls.ContextMenu> controls are attached to button controls.</span></span>  
  
 [!code-xaml[ContextMenu#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>
## <a name="applying-styles-to-a-contextmenu"></a><span data-ttu-id="a254a-114">将样式应用于 ContextMenu</span><span class="sxs-lookup"><span data-stu-id="a254a-114">Applying Styles to a ContextMenu</span></span>  
 <span data-ttu-id="a254a-115">通过使用 控件<xref:System.Windows.Style>，可以显著更改 的外观<xref:System.Windows.Controls.ContextMenu>和行为，而无需编写自定义控件。</span><span class="sxs-lookup"><span data-stu-id="a254a-115">By using a control <xref:System.Windows.Style>, you can dramatically change the appearance and behavior of a <xref:System.Windows.Controls.ContextMenu> without writing a custom control.</span></span> <span data-ttu-id="a254a-116">除了设置可视化属性以外，还可以将样式应用于控件的各个部分。</span><span class="sxs-lookup"><span data-stu-id="a254a-116">In addition to setting visual properties, you can also apply styles to parts of a control.</span></span> <span data-ttu-id="a254a-117">例如，可以使用 属性更改控件的各个部分的行为，也可以向 或 更改<xref:System.Windows.Controls.ContextMenu>的布局添加部件。</span><span class="sxs-lookup"><span data-stu-id="a254a-117">For example, you can change the behavior of parts of the control by using properties, or you can add parts to, or change the layout of, a <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="a254a-118">以下示例显示了向<xref:System.Windows.Controls.ContextMenu>控件添加样式的几种方法。</span><span class="sxs-lookup"><span data-stu-id="a254a-118">The following examples show several ways to add styles to <xref:System.Windows.Controls.ContextMenu> controls.</span></span>  
  
 <span data-ttu-id="a254a-119">第一个示例定义一个名为 `SimpleSysResources` 的样式，它演示如何在样式中使用当前的系统设置。</span><span class="sxs-lookup"><span data-stu-id="a254a-119">The first example defines a style called `SimpleSysResources`, which shows how to use the current system settings in your style.</span></span> <span data-ttu-id="a254a-120">该示例将指定<xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A>为<xref:System.Windows.Controls.Control.Background%2A>颜色和<xref:System.Windows.SystemColors.MenuTextBrushKey%2A><xref:System.Windows.Controls.Control.Foreground%2A>颜色<xref:System.Windows.Controls.ContextMenu>。</span><span class="sxs-lookup"><span data-stu-id="a254a-120">The example assigns <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> as the <xref:System.Windows.Controls.Control.Background%2A> color and <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> as the <xref:System.Windows.Controls.Control.Foreground%2A> color of the <xref:System.Windows.Controls.ContextMenu>.</span></span>  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 <span data-ttu-id="a254a-121">下面的示例使用 元素<xref:System.Windows.Trigger>更改 的外观<xref:System.Windows.Controls.Menu>，以响应在 上引发的事件<xref:System.Windows.Controls.ContextMenu>。</span><span class="sxs-lookup"><span data-stu-id="a254a-121">The following example uses the <xref:System.Windows.Trigger> element to change the appearance of a <xref:System.Windows.Controls.Menu> in response to events that are raised on the <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="a254a-122">当用户将鼠标移到菜单上时，<xref:System.Windows.Controls.ContextMenu>项目的外观会发生变化。</span><span class="sxs-lookup"><span data-stu-id="a254a-122">When a user moves the mouse over the menu, the appearance of the <xref:System.Windows.Controls.ContextMenu> items changes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a254a-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a254a-123">See also</span></span>

- <xref:System.Windows.Controls.ContextMenu>
- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.Menu>
- <xref:System.Windows.Controls.MenuItem>
- [<span data-ttu-id="a254a-124">ContextMenu</span><span class="sxs-lookup"><span data-stu-id="a254a-124">ContextMenu</span></span>](contextmenu.md)
- [<span data-ttu-id="a254a-125">ContextMenu 样式和模板</span><span class="sxs-lookup"><span data-stu-id="a254a-125">ContextMenu Styles and Templates</span></span>](contextmenu-styles-and-templates.md)
- [<span data-ttu-id="a254a-126">WPF 控件库示例</span><span class="sxs-lookup"><span data-stu-id="a254a-126">WPF Controls Gallery Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
