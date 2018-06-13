---
title: 如何：实现 ICommandSource
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
ms.openlocfilehash: 9308bfbbb7fff86ca5e93c1155cc29e4ee0d05f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547022"
---
# <a name="how-to-implement-icommandsource"></a>如何：实现 ICommandSource
此示例演示如何通过实现来创建命令源<xref:System.Windows.Input.ICommandSource>。  命令源是知道如何调用命令的对象。  <xref:System.Windows.Input.ICommandSource>接口公开三个成员： <xref:System.Windows.Input.ICommandSource.Command%2A>， <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>，和<xref:System.Windows.Input.ICommandSource.CommandTarget%2A>。  <xref:System.Windows.Input.ICommandSource.Command%2A> 是将调用该命令。 <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>是从命令源传递到该方法用于处理该命令的用户定义数据类型。 <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>是在其执行该命令的对象。  
  
 在此示例中，创建类的子类<xref:System.Windows.Controls.Slider>控制和实现<xref:System.Windows.Input.ICommandSource>。  
  
## <a name="example"></a>示例  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供了多个类实现该<xref:System.Windows.Input.ICommandSource>，如<xref:System.Windows.Controls.Button>， <xref:System.Windows.Controls.MenuItem>，和<xref:System.Windows.Controls.ListBoxItem>。  命令源定义它将命令的调用。   <xref:System.Windows.Controls.Button> 和<xref:System.Windows.Controls.MenuItem>在被单击时调用的命令。  A<xref:System.Windows.Controls.ListBoxItem>时被双击调用命令。 这些类仅会成为命令源时其<xref:System.Windows.Input.ICommandSource.Command%2A>属性设置。  
  
 此示例中我们将调用该命令，当移动滑块时，更准确地说，当<xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>属性更改。  
  
 下面是类定义。  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]  
  
 下一步是实现<xref:System.Windows.Input.ICommandSource>成员。  在此示例中，属性作为实现<xref:System.Windows.DependencyProperty>对象。  这样，要使用数据绑定的属性。  有关详细信息<xref:System.Windows.DependencyProperty>类，请参阅[依赖项属性概述](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)。  有关数据绑定的详细信息，请参阅[数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)。  
  
 仅<xref:System.Windows.Input.ICommandSource.Command%2A>属性如下所示。  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
 以下是<xref:System.Windows.DependencyProperty>更改回调。  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]  
  
 下一步是添加和删除与命令源关联的命令。  <xref:System.Windows.Input.ICommandSource.Command%2A>属性不能只需被覆盖时添加一个新的命令，因为事件处理程序与前一个命令中，如果有的话，必须先删除。  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]  
  
 最后一步是创建逻辑<xref:System.Windows.Input.ICommand.CanExecuteChanged>处理程序和<xref:System.Windows.Input.ICommand.Execute%2A>方法。  
  
 <xref:System.Windows.Input.ICommand.CanExecuteChanged>事件通知当前的命令目标执行命令的能力可能已更改的命令源。  当命令源收到此事件时，它通常会调用<xref:System.Windows.Input.ICommand.CanExecute%2A>命令的方法。  如果该命令不能执行当前命令目标，命令源通常会禁用自身。  如果此命令可执行对当前的命令目标，命令源通常会启用自身。  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]  
  
 最后一步是<xref:System.Windows.Input.ICommand.Execute%2A>方法。  如果该命令是<xref:System.Windows.Input.RoutedCommand>、 <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A>方法是调用; 否则为<xref:System.Windows.Input.ICommand><xref:System.Windows.Input.ICommand.Execute%2A>调用方法。  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandExecute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
 [!code-vb[ImplementICommandSource#ImplementICommandExecute](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Input.ICommandSource>  
 <xref:System.Windows.Input.ICommand>  
 <xref:System.Windows.Input.RoutedCommand>  
 [命令概述](../../../../docs/framework/wpf/advanced/commanding-overview.md)
