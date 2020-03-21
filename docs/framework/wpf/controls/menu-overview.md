---
title: 菜单概述
ms.date: 03/30/2017
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
ms.openlocfilehash: 53bc8f10e61b6e4e9e1f3b9a484340d9e2ec2a85
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186972"
---
# <a name="menu-overview"></a><span data-ttu-id="71109-102">菜单概述</span><span class="sxs-lookup"><span data-stu-id="71109-102">Menu Overview</span></span>
<span data-ttu-id="71109-103">该<xref:System.Windows.Controls.Menu>类使您能够按分层顺序组织与命令和事件处理程序关联的元素。</span><span class="sxs-lookup"><span data-stu-id="71109-103">The <xref:System.Windows.Controls.Menu> class enables you to organize elements associated with commands and event handlers in a hierarchical order.</span></span> <span data-ttu-id="71109-104">每个<xref:System.Windows.Controls.Menu>元素都包含元素的集合<xref:System.Windows.Controls.MenuItem>。</span><span class="sxs-lookup"><span data-stu-id="71109-104">Each <xref:System.Windows.Controls.Menu> element contains a collection of <xref:System.Windows.Controls.MenuItem> elements.</span></span>  

<a name="menu_control"></a>
## <a name="menu-control"></a><span data-ttu-id="71109-105">Menu 控件</span><span class="sxs-lookup"><span data-stu-id="71109-105">Menu Control</span></span>  
 <span data-ttu-id="71109-106">该<xref:System.Windows.Controls.Menu>控件显示指定应用程序的命令或选项的项列表。</span><span class="sxs-lookup"><span data-stu-id="71109-106">The <xref:System.Windows.Controls.Menu> control presents a list of items that specify commands or options for an application.</span></span> <span data-ttu-id="71109-107">通常，单击<xref:System.Windows.Controls.MenuItem>将打开子菜单或导致应用程序执行命令。</span><span class="sxs-lookup"><span data-stu-id="71109-107">Typically, clicking a <xref:System.Windows.Controls.MenuItem> opens a submenu or causes an application to carry out a command.</span></span>  
  
<a name="creating_menus"></a>
## <a name="creating-menus"></a><span data-ttu-id="71109-108">创建菜单</span><span class="sxs-lookup"><span data-stu-id="71109-108">Creating Menus</span></span>  
 <span data-ttu-id="71109-109">下面的示例创建 一<xref:System.Windows.Controls.Menu>个 用于操作<xref:System.Windows.Controls.TextBox>中的文本。</span><span class="sxs-lookup"><span data-stu-id="71109-109">The following example creates a <xref:System.Windows.Controls.Menu> to manipulate text in a <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="71109-110"><xref:System.Windows.Controls.Menu>包含<xref:System.Windows.Controls.MenuItem>使用<xref:System.Windows.Controls.MenuItem.Command%2A>、<xref:System.Windows.Controls.MenuItem.IsCheckable%2A>和<xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>属性 以及<xref:System.Windows.Controls.MenuItem.Checked>和<xref:System.Windows.Controls.MenuItem.Unchecked>和<xref:System.Windows.Controls.MenuItem.Click>事件的对象。</span><span class="sxs-lookup"><span data-stu-id="71109-110">The <xref:System.Windows.Controls.Menu> contains <xref:System.Windows.Controls.MenuItem> objects that use the <xref:System.Windows.Controls.MenuItem.Command%2A>, <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>, and <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> properties and the <xref:System.Windows.Controls.MenuItem.Checked>, <xref:System.Windows.Controls.MenuItem.Unchecked>, and <xref:System.Windows.Controls.MenuItem.Click> events.</span></span>  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>
