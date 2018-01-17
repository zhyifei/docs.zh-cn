---
title: "如何：将命令挂钩到不支持命令的控件"
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
ms.assetid: dad08f64-700b-46fb-ad3f-fbfee95f0dfe
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 804c4ffd54a0f8cc94e8849a223b1af8b27a58b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-hook-up-a-command-to-a-control-with-no-command-support"></a>如何：将命令挂钩到不支持命令的控件
下面的示例演示如何挂钩<xref:System.Windows.Input.RoutedCommand>到<xref:System.Windows.Controls.Control>其不提供内置的命令的支持。  有关将命令挂钩到多个源的完整示例，请参阅[创建自定义 RoutedCommand 示例](http://go.microsoft.com/fwlink/?LinkID=159980)示例。  
  
## <a name="example"></a>示例  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供了应用程序程序员经常遇到的常见命令库。  构成命令库类，这些类是： <xref:System.Windows.Input.ApplicationCommands>， <xref:System.Windows.Input.ComponentCommands>， <xref:System.Windows.Input.NavigationCommands>， <xref:System.Windows.Input.MediaCommands>，和<xref:System.Windows.Documents.EditingCommands>。  
  
 静态<xref:System.Windows.Input.RoutedCommand>构成这些类的对象未提供命令逻辑。  该命令的逻辑都与命令关联<xref:System.Windows.Input.CommandBinding>。  中的许多控件[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内置了对某些命令库中的命令的支持。  <xref:System.Windows.Controls.TextBox>例如，如支持的许多应用程序编辑命令<xref:System.Windows.Input.ApplicationCommands.Paste%2A>， <xref:System.Windows.Input.ApplicationCommands.Copy%2A>， <xref:System.Windows.Input.ApplicationCommands.Cut%2A>， <xref:System.Windows.Input.ApplicationCommands.Redo%2A>，和<xref:System.Windows.Input.ApplicationCommands.Undo%2A>。  应用程序开发人员不必执行任何特殊操作即可使命令适用于这些控件。  如果<xref:System.Windows.Controls.TextBox>是命令目标执行该命令后，它将处理命令使用<xref:System.Windows.Input.CommandBinding>内置控件。  
  
 下面显示了如何使用<xref:System.Windows.Controls.Button>作为的命令源<xref:System.Windows.Input.ApplicationCommands.Open%2A>命令。  A<xref:System.Windows.Input.CommandBinding>创建指定程序相关联<xref:System.Windows.Input.CanExecuteRoutedEventHandler>和<xref:System.Windows.Input.CanExecuteRoutedEventHandler>与<xref:System.Windows.Input.RoutedCommand>。  
  
 首先，创建命令源。  A<xref:System.Windows.Controls.Button>用作命令源。  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandsource)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbuttoncommandsource)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbuttoncommandsource)]  
  
 接下来，<xref:System.Windows.Input.ExecutedRoutedEventHandler>和<xref:System.Windows.Input.CanExecuteRoutedEventHandler>创建。  <xref:System.Windows.Input.ExecutedRoutedEventHandler>只是打开<xref:System.Windows.MessageBox>以表示执行此命令。  <xref:System.Windows.Input.CanExecuteRoutedEventHandler>设置<xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A>属性`true`。  通常情况下，则可以执行处理程序会执行更可靠的检查，以确定命令无法执行对当前的命令目标。  
  
 [!code-csharp[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerbothhandlers)]
 [!code-vb[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerbothhandlers)]  
  
 最后，<xref:System.Windows.Input.CommandBinding>的根上创建<xref:System.Windows.Window>的应用程序将关联到的路由的事件处理程序<xref:System.Windows.Input.ApplicationCommands.Open%2A>命令。  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
## <a name="see-also"></a>请参阅  
 [命令概述](../../../../docs/framework/wpf/advanced/commanding-overview.md)  
 [将命令挂钩到支持命令的控件](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-command-support.md)
