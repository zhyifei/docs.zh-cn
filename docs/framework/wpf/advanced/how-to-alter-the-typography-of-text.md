---
title: 操作说明：修改文本的版式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- setting Typography attributes [WPF]
- Typography attribute [WPF], setting
ms.assetid: 19a3b49b-60a2-4c11-a786-e26b4c965588
ms.openlocfilehash: eeed93f62802a942915511db060c0e6c029579e0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365772"
---
# <a name="how-to-alter-the-typography-of-text"></a><span data-ttu-id="ba4a8-102">操作说明：修改文本的版式</span><span class="sxs-lookup"><span data-stu-id="ba4a8-102">How-to: Alter the Typography of Text</span></span>
<span data-ttu-id="ba4a8-103">下面的示例演示如何设置<xref:System.Windows.Documents.TextElement.Typography%2A>属性，使用<xref:System.Windows.Documents.Paragraph>作为示例元素。</span><span class="sxs-lookup"><span data-stu-id="ba4a8-103">The following example shows how to set the <xref:System.Windows.Documents.TextElement.Typography%2A> attribute, using <xref:System.Windows.Documents.Paragraph> as the example element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba4a8-104">示例</span><span class="sxs-lookup"><span data-stu-id="ba4a8-104">Example</span></span>  
 [!code-xaml[TextElementSnippets#_TextElement_TypogXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 <span data-ttu-id="ba4a8-105">下图显示了此示例的呈现效果。</span><span class="sxs-lookup"><span data-stu-id="ba4a8-105">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="ba4a8-106">![屏幕快照：改变版式的文本](./media/textelement-typog.png "TextElement_Typog")</span><span class="sxs-lookup"><span data-stu-id="ba4a8-106">![Screenshot: Text with altered typography](./media/textelement-typog.png "TextElement_Typog")</span></span>  
  
 <span data-ttu-id="ba4a8-107">与此相反，下图显示了一个具有默认版式属性的类似示例的呈现效果。</span><span class="sxs-lookup"><span data-stu-id="ba4a8-107">In contrast, the following figure shows how a similar example with default typographic properties renders.</span></span>  
  
 <span data-ttu-id="ba4a8-108">![屏幕快照：改变版式的文本](./media/textelement-typog-default.png "TextElement_Typog_Default")</span><span class="sxs-lookup"><span data-stu-id="ba4a8-108">![Screenshot: Text with altered typography](./media/textelement-typog-default.png "TextElement_Typog_Default")</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba4a8-109">示例</span><span class="sxs-lookup"><span data-stu-id="ba4a8-109">Example</span></span>  
 <span data-ttu-id="ba4a8-110">下面的示例演示如何设置<xref:System.Windows.Controls.TextBox.Typography%2A>属性以编程方式。</span><span class="sxs-lookup"><span data-stu-id="ba4a8-110">The following example shows how to set the <xref:System.Windows.Controls.TextBox.Typography%2A> property programmatically.</span></span>  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
## <a name="see-also"></a><span data-ttu-id="ba4a8-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba4a8-111">See also</span></span>
- [<span data-ttu-id="ba4a8-112">流文档概述</span><span class="sxs-lookup"><span data-stu-id="ba4a8-112">Flow Document Overview</span></span>](flow-document-overview.md)
