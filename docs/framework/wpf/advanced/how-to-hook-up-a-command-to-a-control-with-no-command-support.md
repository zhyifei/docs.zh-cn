---
title: 如何：将命令挂钩到不支持命令的控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Control class [WPF], attaching a RoutedCommand
- classes [WPF], Control [WPF], attaching a RoutedCommand
- RoutedCommand class [WPF], attaching to a Control
- classes [WPF], RoutedCommand [WPF], attaching to a Control
ms.assetid: dad08f64-700b-46fb-ad3f-fbfee95f0dfe
ms.openlocfilehash: 3ae45c9a9e33a3cb53ada6e1e5430ae0f9e6c198
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216972"
---
# <a name="how-to-hook-up-a-command-to-a-control-with-no-command-support"></a>如何：将命令挂钩到不支持命令的控件
以下示例演示如何将 <xref:System.Windows.Input.RoutedCommand> 挂钩到不含对该命令的内置支持的 <xref:System.Windows.Controls.Control>。  有关将命令挂钩到多个源的完整示例，请参阅[创建自定义 RoutedCommand 示例](https://github.com/Microsoft/WPF-Samples/tree/master/Input%20and%20Commands/CustomRoutedCommand)示例。  
  
## <a name="example"></a>示例  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供应用程序程序员经常遇到的常见命令的库。  构成命令库的类为：<xref:System.Windows.Input.ApplicationCommands>、<xref:System.Windows.Input.ComponentCommands>、<xref:System.Windows.Input.NavigationCommands>、<xref:System.Windows.Input.MediaCommands> 和 <xref:System.Windows.Documents.EditingCommands>。  
  
 构成这些类的静态 <xref:System.Windows.Input.RoutedCommand> 对象不提供命令逻辑。  命令的逻辑通过 <xref:System.Windows.Input.CommandBinding> 与命令相关联。  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的许多控件都为命令库中的某些命令提供内置支持。  <xref:System.Windows.Controls.TextBox>例如，如支持的许多应用程序编辑命令<xref:System.Windows.Input.ApplicationCommands.Paste%2A>， <xref:System.Windows.Input.ApplicationCommands.Copy%2A>， <xref:System.Windows.Input.ApplicationCommands.Cut%2A>， <xref:System.Windows.Input.ApplicationCommands.Redo%2A>，和<xref:System.Windows.Input.ApplicationCommands.Undo%2A>。  应用程序开发人员不必执行任何特殊操作即可使命令适用于这些控件。  如果命令执行时，<xref:System.Windows.Controls.TextBox> 是命令目标，它将使用内置于控件中的 <xref:System.Windows.Input.CommandBinding> 处理该命令。  
  
 下面演示了如何将 <xref:System.Windows.Controls.Button> 用作 <xref:System.Windows.Input.ApplicationCommands.Open%2A> 命令的命令源。  创建一个将指定的 <xref:System.Windows.Input.CanExecuteRoutedEventHandler> 和 <xref:System.Windows.Input.CanExecuteRoutedEventHandler> 与 <xref:System.Windows.Input.RoutedCommand> 相关联的 <xref:System.Windows.Input.CommandBinding>。  
  
 首先，创建命令源。  将 <xref:System.Windows.Controls.Button> 用作命令源。  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandSource](~/samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandsource)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerButtonCommandSource](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbuttoncommandsource)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerButtonCommandSource](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbuttoncommandsource)]  
  
 接下来，创建 <xref:System.Windows.Input.ExecutedRoutedEventHandler> 和 <xref:System.Windows.Input.CanExecuteRoutedEventHandler>。  <xref:System.Windows.Input.ExecutedRoutedEventHandler> 只需打开 <xref:System.Windows.MessageBox> 即可表示已执行该命令。  <xref:System.Windows.Input.CanExecuteRoutedEventHandler> 将 <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> 属性设置为 `true`。  通常，can execute 处理程序将执行更可靠的检查，确定是否可以在当前命令目标上执行该命令。  
  
 [!code-csharp[commandWithHandler#CommandHandlerBothHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerbothhandlers)]
 [!code-vb[commandWithHandler#CommandHandlerBothHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerbothhandlers)]  
  
 最后，在将路由事件处理程序与 <xref:System.Windows.Input.ApplicationCommands.Open%2A> 命令相关联的应用程序的根 <xref:System.Windows.Window> 上创建 <xref:System.Windows.Input.CommandBinding>。  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
## <a name="see-also"></a>请参阅

- [命令概述](commanding-overview.md)
- [将命令挂钩到支持命令的控件](how-to-hook-up-a-command-to-a-control-with-command-support.md)
