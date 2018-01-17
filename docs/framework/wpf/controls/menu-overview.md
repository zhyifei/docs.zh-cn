---
title: "菜单概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8ab5092b1bc9db22390a18b2c1cb1ad5725a2037
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="menu-overview"></a>菜单概述
<xref:System.Windows.Controls.Menu>类使您可以组织与命令和分层顺序的事件处理程序关联的元素。 每个<xref:System.Windows.Controls.Menu>元素包含一套<xref:System.Windows.Controls.MenuItem>元素。  
  
  
<a name="menu_control"></a>   
## <a name="menu-control"></a>Menu 控件  
 <xref:System.Windows.Controls.Menu>控件显示的命令或应用程序的选项指定的项的列表。 通常情况下，单击<xref:System.Windows.Controls.MenuItem>打开一个子菜单或导致应用程序执行的命令。  
  
<a name="creating_menus"></a>   
## <a name="creating-menus"></a>创建菜单  
 下面的示例创建<xref:System.Windows.Controls.Menu>操作中的文本<xref:System.Windows.Controls.TextBox>。 <xref:System.Windows.Controls.Menu>包含<xref:System.Windows.Controls.MenuItem>对象使用<xref:System.Windows.Controls.MenuItem.Command%2A>， <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>，和<xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>属性和<xref:System.Windows.Controls.MenuItem.Checked>， <xref:System.Windows.Controls.MenuItem.Unchecked>，和<xref:System.Windows.Controls.MenuItem.Click>事件。  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>   
## <a name="menuitems-with-keyboard-shortcuts"></a>使用键盘快捷方式的菜单项  
 键盘快捷键是可以使用键盘来调用输入的字符组合<xref:System.Windows.Controls.Menu>命令。 例如，“复制”的快捷方式是 CTRL+C。 有两个属性，若要使用键盘快捷方式和菜单项-<xref:System.Windows.Controls.MenuItem.InputGestureText%2A>或<xref:System.Windows.Controls.MenuItem.Command%2A>。  
  
<a name="menus_inputgesturetext"></a>   
### <a name="inputgesturetext"></a>InputGestureText  
 下面的示例演示如何使用<xref:System.Windows.Controls.MenuItem.InputGestureText%2A>要分配到的键盘快捷方式文本属性<xref:System.Windows.Controls.MenuItem>控件。 这仅将键盘快捷方式放置在菜单项中。  不将与命令关联<xref:System.Windows.Controls.MenuItem>。 应用程序必须处理用户的输入才能执行操作。  
  
 [!code-xaml[MenuEvent#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>   
### <a name="command"></a>命令  
 下面的示例演示如何使用<xref:System.Windows.Controls.MenuItem.Command%2A>相关联属性**打开**和**保存**命令与<xref:System.Windows.Controls.MenuItem>控件。 命令属性不仅关联具有的命令<xref:System.Windows.Controls.MenuItem>，但它还提供了要用作快捷方式的输入的笔势文本。  
  
 [!code-xaml[MenuEvent#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 <xref:System.Windows.Controls.MenuItem>类还具有<xref:System.Windows.Controls.MenuItem.CommandTarget%2A>属性，用于指定该命令的出现位置的元素。 如果<xref:System.Windows.Controls.MenuItem.CommandTarget%2A>未设置，具有键盘焦点的元素将收到命令。 有关命令的详细信息，请参阅[命令概述](../../../../docs/framework/wpf/advanced/commanding-overview.md)。  
  
<a name="menu_styling"></a>   
## <a name="menu-styling"></a>菜单样式设置  
 使用控件样式设置，你可以显著改变的外观和行为<xref:System.Windows.Controls.Menu>而无需编写自定义控件的控件。 除了设置的可视属性，你还可以应用<xref:System.Windows.Style>到各个部分的控件，更改组成部分通过属性，该控件的行为或添加其他部分，或更改控件的布局。 下面的示例演示通过多种方式来添加<xref:System.Windows.Style>到<xref:System.Windows.Controls.Menu>控件。  
  
 第一个代码示例定义<xref:System.Windows.Style>调用`Simple`，演示如何以您的方式使用当前的系统设置。 代码将 `MenuHighlightBrush` 的颜色分配为菜单的背景色，将 `MenuTextBrush` 分配为菜单的前景色。 请注意，使用资源键分配画笔。  
  
 [!code-xaml[MenuStylesSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 下面的示例使用<xref:System.Windows.Trigger>元素，您可以更改的外观<xref:System.Windows.Controls.MenuItem>对发生的事件的响应<xref:System.Windows.Controls.Menu>。 将鼠标移<xref:System.Windows.Controls.Menu>的前景色和字体特征的菜单项的更改。  
  
 [!code-xaml[MenuStylesSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a>请参阅  
 [WPF 控件库示例](http://go.microsoft.com/fwlink/?LinkID=160053)
