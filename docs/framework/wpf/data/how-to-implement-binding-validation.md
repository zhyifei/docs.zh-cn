---
title: "如何：实现绑定验证"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ec860cc9cc58febd98d8642c98a50ec296592d02
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-binding-validation"></a>如何：实现绑定验证
此示例演示如何使用<xref:System.Windows.Controls.Validation.ErrorTemplate%2A>和样式触发器，以提供可视反馈以通知用户输入无效值后，基于自定义验证规则。  
  
## <a name="example"></a>示例  
 文本内容<xref:System.Windows.Controls.TextBox>在下面的示例将绑定到`Age`属性 （类型为 int) 的名为的绑定源对象`ods`。 该绑定设置为使用名为 `AgeRangeRule` 的验证规则，以便当用户输入了非数值字符或输入的值小于 21 或者大于 130 时，文本框旁边将显示一个红色感叹号，并且当用户将鼠标移动到该文本框上时，将显示包含错误消息的工具提示。  
  
 [!code-xaml[BindValidation#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]  
  
 下面的示例演示的实现`AgeRangeRule`，它继承自<xref:System.Windows.Controls.ValidationRule>和替代<xref:System.Windows.Controls.ValidationRule.Validate%2A>方法。 对值调用 Int32.Parse() 方法，以确保该值不包含任何无效字符。 <xref:System.Windows.Controls.ValidationRule.Validate%2A>方法返回<xref:System.Windows.Controls.ValidationResult>，该值指示值是否有效基于是否捕获了一个异常在分析过程以及保存期限值是否是外部下限和上限。  
  
 [!code-csharp[BindValidation#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]  
  
 下面的示例演示了自定义<xref:System.Windows.Controls.ControlTemplate>`validationTemplate`创建一个红色的感叹号通知用户的验证错误。 控件模板用于重新定义控件的外观。  
  
 [!code-xaml[BindValidation#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]  
  
 下面的示例中所示<xref:System.Windows.Controls.ToolTip>，显示错误消息创建使用名为的样式`textBoxInError`。 如果值<xref:System.Windows.Controls.Validation.HasError%2A>是`true`，触发器设置当前的工具提示<xref:System.Windows.Controls.TextBox>到其第一个验证错误。 <xref:System.Windows.Data.Binding.RelativeSource%2A>设置为<xref:System.Windows.Data.RelativeSourceMode.Self>，以引用当前元素。  
  
 [!code-xaml[BindValidation#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]  
  
 有关完整示例，请参阅[绑定验证示例](http://go.microsoft.com/fwlink/?LinkID=159972)。  
  
 请注意，如果未提供自定义<xref:System.Windows.Controls.Validation.ErrorTemplate%2A>默认错误模板会显示验证错误时向用户提供可视反馈。 有关详细信息，请参阅[数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)中的“数据验证”。 另外，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 还提供了内置验证规则，该规则捕获在更新绑定源属性期间引发的异常。 有关更多信息，请参见<xref:System.Windows.Controls.ExceptionValidationRule>。  
  
## <a name="see-also"></a>另请参阅  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [操作说明主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
