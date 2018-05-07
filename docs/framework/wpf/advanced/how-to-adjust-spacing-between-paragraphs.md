---
title: 如何：调整段落间的间距
ms.date: 03/30/2017
helpviewer_keywords:
- spacing between paragraphs [WPF]
- paragraphs [WPF], spacing between
- documents [WPF], adjusting spacing between paragraphs
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
ms.openlocfilehash: b232903054cf45b70ba99a9223352391498cf79b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-adjust-spacing-between-paragraphs"></a>如何：调整段落间的间距
此示例演示如何调整或消除在流内容中的段落之间的间距。  
  
 在流内容段落之间出现的额外空间是距这些段落; 上设置的结果因此，可以通过调整这些段落上的边距控制段落之间的间距。  若要完全消除两个段落的额外间距，请将设置到段落的边距**0**。  若要实现在整个整个段落的统一间距<xref:System.Windows.Documents.FlowDocument>，使用样式来设置中的所有段落一个统一的边距值<xref:System.Windows.Documents.FlowDocument>。  
  
 请务必注意，两个相邻段落的边距将"折叠"较大的两个边距，而不是相加。 因此，如果两个相邻段落分别具有 20 像素和 40 个像素的边距，段落之间生成的空间将是 40 像素，较大的两个边距值。  
  
## <a name="example"></a>示例  
 下面的示例使用样式来将边距设置所有<xref:System.Windows.Documents.Paragraph>中的元素<xref:System.Windows.Documents.FlowDocument>到**0**，这有效地消除段落中的额外间距<xref:System.Windows.Documents.FlowDocument>。  
  
 [!code-xaml[BlockSnippets#_ParagraphSpacingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]
