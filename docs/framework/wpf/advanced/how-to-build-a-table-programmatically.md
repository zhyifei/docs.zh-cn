---
title: 如何：以编程方式生成表
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tables [WPF], creating programmatically
ms.assetid: e3ca88f3-6e94-4b61-82fc-42104c10b761
ms.openlocfilehash: 315154b37218c0a6845f0a46149fc056780ee650
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59172622"
---
# <a name="how-to-build-a-table-programmatically"></a><span data-ttu-id="04286-102">如何：以编程方式生成表</span><span class="sxs-lookup"><span data-stu-id="04286-102">How to: Build a Table Programmatically</span></span>
<span data-ttu-id="04286-103">以下示例演示如何以编程方式创建<xref:System.Windows.Documents.Table>并填充其内容。</span><span class="sxs-lookup"><span data-stu-id="04286-103">The following examples show how to programmatically create a <xref:System.Windows.Documents.Table> and populate it with content.</span></span> <span data-ttu-id="04286-104">表的内容被分为五个行 (由<xref:System.Windows.Documents.TableRow>中所含对象<xref:System.Windows.Documents.Table.RowGroups%2A>对象) 和六列 (由<xref:System.Windows.Documents.TableColumn>对象)。</span><span class="sxs-lookup"><span data-stu-id="04286-104">The contents of the table are apportioned into five rows (represented by <xref:System.Windows.Documents.TableRow> objects contained in a <xref:System.Windows.Documents.Table.RowGroups%2A> object) and six columns (represented by <xref:System.Windows.Documents.TableColumn> objects).</span></span> <span data-ttu-id="04286-105">各行用于不同的显示目的，其中，标题行用于显示整个表的标题，标头行用于描述表中的数据列，而页脚行则包含摘要信息。</span><span class="sxs-lookup"><span data-stu-id="04286-105">The rows are used for different presentation purposes, including a title row intended to title the entire table, a header row to describe the columns of data in the table, and a footer row with summary information.</span></span>  <span data-ttu-id="04286-106">请注意，“标题”行、“标头”行和“页脚”行并非表格所固有的，它们只是具有不同特征的行。</span><span class="sxs-lookup"><span data-stu-id="04286-106">Note that the notion of "title", "header", and "footer" rows are not inherent to the table; these are simply rows with different characteristics.</span></span> <span data-ttu-id="04286-107">表单元格包含实际内容，可以包含文本、 图像或几乎任何其他[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]元素。</span><span class="sxs-lookup"><span data-stu-id="04286-107">Table cells contain the actual content, which can be comprised of text, images, or nearly any other [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04286-108">示例</span><span class="sxs-lookup"><span data-stu-id="04286-108">Example</span></span>  
 <span data-ttu-id="04286-109">首先，<xref:System.Windows.Documents.FlowDocument>创建到主机<xref:System.Windows.Documents.Table>，和一个新<xref:System.Windows.Documents.Table>被创建并添加到的内容<xref:System.Windows.Documents.FlowDocument>。</span><span class="sxs-lookup"><span data-stu-id="04286-109">First, a <xref:System.Windows.Documents.FlowDocument> is created to host the <xref:System.Windows.Documents.Table>, and a new <xref:System.Windows.Documents.Table> is created and added to the contents of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
## <a name="example"></a><span data-ttu-id="04286-110">示例</span><span class="sxs-lookup"><span data-stu-id="04286-110">Example</span></span>  
 <span data-ttu-id="04286-111">下一步，六<xref:System.Windows.Documents.TableColumn>创建对象，并添加到表的<xref:System.Windows.Documents.Table.Columns%2A>集合中的，同时应用某些格式设置。</span><span class="sxs-lookup"><span data-stu-id="04286-111">Next, six <xref:System.Windows.Documents.TableColumn> objects are created and added to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection, with some formatting applied.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04286-112">请注意，表的<xref:System.Windows.Documents.Table.Columns%2A>集合使用标准的从零开始索引。</span><span class="sxs-lookup"><span data-stu-id="04286-112">Note that the table's <xref:System.Windows.Documents.Table.Columns%2A> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
## <a name="example"></a><span data-ttu-id="04286-113">示例</span><span class="sxs-lookup"><span data-stu-id="04286-113">Example</span></span>  
 <span data-ttu-id="04286-114">接下来，创建一个标题行，并将其添加到表中，同时应用某些格式设置。</span><span class="sxs-lookup"><span data-stu-id="04286-114">Next, a title row is created and added to the table with some formatting applied.</span></span>  <span data-ttu-id="04286-115">标题行包含一个单元格，该单元格跨表中的全部六列。</span><span class="sxs-lookup"><span data-stu-id="04286-115">The title row happens to contain a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
## <a name="example"></a><span data-ttu-id="04286-116">示例</span><span class="sxs-lookup"><span data-stu-id="04286-116">Example</span></span>  
 <span data-ttu-id="04286-117">接下来，创建一个标头行并将其添加到表中，同时创建标头行中的单元格并填充其内容。</span><span class="sxs-lookup"><span data-stu-id="04286-117">Next, a header row is created and added to the table, and the cells in the header row are created and populated with content.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
## <a name="example"></a><span data-ttu-id="04286-118">示例</span><span class="sxs-lookup"><span data-stu-id="04286-118">Example</span></span>  
 <span data-ttu-id="04286-119">接下来，创建一个数据行并将其添加到表中，同时创建此行中的单元格并填充其内容。</span><span class="sxs-lookup"><span data-stu-id="04286-119">Next, a row for data is created and added to the table, and the cells in this row are created and populated with content.</span></span>  <span data-ttu-id="04286-120">生成此行的过程与生成标头行的过程类似，只是应用的格式设置略有不同。</span><span class="sxs-lookup"><span data-stu-id="04286-120">Building this row is similar to building the header row, with slightly different formatting applied.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
## <a name="example"></a><span data-ttu-id="04286-121">示例</span><span class="sxs-lookup"><span data-stu-id="04286-121">Example</span></span>  
 <span data-ttu-id="04286-122">最后，创建、添加脚注行并设置其格式。</span><span class="sxs-lookup"><span data-stu-id="04286-122">Finally, a footer row is created, added, and formatted.</span></span>  <span data-ttu-id="04286-123">与标题行类似，脚注包含的单元格的跨度为表中的全部六列。</span><span class="sxs-lookup"><span data-stu-id="04286-123">Like the title row, the footer contains a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a><span data-ttu-id="04286-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="04286-124">See also</span></span>

- [<span data-ttu-id="04286-125">表概述</span><span class="sxs-lookup"><span data-stu-id="04286-125">Table Overview</span></span>](table-overview.md)
