---
title: 流文档概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'documents [WPF], flow documents [WPF], , '
- ', '
- flow documents [WPF]
ms.assetid: ef236a50-d44f-43c8-ba7c-82b0c733c0b7
ms.openlocfilehash: 0cf8944298af62a512599fc52998a046c66fed9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="flow-document-overview"></a>流文档概述
流文档旨在优化查看和可读性。 流文档根据运行时变量（例如，窗口大小、设备分辨率和可选的用户首选项）来动态调整和重新排列内容，而不是设置为一个预定义的布局。 此外，流文档还提供一些高级文档功能，例如分页和分栏。 本主题概述了流文档及其创建方式。  
  

  
<a name="what_is_a_flow_document"></a>   
## <a name="what-is-a-flow-document"></a>什么是流文档？  
 流文档旨在根据窗口大小、设备分辨率和其他环境变量来“重排内容”。 此外，流文档还具有很多内置功能，包括搜索、能够优化可读性的查看模式以及更改字体大小和外观的功能。 当易读性是文档的主要使用要求时，最适合使用流文档。 相反，固定文档旨在提供静态表示形式。 当源内容的保真度至关重要时，就适合使用固定文档。 请参阅[WPF 中的文档](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)有关不同类型的文档的详细信息。  
  
 下图演示在多个不同大小的窗口中查看同一个示例流文档的情况。 随着显示区域的变化，内容将重新布局，以充分利用可用空间。  
  
 ![流文档内容重新布局](../../../../docs/framework/wpf/advanced/media/edocs-flowdocument.png "eDocs_FlowDocument")  
  
 如上图所示，流内容可包括多个组成部分，包括段落、列表、图像等等。 这些组成部分对应于标记中的元素和程序代码中的对象。 我们将更高版本在超出中详细介绍这些类[流相关的类](#flow_related_classes)本概述的部分。 现在，下面是创建一个流的文档包含一些以粗体显示的文本和列表段落的一个简单代码示例。
  
 [!code-xaml[FlowOvwSnippets_snip#SimpleFlowExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SimpleFlowExample.xaml#simpleflowexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SimpleFlowExample.cs#simpleflowcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SimpleFlowExample.vb#simpleflowcodeonlyexamplewholepage)]  
  
 下图显示了此代码片段。  
  
 ![屏幕截图：呈现的 FlowDocument 示例](../../../../docs/framework/wpf/advanced/media/flow-ovw-first-example.png "Flow_Ovw_First_Example")  
  
 在此示例中，<xref:System.Windows.Controls.FlowDocumentReader>控件用于承载流内容。 请参阅[流文档类型](#flow_document_types)有关承载的控件的流内容的详细信息。 <xref:System.Windows.Documents.Paragraph><xref:System.Windows.Documents.List>， <xref:System.Windows.Documents.ListItem>，和<xref:System.Windows.Documents.Bold>元素用于控制内容的格式设置，根据在标记中其顺序。 例如，<xref:System.Windows.Documents.Bold>元素跨越仅的段落中的文本的一部分; 因此，仅该部分的文本为粗体。 如果使用过 HTML，你就会了解这一点。  
  
 在上图中突出显示部分时，有几个功能内置于流文档：
  
-   搜索：允许用户对整个文档执行全文搜索。  
  
-   查看模式：用户可选择喜欢的查看模式，包括单页（一次一页）查看模式、一次两页（书本阅读格式）查看模式和连续滚动（无界限）查看模式。  有关这些查看模式的详细信息，请参阅<xref:System.Windows.Controls.FlowDocumentReaderViewingMode>。  
  
-   页面导航控件：如果文档的查看模式使用页面，则页面导航控件包括一个用于跳转到下一页（向下键）或上一页（向上键）的按钮，以及显示当前页码和总页数的指示器。 也可使用键盘上的箭头键来实现翻页操作。  
  
-   缩放：缩放控件可使用户通过单击加号或减号按钮来相应地增大或减小缩放级别。 缩放控件还包括一个用于调整缩放级别的滑块。 有关详细信息，请参阅<xref:System.Windows.Controls.FlowDocumentReader.Zoom%2A>。  
  
 这些功能可根据用于托管流内容的控件进行修改。 下一节介绍了各种控件。  
  
<a name="flow_document_types"></a>   
## <a name="flow-document-types"></a>流文档类型  
 流文档内容的显示和外观依赖于用于托管流内容的对象。 有四个控件支持的流内容查看： <xref:System.Windows.Controls.FlowDocumentReader>， <xref:System.Windows.Controls.FlowDocumentPageViewer>， <xref:System.Windows.Controls.RichTextBox>，和<xref:System.Windows.Controls.FlowDocumentScrollViewer>。 下面简要介绍了这些控件。  
  
 **注意：** <xref:System.Windows.Documents.FlowDocument>不需要直接承载流内容，因此所有这些查看控件使用<xref:System.Windows.Documents.FlowDocument>启用流内容承载。  
  
### <a name="flowdocumentreader"></a>FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader> 包括功能，使用户能够动态各种查看模式，包括单页面 （页上的每一次的） 查看模式，两个--a-次一页 （书本阅读格式） 查看模式和连续滚动 （无界限） 查看模式之间进行选择。 有关这些查看模式的详细信息，请参阅<xref:System.Windows.Controls.FlowDocumentReaderViewingMode>。 如果你不需要动态切换不同的查看模式之间的能力<xref:System.Windows.Controls.FlowDocumentPageViewer>和<xref:System.Windows.Controls.FlowDocumentScrollViewer>提供轻量流内容查看器中使用特定查看模式修复。  
  
### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer 和 FlowDocumentScrollViewer  
 <xref:System.Windows.Controls.FlowDocumentPageViewer> 显示的内容中页每次查看模式时，尽管<xref:System.Windows.Controls.FlowDocumentScrollViewer>显示连续滚动模式中的内容。 同时<xref:System.Windows.Controls.FlowDocumentPageViewer>和<xref:System.Windows.Controls.FlowDocumentScrollViewer>固定为特定的查看模式。 与进行比较<xref:System.Windows.Controls.FlowDocumentReader>，其中包括使用户能够动态各种查看模式之间进行选择的功能 (如由<xref:System.Windows.Controls.FlowDocumentReaderViewingMode>枚举)，但代价是多个资源密集型比<xref:System.Windows.Controls.FlowDocumentPageViewer>或<xref:System.Windows.Controls.FlowDocumentScrollViewer>。  
  
 默认情况下，总是显示垂直滚动条，而水平滚动条则在需要时显示。 默认值用于 UI<xref:System.Windows.Controls.FlowDocumentScrollViewer>不包括工具栏; 但是，<xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A>属性可用来启用内置的工具栏。  
  
### <a name="richtextbox"></a>RichTextBox  
 你使用<xref:System.Windows.Controls.RichTextBox>如果想要允许用户编辑流内容。 例如，如果你想要创建一个编辑器，允许用户处理以下操作： 表、 斜体和粗体格式等，将使用<xref:System.Windows.Controls.RichTextBox>。 请参阅[RichTextBox 概述](../../../../docs/framework/wpf/controls/richtextbox-overview.md)有关详细信息。  
  
 **注意：**内部的流内容<xref:System.Windows.Controls.RichTextBox>的行为与其他控件中包含的流内容完全一样。 例如，有中的没有列<xref:System.Windows.Controls.RichTextBox>和因此没有自动调整大小行为。 此外，例如搜索、 查看模式、 页面导航和缩放的流内容通常内置的功能将不可用内<xref:System.Windows.Controls.RichTextBox>。  
  
<a name="creating_flow_content"></a>   
## <a name="creating-flow-content"></a>创建流内容  
 流内容可能十分复杂，包括文本、 图像、 表，各种元素组成，甚至<xref:System.Windows.UIElement>派生的类，如控件。 若要了解如何创建复杂流内容，掌握下列知识点非常关键：  
  
-   **与流相关的类**：流内容中使用的每个类都有特定用途。 此外，了解各种流类之间的层次关系有助于了解其使用方式。 例如，类派生自<xref:System.Windows.Documents.Block>类用于包含其他对象，而类派生自<xref:System.Windows.Documents.Inline>包含显示的对象。  
  
-   **内容架构**：流文档可能需要大量嵌套元素。 内容架构指定了元素之间可能存在的父/子关系。  
  
 以下各节详细介绍了上述每个方面。  
  
<a name="flow_related_classes"></a>   
## <a name="flow-related-classes"></a>与流相关的类  
 下图演示了流内容中最常使用的对象：  
  
 ![关系图：流内容元素类层次结构](../../../../docs/framework/wpf/advanced/media/flow-class-hierarchy.png "Flow_Class_Hierarchy")  
  
 根据流内容的用途，可分为两个重要类别：  
  
1.  **Block 派生类**：也称为“Block 内容元素”，或简称为“Block 元素”。 从继承元素<xref:System.Windows.Documents.Block>可以在一个公共父级下的元素进行分组，或将公共特性应用到组。  
  
2.  **Inline 派生类**：也称为“Inline 内容元素”，或简称为“Inline 元素”。 从继承元素<xref:System.Windows.Documents.Inline>或者包含在块元素或另一个内联元素。 Inline 元素通常用作在屏幕上呈现的内容的直接容器。 例如， <xref:System.Windows.Documents.Paragraph> （块元素） 可以包含<xref:System.Windows.Documents.Run>（内联元素） 但<xref:System.Windows.Documents.Run>实际包含在屏幕呈现的文本。  
  
 下面简要介绍了这两个类别中的每个类。  
  
### <a name="block-derived-classes"></a>Block 派生类  
 **Paragraph**  
  
 <xref:System.Windows.Documents.Paragraph> 通常用于内容分组到一个段落。 Paragraph 的最简单且最常见的用途是创建文本段落。  
  
 [!code-xaml[FlowOvwSnippets_snip#ParagraphExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ParagraphExample.xaml#paragraphexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ParagraphExample.cs#paragraphcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ParagraphExample.vb#paragraphcodeonlyexamplewholepage)]  
  
 但是，你将会看到下面，还可以包含其他内联派生元素。 
  
 **节**  
  
 <xref:System.Windows.Documents.Section> 仅用于包含其他<xref:System.Windows.Documents.Block>-派生元素。 它不会向其中包含的元素应用任何默认格式。 但是，任何属性值集上<xref:System.Windows.Documents.Section>适用于及其子元素。 使用节能够以编程方式循环访问其子集合。 <xref:System.Windows.Documents.Section> 到类似的方式使用\<DIV > 中 HTML 标记。  
  
 在下面的示例中，三个段落定义下一个<xref:System.Windows.Documents.Section>。 将节<xref:System.Windows.Documents.TextElement.Background%2A>的红色，因此段落的背景色的属性值也为红色。  
  
 [!code-xaml[FlowOvwSnippets_snip#SectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SectionExample.xaml#sectionexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SectionExample.cs#sectioncodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SectionExample.vb#sectioncodeonlyexamplewholepage)]  
  
 **BlockUIContainer**  
  
 <xref:System.Windows.Documents.BlockUIContainer> 使<xref:System.Windows.UIElement>元素 (即<xref:System.Windows.Controls.Button>) 能够嵌入到块派生的流内容。 <xref:System.Windows.Documents.InlineUIContainer> （见下文） 用于嵌入<xref:System.Windows.UIElement>内联派生的流内容中的元素。 <xref:System.Windows.Documents.BlockUIContainer> 和<xref:System.Windows.Documents.InlineUIContainer>非常重要，因为没有其他方法使用<xref:System.Windows.UIElement>在流内容，除非它包含在这两个元素之一中。  
  
 下面的示例演示如何使用<xref:System.Windows.Documents.BlockUIContainer>元素来承载<xref:System.Windows.UIElement>在流内容中的对象。  
  
 [!code-xaml[SpanSnippets#_BlockUIXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml#_blockuixaml)]  
  
 下图显示了此示例的呈现效果。  
  
 ![屏幕截图：嵌入在流内容中的 UIElement](../../../../docs/framework/wpf/advanced/media/blockuicontainer.png "BlockUIContainer")  
  
 **List**  
  
 <xref:System.Windows.Documents.List> 用于创建带项目符号或数值的列表。 设置<xref:System.Windows.Documents.List.MarkerStyle%2A>属性<xref:System.Windows.TextMarkerStyle>枚举值来确定列表的样式。 下例演示了如何创建简单列表。  
  
 [!code-xaml[FlowOvwSnippets_snip#ListExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ListExample.xaml#listexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ListExample.cs#listcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ListExample.vb#listcodeonlyexamplewholepage)]  
  
 **注意：** <xref:System.Windows.Documents.List>是使用的唯一流元素<xref:System.Windows.Documents.ListItemCollection>管理子元素。  
  
 **Table**  
  
 <xref:System.Windows.Documents.Table> 用于创建表。 <xref:System.Windows.Documents.Table> 类似于<xref:System.Windows.Controls.Grid>元素，但它具有更多功能并且，因此，需要更大的资源开销。 因为<xref:System.Windows.Controls.Grid>是<xref:System.Windows.UIElement>，除非它包含在无法在流内容中使用它<xref:System.Windows.Documents.BlockUIContainer>或<xref:System.Windows.Documents.InlineUIContainer>。 有关详细信息<xref:System.Windows.Documents.Table>，请参阅[表概述](../../../../docs/framework/wpf/advanced/table-overview.md)。  
  
### <a name="inline-derived-classes"></a>Inline 派生类  
 **运行**  
  
 <xref:System.Windows.Documents.Run> 用于包含无格式的文本。 你所料<xref:System.Windows.Documents.Run>对象进行了广泛在使用流内容。 但是，在标记中，<xref:System.Windows.Documents.Run>元素不需要显式地使用。 <xref:System.Windows.Documents.Run> 需要创建或使用代码操作流文档时使用。 例如，在下面第一个标记<xref:System.Windows.Documents.Paragraph>指定<xref:System.Windows.Documents.Run>显式时第二个元素不一样。 这两个段落生成相同的输出。  
  
 [!code-xaml[FlowOvwSnippets_snip#RunExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/RunSnippetsExample.xaml#runexample1)]  
  
 **注意：**从[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]、<xref:System.Windows.Documents.Run.Text%2A>属性<xref:System.Windows.Documents.Run>对象是依赖项属性。 你可以将绑定<xref:System.Windows.Documents.Run.Text%2A>属性到数据源，如<xref:System.Windows.Controls.TextBlock>。 <xref:System.Windows.Documents.Run.Text%2A>属性完全支持单向绑定。 <xref:System.Windows.Documents.Run.Text%2A>属性还支持双向绑定，除<xref:System.Windows.Controls.RichTextBox>。 有关示例，请参见 <xref:System.Windows.Documents.Run.Text%2A?displayProperty=nameWithType>。  
  
 **Span**  
  
 <xref:System.Windows.Documents.Span> 组合在一起其他内联内容元素。 中的内容应用没有固有呈现<xref:System.Windows.Documents.Span>元素。 但是，元素继承自<xref:System.Windows.Documents.Span>包括<xref:System.Windows.Documents.Hyperlink>， <xref:System.Windows.Documents.Bold>，<xref:System.Windows.Documents.Italic>和<xref:System.Windows.Documents.Underline>并应用格式设置为文本。  
  
 下面是一个示例的<xref:System.Windows.Documents.Span>正在使用，以包含内联内容，包括文本，<xref:System.Windows.Documents.Bold>元素，和一个<xref:System.Windows.Controls.Button>。  
  
 [!code-xaml[FlowOvwSnippets_snip#SpanExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SpanExample.xaml#spanexamplewholepage)]  
  
 下面的屏幕截图显示了此示例的呈现效果。  
  
 ![屏幕截图：呈现的 Span 示例](../../../../docs/framework/wpf/advanced/media/flow-spanexample.gif "Flow_SpanExample")  
  
 **InlineUIContainer**  
  
 <xref:System.Windows.Documents.InlineUIContainer> 使<xref:System.Windows.UIElement>元素 (即控件喜欢<xref:System.Windows.Controls.Button>) 能够嵌入到<xref:System.Windows.Documents.Inline>内容元素。 此元素是内联等效于<xref:System.Windows.Documents.BlockUIContainer>上面所述。 下面是使用的示例，<xref:System.Windows.Documents.InlineUIContainer>插入<xref:System.Windows.Controls.Button>中的内联<xref:System.Windows.Documents.Paragraph>。  
  
 [!code-xaml[FlowOvwSnippets_snip#InlineUIContainerExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/InlineUIContainerExample.xaml#inlineuicontainerexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/InlineUIContainerExample.cs#inlineuicontainercodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/InlineUIContainerExample.vb#inlineuicontainercodeonlyexamplewholepage)]  
  
 **注意：** <xref:System.Windows.Documents.InlineUIContainer>不需要在标记中显式使用。 如果省略，<xref:System.Windows.Documents.InlineUIContainer>仍将创建时编译的代码。  
  
 **Figure 和 Floater**  
  
 <xref:System.Windows.Documents.Figure> 和<xref:System.Windows.Documents.Floater>用于在流文档中嵌入内容，带有可自定义独立于主内容流的位置属性。 <xref:System.Windows.Documents.Figure> 或<xref:System.Windows.Documents.Floater>元素通常用于突出显示或强调部分内容，到主机的支持图像或其他内容中的主要内容流，或用于插入松散相关如播发的内容。  
  
 下面的示例演示如何嵌入<xref:System.Windows.Documents.Figure>到文本的段落。  
  
 [!code-xaml[FlowOvwSnippets_snip#FigureExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/FigureExample.xaml#figureexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/FigureExample.cs#figurecodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/FigureExample.vb#figurecodeonlyexamplewholepage)]  
  
 下图显示了此示例的呈现效果。  
  
 ![屏幕截图：Figure 示例](../../../../docs/framework/wpf/advanced/media/flow-ovw-figure-example.png "Flow_Ovw_Figure_Example")  
  
 <xref:System.Windows.Documents.Figure> 和<xref:System.Windows.Documents.Floater>有几个方面存在不同，并且可用于不同的情形。  
  
 **Figure：**  
  
-   可定位：可设置其水平和垂直定位点，以便相对于页面、内容、栏或段落进行停靠。 你还可以使用其<xref:System.Windows.Documents.Figure.HorizontalOffset%2A>和<xref:System.Windows.Documents.Figure.VerticalOffset%2A>属性以指定任意偏移量。  
  
-   大小可调整到多个列： 你可以设置<xref:System.Windows.Documents.Figure>高度和宽度为页面、 内容或栏的高度或宽度的倍数。 请注意，对于页面和内容，倍数不能大于 1。 例如，你可以设置的宽度<xref:System.Windows.Documents.Figure>"0.5 页"或"0.25 内容"或"列 2"。 还可将高度和宽度设置为绝对像素值。  
  
-   不分页： 如果中的内容<xref:System.Windows.Documents.Figure>不适合在<xref:System.Windows.Documents.Figure>，它会呈现能够容纳的内容，且其余内容都将丢失  
  
 **Floater：**  
  
-   无法定位，可在能够为其提供空间的任何位置呈现。 无法设置的偏移量或定位点<xref:System.Windows.Documents.Floater>。  
  
-   无法调整到多个列： 默认情况下，<xref:System.Windows.Documents.Floater>位于一个列的大小。 它具有<xref:System.Windows.Documents.Floater.Width%2A>属性可设置为绝对像素值，但如果此值大于它将被忽略的一个列宽度并将浮动对象大小为一个列。 你可以调整其到小于一列大小通过设置正确的像素宽度，但大小不是列相关，因此"0.5 倍栏宽"不是有效的表达式<xref:System.Windows.Documents.Floater>宽度。 <xref:System.Windows.Documents.Floater> 已将没有高度属性，它是高度不能进行设置，它的高度取决于的内容  
  
-   <xref:System.Windows.Documents.Floater> 对进行分页： 如果在其指定宽度其内容扩展到多个列的高度，浮标会断开，并显示到下一列、 下一个页面，等等。  
  
 <xref:System.Windows.Documents.Figure> 最好将独立内容放想要控制的大小和定位，并确信内容将放在指定的大小。 <xref:System.Windows.Documents.Floater> 是要放置自由流动更多内容流动相似的主页面内容，但与它分开的一个好。  
  
 **LineBreak**  
  
 <xref:System.Windows.Documents.LineBreak> 导致换行符在流内容中发生。 以下示例演示了 <xref:System.Windows.Documents.LineBreak> 的用法。  
  
 [!code-xaml[FlowOvwSnippets_snip#LineBreakExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/LineBreakExample.xaml#linebreakexamplewholepage)]  
  
 下面的屏幕截图显示了此示例的呈现效果。  
  
 ![屏幕截图：LineBreak 示例](../../../../docs/framework/wpf/advanced/media/flow-ovw-linebreakexample.png "Flow_Ovw_LineBreakExample")  
  
### <a name="flow-collection-elements"></a>流集合元素  
 在上面的示例通过很多<xref:System.Windows.Documents.BlockCollection>和<xref:System.Windows.Documents.InlineCollection>用于以编程方式构造流内容。 例如，若要将元素添加到<xref:System.Windows.Documents.Paragraph>，你可以使用语法：  
  
 `…`  
  
 `myParagraph.Inlines.Add(new Run("Some text"));`  
  
 `…`  
  
 这将添加<xref:System.Windows.Documents.Run>到<xref:System.Windows.Documents.InlineCollection>的<xref:System.Windows.Documents.Paragraph>。  这是相同的隐式<xref:System.Windows.Documents.Run>内找到<xref:System.Windows.Documents.Paragraph>标记中：  
  
 `…`  
  
 `<Paragraph>`  
  
 `Some Text`  
  
 `</Paragraph>`  
  
 `…`  
  
 作为示例，了解使用<xref:System.Windows.Documents.BlockCollection>，下面的示例创建一个新<xref:System.Windows.Documents.Section>，然后使用**添加**方法添加新<xref:System.Windows.Documents.Paragraph>到<xref:System.Windows.Documents.Section>内容。  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
 除向流集合中添加项之外，还可以移除项。  以下示例将删除最后一个<xref:System.Windows.Documents.Inline>中的元素<xref:System.Windows.Documents.Span>。  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 下面的示例清除的所有内容 (<xref:System.Windows.Documents.Inline>元素) 从<xref:System.Windows.Documents.Span>。  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
 以编程方式使用流内容时，可能会广泛使用这些集合。  
  
 流元素是否使用<xref:System.Windows.Documents.InlineCollection>（内联） 或<xref:System.Windows.Documents.BlockCollection>（块） 来包含它的子元素取决于哪种类型的子元素 (<xref:System.Windows.Documents.Block>或<xref:System.Windows.Documents.Inline>) 可包含由父级。 下一节中的内容架构中概述了流内容元素的包容规则。  
  
 **注意：**没有一种类型的集合用于流内容<xref:System.Windows.Documents.ListItemCollection>，但此集合仅适用于<xref:System.Windows.Documents.List>。 此外，有几个集合与使用<xref:System.Windows.Documents.Table>。 请参阅[表概述](../../../../docs/framework/wpf/advanced/table-overview.md)有关详细信息。  
  
<a name="content_schema"></a>   
## <a name="content-schema"></a>内容架构  
 不同流内容元素的数量是如此之多，因此了解某个元素可包含的子元素类型非常困难。 下面的关系图概述了流元素的包容规则。 箭头表示可能存在的父/子关系。  
  
 ![关系图：流内容包含架构](../../../../docs/framework/wpf/advanced/media/flow-content-schema.png "Flow_Content_Schema")  
  
 从上图中可看出，允许的元素的子级不一定由是<xref:System.Windows.Documents.Block>元素或<xref:System.Windows.Documents.Inline>元素。 例如， <xref:System.Windows.Documents.Span> (<xref:System.Windows.Documents.Inline>元素) 只能有<xref:System.Windows.Documents.Inline>子元素，而<xref:System.Windows.Documents.Figure>(还<xref:System.Windows.Documents.Inline>元素) 只能有<xref:System.Windows.Documents.Block>子元素。 因此，关系图可用于快速确定哪些元素可以包含在其他元素中。 例如，让我们使用关系图来确定如何构造的流内容<xref:System.Windows.Controls.RichTextBox>。  
  
 **1.** A<xref:System.Windows.Controls.RichTextBox>必须包含<xref:System.Windows.Documents.FlowDocument>其中反过来必须包含<xref:System.Windows.Documents.Block>-派生对象。 下面是上述关系图中的对应部分。  
  
 ![关系图：RichTextBox 包含规则](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
 到此为止，标记可能类似于所示内容。  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
 **2.** 根据关系图中，有几个<xref:System.Windows.Documents.Block>元素可供选择包括<xref:System.Windows.Documents.Paragraph>， <xref:System.Windows.Documents.Section>， <xref:System.Windows.Documents.Table>， <xref:System.Windows.Documents.List>，和<xref:System.Windows.Documents.BlockUIContainer>（请参阅上面的块派生的类）。 假设我们想<xref:System.Windows.Documents.Table>。 图中，根据<xref:System.Windows.Documents.Table>包含<xref:System.Windows.Documents.TableRowGroup>包含<xref:System.Windows.Documents.TableRow>元素，其中包含<xref:System.Windows.Documents.TableCell>元素包含<xref:System.Windows.Documents.Block>-派生对象。 下面是为相应的分段<xref:System.Windows.Documents.Table>取自上述关系图。  
  
 ![关系图：Table 的父/子架构](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
 下面是对应的标记。  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
 **3.** 同样，一个或多个<xref:System.Windows.Documents.Block>下都需要所元素<xref:System.Windows.Documents.TableCell>。 为简单起见，在单元格内部放置一些文本。 可以执行此操作使用<xref:System.Windows.Documents.Paragraph>与<xref:System.Windows.Documents.Run>元素。 下面是从显示的关系图中的相应段<xref:System.Windows.Documents.Paragraph>可以<xref:System.Windows.Documents.Inline>元素，而<xref:System.Windows.Documents.Run>(<xref:System.Windows.Documents.Inline>元素) 只能采用纯文本。  
  
 ![关系图：Paragraph 的父/子架构](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
 ![关系图：Run 的父/子架构](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 下面是标记中的完整示例。  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="customizing_text"></a>   
## <a name="customizing-text"></a>自定义文本  
 通常，文本是流文档中最普遍的内容类型。 尽管上面介绍的对象可用于控制文本呈现方式的大多数方面，但本文还介绍了其他一些自定义文本的方法。  
  
### <a name="text-decorations"></a>文本修饰  
 使用文本修饰，可向文本应用下划线、上划线、基线和删除线效果（请参见下图）。 使用要添加这些效果<xref:System.Windows.Documents.Inline.TextDecorations%2A>属性，公开由大量对象包括<xref:System.Windows.Documents.Inline>， <xref:System.Windows.Documents.Paragraph>， <xref:System.Windows.Controls.TextBlock>，和<xref:System.Windows.Controls.TextBox>。  
  
 以下示例演示如何设置 <xref:System.Windows.Documents.Paragraph.TextDecorations%2A> 的 <xref:System.Windows.Documents.Paragraph> 属性。  
  
 [!code-xaml[InlineSnippets#_Paragraph_TextDecXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml#_paragraph_textdecxaml)]  
  
 [!code-csharp[InlineSnippets#_Paragraph_TextDec](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml.cs#_paragraph_textdec)]
 [!code-vb[InlineSnippets#_Paragraph_TextDec](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InlineSnippets/visualbasic/window1.xaml.vb#_paragraph_textdec)]  
  
 下图显示了此示例的呈现效果。  
  
 ![屏幕截图：具有默认删除线效果的文本](../../../../docs/framework/wpf/advanced/media/inline-textdec-strike.png "Inline_TextDec_Strike")  
  
 下图显示了**上划线**，**基线**，和**Underline**修饰呈现，分别。  
  
 ![屏幕截图：上划线 TextDecorator](../../../../docs/framework/wpf/advanced/media/inline-textdec-over.png "Inline_TextDec_Over")  
  
 ![屏幕截图：文本上的默认基线效果](../../../../docs/framework/wpf/advanced/media/inline-textdec-base.png "Inline_TextDec_Base")  
  
 ![屏幕截图：具有默认下划线效果的文本](../../../../docs/framework/wpf/advanced/media/inline-textdec-under.png "Inline_TextDec_Under")  
  
### <a name="typography"></a>版式  
 <xref:System.Windows.Documents.TextElement.Typography%2A>属性公开的大多数与流相关内容包括<xref:System.Windows.Documents.TextElement>， <xref:System.Windows.Documents.FlowDocument>， <xref:System.Windows.Controls.TextBlock>，和<xref:System.Windows.Controls.TextBox>。 此属性用于控制文本的版式特征/变体（即小型大写字母或大型大写字母、设置上标和下标等）。  
  
 下面的示例演示如何设置<xref:System.Windows.Documents.TextElement.Typography%2A>属性，使用<xref:System.Windows.Documents.Paragraph>作为示例元素。  
  
 [!code-xaml[TextElementSnippets#_TextElement_TypogXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 下图显示了此示例的呈现效果。  
  
 ![屏幕截图：改变版式的文本](../../../../docs/framework/wpf/advanced/media/textelement-typog.png "TextElement_Typog")  
  
 与此相反，下图显示了一个具有默认版式属性的类似示例的呈现效果。  
  
 ![屏幕截图：改变版式的文本](../../../../docs/framework/wpf/advanced/media/textelement-typog-default.png "TextElement_Typog_Default")  
  
 下面的示例演示如何设置<xref:System.Windows.Controls.TextBox.Typography%2A>属性以编程方式。  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
 请参阅[WPF 中的版式](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)有关版式的详细信息。  
  
## <a name="see-also"></a>请参阅  
 [文本](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [WPF 中的版式](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [帮助主题](../../../../docs/framework/wpf/advanced/flow-content-elements-how-to-topics.md)  
 [TextElement 内容模型概述](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md)  
 [RichTextBox 概述](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [WPF 中的文档](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [表概述](../../../../docs/framework/wpf/advanced/table-overview.md)  
 [批注概述](../../../../docs/framework/wpf/advanced/annotations-overview.md)
