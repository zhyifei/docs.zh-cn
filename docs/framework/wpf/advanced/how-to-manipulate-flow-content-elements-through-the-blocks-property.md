---
title: 如何：通过 Blocks 属性操作流内容元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], manipulating flow content elements through Blocks property
- flow content elements [WPF], manipulating through Blocks property
- properties [WPF], Blocks [WPF], manipulating flow content elements
- Blocks property [WPF], manipulating flow content elements
ms.assetid: aeda4ece-b979-4818-a093-ef938e908751
ms.openlocfilehash: 74710c4a6dd58cf2836cd7671a3e39401a5ea774
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544545"
---
# <a name="how-to-manipulate-flow-content-elements-through-the-blocks-property"></a><span data-ttu-id="3befa-102">如何：通过 Blocks 属性操作流内容元素</span><span class="sxs-lookup"><span data-stu-id="3befa-102">How to: Manipulate Flow Content Elements through the Blocks Property</span></span>
<span data-ttu-id="3befa-103">这些示例演示一些较常见的操作，可以通过流内容元素对执行**块**属性。</span><span class="sxs-lookup"><span data-stu-id="3befa-103">These examples demonstrate some of the more common operations that can be performed on flow content elements through the **Blocks** property.</span></span> <span data-ttu-id="3befa-104">此属性用于添加和移除项从<xref:System.Windows.Documents.BlockCollection>。</span><span class="sxs-lookup"><span data-stu-id="3befa-104">This property is used to add and remove items from <xref:System.Windows.Documents.BlockCollection>.</span></span> <span data-ttu-id="3befa-105">流内容元素，该功能**块**属性包括：</span><span class="sxs-lookup"><span data-stu-id="3befa-105">Flow content elements that feature a **Blocks** property include:</span></span>  
  
-   <xref:System.Windows.Documents.Figure>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.ListItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
 <span data-ttu-id="3befa-106">这些示例碰巧使用<xref:System.Windows.Documents.Section>作为流内容元素，但是，这些技术是适用于承载流内容元素集合的所有元素。</span><span class="sxs-lookup"><span data-stu-id="3befa-106">These examples happen to use <xref:System.Windows.Documents.Section> as the flow content element, but these techniques are applicable to all elements that host a flow content element collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3befa-107">示例</span><span class="sxs-lookup"><span data-stu-id="3befa-107">Example</span></span>  
 <span data-ttu-id="3befa-108">下面的示例创建一个新<xref:System.Windows.Documents.Section>，然后使用**添加**方法将添加到新段落**部分**内容。</span><span class="sxs-lookup"><span data-stu-id="3befa-108">The following example creates a new <xref:System.Windows.Documents.Section> and then uses the **Add** method to add a new Paragraph to the **Section** contents.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
## <a name="example"></a><span data-ttu-id="3befa-109">示例</span><span class="sxs-lookup"><span data-stu-id="3befa-109">Example</span></span>  
 <span data-ttu-id="3befa-110">下面的示例创建一个新<xref:System.Windows.Documents.Paragraph>元素并将其插入的开始处<xref:System.Windows.Documents.Section>。</span><span class="sxs-lookup"><span data-stu-id="3befa-110">The following example creates a new <xref:System.Windows.Documents.Paragraph> element and inserts it at the beginning of the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksinsert)]  
  
## <a name="example"></a><span data-ttu-id="3befa-111">示例</span><span class="sxs-lookup"><span data-stu-id="3befa-111">Example</span></span>  
 <span data-ttu-id="3befa-112">下面的示例获取的顶级数<xref:System.Windows.Documents.Block>中所含元素<xref:System.Windows.Documents.Section>。</span><span class="sxs-lookup"><span data-stu-id="3befa-112">The following example gets the number of top-level <xref:System.Windows.Documents.Block> elements contained in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblockscount)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblockscount)]  
  
## <a name="example"></a><span data-ttu-id="3befa-113">示例</span><span class="sxs-lookup"><span data-stu-id="3befa-113">Example</span></span>  
 <span data-ttu-id="3befa-114">以下示例将删除最后一个<xref:System.Windows.Documents.Block>中的元素<xref:System.Windows.Documents.Section>。</span><span class="sxs-lookup"><span data-stu-id="3befa-114">The following example deletes the last <xref:System.Windows.Documents.Block> element in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksremovelast)]  
  
## <a name="example"></a><span data-ttu-id="3befa-115">示例</span><span class="sxs-lookup"><span data-stu-id="3befa-115">Example</span></span>  
 <span data-ttu-id="3befa-116">下面的示例清除的所有内容 (<xref:System.Windows.Documents.Block>元素) 从<xref:System.Windows.Documents.Section>。</span><span class="sxs-lookup"><span data-stu-id="3befa-116">The following example clears all of the contents (<xref:System.Windows.Documents.Block> elements) from the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksclear)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksclear)]  
  
## <a name="see-also"></a><span data-ttu-id="3befa-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="3befa-117">See Also</span></span>  
 <xref:System.Windows.Documents.BlockCollection>  
 <xref:System.Windows.Documents.InlineCollection>  
 <xref:System.Windows.Documents.ListItemCollection>  
 [<span data-ttu-id="3befa-118">流文档概述</span><span class="sxs-lookup"><span data-stu-id="3befa-118">Flow Document Overview</span></span>](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [<span data-ttu-id="3befa-119">通过 RowGroups 属性操作表的行组</span><span class="sxs-lookup"><span data-stu-id="3befa-119">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)  
 [<span data-ttu-id="3befa-120">通过 Columns 属性控制表列</span><span class="sxs-lookup"><span data-stu-id="3befa-120">Manipulate a Table's Columns through the Columns Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)  
 [<span data-ttu-id="3befa-121">通过 RowGroups 属性操作表的行组</span><span class="sxs-lookup"><span data-stu-id="3befa-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
