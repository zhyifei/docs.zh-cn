---
title: "表概述"
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
- flow content elements [WPF], Table
- documents [WPF], tables
- tables [WPF]
ms.assetid: 5e1105f4-8fc4-473a-ba55-88c8e71386e6
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 922faa06456a1aa86ffd0c805ab33577280ccf4f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="table-overview"></a><span data-ttu-id="8b120-102">表概述</span><span class="sxs-lookup"><span data-stu-id="8b120-102">Table Overview</span></span>
<span data-ttu-id="8b120-103"><xref:System.Windows.Documents.Table>是支持的流文档内容的基于网格的演示文稿的块级别元素。</span><span class="sxs-lookup"><span data-stu-id="8b120-103"><xref:System.Windows.Documents.Table> is a block level element that supports grid-based presentation of Flow document content.</span></span> <span data-ttu-id="8b120-104">此元素极具灵活性，因此很有用，但也因此显得更加复杂，从而不容易理解和正确使用。</span><span class="sxs-lookup"><span data-stu-id="8b120-104">The flexibility of this element makes it very useful, but also makes it more complicated to understand and use correctly.</span></span>  
  
 <span data-ttu-id="8b120-105">本主题包含以下各节：</span><span class="sxs-lookup"><span data-stu-id="8b120-105">This topic contains the following sections.</span></span>  
  
