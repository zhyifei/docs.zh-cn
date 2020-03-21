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
# <a name="menu-overview"></a>菜单概述
该<xref:System.Windows.Controls.Menu>类使您能够按分层顺序组织与命令和事件处理程序关联的元素。 每个<xref:System.Windows.Controls.Menu>元素都包含元素的集合<xref:System.Windows.Controls.MenuItem>。  

<a name="menu_control"></a>
## <a name="menu-control"></a>Menu 控件  
 该<xref:System.Windows.Controls.Menu>控件显示指定应用程序的命令或选项的项列表。 通常，单击<xref:System.Windows.Controls.MenuItem>将打开子菜单或导致应用程序执行命令。  
  
<a name="creating_menus"></a>
## <a name="creating-menus"></a>创建菜单  
 下面的示例创建 一<xref:System.Windows.Controls.Menu>个 用于操作<xref:System.Windows.Controls.TextBox>中的文本。 <xref:System.Windows.Controls.Menu>包含<xref:System.Windows.Controls.MenuItem>使用<xref:System.Windows.Controls.MenuItem.Command%2A>、<xref:System.Windows.Controls.MenuItem.IsCheckable%2A>和<xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>属性 以及<xref:System.Windows.Controls.MenuItem.Checked>和<xref:System.Windows.Controls.MenuItem.Unchecked>和<xref:System.Windows.Controls.MenuItem.Click>事件的对象。  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>
## <a name="menuitems-with-keyboard-shortcuts"></a>使用键盘快捷方式的菜单项  
 键盘快捷键是可以使用键盘输入以调用<xref:System.Windows.Controls.Menu>命令的字符组合。 例如，“复制”**** 的快捷方式是 CTRL+C。 有两个属性可用于键盘快捷键和菜单项 -<xref:System.Windows.Controls.MenuItem.InputGestureText%2A>或<xref:System.Windows.Controls.MenuItem.Command%2A>。  
  
<a name="menus_inputgesturetext"></a>
### <a name="inputgesturetext"></a>InputGestureText  
 下面的示例演示如何使用 属性<xref:System.Windows.Controls.MenuItem.InputGestureText%2A>将键盘快捷文本分配给<xref:System.Windows.Controls.MenuItem>控件。 这仅将键盘快捷方式放置在菜单项中。  它不将命令与 相关联<xref:System.Windows.Controls.MenuItem>。 应用程序必须处理用户的输入才能执行操作。  
  
 [!code-xaml[MenuEvent#6](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>
### <a name="command"></a>Command  
 下面的示例<xref:System.Windows.Controls.MenuItem.Command%2A>演示如何使用 属性将 **"打开**"和"**保存"** 命令与<xref:System.Windows.Controls.MenuItem>控件相关联。 命令属性不仅将命令与<xref:System.Windows.Controls.MenuItem>相关联，而且还提供用作快捷方式的输入手势文本。  
  
 [!code-xaml[MenuEvent#8](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 类<xref:System.Windows.Controls.MenuItem>还具有一个<xref:System.Windows.Controls.MenuItem.CommandTarget%2A>属性，该属性指定发生命令的元素。 如果未<xref:System.Windows.Controls.MenuItem.CommandTarget%2A>设置，具有键盘焦点的元素将接收该命令。 有关命令的详细信息，请参阅[命令概述](../advanced/commanding-overview.md)。  
  
<a name="menu_styling"></a>
## <a name="menu-styling"></a>菜单样式设置  
 使用控件样式，您可以显著更改<xref:System.Windows.Controls.Menu>控件的外观和行为，而无需编写自定义控件。 除了设置可视属性外，还可以<xref:System.Windows.Style>将 应用于控件的各个部分、通过属性更改控件各部分的行为、添加其他部分或更改控件的布局。 以下示例演示了向<xref:System.Windows.Style><xref:System.Windows.Controls.Menu>控件添加 的几种方法。  
  
 第一个代码示例定义一<xref:System.Windows.Style>个`Simple`调用，该调用示例演示如何在样式中使用当前系统设置。 代码将 `MenuHighlightBrush` 的颜色分配为菜单的背景色，将 `MenuTextBrush` 分配为菜单的前景色。 请注意，使用资源键分配画笔。  
  
 [!code-xaml[MenuStylesSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 以下示例使用<xref:System.Windows.Trigger>元素，以便更改 的外观<xref:System.Windows.Controls.MenuItem>以响应 在 上发生的事件。 <xref:System.Windows.Controls.Menu> 将鼠标移到 上<xref:System.Windows.Controls.Menu>时，菜单项的前景颜色和字体特征将发生变化。  
  
 [!code-xaml[MenuStylesSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a>另请参阅

- [WPF 控件库示例](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