## <a name="menuitems-with-keyboard-shortcuts"></a><span data-ttu-id="71109-111">使用键盘快捷方式的菜单项</span><span class="sxs-lookup"><span data-stu-id="71109-111">MenuItems with Keyboard Shortcuts</span></span>  
 <span data-ttu-id="71109-112">键盘快捷键是可以使用键盘输入以调用<xref:System.Windows.Controls.Menu>命令的字符组合。</span><span class="sxs-lookup"><span data-stu-id="71109-112">Keyboard shortcuts are character combinations that can be entered with the keyboard to invoke <xref:System.Windows.Controls.Menu> commands.</span></span> <span data-ttu-id="71109-113">例如，“复制”\*\*\*\* 的快捷方式是 CTRL+C。</span><span class="sxs-lookup"><span data-stu-id="71109-113">For example, the shortcut for **Copy** is CTRL+C.</span></span> <span data-ttu-id="71109-114">有两个属性可用于键盘快捷键和菜单项 -<xref:System.Windows.Controls.MenuItem.InputGestureText%2A>或<xref:System.Windows.Controls.MenuItem.Command%2A>。</span><span class="sxs-lookup"><span data-stu-id="71109-114">There are two properties to use with keyboard shortcuts and menu items —<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> or <xref:System.Windows.Controls.MenuItem.Command%2A>.</span></span>  
  
