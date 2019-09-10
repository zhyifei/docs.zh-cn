---
title: 如何：检测 TextBox 中的文本何时更改
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
ms.openlocfilehash: 8c7744e9e61b8ba796802e54435c0bf9fdbee50e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855617"
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a>如何：检测 TextBox 中的文本何时更改

此示例演示一种在<xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> <xref:System.Windows.Controls.TextBox>控件中的文本发生更改时使用事件执行方法的一种方法。

在[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 包含要监视其<xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>更改的控件的代码隐藏类中，插入每当事件激发时要调用的方法。<xref:System.Windows.Controls.TextBox>  此方法的签名必须与<xref:System.Windows.Controls.TextChangedEventHandler>委托所需的签名相匹配。

只要用户或以编程方式更改<xref:System.Windows.Controls.TextBox>控件的内容，就会调用事件处理程序。

> [!NOTE]
> 此事件在创建<xref:System.Windows.Controls.TextBox>控件时和最初用文本填充时引发。

## <a name="example"></a>示例

在定义控件的中，使用与事件<xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>处理程序方法名称匹配的值指定特性。 <xref:System.Windows.Controls.TextBox> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]

[!code-xaml[TextBox_MiscCode#_TextChangedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]

## <a name="example"></a>示例

在[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 包含要监视其<xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>更改的控件的代码隐藏类中，插入每当事件激发时要调用的方法。<xref:System.Windows.Controls.TextBox>  此方法的签名必须与<xref:System.Windows.Controls.TextChangedEventHandler>委托所需的签名相匹配。

[!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
[!code-vb[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]

只要用户或以编程方式更改<xref:System.Windows.Controls.TextBox>控件的内容，就会调用事件处理程序。

> [!NOTE]
> 此事件在创建<xref:System.Windows.Controls.TextBox>控件时和最初用文本填充时引发。

注释

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.TextChangedEventArgs>
- [TextBox 概述](textbox-overview.md)
- [RichTextBox 概述](richtextbox-overview.md)
