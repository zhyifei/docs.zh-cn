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
ms.openlocfilehash: acd67dd870c6912eddc368bf674804d98dba2db8
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740756"
---
# <a name="textelement-content-model-overview"></a>TextElement 内容模型概述
此内容模型概述介绍 <xref:System.Windows.Documents.TextElement>支持的内容。 <xref:System.Windows.Documents.Paragraph> 类是一种 <xref:System.Windows.Documents.TextElement>类型。 内容模型描述哪些对象/元素可包含在其他对象/元素中。 本概述汇总了用于派生自 <xref:System.Windows.Documents.TextElement>的对象的内容模型。 有关详细信息，请参阅[流文档概述](flow-document-overview.md)。  

<a name="text_element_classes"></a>   
## <a name="content-model-diagram"></a>内容模型图  
 下图汇总了从 <xref:System.Windows.Documents.TextElement> 派生的类的内容模型，以及其他非 `TextElement` 类如何适应此模型。  
  
 ![关系图：流内容包含架构](./media/flow-content-schema.png "Flow_Content_Schema")  
  
 正如前面的关系图中所示，允许元素的子元素不一定由类派生自 <xref:System.Windows.Documents.Block> 类还是 <xref:System.Windows.Documents.Inline> 类来确定。 例如，<xref:System.Windows.Documents.Span> （<xref:System.Windows.Documents.Inline>派生类）只能具有 <xref:System.Windows.Documents.Inline> 子元素，但 <xref:System.Windows.Documents.Figure> （也是 <xref:System.Windows.Documents.Inline>派生的类）只能具有 <xref:System.Windows.Documents.Block> 的子元素。 因此，关系图可用于快速确定哪些元素可以包含在其他元素中。 例如，使用关系图确定如何构造 <xref:System.Windows.Controls.RichTextBox>的流内容。  
  