<a name="menus_inputgesturetext"></a>
### <a name="inputgesturetext"></a><span data-ttu-id="71109-115">InputGestureText</span><span class="sxs-lookup"><span data-stu-id="71109-115">InputGestureText</span></span>  
 <span data-ttu-id="71109-116">下面的示例演示如何使用 属性<xref:System.Windows.Controls.MenuItem.InputGestureText%2A>将键盘快捷文本分配给<xref:System.Windows.Controls.MenuItem>控件。</span><span class="sxs-lookup"><span data-stu-id="71109-116">The following example shows how to use the <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> property to assign keyboard shortcut text to <xref:System.Windows.Controls.MenuItem> controls.</span></span> <span data-ttu-id="71109-117">这仅将键盘快捷方式放置在菜单项中。</span><span class="sxs-lookup"><span data-stu-id="71109-117">This only places the keyboard shortcut in the menu item.</span></span>  <span data-ttu-id="71109-118">它不将命令与 相关联<xref:System.Windows.Controls.MenuItem>。</span><span class="sxs-lookup"><span data-stu-id="71109-118">It does not associate the command with the <xref:System.Windows.Controls.MenuItem>.</span></span> <span data-ttu-id="71109-119">应用程序必须处理用户的输入才能执行操作。</span><span class="sxs-lookup"><span data-stu-id="71109-119">The application must handle the user's input to carry out the action.</span></span>  
  
 [!code-xaml[MenuEvent#6](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>
### <a name="command"></a><span data-ttu-id="71109-120">Command</span><span class="sxs-lookup"><span data-stu-id="71109-120">Command</span></span>  
 <span data-ttu-id="71109-121">下面的示例<xref:System.Windows.Controls.MenuItem.Command%2A>演示如何使用 属性将 **"打开**"和"**保存"** 命令与<xref:System.Windows.Controls.MenuItem>控件相关联。</span><span class="sxs-lookup"><span data-stu-id="71109-121">The following example shows how to use the <xref:System.Windows.Controls.MenuItem.Command%2A> property to associate the **Open** and **Save** commands with <xref:System.Windows.Controls.MenuItem> controls.</span></span> <span data-ttu-id="71109-122">命令属性不仅将命令与<xref:System.Windows.Controls.MenuItem>相关联，而且还提供用作快捷方式的输入手势文本。</span><span class="sxs-lookup"><span data-stu-id="71109-122">Not only does the command property associate a command with a <xref:System.Windows.Controls.MenuItem>, but it also supplies the input gesture text to use as a shortcut.</span></span>  
  
 [!code-xaml[MenuEvent#8](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 <span data-ttu-id="71109-123">类<xref:System.Windows.Controls.MenuItem>还具有一个<xref:System.Windows.Controls.MenuItem.CommandTarget%2A>属性，该属性指定发生命令的元素。</span><span class="sxs-lookup"><span data-stu-id="71109-123">The <xref:System.Windows.Controls.MenuItem> class also has a <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> property, which specifies the element where the command occurs.</span></span> <span data-ttu-id="71109-124">如果未<xref:System.Windows.Controls.MenuItem.CommandTarget%2A>设置，具有键盘焦点的元素将接收该命令。</span><span class="sxs-lookup"><span data-stu-id="71109-124">If <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> is not set, the element that has keyboard focus receives the command.</span></span> <span data-ttu-id="71109-125">有关命令的详细信息，请参阅[命令概述](../advanced/commanding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="71109-125">For more information about commands, see [Commanding Overview](../advanced/commanding-overview.md).</span></span>  
  
<a name="menu_styling"></a>
## <a name="menu-styling"></a><span data-ttu-id="71109-126">菜单样式设置</span><span class="sxs-lookup"><span data-stu-id="71109-126">Menu Styling</span></span>  
 <span data-ttu-id="71109-127">使用控件样式，您可以显著更改<xref:System.Windows.Controls.Menu>控件的外观和行为，而无需编写自定义控件。</span><span class="sxs-lookup"><span data-stu-id="71109-127">With control styling, you can dramatically change the appearance and behavior of <xref:System.Windows.Controls.Menu> controls without having to write a custom control.</span></span> <span data-ttu-id="71109-128">除了设置可视属性外，还可以<xref:System.Windows.Style>将 应用于控件的各个部分、通过属性更改控件各部分的行为、添加其他部分或更改控件的布局。</span><span class="sxs-lookup"><span data-stu-id="71109-128">In addition to setting visual properties, you can also apply a <xref:System.Windows.Style> to individual parts of a control, change the behavior of parts of the control through properties, or add additional parts or change the layout of a control.</span></span> <span data-ttu-id="71109-129">以下示例演示了向<xref:System.Windows.Style><xref:System.Windows.Controls.Menu>控件添加 的几种方法。</span><span class="sxs-lookup"><span data-stu-id="71109-129">The following examples demonstrate several ways to add a <xref:System.Windows.Style> to a <xref:System.Windows.Controls.Menu> control.</span></span>  
  
 <span data-ttu-id="71109-130">第一个代码示例定义一<xref:System.Windows.Style>个`Simple`调用，该调用示例演示如何在样式中使用当前系统设置。</span><span class="sxs-lookup"><span data-stu-id="71109-130">The first code example defines a <xref:System.Windows.Style> called `Simple` that shows how to use the current system settings in your style.</span></span> <span data-ttu-id="71109-131">代码将 `MenuHighlightBrush` 的颜色分配为菜单的背景色，将 `MenuTextBrush` 分配为菜单的前景色。</span><span class="sxs-lookup"><span data-stu-id="71109-131">The code assigns the color of the `MenuHighlightBrush` as the menu's background color and the `MenuTextBrush` as the menu's foreground color.</span></span> <span data-ttu-id="71109-132">请注意，使用资源键分配画笔。</span><span class="sxs-lookup"><span data-stu-id="71109-132">Notice that you use resource keys to assign the brushes.</span></span>  
  
 [!code-xaml[MenuStylesSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 <span data-ttu-id="71109-133">以下示例使用<xref:System.Windows.Trigger>元素，以便更改 的外观<xref:System.Windows.Controls.MenuItem>以响应 在 上发生的事件。 <xref:System.Windows.Controls.Menu></span><span class="sxs-lookup"><span data-stu-id="71109-133">The following sample uses <xref:System.Windows.Trigger> elements that enable you to change the appearance of a <xref:System.Windows.Controls.MenuItem> in response to events that occur on the <xref:System.Windows.Controls.Menu>.</span></span> <span data-ttu-id="71109-134">将鼠标移到 上<xref:System.Windows.Controls.Menu>时，菜单项的前景颜色和字体特征将发生变化。</span><span class="sxs-lookup"><span data-stu-id="71109-134">When you move the mouse over the <xref:System.Windows.Controls.Menu>, the foreground color and the font characteristics of the menu items change.</span></span>  
  
 [!code-xaml[MenuStylesSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a><span data-ttu-id="71109-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71109-135">See also</span></span>

- [<span data-ttu-id="71109-136">WPF 控件库示例</span><span class="sxs-lookup"><span data-stu-id="71109-136">WPF Controls Gallery Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
