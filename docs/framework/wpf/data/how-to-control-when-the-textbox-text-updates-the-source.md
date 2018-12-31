---
title: 如何：控制文本框文本更新源的时间
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
ms.openlocfilehash: 52f3a8d3a5d78a211367722b3042eb50f6ac36d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557220"
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a>如何：控制文本框文本更新源的时间
本主题介绍如何使用<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>属性控制绑定源更新的时机。 本主题使用<xref:System.Windows.Controls.TextBox>控件作为示例。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> 属性具有一个<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>的默认值<xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>。 这意味着如果应用程序中有一个<xref:System.Windows.Controls.TextBox>设置了<xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> 属性的数据绑定，你键入的文本<xref:System.Windows.Controls.TextBox>不会更新，直到源<xref:System.Windows.Controls.TextBox>失去焦点 (例如，单击<xref:System.Windows.Controls.TextBox>以外的地方)。  
  
 如果你想源在输入时更新，设置绑定的<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>为<xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>。 在下面的示例中，突出显示的代码行表明<xref:System.Windows.Controls.TextBox>和<xref:System.Windows.Controls.TextBlock>的`Text`属性绑定到相同的源属性。 <xref:System.Windows.Controls.TextBox>绑定的<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>属性设置为<xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>。  
  
 [!code-xaml[SimpleBinding#USTHowTo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]  
  
 因此，<xref:System.Windows.Controls.TextBlock>在用户输入文本到<xref:System.Windows.Controls.TextBox>时显示相同的文本 （因为源发生了更改），如下面的屏幕截图中的示例所示：  
  
 ![简单数据绑定示例屏幕快照](../../../../docs/framework/wpf/data/media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")  
  
 如果你有一个对话框或用户可编辑窗体，并且您想要延迟源更新，直到用户完成字段的编辑，并单击"确定"，你可以设置绑定的<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>为<xref:System.Windows.Data.UpdateSourceTrigger.Explicit>，如下面的示例所示：  
  
 [!code-xaml[UpdateSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]  
  
 当你将设置<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>的值为<xref:System.Windows.Data.UpdateSourceTrigger.Explicit>，源值只会在应用程序调用<xref:System.Windows.Data.BindingExpression.UpdateSource%2A>方法时更改。 下面的示例演示如何为`itemNameTextBox`调用<xref:System.Windows.Data.BindingExpression.UpdateSource%2A>:  
  
 [!code-csharp[UpdateSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]  
  
> [!NOTE]
>  你可以对其他控件的属性使用相同的技术，但请记住其他大多数属性的<xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>的默认值为<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>。 有关详细信息，请参阅<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>属性页。  
  
> [!NOTE]
>  <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>属性用于处理源更新并且因此仅适用于<xref:System.Windows.Data.BindingMode.TwoWay>或<xref:System.Windows.Data.BindingMode.OneWayToSource>绑定。 为了使<xref:System.Windows.Data.BindingMode.TwoWay>和<xref:System.Windows.Data.BindingMode.OneWayToSource>绑定生效，源对象需要提供属性更改通知。 有关详细信息，可以参见本主题中引用的示例。 此外，也可以参见[实现属性更改通知](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md)。  
  
## <a name="see-also"></a>请参阅  
 [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
