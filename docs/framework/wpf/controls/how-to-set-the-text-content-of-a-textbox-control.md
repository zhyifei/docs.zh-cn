---
title: 如何：设置 TextBox 控件的文本内容
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], setting
- TextBox control [WPF], setting text content
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
ms.openlocfilehash: 2e2bc70b108991fd4e3c138bfac5bff942173e33
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70856110"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a>如何：设置 TextBox 控件的文本内容

此示例演示如何使用<xref:System.Windows.Controls.TextBox.Text%2A>属性来设置<xref:System.Windows.Controls.TextBox>控件的初始文本内容。

> [!NOTE]
> <xref:System.Windows.Markup.ContentPropertyAttribute> <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.TextBox.Text%2A> <xref:System.Windows.Controls.TextBox>尽管该示例的`<TextBox.Text>`版本可以在每个按钮内容的文本周围使用标记，但这并不是必需的，因为将特性应用于属性[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. 有关详细信息, 请参阅[XAML 概述 (WPF)](../advanced/xaml-overview-wpf.md)。

## <a name="example"></a>示例

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a>示例

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a>请参阅

- [TextBox 概述](textbox-overview.md)
- [RichTextBox 概述](richtextbox-overview.md)
