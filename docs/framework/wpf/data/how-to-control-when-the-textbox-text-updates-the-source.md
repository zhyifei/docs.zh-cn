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
ms.openlocfilehash: b211eb67e3bac95f74255935a39cc0d6aec61531
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974786"
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a>如何：控制文本框文本更新源的时间
本主题介绍如何使用 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 属性控制绑定源更新的计时。 本主题使用 <xref:System.Windows.Controls.TextBox> 控件作为示例。

## <a name="example"></a>示例
 <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> 属性的默认 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 值为 <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>。 这意味着，如果应用程序具有包含数据绑定 <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> 属性的 <xref:System.Windows.Controls.TextBox>，则键入 <xref:System.Windows.Controls.TextBox> 的文本将不会更新源，直到 <xref:System.Windows.Controls.TextBox> 失去焦点为止（例如，当您单击 <xref:System.Windows.Controls.TextBox>上的 "离开" 时）。

 如果希望在键入时更新源，请将绑定的 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 设置为 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>。 在下面的示例中，突出显示的代码行显示 <xref:System.Windows.Controls.TextBox> 和 <xref:System.Windows.Controls.TextBlock> 的 `Text` 属性都绑定到同一个源属性。 <xref:System.Windows.Controls.TextBox> 绑定的 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 属性设置为 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>。

 [!code-xaml[SimpleBinding#USTHowTo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]

 因此，当用户向 <xref:System.Windows.Controls.TextBox>中输入文本时，<xref:System.Windows.Controls.TextBlock> 会显示相同的文本（因为源发生更改），如以下示例屏幕截图所示：

 ![显示简单数据绑定的屏幕截图。](./media/how-to-control-when-the-textbox-text-updates-the-source/data-binding-simple-binding-sample.png)

 如果您有一个对话框或用户可编辑的窗体，而您希望在用户完成编辑字段并单击 "确定" 之前延迟源更新，则可以将绑定的 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 值设置为 <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>，如以下示例中所示：

 [!code-xaml[UpdateSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]

 将 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 值设置为 <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>时，源值仅在应用程序调用 <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> 方法时才会发生更改。 下面的示例演示如何为 `itemNameTextBox`调用 <xref:System.Windows.Data.BindingExpression.UpdateSource%2A>：

 [!code-csharp[UpdateSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]

> [!NOTE]
> 您可以为其他控件的属性使用相同的技术，但请记住，大多数其他属性的默认 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 值都为 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>。 有关详细信息，请参阅 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 属性页。

> [!NOTE]
> <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 属性处理源更新，因此仅适用于 <xref:System.Windows.Data.BindingMode.TwoWay> 或 <xref:System.Windows.Data.BindingMode.OneWayToSource> 绑定。 要使 <xref:System.Windows.Data.BindingMode.TwoWay> 和 <xref:System.Windows.Data.BindingMode.OneWayToSource> 绑定正常工作，源对象需要提供属性更改通知。 有关详细信息，可以参见本主题中引用的示例。 此外，也可以参见[实现属性更改通知](how-to-implement-property-change-notification.md)。

## <a name="see-also"></a>请参阅

- [帮助主题](data-binding-how-to-topics.md)
