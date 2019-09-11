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
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a><span data-ttu-id="f0b3f-102">如何：设置 TextBox 控件的文本内容</span><span class="sxs-lookup"><span data-stu-id="f0b3f-102">How to: Set the Text Content of a TextBox Control</span></span>

<span data-ttu-id="f0b3f-103">此示例演示如何使用<xref:System.Windows.Controls.TextBox.Text%2A>属性来设置<xref:System.Windows.Controls.TextBox>控件的初始文本内容。</span><span class="sxs-lookup"><span data-stu-id="f0b3f-103">This example shows how to use the <xref:System.Windows.Controls.TextBox.Text%2A> property to set the initial text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>

> [!NOTE]
> <span data-ttu-id="f0b3f-104"><xref:System.Windows.Markup.ContentPropertyAttribute> <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.TextBox.Text%2A> <xref:System.Windows.Controls.TextBox>尽管该示例的`<TextBox.Text>`版本可以在每个按钮内容的文本周围使用标记，但这并不是必需的，因为将特性应用于属性[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0b3f-104">Although the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] version of the example could use the `<TextBox.Text>` tags around the text of each button's <xref:System.Windows.Controls.TextBox> content, it is not necessary because the <xref:System.Windows.Controls.TextBox> applies the <xref:System.Windows.Markup.ContentPropertyAttribute> attribute to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="f0b3f-105">有关详细信息, 请参阅[XAML 概述 (WPF)](../advanced/xaml-overview-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="f0b3f-105">For more information, see [XAML Overview (WPF)](../advanced/xaml-overview-wpf.md).</span></span>

## <a name="example"></a><span data-ttu-id="f0b3f-106">示例</span><span class="sxs-lookup"><span data-stu-id="f0b3f-106">Example</span></span>

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a><span data-ttu-id="f0b3f-107">示例</span><span class="sxs-lookup"><span data-stu-id="f0b3f-107">Example</span></span>

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a><span data-ttu-id="f0b3f-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0b3f-108">See also</span></span>

- [<span data-ttu-id="f0b3f-109">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="f0b3f-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="f0b3f-110">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="f0b3f-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
