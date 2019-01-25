---
title: 菜单概述
ms.date: 03/30/2017
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
ms.openlocfilehash: b1f3889803ba681542349443276041d312293bcf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626870"
---
# <a name="menu-overview"></a><span data-ttu-id="1b04d-102">菜单概述</span><span class="sxs-lookup"><span data-stu-id="1b04d-102">Menu Overview</span></span>
<span data-ttu-id="1b04d-103"><xref:System.Windows.Controls.Menu>类可用于组织与命令和事件处理程序的层次结构顺序关联的元素。</span><span class="sxs-lookup"><span data-stu-id="1b04d-103">The <xref:System.Windows.Controls.Menu> class enables you to organize elements associated with commands and event handlers in a hierarchical order.</span></span> <span data-ttu-id="1b04d-104">每个<xref:System.Windows.Controls.Menu>元素包含一系列<xref:System.Windows.Controls.MenuItem>元素。</span><span class="sxs-lookup"><span data-stu-id="1b04d-104">Each <xref:System.Windows.Controls.Menu> element contains a collection of <xref:System.Windows.Controls.MenuItem> elements.</span></span>  
  
  
<a name="menu_control"></a>   
## <a name="menu-control"></a><span data-ttu-id="1b04d-105">Menu 控件</span><span class="sxs-lookup"><span data-stu-id="1b04d-105">Menu Control</span></span>  
 <span data-ttu-id="1b04d-106"><xref:System.Windows.Controls.Menu>控件显示的项的指定命令或应用程序的选项列表。</span><span class="sxs-lookup"><span data-stu-id="1b04d-106">The <xref:System.Windows.Controls.Menu> control presents a list of items that specify commands or options for an application.</span></span> <span data-ttu-id="1b04d-107">通常情况下，单击<xref:System.Windows.Controls.MenuItem>打开子菜单或导致应用程序执行某个命令。</span><span class="sxs-lookup"><span data-stu-id="1b04d-107">Typically, clicking a <xref:System.Windows.Controls.MenuItem> opens a submenu or causes an application to carry out a command.</span></span>  
  
<a name="creating_menus"></a>   
## <a name="creating-menus"></a><span data-ttu-id="1b04d-108">创建菜单</span><span class="sxs-lookup"><span data-stu-id="1b04d-108">Creating Menus</span></span>  
 <span data-ttu-id="1b04d-109">下面的示例创建<xref:System.Windows.Controls.Menu>操作中的文本<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="1b04d-109">The following example creates a <xref:System.Windows.Controls.Menu> to manipulate text in a <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="1b04d-110"><xref:System.Windows.Controls.Menu>包含<xref:System.Windows.Controls.MenuItem>对象使用<xref:System.Windows.Controls.MenuItem.Command%2A>， <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>，并<xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>属性和<xref:System.Windows.Controls.MenuItem.Checked>， <xref:System.Windows.Controls.MenuItem.Unchecked>，和<xref:System.Windows.Controls.MenuItem.Click>事件。</span><span class="sxs-lookup"><span data-stu-id="1b04d-110">The <xref:System.Windows.Controls.Menu> contains <xref:System.Windows.Controls.MenuItem> objects that use the <xref:System.Windows.Controls.MenuItem.Command%2A>, <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>, and <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> properties and the <xref:System.Windows.Controls.MenuItem.Checked>, <xref:System.Windows.Controls.MenuItem.Unchecked>, and <xref:System.Windows.Controls.MenuItem.Click> events.</span></span>  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>   
