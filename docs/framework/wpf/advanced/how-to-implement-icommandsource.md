---
title: 如何：实现 ICommandSource
ms.date: 12/05/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
ms.openlocfilehash: 6c18e0b77ec53d9bd3e7ce610f2940effe603c88
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174688"
---
# <a name="how-to-implement-icommandsource"></a>如何：实现 ICommandSource

此示例演示如何通过实现<xref:System.Windows.Input.ICommandSource>创建命令源。 命令源是知道如何调用命令的对象。 该<xref:System.Windows.Input.ICommandSource>接口公开三个成员：

- <xref:System.Windows.Input.ICommandSource.Command%2A>：将调用的命令。
- <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>：用户定义的数据类型，从命令源传递到处理命令的方法。
- <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>：正在执行命令的对象。

在此示例中，将创建一个从<xref:System.Windows.Controls.Slider>控件继承并实现接口的<xref:System.Windows.Input.ICommandSource>类。
  
## <a name="example"></a>示例

WPF<xref:System.Windows.Input.ICommandSource>提供了许多实现 的类，例如<xref:System.Windows.Controls.Button>，<xref:System.Windows.Controls.MenuItem>和<xref:System.Windows.Documents.Hyperlink>。 命令源定义它如何调用命令。 这些类在单击时调用命令，并且只有在设置其<xref:System.Windows.Input.ICommandSource.Command%2A>属性时才会成为命令源。

在此示例中，您将在移动滑块时调用该命令，或者更准确地在更改<xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>属性时调用该命令。

以下是类定义：

[!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]

下一步是实现<xref:System.Windows.Input.ICommandSource>成员。 在此示例中，属性作为<xref:System.Windows.DependencyProperty>对象实现。 这使属性能够使用数据绑定。 有关类的详细信息，<xref:System.Windows.DependencyProperty>请参阅[依赖项属性概述](dependency-properties-overview.md)。 有关数据绑定的详细信息，请参阅[数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)。

此处仅<xref:System.Windows.Input.ICommandSource.Command%2A>显示该属性。

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
以下是<xref:System.Windows.DependencyProperty>更改回调：

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]

下一步是添加和删除与命令源关联的命令。 在<xref:System.Windows.Input.ICommandSource.Command%2A>添加新命令时，不能简单地覆盖该属性，因为必须先删除与上一个命令关联的事件处理程序（如果有）。

[!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]

下一步是为<xref:System.Windows.Input.ICommand.CanExecuteChanged>处理程序创建逻辑。

该<xref:System.Windows.Input.ICommand.CanExecuteChanged>事件通知命令源命令对当前命令目标执行的能力可能已更改。 当命令源收到此事件时，它通常会在 命令<xref:System.Windows.Input.ICommand.CanExecute%2A>上调用 方法。 如果命令无法对当前命令目标执行，则命令源通常会自行禁用。 如果命令可以在当前命令目标上执行，则命令源通常会启用自身。

[!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
[!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]

最后一步是方法<xref:System.Windows.Input.ICommand.Execute%2A>。 如果命令为 ，<xref:System.Windows.Input.RoutedCommand><xref:System.Windows.Input.RoutedCommand><xref:System.Windows.Input.RoutedCommand.Execute%2A>则调用 方法;否则，将<xref:System.Windows.Input.ICommand><xref:System.Windows.Input.ICommand.Execute%2A>调用 该方法。

[!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
[!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [命令概述](commanding-overview.md)
