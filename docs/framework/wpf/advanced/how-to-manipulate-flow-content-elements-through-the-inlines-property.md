---
title: 如何：通过 Inlines 属性操作流内容元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flow content elements [WPF], manipulating through Inlines property
- documents [WPF], manipulating flow Content elements through Inlines property
- Inlines property [WPF], manipulating flow Content elements
- properties [WPF], Inlines [WPF], manipulating flow Content elements
ms.assetid: 510780d2-3da1-4360-8763-7054bda22ea3
ms.openlocfilehash: 3bbeac2eda8811939be3c710a8ce28349e7f0759
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545566"
---
# <a name="how-to-manipulate-flow-content-elements-through-the-inlines-property"></a><span data-ttu-id="d0ab1-102">如何：通过 Inlines 属性操作流内容元素</span><span class="sxs-lookup"><span data-stu-id="d0ab1-102">How to: Manipulate Flow Content Elements through the Inlines Property</span></span>
<span data-ttu-id="d0ab1-103">这些示例演示一些较常见可以在内联流内容元素执行的操作 (和容器的此类元素，如<xref:System.Windows.Controls.TextBlock>) 通过**内联**属性。</span><span class="sxs-lookup"><span data-stu-id="d0ab1-103">These examples demonstrate some of the more common operations that can be performed on inline flow content elements (and containers of such elements, such as <xref:System.Windows.Controls.TextBlock>) through the **Inlines** property.</span></span> <span data-ttu-id="d0ab1-104">此属性用于添加和移除项从<xref:System.Windows.Documents.InlineCollection>。</span><span class="sxs-lookup"><span data-stu-id="d0ab1-104">This property is used to add and remove items from <xref:System.Windows.Documents.InlineCollection>.</span></span> <span data-ttu-id="d0ab1-105">流内容元素，该功能**内联**属性包括：</span><span class="sxs-lookup"><span data-stu-id="d0ab1-105">Flow content elements that feature an **Inlines** property include:</span></span>  
  
-   <xref:System.Windows.Documents.Bold>  
  
-   <xref:System.Windows.Documents.Hyperlink>  
  
-   <xref:System.Windows.Documents.Italic>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Span>  
  
-   <xref:System.Windows.Documents.Underline>  
  
 <span data-ttu-id="d0ab1-106">这些示例碰巧使用<xref:System.Windows.Documents.Span>作为流内容元素，但是，这些技术是适用于所有元素或控件承载<xref:System.Windows.Documents.InlineCollection>集合。</span><span class="sxs-lookup"><span data-stu-id="d0ab1-106">These examples happen to use <xref:System.Windows.Documents.Span> as the flow content element, but these techniques are applicable to all elements or controls that host an <xref:System.Windows.Documents.InlineCollection> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0ab1-107">示例</span><span class="sxs-lookup"><span data-stu-id="d0ab1-107">Example</span></span>  
 <span data-ttu-id="d0ab1-108">下面的示例创建一个新<xref:System.Windows.Documents.Span>对象，然后使用**添加**方法添加两个文本运行，作为内容的子级<xref:System.Windows.Documents.Span>。</span><span class="sxs-lookup"><span data-stu-id="d0ab1-108">The following example creates a new <xref:System.Windows.Documents.Span> object, and then uses the **Add** method to add two text runs as content children of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
## <a name="example"></a><span data-ttu-id="d0ab1-109">示例</span><span class="sxs-lookup"><span data-stu-id="d0ab1-109">Example</span></span>  
 <span data-ttu-id="d0ab1-110">下面的示例创建一个新<xref:System.Windows.Documents.Run>元素并将其插入的开始处<xref:System.Windows.Documents.Span>。</span><span class="sxs-lookup"><span data-stu-id="d0ab1-110">The following example creates a new <xref:System.Windows.Documents.Run> element and inserts it at the beginning of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
## <a name="example"></a><span data-ttu-id="d0ab1-111">示例</span><span class="sxs-lookup"><span data-stu-id="d0ab1-111">Example</span></span>  
 <span data-ttu-id="d0ab1-112">下面的示例获取的顶级数<xref:System.Windows.Documents.Inline>中所含元素<xref:System.Windows.Documents.Span>。</span><span class="sxs-lookup"><span data-stu-id="d0ab1-112">The following example gets the number of top-level <xref:System.Windows.Documents.Inline> elements contained in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinescount)]
 [!code-vb[SpanSnippets#_SpanInlinesCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinescount)]  
  
## <a name="example"></a><span data-ttu-id="d0ab1-113">示例</span><span class="sxs-lookup"><span data-stu-id="d0ab1-113">Example</span></span>  
 <span data-ttu-id="d0ab1-114">以下示例将删除最后一个<xref:System.Windows.Documents.Inline>中的元素<xref:System.Windows.Documents.Span>。</span><span class="sxs-lookup"><span data-stu-id="d0ab1-114">The following example deletes the last <xref:System.Windows.Documents.Inline> element in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
## <a name="example"></a><span data-ttu-id="d0ab1-115">示例</span><span class="sxs-lookup"><span data-stu-id="d0ab1-115">Example</span></span>  
 <span data-ttu-id="d0ab1-116">下面的示例清除的所有内容 (<xref:System.Windows.Documents.Inline>元素) 从<xref:System.Windows.Documents.Span>。</span><span class="sxs-lookup"><span data-stu-id="d0ab1-116">The following example clears all of the contents (<xref:System.Windows.Documents.Inline> elements) from the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
## <a name="see-also"></a><span data-ttu-id="d0ab1-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0ab1-117">See Also</span></span>  
 <xref:System.Windows.Documents.BlockCollection>  
 <xref:System.Windows.Documents.InlineCollection>  
 <xref:System.Windows.Documents.ListItemCollection>  
 [<span data-ttu-id="d0ab1-118">流文档概述</span><span class="sxs-lookup"><span data-stu-id="d0ab1-118">Flow Document Overview</span></span>](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [<span data-ttu-id="d0ab1-119">通过 Blocks 属性控制 FlowDocument</span><span class="sxs-lookup"><span data-stu-id="d0ab1-119">Manipulate a FlowDocument through the Blocks Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [<span data-ttu-id="d0ab1-120">通过 Columns 属性控制表列</span><span class="sxs-lookup"><span data-stu-id="d0ab1-120">Manipulate a Table's Columns through the Columns Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)  
 [<span data-ttu-id="d0ab1-121">通过 RowGroups 属性操作表的行组</span><span class="sxs-lookup"><span data-stu-id="d0ab1-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
