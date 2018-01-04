---
title: "如何：通过 Blocks 属性操作 FlowDocument"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'documents [WPF], manipulating FlowDocuments through Blocks property [WPF], , '
- ', '
ms.assetid: cbb7291e-3f1b-433e-9e16-f4d93ced14e8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8f6ea0a1ada69c33a738985c5340aab94453e895
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-manipulate-a-flowdocument-through-the-blocks-property"></a><span data-ttu-id="e8f9f-102">如何：通过 Blocks 属性操作 FlowDocument</span><span class="sxs-lookup"><span data-stu-id="e8f9f-102">How to: Manipulate a FlowDocument through the Blocks Property</span></span>
<span data-ttu-id="e8f9f-103">这些示例演示一些较常见的操作，可以对执行<xref:System.Windows.Documents.FlowDocument>通过<xref:System.Windows.Documents.FlowDocument.Blocks%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="e8f9f-103">These examples demonstrate some of the more common operations that can be performed on a <xref:System.Windows.Documents.FlowDocument> through the <xref:System.Windows.Documents.FlowDocument.Blocks%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8f9f-104">示例</span><span class="sxs-lookup"><span data-stu-id="e8f9f-104">Example</span></span>  
 <span data-ttu-id="e8f9f-105">下面的示例创建一个新<xref:System.Windows.Documents.FlowDocument>，然后追加一个新<xref:System.Windows.Documents.Paragraph>元素<xref:System.Windows.Documents.FlowDocument>。</span><span class="sxs-lookup"><span data-stu-id="e8f9f-105">The following example creates a new <xref:System.Windows.Documents.FlowDocument> and then appends a new <xref:System.Windows.Documents.Paragraph> element to the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksadd)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksadd)]  
  
## <a name="example"></a><span data-ttu-id="e8f9f-106">示例</span><span class="sxs-lookup"><span data-stu-id="e8f9f-106">Example</span></span>  
 <span data-ttu-id="e8f9f-107">下面的示例创建一个新<xref:System.Windows.Documents.Paragraph>元素并将其插入的开始处<xref:System.Windows.Documents.FlowDocument>。</span><span class="sxs-lookup"><span data-stu-id="e8f9f-107">The following example creates a new <xref:System.Windows.Documents.Paragraph> element and inserts it at the beginning of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksinsert)]  
  
## <a name="example"></a><span data-ttu-id="e8f9f-108">示例</span><span class="sxs-lookup"><span data-stu-id="e8f9f-108">Example</span></span>  
 <span data-ttu-id="e8f9f-109">下面的示例获取的顶级数<xref:System.Windows.Documents.Block>中所含元素<xref:System.Windows.Documents.FlowDocument>。</span><span class="sxs-lookup"><span data-stu-id="e8f9f-109">The following example gets the number of top-level <xref:System.Windows.Documents.Block> elements contained in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblockscount)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblockscount)]  
  
## <a name="example"></a><span data-ttu-id="e8f9f-110">示例</span><span class="sxs-lookup"><span data-stu-id="e8f9f-110">Example</span></span>  
 <span data-ttu-id="e8f9f-111">以下示例将删除最后一个<xref:System.Windows.Documents.Block>中的元素<xref:System.Windows.Documents.FlowDocument>。</span><span class="sxs-lookup"><span data-stu-id="e8f9f-111">The following example deletes the last <xref:System.Windows.Documents.Block> element in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksremovelast)]  
  
## <a name="example"></a><span data-ttu-id="e8f9f-112">示例</span><span class="sxs-lookup"><span data-stu-id="e8f9f-112">Example</span></span>  
 <span data-ttu-id="e8f9f-113">下面的示例清除的所有内容 (<xref:System.Windows.Documents.Block>元素) 从<xref:System.Windows.Documents.FlowDocument>。</span><span class="sxs-lookup"><span data-stu-id="e8f9f-113">The following example clears all of the contents (<xref:System.Windows.Documents.Block> elements) from the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksclear)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksclear)]  
  
## <a name="see-also"></a><span data-ttu-id="e8f9f-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="e8f9f-114">See Also</span></span>  
 [<span data-ttu-id="e8f9f-115">通过 RowGroups 属性操作表的行组</span><span class="sxs-lookup"><span data-stu-id="e8f9f-115">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)  
 [<span data-ttu-id="e8f9f-116">通过 Columns 属性控制表列</span><span class="sxs-lookup"><span data-stu-id="e8f9f-116">Manipulate a Table's Columns through the Columns Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)  
 [<span data-ttu-id="e8f9f-117">通过 RowGroups 属性操作表的行组</span><span class="sxs-lookup"><span data-stu-id="e8f9f-117">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
