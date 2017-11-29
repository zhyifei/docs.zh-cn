---
title: "如何：将命令挂钩到支持命令的控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Control class [WPF], attaching a RoutedCommand
- classes [WPF], Control [WPF], attaching a RoutedCommand
- RoutedCommand class [WPF], attaching to a Control
- classes [WPF], RoutedCommand [WPF], attaching to a Control
ms.assetid: 8d8592ae-0c91-469e-a1cd-d179c4544548
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 61148e1249f7bfcf319c3be4a30c706c5c4dc344
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hook-up-a-command-to-a-control-with-command-support"></a>如何：将命令挂钩到支持命令的控件
下面的示例演示如何挂钩<xref:System.Windows.Input.RoutedCommand>到<xref:System.Windows.Controls.Control>提供了内置命令的支持。  有关将命令挂钩到多个源的完整示例，请参阅[创建自定义 RoutedCommand 示例](http://go.microsoft.com/fwlink/?LinkID=159980)示例。  
  
## <a name="example"></a>示例  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供了应用程序程序员经常遇到的常见命令库。  构成命令库类，这些类是： <xref:System.Windows.Input.ApplicationCommands>， <xref:System.Windows.Input.ComponentCommands>， <xref:System.Windows.Input.NavigationCommands>， <xref:System.Windows.Input.MediaCommands>，和<xref:System.Windows.Documents.EditingCommands>。  
  
 静态<xref:System.Windows.Input.RoutedCommand>构成这些类的对象未提供命令逻辑。  该命令的逻辑都与命令关联<xref:System.Windows.Input.CommandBinding>。  某些控件的部分命令具有内置的 CommandBindings。  这种机制可使命令的语义保持不变，而实际实现可以更改。  A <xref:System.Windows.Controls.TextBox>，例如，处理<xref:System.Windows.Input.ApplicationCommands.Paste%2A>命令以不同的方式不是控件设计为支持映像，但基本要旨粘贴操作意味着什么保持不变。  命令无法提供命令逻辑，但是控件或应用程序必须提供命令逻辑。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的许多控件都为命令库中的某些命令提供内置支持。  <xref:System.Windows.Controls.TextBox>例如，如支持的许多应用程序编辑命令<xref:System.Windows.Input.ApplicationCommands.Paste%2A>， <xref:System.Windows.Input.ApplicationCommands.Copy%2A>， <xref:System.Windows.Input.ApplicationCommands.Cut%2A>， <xref:System.Windows.Input.ApplicationCommands.Redo%2A>，和<xref:System.Windows.Input.ApplicationCommands.Undo%2A>。  应用程序开发人员不必执行任何特殊操作即可使命令适用于这些控件。  如果<xref:System.Windows.Controls.TextBox>是命令目标执行该命令后，它将处理命令使用<xref:System.Windows.Input.CommandBinding>内置控件。  
  
 下面显示了如何使用<xref:System.Windows.Controls.MenuItem>作为的命令源<xref:System.Windows.Input.ApplicationCommands.Paste%2A>命令，其中<xref:System.Windows.Controls.TextBox>目标的命令。  定义的所有逻辑如何<xref:System.Windows.Controls.TextBox>执行粘贴内置于<xref:System.Windows.Controls.TextBox>控件。  
  
 A<xref:System.Windows.Controls.MenuItem>创建它并且<xref:System.Windows.Controls.MenuItem.Command%2A>属性设置为<xref:System.Windows.Input.ApplicationCommands.Paste%2A>命令。  <xref:System.Windows.Controls.MenuItem.CommandTarget%2A>未显式设置为<xref:System.Windows.Controls.TextBox>对象。  当<xref:System.Windows.Controls.MenuItem.CommandTarget%2A>未设置，则目标命令为具有键盘焦点的元素。  如果具有键盘焦点的元素不支持<xref:System.Windows.Input.ApplicationCommands.Paste%2A>命令或当前无法执行粘贴命令 （剪贴板为空，例如） 则<xref:System.Windows.Controls.MenuItem>将灰显。  
  
 [!code-xaml[MenuItemCommandTask_XAML#MenuItemCommanding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask_XAML/CS/Window1.xaml#menuitemcommanding)]  
  
 [!code-csharp[MenuItemCommandTask#MenuItemCommandingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask/CSharp/Window1.xaml.cs#menuitemcommandingcodebehind)]
 [!code-vb[MenuItemCommandTask#MenuItemCommandingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandTask/VisualBasic/Window1.xaml.vb#menuitemcommandingcodebehind)]  
  
## <a name="see-also"></a>另请参阅  
 [命令概述](../../../../docs/framework/wpf/advanced/commanding-overview.md)  
 [将命令挂钩到不支持命令的控件](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-no-command-support.md)
