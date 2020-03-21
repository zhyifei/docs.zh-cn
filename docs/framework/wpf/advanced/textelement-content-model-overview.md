---
title: TextElement 内容模型概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], flow documents
- TextElement content model [WPF]
- flow content elements [WPF], TextElement content model
ms.assetid: d0a7791c-b090-438c-812f-b9d009d83ee9
ms.openlocfilehash: ddb2613dc924424b5f4b9d90f06d44b45b7b5e77
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186894"
---
# <a name="textelement-content-model-overview"></a>TextElement 内容模型概述
此内容模型概述描述 受 支持的内容<xref:System.Windows.Documents.TextElement>。 类<xref:System.Windows.Documents.Paragraph>是 一<xref:System.Windows.Documents.TextElement>种 类型。 内容模型描述哪些对象/元素可包含在其他对象/元素中。 此概述总结了用于派生从<xref:System.Windows.Documents.TextElement>的对象的内容模型。 有关详细信息，请参阅[流文档概述](flow-document-overview.md)。  

<a name="text_element_classes"></a>
## <a name="content-model-diagram"></a>内容模型图  
 下图总结了派生自类<xref:System.Windows.Documents.TextElement>的内容模型以及其他非`TextElement`类如何适应此模型。  
  
 ![示意图：流内容包含架构](./media/flow-content-schema.png "Flow_Content_Schema")  
  
 从上图可以看出，允许元素的子级不一定由类派生自<xref:System.Windows.Documents.Block>类或<xref:System.Windows.Documents.Inline>类来决定。 例如，（<xref:System.Windows.Documents.Span>派生<xref:System.Windows.Documents.Inline>类）只能具有<xref:System.Windows.Documents.Inline>子元素，但 （<xref:System.Windows.Documents.Figure>也是<xref:System.Windows.Documents.Inline>派生类） 只能具有<xref:System.Windows.Documents.Block>子元素。 因此，关系图可用于快速确定哪些元素可以包含在其他元素中。 例如，让我们使用关系图来确定如何构造 的流内容<xref:System.Windows.Controls.RichTextBox>。  
  
1. 必须<xref:System.Windows.Controls.RichTextBox>包含又必须<xref:System.Windows.Documents.FlowDocument>包含<xref:System.Windows.Documents.Block>派生对象的 。 以下是上述关系图中的相应部分。  
  
     ![示意图：RichTextBox 包含规则](./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
     到此为止，标记可能类似于所示内容。  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2. 根据该<xref:System.Windows.Documents.Block>图，有几个元素可供选择，<xref:System.Windows.Documents.Paragraph><xref:System.Windows.Documents.Section>包括 、、<xref:System.Windows.Documents.Table>和<xref:System.Windows.Documents.List> <xref:System.Windows.Documents.BlockUIContainer> （请参阅上图中的块派生类）。 假设我们想要一个<xref:System.Windows.Documents.Table>。 根据上图，<xref:System.Windows.Documents.Table>包含<xref:System.Windows.Documents.TableRowGroup><xref:System.Windows.Documents.TableRow>的元素包含元素，其中包含包含<xref:System.Windows.Documents.TableCell><xref:System.Windows.Documents.Block>派生对象的元素。 以下是从上图<xref:System.Windows.Documents.Table>中获取的相应段。  
  
     ![图表：表的父&#47;子架构](./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
     下面是相应的标记。  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3. 同样，在 下<xref:System.Windows.Documents.Block>需要一<xref:System.Windows.Documents.TableCell>个或多个元素。 为简单起见，在单元格内部放置一些文本。 我们可以使用 元素的<xref:System.Windows.Documents.Paragraph><xref:System.Windows.Documents.Run> 下面是关系图中的相应段，<xref:System.Windows.Documents.Paragraph>显示 a 可以获取<xref:System.Windows.Documents.Inline>元素，<xref:System.Windows.Documents.Run>并且 （元素<xref:System.Windows.Documents.Inline>） 只能采用纯文本。  
  
     ![图：父&#47;段落的子架构](./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
     ![图表：运行的父&#47;子架构](./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 下面是标记中的完整示例。  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>
## <a name="working-with-textelement-content-programmatically"></a>以编程方式处理 TextElement 内容  
 的内容<xref:System.Windows.Documents.TextElement>由集合组成，因此通过使用这些集合来以编程方式操作<xref:System.Windows.Documents.TextElement>对象的内容。 <xref:System.Windows.Documents.TextElement>派生类使用三种不同的集合：  
  
- <xref:System.Windows.Documents.InlineCollection>：表示元素的集合<xref:System.Windows.Documents.Inline>。 <xref:System.Windows.Documents.InlineCollection> 定义 <xref:System.Windows.Documents.Paragraph>、<xref:System.Windows.Documents.Span> 和 <xref:System.Windows.Controls.TextBlock> 元素允许的子内容。  
  
- <xref:System.Windows.Documents.BlockCollection>：表示元素的集合<xref:System.Windows.Documents.Block>。 <xref:System.Windows.Documents.BlockCollection> 定义 <xref:System.Windows.Documents.FlowDocument>、<xref:System.Windows.Documents.Section>、<xref:System.Windows.Documents.ListItem>、<xref:System.Windows.Documents.TableCell>、<xref:System.Windows.Documents.Floater> 和 <xref:System.Windows.Documents.Figure> 元素允许的子内容。  
  
- <xref:System.Windows.Documents.ListItemCollection>：表示有序或无序<xref:System.Windows.Documents.List>中的特定内容项的流内容元素。  
  
 您可以使用**内联**、**块**和**列表项**的相应属性从这些集合中操作（添加或删除项）。 以下示例演示如何使用**内线**属性操作 Span 的内容。  
  
> [!NOTE]
> 表格使用多个集合来操作其内容，但这里不对其进行说明。 有关详细信息，请参阅[表概述](table-overview.md)。  
  
 下面的示例创建一个新<xref:System.Windows.Documents.Span>对象，然后使用 方法`Add`添加两个文本运行作为 的内容<xref:System.Windows.Documents.Span>子级。  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 下面的示例创建一个新<xref:System.Windows.Documents.Run>元素，并在 的<xref:System.Windows.Documents.Span>开头插入它。  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 以下示例删除 中<xref:System.Windows.Documents.Inline><xref:System.Windows.Documents.Span>的最后一个元素。  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 下面的示例清除 中<xref:System.Windows.Documents.Inline><xref:System.Windows.Documents.Span>的所有内容（元素）。  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>
## <a name="types-that-share-this-content-model"></a>共享此内容模型的类型  
 以下类型从<xref:System.Windows.Documents.TextElement>类继承，可用于显示此概述中描述的内容。  
  
 <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.Underline>.  
  
 请注意，此列表仅包括与 Windows SDK 一起分发的非抽象类型。 您可以使用继承从<xref:System.Windows.Documents.TextElement>的其他类型的类型。  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>
## <a name="types-that-can-contain-textelement-objects"></a>可包含 TextElement 对象的类型  
 请参阅[WPF 内容模型](../controls/wpf-content-model.md)。  
  
## <a name="see-also"></a>另请参阅

- [通过 Blocks 属性操作 FlowDocument](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [通过 Blocks 属性操作流内容元素](how-to-manipulate-flow-content-elements-through-the-blocks-property.md)
- [通过 Blocks 属性操作 FlowDocument](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [通过 Columns 属性操作表列](how-to-manipulate-table-columns-through-the-columns-property.md)
- [通过 RowGroups 属性操作表的行组](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
