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
ms.openlocfilehash: 8c7fd54931fad060a5d78e4c47c2cfce2767025a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355241"
---
# <a name="how-to-extract-the-text-content-from-a-richtextbox"></a><span data-ttu-id="4ece6-102">如何：从 RichTextBox 中提取文本内容</span><span class="sxs-lookup"><span data-stu-id="4ece6-102">How to: Extract the Text Content from a RichTextBox</span></span>
<span data-ttu-id="4ece6-103">此示例演示如何将内容提取<xref:System.Windows.Controls.RichTextBox>以纯文本格式。</span><span class="sxs-lookup"><span data-stu-id="4ece6-103">This example shows how to extract the contents of a <xref:System.Windows.Controls.RichTextBox> as plain text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ece6-104">示例</span><span class="sxs-lookup"><span data-stu-id="4ece6-104">Example</span></span>  
 <span data-ttu-id="4ece6-105">以下[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]代码描述命名<xref:System.Windows.Controls.RichTextBox>具有简单内容的控件。</span><span class="sxs-lookup"><span data-stu-id="4ece6-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a named <xref:System.Windows.Controls.RichTextBox> control with simple content.</span></span>  
  
 [!code-xaml[RichTextBoxSnippets#_RTB_XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## <a name="example"></a><span data-ttu-id="4ece6-106">示例</span><span class="sxs-lookup"><span data-stu-id="4ece6-106">Example</span></span>  
 <span data-ttu-id="4ece6-107">下面的代码实现采用的方法<xref:System.Windows.Controls.RichTextBox>作为参数，并返回一个字符串，表示的纯文本内容<xref:System.Windows.Controls.RichTextBox>。</span><span class="sxs-lookup"><span data-stu-id="4ece6-107">The following code implements a method that takes a <xref:System.Windows.Controls.RichTextBox> as an argument, and returns a string representing the plain text contents of the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="4ece6-108">该方法创建一个新<xref:System.Windows.Documents.TextRange>中的内容<xref:System.Windows.Controls.RichTextBox>，并使用<xref:System.Windows.Documents.FlowDocument.ContentStart%2A>和<xref:System.Windows.Documents.FlowDocument.ContentEnd%2A>以指示要提取的内容的范围。</span><span class="sxs-lookup"><span data-stu-id="4ece6-108">The method creates a new <xref:System.Windows.Documents.TextRange> from the contents of the <xref:System.Windows.Controls.RichTextBox>, using the <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> and <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> to indicate the range of the contents to extract.</span></span>  <span data-ttu-id="4ece6-109"><xref:System.Windows.Documents.FlowDocument.ContentStart%2A> 并<xref:System.Windows.Documents.FlowDocument.ContentEnd%2A>每个属性返回<xref:System.Windows.Documents.TextPointer>，并可以访问在表示的内容基础 FlowDocument <xref:System.Windows.Controls.RichTextBox>。</span><span class="sxs-lookup"><span data-stu-id="4ece6-109"><xref:System.Windows.Documents.FlowDocument.ContentStart%2A> and <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> properties each return a <xref:System.Windows.Documents.TextPointer>, and are accessible on the underlying FlowDocument that represents the contents of the <xref:System.Windows.Controls.RichTextBox>.</span></span>  <span data-ttu-id="4ece6-110"><xref:System.Windows.Documents.TextRange> 提供文本属性，返回的纯文本部分<xref:System.Windows.Documents.TextRange>作为字符串。</span><span class="sxs-lookup"><span data-stu-id="4ece6-110"><xref:System.Windows.Documents.TextRange> provides a Text property, which returns the plain text portions of the <xref:System.Windows.Documents.TextRange> as a string.</span></span>  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## <a name="see-also"></a><span data-ttu-id="4ece6-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ece6-111">See also</span></span>
- [<span data-ttu-id="4ece6-112">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="4ece6-112">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="4ece6-113">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="4ece6-113">TextBox Overview</span></span>](textbox-overview.md)
