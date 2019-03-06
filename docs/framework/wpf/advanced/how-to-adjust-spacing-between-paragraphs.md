---
title: 如何：调整段落间的间距
ms.date: 03/30/2017
helpviewer_keywords:
- spacing between paragraphs [WPF]
- paragraphs [WPF], spacing between
- documents [WPF], adjusting spacing between paragraphs
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
ms.openlocfilehash: e2a6ba34e3ab15eb316671fef7c11bea03d53c73
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367474"
---
# <a name="how-to-adjust-spacing-between-paragraphs"></a><span data-ttu-id="97692-102">如何：调整段落间的间距</span><span class="sxs-lookup"><span data-stu-id="97692-102">How to: Adjust Spacing Between Paragraphs</span></span>
<span data-ttu-id="97692-103">此示例演示如何以调整或消除在流内容中的段落间的间距。</span><span class="sxs-lookup"><span data-stu-id="97692-103">This example shows how to adjust or eliminate spacing between paragraphs in flow content.</span></span>  
  
 <span data-ttu-id="97692-104">在流内容中显示段落间的额外空间是这些段落; 上设置的边距的结果因此，可以通过调整这些段落上的边距控制段落间的间距。</span><span class="sxs-lookup"><span data-stu-id="97692-104">In flow content, extra space that appears between paragraphs is the result of margins set on these paragraphs; thus, the spacing between paragraphs can be controlled by adjusting the margins on those paragraphs.</span></span>  <span data-ttu-id="97692-105">若要完全消除两个段落间的额外间距，请将设置到段落的边距**0**。</span><span class="sxs-lookup"><span data-stu-id="97692-105">To eliminate extra spacing between two paragraphs altogether, set the margins for the paragraphs to **0**.</span></span>  <span data-ttu-id="97692-106">若要实现在整个整个段落间的统一间距<xref:System.Windows.Documents.FlowDocument>，使用样式设置中的所有段落的统一边距值<xref:System.Windows.Documents.FlowDocument>。</span><span class="sxs-lookup"><span data-stu-id="97692-106">To achieve uniform spacing between paragraphs throughout an entire <xref:System.Windows.Documents.FlowDocument>, use styling to set a uniform margin value for all paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 <span data-ttu-id="97692-107">请务必注意，两个相邻的段落的边距将会"折叠"到较大的两个边距，而不是相加。</span><span class="sxs-lookup"><span data-stu-id="97692-107">It is important to note that the margins for two adjacent paragraphs will "collapse" to the larger of the two margins, rather than doubling up.</span></span> <span data-ttu-id="97692-108">因此，如果两个相邻段落分别有 20 个像素和 40 个像素的边距，请在段落间的生成空间是 40 个像素，较大的两个边距值。</span><span class="sxs-lookup"><span data-stu-id="97692-108">So, if two adjacent paragraphs have margins of 20 pixels and 40 pixels respectively, the resulting space between the paragraphs is 40 pixels, the larger of the two margin values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97692-109">示例</span><span class="sxs-lookup"><span data-stu-id="97692-109">Example</span></span>  
 <span data-ttu-id="97692-110">下面的示例使用样式设置为所有设置边距<xref:System.Windows.Documents.Paragraph>中的元素<xref:System.Windows.Documents.FlowDocument>到**0**，从而有效地消除在段落间的额外间距<xref:System.Windows.Documents.FlowDocument>。</span><span class="sxs-lookup"><span data-stu-id="97692-110">The following example uses styling to set the margin for all <xref:System.Windows.Documents.Paragraph> elements in a <xref:System.Windows.Documents.FlowDocument> to **0**, which effectively eliminates extra spacing between paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-xaml[BlockSnippets#_ParagraphSpacingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]
