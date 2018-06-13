---
title: 如何：创建 RoutedCommand
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- RoutedCommand class [WPF], creating
ms.assetid: aaf6979f-69ab-406f-979f-5766daa85fa0
ms.openlocfilehash: 75e6c435516fe2a174cf991bd41f24e1b30a212a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544099"
---
# <a name="how-to-create-a-routedcommand"></a>如何：创建 RoutedCommand
此示例演示如何创建自定义<xref:System.Windows.Input.RoutedCommand>以及如何通过创建实现自定义命令<xref:System.Windows.Input.ExecutedRoutedEventHandler>和<xref:System.Windows.Input.CanExecuteRoutedEventHandler>和附加到<xref:System.Windows.Input.CommandBinding>。  有关命令的详细信息，请参阅[命令概述](../../../../docs/framework/wpf/advanced/commanding-overview.md)。  
  
## <a name="example"></a>示例  
 创建的第一步<xref:System.Windows.Input.RoutedCommand>定义该命令并实例化。  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommanddefinition)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommanddefinition)]  
  
 为了在应用程序中使用该命令，就必须创建事件处理程序以定义该命令的行为  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewExecuted](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewexecuted)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewExecuted](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewexecuted)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCanExecute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcanexecute)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCanExecute](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcanexecute)]  
  
 接下来，<xref:System.Windows.Input.CommandBinding>创建其将命令与事件处理程序相关联。 <xref:System.Windows.Input.CommandBinding>的特定对象上创建。  此对象用于定义的作用域<xref:System.Windows.Input.CommandBinding>元素树中  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewWindowCommandBindingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewwindowcommandbindingxaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandbindingcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandbindingcodebehind)]  
  
 最后一步调用该命令。  一种方法来调用命令是将其与相关联<xref:System.Windows.Input.ICommandSource>，如<xref:System.Windows.Controls.Button>。  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcustomcommandsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandsourcecodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandsourcecodebehind)]  
  
 单击该按钮，<xref:System.Windows.Input.RoutedCommand.Execute%2A>自定义的方法<xref:System.Windows.Input.RoutedCommand>调用。  <xref:System.Windows.Input.RoutedCommand>引发<xref:System.Windows.Input.CommandManager.PreviewExecuted>和<xref:System.Windows.Input.CommandManager.Executed>路由事件。  这些事件会遍历元素树，以查找<xref:System.Windows.Input.CommandBinding>此特定的命令。  如果<xref:System.Windows.Input.CommandBinding>找到，则<xref:System.Windows.Input.ExecutedRoutedEventHandler>与关联<xref:System.Windows.Input.CommandBinding>调用。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Input.RoutedCommand>  
 [命令概述](../../../../docs/framework/wpf/advanced/commanding-overview.md)