1. <xref:System.Windows.Controls.RichTextBox> 必须包含 <xref:System.Windows.Documents.FlowDocument>，而后者又必须包含一个 <xref:System.Windows.Documents.Block>派生的对象。 以下是上述关系图中的相应部分。  
  
     ![关系图： RichTextBox 包含规则](./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
     到此为止，标记可能类似于所示内容。  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2. 根据关系图，有几个 <xref:System.Windows.Documents.Block> 元素可供选择，包括 <xref:System.Windows.Documents.Paragraph>、<xref:System.Windows.Documents.Section>、<xref:System.Windows.Documents.Table>、<xref:System.Windows.Documents.List>和 <xref:System.Windows.Documents.BlockUIContainer> （请参阅上图中的块派生类）。 假设我们想要 <xref:System.Windows.Documents.Table>。 根据前面的关系图，<xref:System.Windows.Documents.Table> 包含包含 <xref:System.Windows.Documents.TableRow> 元素的 <xref:System.Windows.Documents.TableRowGroup>，其中包含包含 <xref:System.Windows.Documents.Block>派生对象的 <xref:System.Windows.Documents.TableCell> 元素。 下面是从上图中获取 <xref:System.Windows.Documents.Table> 的相应段。  
  
     ![关系图：&#47;表的父子架构](./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
     下面是相应的标记。  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3. 同样，<xref:System.Windows.Documents.TableCell>下需要一个或多个 <xref:System.Windows.Documents.Block> 元素。 为简单起见，在单元格内部放置一些文本。 使用 <xref:System.Windows.Documents.Run> 元素的 <xref:System.Windows.Documents.Paragraph> 可以实现此目的。 下图显示了关系图中的相应段，其中显示 <xref:System.Windows.Documents.Paragraph> 可以采用 <xref:System.Windows.Documents.Inline> 元素，而 <xref:System.Windows.Documents.Run> （<xref:System.Windows.Documents.Inline> 元素）只能采用纯文本。  
  
     ![关系图：&#47;段落的父子架构](./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
     ![关系图：&#47;用于运行的父子架构](./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 下面是标记中的完整示例。  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>   
## <a name="working-with-textelement-content-programmatically"></a>以编程方式处理 TextElement 内容  
 <xref:System.Windows.Documents.TextElement> 的内容由集合构成，因此，通过使用这些集合以编程方式操作 <xref:System.Windows.Documents.TextElement> 对象的内容。 <xref:System.Windows.Documents.TextElement> 派生类使用三个不同的集合：  
  
- <xref:System.Windows.Documents.InlineCollection>：表示 <xref:System.Windows.Documents.Inline> 元素的集合。 <xref:System.Windows.Documents.InlineCollection> 定义 <xref:System.Windows.Documents.Paragraph>、<xref:System.Windows.Documents.Span> 和 <xref:System.Windows.Controls.TextBlock> 元素允许的子内容。  
  
- <xref:System.Windows.Documents.BlockCollection>：表示 <xref:System.Windows.Documents.Block> 元素的集合。 <xref:System.Windows.Documents.BlockCollection> 定义 <xref:System.Windows.Documents.FlowDocument>、<xref:System.Windows.Documents.Section>、<xref:System.Windows.Documents.ListItem>、<xref:System.Windows.Documents.TableCell>、<xref:System.Windows.Documents.Floater> 和 <xref:System.Windows.Documents.Figure> 元素允许的子内容。  
  
- <xref:System.Windows.Documents.ListItemCollection>：表示有序或无序 <xref:System.Windows.Documents.List>中特定内容项的流内容元素。  
  
 可以使用**Inlines**、**块**和**ListItems**各自的属性，从这些集合中操作（添加或删除项）。 下面的示例演示如何使用**Inlines**属性操作跨度的内容。  
  
> [!NOTE]
> 表格使用多个集合来操作其内容，但这里不对其进行说明。 有关详细信息，请参阅[表概述](table-overview.md)。  
  
 下面的示例创建一个新的 <xref:System.Windows.Documents.Span> 对象，然后使用 `Add` 方法将两个文本运行添加为 <xref:System.Windows.Documents.Span>的内容子级。  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 下面的示例创建一个新的 <xref:System.Windows.Documents.Run> 元素，并将其插入到 <xref:System.Windows.Documents.Span>的开头。  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 下面的示例删除 <xref:System.Windows.Documents.Span>中的最后一个 <xref:System.Windows.Documents.Inline> 元素。  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 下面的示例从 <xref:System.Windows.Documents.Span>中清除所有内容（<xref:System.Windows.Documents.Inline> 元素）。  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>   
## <a name="types-that-share-this-content-model"></a>共享此内容模型的类型  
 以下类型继承自 <xref:System.Windows.Documents.TextElement> 类，可用于显示本概述中所述的内容。  
  
 <xref:System.Windows.Documents.Bold>、<xref:System.Windows.Documents.Figure>、<xref:System.Windows.Documents.Floater>、<xref:System.Windows.Documents.Hyperlink>、<xref:System.Windows.Documents.InlineUIContainer>、<xref:System.Windows.Documents.Italic>、<xref:System.Windows.Documents.LineBreak>、<xref:System.Windows.Documents.List>、<xref:System.Windows.Documents.ListItem>、<xref:System.Windows.Documents.Paragraph>、<xref:System.Windows.Documents.Run>、<xref:System.Windows.Documents.Section>、<xref:System.Windows.Documents.Span>、<xref:System.Windows.Documents.Table>、<xref:System.Windows.Documents.Underline>。  
  
 请注意，此列表仅包含与 Windows SDK 一起分发的非抽象类型。 您可以使用继承自 <xref:System.Windows.Documents.TextElement>的其他类型。  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>   
## <a name="types-that-can-contain-textelement-objects"></a>可包含 TextElement 对象的类型  
 请参阅[WPF 内容模型](../controls/wpf-content-model.md)。  
  
## <a name="see-also"></a>请参阅

- [通过 Blocks 属性控制 FlowDocument](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [通过 Blocks 属性控制流内容元素](how-to-manipulate-flow-content-elements-through-the-blocks-property.md)
- [通过 Blocks 属性控制 FlowDocument](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [通过 Columns 属性控制表列](how-to-manipulate-table-columns-through-the-columns-property.md)
- [通过 RowGroups 属性操作表的行组](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
