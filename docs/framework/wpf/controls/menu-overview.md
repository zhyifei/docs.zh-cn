---
title: 菜单概述
ms.date: 03/30/2017
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
ms.openlocfilehash: 3d5cfba0734e684349f7d73b7242f4b69089b94d
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124645"
---
# <a name="menu-overview"></a>菜单概述
使用 <xref:System.Windows.Controls.Menu> 类，可以按分层顺序组织与命令和事件处理程序关联的元素。 每个 <xref:System.Windows.Controls.Menu> 元素都包含一个 <xref:System.Windows.Controls.MenuItem> 元素的集合。  

<a name="menu_control"></a>   
## <a name="menu-control"></a>Menu 控件  
 <xref:System.Windows.Controls.Menu> 控件提供了一个项列表，这些项指定了应用程序的命令或选项。 通常，单击 <xref:System.Windows.Controls.MenuItem> 会打开子菜单或使应用程序执行命令。  
  
<a name="creating_menus"></a>   
## <a name="creating-menus"></a>创建菜单  
 下面的示例创建一个 <xref:System.Windows.Controls.Menu> 来操作 <xref:System.Windows.Controls.TextBox>中的文本。 <xref:System.Windows.Controls.Menu> 包含 <xref:System.Windows.Controls.MenuItem> 对象，这些对象使用 <xref:System.Windows.Controls.MenuItem.Command%2A>、<xref:System.Windows.Controls.MenuItem.IsCheckable%2A>和 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 属性以及 <xref:System.Windows.Controls.MenuItem.Checked>、<xref:System.Windows.Controls.MenuItem.Unchecked>和 <xref:System.Windows.Controls.MenuItem.Click> 事件。  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>   
## <a name="menuitems-with-keyboard-shortcuts"></a>使用键盘快捷方式的菜单项  
 键盘快捷方式是可通过键盘输入的字符组合，用于调用 <xref:System.Windows.Controls.Menu> 命令。 例如，“复制”的快捷方式是 CTRL+C。 键盘快捷方式和菜单项可以使用两个属性，<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> 或 <xref:System.Windows.Controls.MenuItem.Command%2A>。  
  
<a name="menus_inputgesturetext"></a>   
### <a name="inputgesturetext"></a>InputGestureText  
 下面的示例演示如何使用 <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> 属性向 <xref:System.Windows.Controls.MenuItem> 控件分配键盘快捷方式文本。 这仅将键盘快捷方式放置在菜单项中。  它不会将命令与 <xref:System.Windows.Controls.MenuItem>相关联。 应用程序必须处理用户的输入才能执行操作。  
  
 [!code-xaml[MenuEvent#6](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>   
### <a name="command"></a>Command  
 下面的示例演示如何使用 <xref:System.Windows.Controls.MenuItem.Command%2A> 属性将**打开**和**保存**命令与 <xref:System.Windows.Controls.MenuItem> 控件相关联。 命令属性不仅将命令与 <xref:System.Windows.Controls.MenuItem>相关联，而且它还提供要用作快捷方式的输入笔势文本。  
  
 [!code-xaml[MenuEvent#8](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 <xref:System.Windows.Controls.MenuItem> 类还具有一个 <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> 属性，该属性指定发生命令的元素。 如果未设置 <xref:System.Windows.Controls.MenuItem.CommandTarget%2A>，具有键盘焦点的元素将接收命令。 有关命令的详细信息，请参阅[命令概述](../advanced/commanding-overview.md)。  
  
<a name="menu_styling"></a>   
## <a name="menu-styling"></a>菜单样式设置  
 使用控件样式，无需编写自定义控件即可显著更改 <xref:System.Windows.Controls.Menu> 控件的外观和行为。 除了设置视觉对象属性之外，您还可以将 <xref:System.Windows.Style> 应用于控件的各个部分，通过属性更改控件部件的行为，或添加其他部分或更改控件的布局。 下面的示例演示了向 <xref:System.Windows.Controls.Menu> 控件添加 <xref:System.Windows.Style> 的几种方法。  
  
 第一个代码示例定义一个名为 `Simple` 的 <xref:System.Windows.Style>，它演示如何在样式中使用当前系统设置。 代码将 `MenuHighlightBrush` 的颜色分配为菜单的背景色，将 `MenuTextBrush` 分配为菜单的前景色。 请注意，使用资源键分配画笔。  
  
 [!code-xaml[MenuStylesSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 下面的示例使用 <xref:System.Windows.Trigger> 元素，这些元素使你可以更改 <xref:System.Windows.Controls.MenuItem> 的外观，以响应在 <xref:System.Windows.Controls.Menu>上发生的事件。 将鼠标移到 <xref:System.Windows.Controls.Menu>上时，菜单项的前景色和字体特征会改变。  
  
 [!code-xaml[MenuStylesSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a>另请参阅

- [WPF 控件库示例](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
