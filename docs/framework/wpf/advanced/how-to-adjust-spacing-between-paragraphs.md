---
title: "如何：调整段落间的间距"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- spacing between paragraphs [WPF]
- paragraphs [WPF], spacing between
- documents [WPF], adjusting spacing between paragraphs
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1936426b44ed667d03e4881e66a081d5097a2880
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-adjust-spacing-between-paragraphs"></a><span data-ttu-id="47472-102">如何：调整段落间的间距</span><span class="sxs-lookup"><span data-stu-id="47472-102">How to: Adjust Spacing Between Paragraphs</span></span>
<span data-ttu-id="47472-103">此示例演示如何调整或消除在流内容中的段落之间的间距。</span><span class="sxs-lookup"><span data-stu-id="47472-103">This example shows how to adjust or eliminate spacing between paragraphs in flow content.</span></span>  
  
 <span data-ttu-id="47472-104">在流内容段落之间出现的额外空间是距这些段落; 上设置的结果因此，可以通过调整这些段落上的边距控制段落之间的间距。</span><span class="sxs-lookup"><span data-stu-id="47472-104">In flow content, extra space that appears between paragraphs is the result of margins set on these paragraphs; thus, the spacing between paragraphs can be controlled by adjusting the margins on those paragraphs.</span></span>  <span data-ttu-id="47472-105">若要完全消除两个段落的额外间距，请将设置到段落的边距**0**。</span><span class="sxs-lookup"><span data-stu-id="47472-105">To eliminate extra spacing between two paragraphs altogether, set the margins for the paragraphs to **0**.</span></span>  <span data-ttu-id="47472-106">若要实现在整个整个段落的统一间距<xref:System.Windows.Documents.FlowDocument>，使用样式来设置中的所有段落一个统一的边距值<xref:System.Windows.Documents.FlowDocument>。</span><span class="sxs-lookup"><span data-stu-id="47472-106">To achieve uniform spacing between paragraphs throughout an entire <xref:System.Windows.Documents.FlowDocument>, use styling to set a uniform margin value for all paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 <span data-ttu-id="47472-107">请务必注意，两个相邻段落的边距将"折叠"较大的两个边距，而不是相加。</span><span class="sxs-lookup"><span data-stu-id="47472-107">It is important to note that the margins for two adjacent paragraphs will "collapse" to the larger of the two margins, rather than doubling up.</span></span> <span data-ttu-id="47472-108">因此，如果两个相邻段落分别具有 20 像素和 40 个像素的边距，段落之间生成的空间将是 40 像素，较大的两个边距值。</span><span class="sxs-lookup"><span data-stu-id="47472-108">So, if two adjacent paragraphs have margins of 20 pixels and 40 pixels respectively, the resulting space between the paragraphs is 40 pixels, the larger of the two margin values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47472-109">示例</span><span class="sxs-lookup"><span data-stu-id="47472-109">Example</span></span>  
 <span data-ttu-id="47472-110">下面的示例使用样式来将边距设置所有<xref:System.Windows.Documents.Paragraph>中的元素<xref:System.Windows.Documents.FlowDocument>到**0**，这有效地消除段落中的额外间距<xref:System.Windows.Documents.FlowDocument>。</span><span class="sxs-lookup"><span data-stu-id="47472-110">The following example uses styling to set the margin for all <xref:System.Windows.Documents.Paragraph> elements in a <xref:System.Windows.Documents.FlowDocument> to **0**, which effectively eliminates extra spacing between paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-xaml[BlockSnippets#_ParagraphSpacingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]