## <a name="menuitems-with-keyboard-shortcuts"></a><span data-ttu-id="1b04d-111">使用键盘快捷方式的菜单项</span><span class="sxs-lookup"><span data-stu-id="1b04d-111">MenuItems with Keyboard Shortcuts</span></span>  
 <span data-ttu-id="1b04d-112">键盘快捷方式可通过键盘来调用输入的字符组合<xref:System.Windows.Controls.Menu>命令。</span><span class="sxs-lookup"><span data-stu-id="1b04d-112">Keyboard shortcuts are character combinations that can be entered with the keyboard to invoke <xref:System.Windows.Controls.Menu> commands.</span></span> <span data-ttu-id="1b04d-113">例如，“复制”的快捷方式是 CTRL+C。</span><span class="sxs-lookup"><span data-stu-id="1b04d-113">For example, the shortcut for **Copy** is CTRL+C.</span></span> <span data-ttu-id="1b04d-114">有两个属性将与键盘快捷方式和菜单项 —<xref:System.Windows.Controls.MenuItem.InputGestureText%2A>或<xref:System.Windows.Controls.MenuItem.Command%2A>。</span><span class="sxs-lookup"><span data-stu-id="1b04d-114">There are two properties to use with keyboard shortcuts and menu items —<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> or <xref:System.Windows.Controls.MenuItem.Command%2A>.</span></span>  
  
