---
title: 如何：实现绑定验证
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
ms.openlocfilehash: 245b05d9cfa7ca66dec310bd9a5291def0101d19
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459112"
---
# <a name="how-to-implement-binding-validation"></a>如何：实现绑定验证

此示例演示如何使用 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 和样式触发器来提供可视反馈，以根据自定义验证规则输入无效值时通知用户。

## <a name="example"></a>示例

以下示例中 <xref:System.Windows.Controls.TextBox> 的文本内容绑定到名为 `ods`的绑定源对象的 `Age` 属性（类型为 int）。 该绑定设置为使用名为 `AgeRangeRule` 的验证规则，以便当用户输入了非数值字符或输入的值小于 21 或者大于 130 时，文本框旁边将显示一个红色感叹号，并且当用户将鼠标移动到该文本框上时，将显示包含错误消息的工具提示。

[!code-xaml[BindValidation#2](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]

下面的示例演示 `AgeRangeRule`的实现，该实现继承自 <xref:System.Windows.Controls.ValidationRule> 并覆盖 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 方法。 对值调用 `Int32.Parse` 方法，以确保它不包含任何无效字符。 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 方法返回一个 <xref:System.Windows.Controls.ValidationResult>，该值指示此值是否有效，这是因为在分析期间是否捕获到了异常以及 age 值是否超出了下限和上限。

[!code-csharp[BindValidation#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]
[!code-vb[BindValidation#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindValidation/VisualBasic/AgeRangeRule.vb#3)]

下面的示例演示了自定义 <xref:System.Windows.Controls.ControlTemplate> `validationTemplate`，该自定义创建一个红色感叹号来通知用户验证错误。 控件模板用于重新定义控件的外观。

[!code-xaml[BindValidation#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]

如下面的示例中所示，将使用名为 `textBoxInError`的样式创建显示错误消息的 <xref:System.Windows.Controls.ToolTip>。 如果 <xref:System.Windows.Controls.Validation.HasError%2A> 的值 `true`，则触发器会将当前 <xref:System.Windows.Controls.TextBox> 的工具提示设置为其第一个验证错误。 <xref:System.Windows.Data.Binding.RelativeSource%2A> 设置为 <xref:System.Windows.Data.RelativeSourceMode.Self>，引用当前元素。

[!code-xaml[BindValidation#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]

有关完整的示例，请参阅[绑定验证示例](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation)。
  
请注意，如果未提供自定义 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 默认错误模板会出现，以便在出现验证错误时向用户提供视觉反馈。 有关详细信息，请参阅[数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)中的“数据验证”。 另外，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 还提供了内置验证规则，该规则捕获在更新绑定源属性期间引发的异常。 有关更多信息，请参见<xref:System.Windows.Controls.ExceptionValidationRule>。

## <a name="see-also"></a>请参阅

- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [帮助主题](data-binding-how-to-topics.md)
