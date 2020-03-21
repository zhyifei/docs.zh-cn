---
title: 表概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flow content elements [WPF], Table
- documents [WPF], tables
- tables [WPF]
ms.assetid: 5e1105f4-8fc4-473a-ba55-88c8e71386e6
ms.openlocfilehash: 4bd747cea43755116c56b16f1de9a6ffb59935ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187276"
---
# <a name="table-overview"></a>表概述
<xref:System.Windows.Documents.Table>是支持基于网格的 Flow 文档内容的块级元素。 此元素极具灵活性，因此很有用，但也因此显得更加复杂，从而不容易理解和正确使用。  
  
 本主题包含以下各节。  
  
- [表基础](#table_basics)  
  
- [表与网格有什么区别？](#table_vs_Grid)  
  
- [基本表结构](#basic_table_structure)  
  
- [表包容](#table_containment)  
  
- [行分组](#row_groupings)  
  
- [背景呈现优先级](#rendering_precedence)  
  
- [跨行或列 ](#spanning_rows_or_columns)  
  
- [使用代码生成表](#building_a_table_with_code)  
  
- [相关主题]
  
<a name="table_basics"></a>
## <a name="table-basics"></a>表基础  
  
<a name="table_vs_Grid"></a>
### <a name="how-is-table-different-then-grid"></a>表与网格有什么区别？  
 <xref:System.Windows.Documents.Table>并<xref:System.Windows.Controls.Grid>共享一些通用功能，但每个功能最适合不同的方案。 A<xref:System.Windows.Documents.Table>设计用于流内容中（有关流内容的详细信息，请参阅[流文档概述](flow-document-overview.md)）。 网格最适合在表单中（主要在流内容以外的任意位置）使用。 在<xref:System.Windows.Documents.FlowDocument>中<xref:System.Windows.Documents.Table>，支持流内容行为，如分页、列重流和内容选择，而<xref:System.Windows.Controls.Grid>不支持。 另<xref:System.Windows.Controls.Grid>一方面，由于许多原因，包括<xref:System.Windows.Documents.FlowDocument><xref:System.Windows.Controls.Grid>添加基于行和列索引的元素，<xref:System.Windows.Documents.Table>最好在 外部使用。 该<xref:System.Windows.Controls.Grid>元素允许分层子内容，允许多个元素存在于单个"单元格"中。 <xref:System.Windows.Documents.Table>不支持分层。 子<xref:System.Windows.Controls.Grid>元素的子元素可以相对于其"单元格"边界区域绝对定位。 <xref:System.Windows.Documents.Table>不支持此功能。 最后，A<xref:System.Windows.Controls.Grid>需要更少的资源，<xref:System.Windows.Documents.Table>然后考虑使用<xref:System.Windows.Controls.Grid>a 来提高性能。  
  
<a name="basic_table_structure"></a>
### <a name="basic-table-structure"></a>基本表结构  
 <xref:System.Windows.Documents.Table>提供基于网格的表示，由列（由<xref:System.Windows.Documents.TableColumn>元素表示）和行（由<xref:System.Windows.Documents.TableRow>元素表示）。 <xref:System.Windows.Documents.TableColumn>元素不承载内容;元素不承载内容。它们只定义列和列的特征。 <xref:System.Windows.Documents.TableRow>元素必须托管在一个<xref:System.Windows.Documents.TableRowGroup>元素中，该元素定义表的行分组。 <xref:System.Windows.Documents.TableCell>元素包含表要显示的实际内容，必须托管在<xref:System.Windows.Documents.TableRow>元素中。 <xref:System.Windows.Documents.TableCell>可能只包含派生自<xref:System.Windows.Documents.Block>的元素。  <xref:System.Windows.Documents.TableCell>包括的有效子元素。  
  
- <xref:System.Windows.Documents.BlockUIContainer>  
  
- <xref:System.Windows.Documents.List>  
  
- <xref:System.Windows.Documents.Paragraph>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
> <xref:System.Windows.Documents.TableCell>元素不能直接承载文本内容。 有关流内容元素的包含规则的详细信息，请参阅<xref:System.Windows.Documents.TableCell>流[文档概述](flow-document-overview.md)。  
  
> [!NOTE]
> <xref:System.Windows.Documents.Table>与元素类似，<xref:System.Windows.Controls.Grid>但具有更多功能，因此需要更大的资源开销。  
  
 下面的示例定义了一个简单的 2 x 3 表与 XAML。  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 下图显示了此示例的呈现效果。  
  
 ![显示基本表呈现方式的屏幕截图。](./media/table-overview/basic-table-render-example.png)  
  
<a name="table_containment"></a>
### <a name="table-containment"></a>表包容  
 <xref:System.Windows.Documents.Table>派生自元素<xref:System.Windows.Documents.Block>，并遵循<xref:System.Windows.Documents.Block>级别元素的通用规则。  元素<xref:System.Windows.Documents.Table>可以由以下任何元素包含：  
  
- <xref:System.Windows.Documents.FlowDocument>  
  
- <xref:System.Windows.Documents.TableCell>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Floater>  
  
- <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>
### <a name="row-groupings"></a>行分组  
 该<xref:System.Windows.Documents.TableRowGroup>元素提供了一种对表中的行进行任意分组的方法;表中的每一行都必须属于行分组。  行分组中的行通常具有相同的用途，并可作为一个组来设置样式。  行分组的一个常见使用方式是用于将特定用途的行（如标题行、标头和页脚行）与表中所含的主内容分隔开来。  
  
 下面的示例使用 XAML 定义具有样式标题和页脚行的表。  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 下图显示了此示例的呈现效果。  
  
 ![屏幕快照：表行组](./media/table-rowgroups.png "Table_RowGroups")  
  
<a name="rendering_precedence"></a>
### <a name="background-rendering-precedence"></a>背景呈现优先级  
 表元素以下列顺序呈现（按 Z 顺序从最低到最高排列）。 此顺序不能更改。 例如，对于这些元素，没有可用于替换此已有顺序的“Z 顺序”属性。  
  
1. <xref:System.Windows.Documents.Table>  
  
2. <xref:System.Windows.Documents.TableColumn>  
  
3. <xref:System.Windows.Documents.TableRowGroup>  
  
4. <xref:System.Windows.Documents.TableRow>  
  
5. <xref:System.Windows.Documents.TableCell>  
  
 请参考以下示例，该示例对表内每个元素的背景色进行定义。  
  
 [!code-xaml[TableSnippets2#_Table_ZOrder](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 下图显示了此示例的呈现方式（仅显示背景色）。  
  
 ![屏幕截图：表 z&#45;顺序](./media/table-zorder.png "Table_ZOrder")  
  
<a name="spanning_rows_or_columns"></a>
### <a name="spanning-rows-or-columns"></a>跨行或列  
 表单元格可以分别配置为使用<xref:System.Windows.Documents.TableCell.RowSpan%2A>或 属性跨越多个行或<xref:System.Windows.Documents.TableCell.ColumnSpan%2A>列。  
  
 请参考以下示例，该示例中有一个跨三列的单元格。  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 下图显示了此示例的呈现效果。  
  
 ![屏幕快照：跨全部三列的单元格](./media/table-columnspan.png "Table_ColumnSpan")  
  
<a name="building_a_table_with_code"></a>
## <a name="building-a-table-with-code"></a>使用代码生成表  
 以下示例演示如何以编程方式创建 和<xref:System.Windows.Documents.Table>填充内容。 表的内容被分摊成五行（由<xref:System.Windows.Documents.TableRow><xref:System.Windows.Documents.Table.RowGroups%2A>包含在对象中的对象表示）和六列（由<xref:System.Windows.Documents.TableColumn>对象表示）。 各行用于不同的显示目的，其中，标题行用于显示整个表的标题，标头行用于描述表中的数据列，而页脚行则包含摘要信息。  请注意，“标题”行、“标头”行和“页脚”行并非表格所固有的，它们只是具有不同特征的行。 表单元格包含实际内容，内容可以由文本、图像或几乎任何其他[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]元素组成。  
  
 首先，将<xref:System.Windows.Documents.FlowDocument>创建 承载 的<xref:System.Windows.Documents.Table>，并创建<xref:System.Windows.Documents.Table>一个新内容并将其添加到 中<xref:System.Windows.Documents.FlowDocument>。  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 接下来，将<xref:System.Windows.Documents.TableColumn>创建六个对象并将其添加到表的集合<xref:System.Windows.Documents.Table.Columns%2A>中，并应用了一些格式。  
  
> [!NOTE]
> 请注意，表的集合<xref:System.Windows.Documents.Table.Columns%2A>使用标准的零基索引。  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 接下来，创建一个标题行，并将其添加到表中，同时应用某些格式设置。  标题行包含一个单元格，该单元格跨表中的全部六列。  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 接下来，创建一个标头行并将其添加到表中，同时创建标头行中的单元格并填充其内容。  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 接下来，创建一个数据行并将其添加到表中，同时创建此行中的单元格并填充其内容。  生成此行的过程与生成标头行的过程类似，只是应用的格式设置略有不同。  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 最后，创建、添加脚注行并设置其格式。  与标题行类似，脚注包含的单元格的跨度为表中的全部六列。  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a>另请参阅

- [流文档概述](flow-document-overview.md)
- [使用 XAML 定义表](how-to-define-a-table-with-xaml.md)
- [WPF 中的文档](documents-in-wpf.md)
- [使用流内容元素](how-to-use-flow-content-elements.md)
