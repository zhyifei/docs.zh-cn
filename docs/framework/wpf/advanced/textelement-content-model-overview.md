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
ms.openlocfilehash: 21df7228f8dca884c5f36be23ae1aced7b31cc9a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942221"
---
# <a name="textelement-content-model-overview"></a>TextElement 内容模型概述
此内容模型概述介绍了支持的内容<xref:System.Windows.Documents.TextElement>。 类是的<xref:System.Windows.Documents.TextElement>类型。 <xref:System.Windows.Documents.Paragraph> 内容模型描述哪些对象/元素可包含在其他对象/元素中。 本概述汇总了用于派生自<xref:System.Windows.Documents.TextElement>的对象的内容模型。 有关详细信息, 请参阅[流文档概述](flow-document-overview.md)。  

<a name="text_element_classes"></a>   
## <a name="content-model-diagram"></a>内容模型图  
 下图汇总了从派生的<xref:System.Windows.Documents.TextElement>类的内容模型, 以及其他`TextElement`非类如何适应此模型。  
  
 ![示意图：流内容包含架构](./media/flow-content-schema.png "Flow_Content_Schema")  
  
 如前面的关系图中所示, 允许元素的子元素不一定由类派生自<xref:System.Windows.Documents.Block>类<xref:System.Windows.Documents.Inline>或类。 例如<xref:System.Windows.Documents.Span> , <xref:System.Windows.Documents.Figure> <xref:System.Windows.Documents.Inline> <xref:System.Windows.Documents.Block> (派生类) 只能具有<xref:System.Windows.Documents.Inline>子元素, 但 (也是派生的类) 只能具有子元素。 <xref:System.Windows.Documents.Inline> 因此，关系图可用于快速确定哪些元素可以包含在其他元素中。 例如, 使用关系图确定如何构造的流内容<xref:System.Windows.Controls.RichTextBox>。  
  
1. 必须包含一个<xref:System.Windows.Documents.FlowDocument> , 而后者又必须包含一个<xref:System.Windows.Documents.Block>派生的对象。 <xref:System.Windows.Controls.RichTextBox> 以下是上述关系图中的相应部分。  
  
     ![示意图：RichTextBox 包含规则](./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
     到此为止，标记可能类似于所示内容。  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2. 根据关系图, 可以选择多个<xref:System.Windows.Documents.Block>元素, 包括<xref:System.Windows.Documents.Paragraph>、 <xref:System.Windows.Documents.Section> <xref:System.Windows.Documents.Table>、、 <xref:System.Windows.Documents.List>和<xref:System.Windows.Documents.BlockUIContainer> (请参阅上图中的块派生类)。 假设我们需要<xref:System.Windows.Documents.Table>。 根据前面的关系<xref:System.Windows.Documents.Table>图, <xref:System.Windows.Documents.TableRowGroup>包含<xref:System.Windows.Documents.TableRow>一个包含元素的元素, 这些<xref:System.Windows.Documents.TableCell>元素包含一个<xref:System.Windows.Documents.Block>派生的对象。 下面是前面的关系图中<xref:System.Windows.Documents.Table>所采用的对应段。  
  
     ![示意图：&#47;表](./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")的父子架构  
  
     下面是相应的标记。  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3. 同样, 在<xref:System.Windows.Documents.TableCell>下需要<xref:System.Windows.Documents.Block>一个或多个元素。 为简单起见，在单元格内部放置一些文本。 <xref:System.Windows.Documents.Paragraph> 使用<xref:System.Windows.Documents.Run>带有元素的可以实现此目的。 下图显示了关系图中的相应段, 其中<xref:System.Windows.Documents.Paragraph>显示了可以<xref:System.Windows.Documents.Inline>采用元素<xref:System.Windows.Documents.Inline> , 并且<xref:System.Windows.Documents.Run> (元素) 只能采用纯文本。  
  
     ![示意图：&#47;段落](./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")的父子架构  
  
     ![示意图：用于&#47;运行](./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")的父子架构  
  
 下面是标记中的完整示例。  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>   
## <a name="working-with-textelement-content-programmatically"></a>以编程方式处理 TextElement 内容  
 的内容<xref:System.Windows.Documents.TextElement>由集合构成, 因此, 通过使用这些集合以编程方式处理<xref:System.Windows.Documents.TextElement>对象的内容。 派生类使用<xref:System.Windows.Documents.TextElement>三个不同的集合:  
  
- <xref:System.Windows.Documents.InlineCollection>：表示 <xref:System.Windows.Documents.Inline> 元素的集合。 <xref:System.Windows.Documents.InlineCollection> 定义 <xref:System.Windows.Documents.Paragraph>、<xref:System.Windows.Documents.Span> 和 <xref:System.Windows.Controls.TextBlock> 元素允许的子内容。  
  
- <xref:System.Windows.Documents.BlockCollection>：表示 <xref:System.Windows.Documents.Block> 元素的集合。 <xref:System.Windows.Documents.BlockCollection> 定义 <xref:System.Windows.Documents.FlowDocument>、<xref:System.Windows.Documents.Section>、<xref:System.Windows.Documents.ListItem>、<xref:System.Windows.Documents.TableCell>、<xref:System.Windows.Documents.Floater> 和 <xref:System.Windows.Documents.Figure> 元素允许的子内容。  
  
- <xref:System.Windows.Documents.ListItemCollection>：流内容元素, 表示有序或无序<xref:System.Windows.Documents.List>的特定内容项。  
  
 可以使用**Inlines**、**块**和**ListItems**各自的属性, 从这些集合中操作 (添加或删除项)。 下面的示例演示如何使用**Inlines**属性操作跨度的内容。  
  
> [!NOTE]
> 表格使用多个集合来操作其内容，但这里不对其进行说明。 有关详细信息, 请参阅[表概述](table-overview.md)。  
  
 下面的示例创建一个新<xref:System.Windows.Documents.Span>的对象, 然后`Add`使用方法将两个文本运行添加为的<xref:System.Windows.Documents.Span>内容子对象。  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 下面的示例创建一个新<xref:System.Windows.Documents.Run>的元素, 并将其插入到的<xref:System.Windows.Documents.Span>开头。  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 下面的示例删除<xref:System.Windows.Documents.Inline> <xref:System.Windows.Documents.Span>中的最后一个元素。  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 下面的示例<xref:System.Windows.Documents.Span>从中清除所有内容 (<xref:System.Windows.Documents.Inline>元素)。  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>   
## <a name="types-that-share-this-content-model"></a>共享此内容模型的类型  
 以下类型继承自<xref:System.Windows.Documents.TextElement>类, 可用于显示本概述中所述的内容。  
  
 <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.Underline>.  
  
 请注意, 此列表仅包含与一起分发的[!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]非抽象类型。 您可以使用从<xref:System.Windows.Documents.TextElement>继承的其他类型。  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>   
## <a name="types-that-can-contain-textelement-objects"></a>可包含 TextElement 对象的类型  
 请参阅[WPF 内容模型](../controls/wpf-content-model.md)。  
  
## <a name="see-also"></a>请参阅

- [通过 Blocks 属性控制 FlowDocument](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [通过 Blocks 属性控制流内容元素](how-to-manipulate-flow-content-elements-through-the-blocks-property.md)
- [通过 Blocks 属性控制 FlowDocument](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [通过 Columns 属性控制表列](how-to-manipulate-table-columns-through-the-columns-property.md)
- [通过 RowGroups 属性操作表的行组](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