<a name="menus_inputgesturetext"></a>   
### <a name="inputgesturetext"></a><span data-ttu-id="1b04d-115">InputGestureText</span><span class="sxs-lookup"><span data-stu-id="1b04d-115">InputGestureText</span></span>  
 <span data-ttu-id="1b04d-116">下面的示例演示如何使用<xref:System.Windows.Controls.MenuItem.InputGestureText%2A>要分配到的键盘快捷方式文本属性<xref:System.Windows.Controls.MenuItem>控件。</span><span class="sxs-lookup"><span data-stu-id="1b04d-116">The following example shows how to use the <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> property to assign keyboard shortcut text to <xref:System.Windows.Controls.MenuItem> controls.</span></span> <span data-ttu-id="1b04d-117">这仅将键盘快捷方式放置在菜单项中。</span><span class="sxs-lookup"><span data-stu-id="1b04d-117">This only places the keyboard shortcut in the menu item.</span></span>  <span data-ttu-id="1b04d-118">它不会将与命令关联<xref:System.Windows.Controls.MenuItem>。</span><span class="sxs-lookup"><span data-stu-id="1b04d-118">It does not associate the command with the <xref:System.Windows.Controls.MenuItem>.</span></span> <span data-ttu-id="1b04d-119">应用程序必须处理用户的输入才能执行操作。</span><span class="sxs-lookup"><span data-stu-id="1b04d-119">The application must handle the user's input to carry out the action.</span></span>  
  
 [!code-xaml[MenuEvent#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>   
### <a name="command"></a><span data-ttu-id="1b04d-120">命令</span><span class="sxs-lookup"><span data-stu-id="1b04d-120">Command</span></span>  
 <span data-ttu-id="1b04d-121">下面的示例演示如何使用<xref:System.Windows.Controls.MenuItem.Command%2A>要关联属性**开放**并**保存**命令<xref:System.Windows.Controls.MenuItem>控件。</span><span class="sxs-lookup"><span data-stu-id="1b04d-121">The following example shows how to use the <xref:System.Windows.Controls.MenuItem.Command%2A> property to associate the **Open** and **Save** commands with <xref:System.Windows.Controls.MenuItem> controls.</span></span> <span data-ttu-id="1b04d-122">命令属性不仅将命令与<xref:System.Windows.Controls.MenuItem>，但它还会提供输入的手势文本以用作快捷方式。</span><span class="sxs-lookup"><span data-stu-id="1b04d-122">Not only does the command property associate a command with a <xref:System.Windows.Controls.MenuItem>, but it also supplies the input gesture text to use as a shortcut.</span></span>  
  
 [!code-xaml[MenuEvent#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 <span data-ttu-id="1b04d-123"><xref:System.Windows.Controls.MenuItem>类还具有<xref:System.Windows.Controls.MenuItem.CommandTarget%2A>属性，用于指定发生命令的元素。</span><span class="sxs-lookup"><span data-stu-id="1b04d-123">The <xref:System.Windows.Controls.MenuItem> class also has a <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> property, which specifies the element where the command occurs.</span></span> <span data-ttu-id="1b04d-124">如果<xref:System.Windows.Controls.MenuItem.CommandTarget%2A>未设置，具有键盘焦点的元素接收命令。</span><span class="sxs-lookup"><span data-stu-id="1b04d-124">If <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> is not set, the element that has keyboard focus receives the command.</span></span> <span data-ttu-id="1b04d-125">有关命令的详细信息，请参阅[命令概述](../../../../docs/framework/wpf/advanced/commanding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="1b04d-125">For more information about commands, see [Commanding Overview](../../../../docs/framework/wpf/advanced/commanding-overview.md).</span></span>  
  
<a name="menu_styling"></a>   
## <a name="menu-styling"></a><span data-ttu-id="1b04d-126">菜单样式设置</span><span class="sxs-lookup"><span data-stu-id="1b04d-126">Menu Styling</span></span>  
 <span data-ttu-id="1b04d-127">使用控件样式设置，你可以显著改变外观和行为<xref:System.Windows.Controls.Menu>而无需编写自定义控件的控件。</span><span class="sxs-lookup"><span data-stu-id="1b04d-127">With control styling, you can dramatically change the appearance and behavior of <xref:System.Windows.Controls.Menu> controls without having to write a custom control.</span></span> <span data-ttu-id="1b04d-128">除了设置视觉属性，还可以应用<xref:System.Windows.Style>到控件的各个部分，更改通过属性，控件的部件的行为或添加其他部分，或更改控件的布局。</span><span class="sxs-lookup"><span data-stu-id="1b04d-128">In addition to setting visual properties, you can also apply a <xref:System.Windows.Style> to individual parts of a control, change the behavior of parts of the control through properties, or add additional parts or change the layout of a control.</span></span> <span data-ttu-id="1b04d-129">下面的示例演示几种方法添加<xref:System.Windows.Style>到<xref:System.Windows.Controls.Menu>控件。</span><span class="sxs-lookup"><span data-stu-id="1b04d-129">The following examples demonstrate several ways to add a <xref:System.Windows.Style> to a <xref:System.Windows.Controls.Menu> control.</span></span>  
  
 <span data-ttu-id="1b04d-130">第一个代码示例定义了<xref:System.Windows.Style>调用`Simple`，演示如何在样式中使用当前系统设置。</span><span class="sxs-lookup"><span data-stu-id="1b04d-130">The first code example defines a <xref:System.Windows.Style> called `Simple` that shows how to use the current system settings in your style.</span></span> <span data-ttu-id="1b04d-131">代码将 `MenuHighlightBrush` 的颜色分配为菜单的背景色，将 `MenuTextBrush` 分配为菜单的前景色。</span><span class="sxs-lookup"><span data-stu-id="1b04d-131">The code assigns the color of the `MenuHighlightBrush` as the menu's background color and the `MenuTextBrush` as the menu's foreground color.</span></span> <span data-ttu-id="1b04d-132">请注意，使用资源键分配画笔。</span><span class="sxs-lookup"><span data-stu-id="1b04d-132">Notice that you use resource keys to assign the brushes.</span></span>  
  
 [!code-xaml[MenuStylesSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 <span data-ttu-id="1b04d-133">下面的示例使用<xref:System.Windows.Trigger>元素，您可以更改的外观<xref:System.Windows.Controls.MenuItem>发生的事件响应<xref:System.Windows.Controls.Menu>。</span><span class="sxs-lookup"><span data-stu-id="1b04d-133">The following sample uses <xref:System.Windows.Trigger> elements that enable you to change the appearance of a <xref:System.Windows.Controls.MenuItem> in response to events that occur on the <xref:System.Windows.Controls.Menu>.</span></span> <span data-ttu-id="1b04d-134">当将鼠标移到<xref:System.Windows.Controls.Menu>的前景色和字体特征的菜单项的更改。</span><span class="sxs-lookup"><span data-stu-id="1b04d-134">When you move the mouse over the <xref:System.Windows.Controls.Menu>, the foreground color and the font characteristics of the menu items change.</span></span>  
  
 [!code-xaml[MenuStylesSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a><span data-ttu-id="1b04d-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="1b04d-135">See also</span></span>
- [<span data-ttu-id="1b04d-136">WPF 控件库示例</span><span class="sxs-lookup"><span data-stu-id="1b04d-136">WPF Controls Gallery Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160053)
