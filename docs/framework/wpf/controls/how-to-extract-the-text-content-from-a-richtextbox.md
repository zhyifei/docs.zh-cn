---
title: 如何：从 RichTextBox 中提取文本内容
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], extracting
- RichTextBox control [WPF], extracting text content
- content [WPF], extracting
- extracting text content [WPF]
ms.assetid: f13c093f-1a05-45b3-ac8f-c9ea5e4a11c5
ms.openlocfilehash: 309fe15c76c17a79e11341f3a50c0bf5a7a2cc21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33553931"
---
# <a name="how-to-extract-the-text-content-from-a-richtextbox"></a>如何：从 RichTextBox 中提取文本内容
此示例演示如何将内容提取<xref:System.Windows.Controls.RichTextBox>作为纯文本。  
  
## <a name="example"></a>示例  
 以下[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]代码描述命名<xref:System.Windows.Controls.RichTextBox>具有简单内容的控件。  
  
 [!code-xaml[RichTextBoxSnippets#_RTB_XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## <a name="example"></a>示例  
 下面的代码实现采用的方法<xref:System.Windows.Controls.RichTextBox>作为自变量，并返回一个字符串，表示的纯文本内容<xref:System.Windows.Controls.RichTextBox>。  
  
 该方法将创建一个新<xref:System.Windows.Documents.TextRange>的内容<xref:System.Windows.Controls.RichTextBox>，使用<xref:System.Windows.Documents.FlowDocument.ContentStart%2A>和<xref:System.Windows.Documents.FlowDocument.ContentEnd%2A>来表示要提取的内容的范围。  <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> 和<xref:System.Windows.Documents.FlowDocument.ContentEnd%2A>每个属性返回<xref:System.Windows.Documents.TextPointer>，和可以访问在表示的内容基础 FlowDocument <xref:System.Windows.Controls.RichTextBox>。  <xref:System.Windows.Documents.TextRange> 提供一个 Text 属性，它返回的纯文本部分<xref:System.Windows.Documents.TextRange>作为字符串。  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## <a name="see-also"></a>请参阅  
 [RichTextBox 概述](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [TextBox 概述](../../../../docs/framework/wpf/controls/textbox-overview.md)