-   [<span data-ttu-id="8b120-106">表基础</span><span class="sxs-lookup"><span data-stu-id="8b120-106">Table Basics</span></span>](#table_basics)  
  
-   [<span data-ttu-id="8b120-107">表与网格有什么区别？</span><span class="sxs-lookup"><span data-stu-id="8b120-107">How is Table Different then Grid?</span></span>](#table_vs_Grid)  
  
-   [<span data-ttu-id="8b120-108">基本表结构</span><span class="sxs-lookup"><span data-stu-id="8b120-108">Basic Table Structure</span></span>](#basic_table_structure)  
  
-   [<span data-ttu-id="8b120-109">表包含</span><span class="sxs-lookup"><span data-stu-id="8b120-109">Table Containment</span></span>](#table_containment)  
  
-   [<span data-ttu-id="8b120-110">行分组</span><span class="sxs-lookup"><span data-stu-id="8b120-110">Row Groupings</span></span>](#row_groupings)  
  
-   [<span data-ttu-id="8b120-111">背景呈现优先级</span><span class="sxs-lookup"><span data-stu-id="8b120-111">Background Rendering Precedence</span></span>](#rendering_precedence)  
  
-   [<span data-ttu-id="8b120-112">跨行或列 </span><span class="sxs-lookup"><span data-stu-id="8b120-112">Spanning Rows or Columns</span></span>](#spanning_rows_or_columns)  
  
-   [<span data-ttu-id="8b120-113">使用代码生成表 </span><span class="sxs-lookup"><span data-stu-id="8b120-113">Building a Table With Code</span></span>](#building_a_table_with_code)  
  
-   <span data-ttu-id="8b120-114">[相关主题]</span><span class="sxs-lookup"><span data-stu-id="8b120-114">[Related Topics]</span></span> 
  
<a name="table_basics"></a>   
## <a name="table-basics"></a><span data-ttu-id="8b120-115">表基础</span><span class="sxs-lookup"><span data-stu-id="8b120-115">Table Basics</span></span>  
  
<a name="table_vs_Grid"></a>   
### <a name="how-is-table-different-then-grid"></a><span data-ttu-id="8b120-116">表与网格有什么区别？</span><span class="sxs-lookup"><span data-stu-id="8b120-116">How is Table Different then Grid?</span></span>  
 <span data-ttu-id="8b120-117"><xref:System.Windows.Documents.Table>和<xref:System.Windows.Controls.Grid>共享一些常见的功能，但每个最适合于不同的方案。</span><span class="sxs-lookup"><span data-stu-id="8b120-117"><xref:System.Windows.Documents.Table> and <xref:System.Windows.Controls.Grid> share some common functionality, but each is best suited for different scenarios.</span></span> <span data-ttu-id="8b120-118">A<xref:System.Windows.Documents.Table>旨在用于在流内容中 (请参阅[流文档概述](../../../../docs/framework/wpf/advanced/flow-document-overview.md)有关流内容的详细信息)。</span><span class="sxs-lookup"><span data-stu-id="8b120-118">A <xref:System.Windows.Documents.Table> is designed for use within flow content (see [Flow Document Overview](../../../../docs/framework/wpf/advanced/flow-document-overview.md) for more information on flow content).</span></span> <span data-ttu-id="8b120-119">网格最适合在表单内（主要在流内容以外的任意位置）使用。</span><span class="sxs-lookup"><span data-stu-id="8b120-119">Grids are best used inside of forms (basically anywhere outside of flow content).</span></span> <span data-ttu-id="8b120-120">在<xref:System.Windows.Documents.FlowDocument>，<xref:System.Windows.Documents.Table>支持流分页、 列回流等内容时选择的内容行为<xref:System.Windows.Controls.Grid>却没有。</span><span class="sxs-lookup"><span data-stu-id="8b120-120">Within a <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Table> supports flow content behaviors like pagination, column reflow, and content selection while a <xref:System.Windows.Controls.Grid> does not.</span></span> <span data-ttu-id="8b120-121">A<xref:System.Windows.Controls.Grid>另一方面最佳使用外部<xref:System.Windows.Documents.FlowDocument>包括的原因有很多<xref:System.Windows.Controls.Grid>添加基于一个行和列的索引，元素<xref:System.Windows.Documents.Table>却没有。</span><span class="sxs-lookup"><span data-stu-id="8b120-121">A <xref:System.Windows.Controls.Grid> on the other hand is best used outside of a <xref:System.Windows.Documents.FlowDocument> for many reasons including <xref:System.Windows.Controls.Grid> adds elements based on a row and column index, <xref:System.Windows.Documents.Table> does not.</span></span> <span data-ttu-id="8b120-122"><xref:System.Windows.Controls.Grid>元素允许的子内容，允许多个元素中的单个"单元格。"存在分层</span><span class="sxs-lookup"><span data-stu-id="8b120-122">The <xref:System.Windows.Controls.Grid> element allows layering of child content, allowing more than one element to exist within a single "cell."</span></span> <span data-ttu-id="8b120-123"><xref:System.Windows.Documents.Table>不支持分层。</span><span class="sxs-lookup"><span data-stu-id="8b120-123"><xref:System.Windows.Documents.Table> does not support layering.</span></span> <span data-ttu-id="8b120-124">子元素的<xref:System.Windows.Controls.Grid>进行绝对定位相对于其"单元格"边界的区域。</span><span class="sxs-lookup"><span data-stu-id="8b120-124">Child elements of a <xref:System.Windows.Controls.Grid> can be absolutely positioned relative to the area of their "cell" boundaries.</span></span> <span data-ttu-id="8b120-125"><xref:System.Windows.Documents.Table>不支持此功能。</span><span class="sxs-lookup"><span data-stu-id="8b120-125"><xref:System.Windows.Documents.Table> does not support this feature.</span></span> <span data-ttu-id="8b120-126">最后，<xref:System.Windows.Controls.Grid>需要较少的资源则<xref:System.Windows.Documents.Table>因此请考虑使用<xref:System.Windows.Controls.Grid>以提高性能。</span><span class="sxs-lookup"><span data-stu-id="8b120-126">Finally, a <xref:System.Windows.Controls.Grid> requires less resources then a <xref:System.Windows.Documents.Table> so consider using a <xref:System.Windows.Controls.Grid> to improve performance.</span></span>  
  
<a name="basic_table_structure"></a>   
### <a name="basic-table-structure"></a><span data-ttu-id="8b120-127">基本表结构</span><span class="sxs-lookup"><span data-stu-id="8b120-127">Basic Table Structure</span></span>  
 <span data-ttu-id="8b120-128"><xref:System.Windows.Documents.Table>提供基于网格的表示形式，包括列 (由表示<xref:System.Windows.Documents.TableColumn>元素) 和行 (由表示<xref:System.Windows.Documents.TableRow>元素)。</span><span class="sxs-lookup"><span data-stu-id="8b120-128"><xref:System.Windows.Documents.Table> provides a grid-based presentation consisting of columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and rows (represented by <xref:System.Windows.Documents.TableRow> elements).</span></span> <span data-ttu-id="8b120-129"><xref:System.Windows.Documents.TableColumn>元素未承载内容;它们只需定义列和列的特性。</span><span class="sxs-lookup"><span data-stu-id="8b120-129"><xref:System.Windows.Documents.TableColumn> elements do not host content; they simply define columns and characteristics of columns.</span></span> <span data-ttu-id="8b120-130"><xref:System.Windows.Documents.TableRow>元素必须承载于<xref:System.Windows.Documents.TableRowGroup>元素，它定义的表的行分组。</span><span class="sxs-lookup"><span data-stu-id="8b120-130"><xref:System.Windows.Documents.TableRow> elements must be hosted in a <xref:System.Windows.Documents.TableRowGroup> element, which defines a grouping of rows for the table.</span></span> <span data-ttu-id="8b120-131"><xref:System.Windows.Documents.TableCell>元素，其中包含由表中显示的实际内容，必须承载于<xref:System.Windows.Documents.TableRow>元素。</span><span class="sxs-lookup"><span data-stu-id="8b120-131"><xref:System.Windows.Documents.TableCell> elements, which contain the actual content to be presented by the table, must be hosted in a <xref:System.Windows.Documents.TableRow> element.</span></span> <span data-ttu-id="8b120-132"><xref:System.Windows.Documents.TableCell>只能包含派生自的元素<xref:System.Windows.Documents.Block>。</span><span class="sxs-lookup"><span data-stu-id="8b120-132"><xref:System.Windows.Documents.TableCell> may only contain elements that derive from <xref:System.Windows.Documents.Block>.</span></span>  <span data-ttu-id="8b120-133">有效的子元素<xref:System.Windows.Documents.TableCell>包括。</span><span class="sxs-lookup"><span data-stu-id="8b120-133">Valid child elements for a <xref:System.Windows.Documents.TableCell> include.</span></span>  
  
-   <xref:System.Windows.Documents.BlockUIContainer>  
  
-   <xref:System.Windows.Documents.List>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
>  <span data-ttu-id="8b120-134"><xref:System.Windows.Documents.TableCell>元素可能不会直接承载文本内容。</span><span class="sxs-lookup"><span data-stu-id="8b120-134"><xref:System.Windows.Documents.TableCell> elements may not directly host text content.</span></span> <span data-ttu-id="8b120-135">有关流的包含规则详细信息之类的内容元素<xref:System.Windows.Documents.TableCell>，请参阅[流文档概述](../../../../docs/framework/wpf/advanced/flow-document-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="8b120-135">For more information about the containment rules for flow content elements like <xref:System.Windows.Documents.TableCell>, see [Flow Document Overview](../../../../docs/framework/wpf/advanced/flow-document-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b120-136"><xref:System.Windows.Documents.Table>类似于<xref:System.Windows.Controls.Grid>元素但具有更多功能，因此，需要更大的资源开销。</span><span class="sxs-lookup"><span data-stu-id="8b120-136"><xref:System.Windows.Documents.Table> is similar to the <xref:System.Windows.Controls.Grid> element but has more capabilities and, therefore, requires greater resource overhead.</span></span>  
  
 <span data-ttu-id="8b120-137">下面的示例定义的简单 2x3 表[!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8b120-137">The following example defines a simple 2 x 3 table with [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)].</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 <span data-ttu-id="8b120-138">下图显示了此示例的呈现效果。</span><span class="sxs-lookup"><span data-stu-id="8b120-138">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="8b120-139">![屏幕快照：呈现一个基本表](../../../../docs/framework/wpf/advanced/media/basictablerrender.png "BasicTablerRender")</span><span class="sxs-lookup"><span data-stu-id="8b120-139">![Screenshot: Render a basic table](../../../../docs/framework/wpf/advanced/media/basictablerrender.png "BasicTablerRender")</span></span>  
  
<a name="table_containment"></a>   
### <a name="table-containment"></a><span data-ttu-id="8b120-140">表包容</span><span class="sxs-lookup"><span data-stu-id="8b120-140">Table Containment</span></span>  
 <span data-ttu-id="8b120-141"><xref:System.Windows.Documents.Table>派生自<xref:System.Windows.Documents.Block>元素，并遵循常见规则<xref:System.Windows.Documents.Block>级别元素。</span><span class="sxs-lookup"><span data-stu-id="8b120-141"><xref:System.Windows.Documents.Table> derives from the <xref:System.Windows.Documents.Block> element, and adheres to the common rules for <xref:System.Windows.Documents.Block> level elements.</span></span>  <span data-ttu-id="8b120-142">A<xref:System.Windows.Documents.Table>元素可能包含任何以下元素：</span><span class="sxs-lookup"><span data-stu-id="8b120-142">A <xref:System.Windows.Documents.Table> element may be contained by any of the following elements:</span></span>  
  
-   <xref:System.Windows.Documents.FlowDocument>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.ListViewItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>   
### <a name="row-groupings"></a><span data-ttu-id="8b120-143">行分组</span><span class="sxs-lookup"><span data-stu-id="8b120-143">Row Groupings</span></span>  
 <span data-ttu-id="8b120-144"><xref:System.Windows.Documents.TableRowGroup>元素提供对任意行进行分组表中的一种方法; 表中的每行必须属于的行分组。</span><span class="sxs-lookup"><span data-stu-id="8b120-144">The <xref:System.Windows.Documents.TableRowGroup> element provides a way to arbitrarily group rows within a table; every row in a table must belong to a row grouping.</span></span>  <span data-ttu-id="8b120-145">行分组中的行通常具有相同的用途，并可作为一个组来设置样式。</span><span class="sxs-lookup"><span data-stu-id="8b120-145">Rows within a row group often share a common intent, and may be styled as a group.</span></span>  <span data-ttu-id="8b120-146">行分组的一个常见使用方式是用于将特定用途的行（如标题行、标头和页脚行）与表中所含的主内容分隔开来。</span><span class="sxs-lookup"><span data-stu-id="8b120-146">A common use for row groupings is to separate special-purpose rows, such as a title, header, and footer rows, from the primary content contained by the table.</span></span>  
  
 <span data-ttu-id="8b120-147">下面的示例使用[!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]定义具有带样式的页眉和页脚行的表。</span><span class="sxs-lookup"><span data-stu-id="8b120-147">The following example uses [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] to define a table with styled header and footer rows.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 <span data-ttu-id="8b120-148">下图显示了此示例的呈现效果。</span><span class="sxs-lookup"><span data-stu-id="8b120-148">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="8b120-149">![屏幕快照：表行组](../../../../docs/framework/wpf/advanced/media/table-rowgroups.png "Table_RowGroups")</span><span class="sxs-lookup"><span data-stu-id="8b120-149">![Screenshot: Table row groups](../../../../docs/framework/wpf/advanced/media/table-rowgroups.png "Table_RowGroups")</span></span>  
  
<a name="rendering_precedence"></a>   
### <a name="background-rendering-precedence"></a><span data-ttu-id="8b120-150">背景呈现优先级</span><span class="sxs-lookup"><span data-stu-id="8b120-150">Background Rendering Precedence</span></span>  
 <span data-ttu-id="8b120-151">表元素以下列顺序呈现（按 Z 顺序从最低到最高排列）。</span><span class="sxs-lookup"><span data-stu-id="8b120-151">Table elements render in the following order (z-order from lowest to highest).</span></span> <span data-ttu-id="8b120-152">此顺序不能更改。</span><span class="sxs-lookup"><span data-stu-id="8b120-152">This order cannot be changed.</span></span> <span data-ttu-id="8b120-153">例如，对于这些元素，没有可用于替换此已有顺序的“Z 顺序”属性。</span><span class="sxs-lookup"><span data-stu-id="8b120-153">For example, there is no "Z-order" property for these elements that you can use to override this established order.</span></span>  
  
1.  <xref:System.Windows.Documents.Table>  
  
2.  <xref:System.Windows.Documents.TableColumn>  
  
3.  <xref:System.Windows.Documents.TableRowGroup>  
  
4.  <xref:System.Windows.Documents.TableRow>  
  
5.  <xref:System.Windows.Documents.TableCell>  
  
 <span data-ttu-id="8b120-154">请参考以下示例，该示例对表内每个元素的背景色进行定义。</span><span class="sxs-lookup"><span data-stu-id="8b120-154">Consider the following example, which defines background colors for each of these elements within a table.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_ZOrder](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 <span data-ttu-id="8b120-155">下图显示了此示例的呈现方式（仅显示背景色）。</span><span class="sxs-lookup"><span data-stu-id="8b120-155">The following figure shows how this example renders (showing background colors only).</span></span>  
  
 <span data-ttu-id="8b120-156">![屏幕快照：表 Z 顺序](../../../../docs/framework/wpf/advanced/media/table-zorder.png "Table_ZOrder")</span><span class="sxs-lookup"><span data-stu-id="8b120-156">![Screenshot: Table z&#45;order](../../../../docs/framework/wpf/advanced/media/table-zorder.png "Table_ZOrder")</span></span>  
  
<a name="spanning_rows_or_columns"></a>   
### <a name="spanning-rows-or-columns"></a><span data-ttu-id="8b120-157">跨行或列</span><span class="sxs-lookup"><span data-stu-id="8b120-157">Spanning Rows or Columns</span></span>  
 <span data-ttu-id="8b120-158">表格单元格可能配置为通过使用跨多个行或列<xref:System.Windows.Documents.TableCell.RowSpan%2A>或<xref:System.Windows.Documents.TableCell.ColumnSpan%2A>属性，分别。</span><span class="sxs-lookup"><span data-stu-id="8b120-158">Table cells may be configured to span multiple rows or columns by using the <xref:System.Windows.Documents.TableCell.RowSpan%2A> or <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> attributes, respectively.</span></span>  
  
 <span data-ttu-id="8b120-159">请参考以下示例，该示例中有一个跨三列的单元格。</span><span class="sxs-lookup"><span data-stu-id="8b120-159">Consider the following example, in which a cell spans three columns.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 <span data-ttu-id="8b120-160">下图显示了此示例的呈现效果。</span><span class="sxs-lookup"><span data-stu-id="8b120-160">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="8b120-161">![屏幕快照：跨全部三列的单元格](../../../../docs/framework/wpf/advanced/media/table-columnspan.png "Table_ColumnSpan")</span><span class="sxs-lookup"><span data-stu-id="8b120-161">![Screenshot: Cell spanning all three columns](../../../../docs/framework/wpf/advanced/media/table-columnspan.png "Table_ColumnSpan")</span></span>  
  
<a name="building_a_table_with_code"></a>   
## <a name="building-a-table-with-code"></a><span data-ttu-id="8b120-162">使用代码生成表</span><span class="sxs-lookup"><span data-stu-id="8b120-162">Building a Table With Code</span></span>  
 <span data-ttu-id="8b120-163">下面的示例演示如何以编程方式创建<xref:System.Windows.Documents.Table>和填充其内容。</span><span class="sxs-lookup"><span data-stu-id="8b120-163">The following examples show how to programmatically create a <xref:System.Windows.Documents.Table> and populate it with content.</span></span> <span data-ttu-id="8b120-164">表的内容分配到五个行 (由表示<xref:System.Windows.Documents.TableRow>中所含对象<xref:System.Windows.Documents.Table.RowGroups%2A>对象) 和六个列 (由表示<xref:System.Windows.Documents.TableColumn>对象)。</span><span class="sxs-lookup"><span data-stu-id="8b120-164">The contents of the table are apportioned into five rows (represented by <xref:System.Windows.Documents.TableRow> objects contained in a <xref:System.Windows.Documents.Table.RowGroups%2A> object) and six columns (represented by <xref:System.Windows.Documents.TableColumn> objects).</span></span> <span data-ttu-id="8b120-165">各行用于不同的显示目的，其中，标题行用于显示整个表的标题，标头行用于描述表中的数据列，而页脚行则包含摘要信息。</span><span class="sxs-lookup"><span data-stu-id="8b120-165">The rows are used for different presentation purposes, including a title row intended to title the entire table, a header row to describe the columns of data in the table, and a footer row with summary information.</span></span>  <span data-ttu-id="8b120-166">请注意，“标题”行、“标头”行和“页脚”行并非表格所固有的，它们只是具有不同特征的行。</span><span class="sxs-lookup"><span data-stu-id="8b120-166">Note that the notion of "title", "header", and "footer" rows are not inherent to the table; these are simply rows with different characteristics.</span></span> <span data-ttu-id="8b120-167">表格单元格包含实际的内容，它可以包含文本、 图像或几乎任何其他[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]元素。</span><span class="sxs-lookup"><span data-stu-id="8b120-167">Table cells contain the actual content, which can be comprised of text, images, or nearly any other [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] element.</span></span>  
  
 <span data-ttu-id="8b120-168">首先，<xref:System.Windows.Documents.FlowDocument>创建到主机<xref:System.Windows.Documents.Table>，和一个新<xref:System.Windows.Documents.Table>被创建并添加到的内容<xref:System.Windows.Documents.FlowDocument>。</span><span class="sxs-lookup"><span data-stu-id="8b120-168">First, a <xref:System.Windows.Documents.FlowDocument> is created to host the <xref:System.Windows.Documents.Table>, and a new <xref:System.Windows.Documents.Table> is created and added to the contents of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 <span data-ttu-id="8b120-169">接下来，六个<xref:System.Windows.Documents.TableColumn>对象会创建并添加到表的<xref:System.Windows.Documents.Table.Columns%2A>集合中的，同时应用一些格式设置。</span><span class="sxs-lookup"><span data-stu-id="8b120-169">Next, six <xref:System.Windows.Documents.TableColumn> objects are created and added to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection, with some formatting applied.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b120-170">请注意，表的<xref:System.Windows.Documents.Table.Columns%2A>集合使用标准的从零开始索引。</span><span class="sxs-lookup"><span data-stu-id="8b120-170">Note that the table's <xref:System.Windows.Documents.Table.Columns%2A> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 <span data-ttu-id="8b120-171">接下来，创建一个标题行，并将其添加到表中，同时应用某些格式设置。</span><span class="sxs-lookup"><span data-stu-id="8b120-171">Next, a title row is created and added to the table with some formatting applied.</span></span>  <span data-ttu-id="8b120-172">标题行包含一个单元格，该单元格跨表中的全部六列。</span><span class="sxs-lookup"><span data-stu-id="8b120-172">The title row happens to contain a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 <span data-ttu-id="8b120-173">接下来，创建一个标头行并将其添加到表中，同时创建标头行中的单元格并填充其内容。</span><span class="sxs-lookup"><span data-stu-id="8b120-173">Next, a header row is created and added to the table, and the cells in the header row are created and populated with content.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 <span data-ttu-id="8b120-174">接下来，创建一个数据行并将其添加到表中，同时创建此行中的单元格并填充其内容。</span><span class="sxs-lookup"><span data-stu-id="8b120-174">Next, a row for data is created and added to the table, and the cells in this row are created and populated with content.</span></span>  <span data-ttu-id="8b120-175">生成此行的过程与生成标头行的过程类似，只是应用的格式设置略有不同。</span><span class="sxs-lookup"><span data-stu-id="8b120-175">Building this row is similar to building the header row, with slightly different formatting applied.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 <span data-ttu-id="8b120-176">最后，创建、添加脚注行并设置其格式。</span><span class="sxs-lookup"><span data-stu-id="8b120-176">Finally, a footer row is created, added, and formatted.</span></span>  <span data-ttu-id="8b120-177">与标题行类似，脚注包含的单元格的跨度为表中的全部六列。</span><span class="sxs-lookup"><span data-stu-id="8b120-177">Like the title row, the footer contains a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a><span data-ttu-id="8b120-178">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b120-178">See Also</span></span>  
 [<span data-ttu-id="8b120-179">流文档概述</span><span class="sxs-lookup"><span data-stu-id="8b120-179">Flow Document Overview</span></span>](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [<span data-ttu-id="8b120-180">使用 XAML 定义表</span><span class="sxs-lookup"><span data-stu-id="8b120-180">Define a Table with XAML</span></span>](../../../../docs/framework/wpf/advanced/how-to-define-a-table-with-xaml.md)  
 [<span data-ttu-id="8b120-181">WPF 中的文档</span><span class="sxs-lookup"><span data-stu-id="8b120-181">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="8b120-182">使用流内容元素</span><span class="sxs-lookup"><span data-stu-id="8b120-182">Use Flow Content Elements</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-flow-content-elements.md)
