---
title: 如何：以编程方式生成表
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tables [WPF], creating programmatically
ms.assetid: e3ca88f3-6e94-4b61-82fc-42104c10b761
ms.openlocfilehash: 9c9061d3c4d6b3de5e1ab42a6b98c20813835ba8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964162"
---
# <a name="how-to-build-a-table-programmatically"></a><span data-ttu-id="df764-102">如何：以编程方式生成表</span><span class="sxs-lookup"><span data-stu-id="df764-102">How to: Build a Table Programmatically</span></span>
<span data-ttu-id="df764-103">下面的示例演示如何以编程方式创建<xref:System.Windows.Documents.Table>和填充内容。</span><span class="sxs-lookup"><span data-stu-id="df764-103">The following examples show how to programmatically create a <xref:System.Windows.Documents.Table> and populate it with content.</span></span> <span data-ttu-id="df764-104">该表的内容分配为五行 (由<xref:System.Windows.Documents.TableRow> <xref:System.Windows.Documents.Table.RowGroups%2A>对象中包含的对象表示) 和<xref:System.Windows.Documents.TableColumn>六个列 (由对象表示)。</span><span class="sxs-lookup"><span data-stu-id="df764-104">The contents of the table are apportioned into five rows (represented by <xref:System.Windows.Documents.TableRow> objects contained in a <xref:System.Windows.Documents.Table.RowGroups%2A> object) and six columns (represented by <xref:System.Windows.Documents.TableColumn> objects).</span></span> <span data-ttu-id="df764-105">各行用于不同的显示目的，其中，标题行用于显示整个表的标题，标头行用于描述表中的数据列，而页脚行则包含摘要信息。</span><span class="sxs-lookup"><span data-stu-id="df764-105">The rows are used for different presentation purposes, including a title row intended to title the entire table, a header row to describe the columns of data in the table, and a footer row with summary information.</span></span>  <span data-ttu-id="df764-106">请注意，“标题”行、“标头”行和“页脚”行并非表格所固有的，它们只是具有不同特征的行。</span><span class="sxs-lookup"><span data-stu-id="df764-106">Note that the notion of "title", "header", and "footer" rows are not inherent to the table; these are simply rows with different characteristics.</span></span> <span data-ttu-id="df764-107">表单元格包含实际内容, 这些内容可以包括文本、图像或几乎任何其他[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]元素。</span><span class="sxs-lookup"><span data-stu-id="df764-107">Table cells contain the actual content, which can be comprised of text, images, or nearly any other [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df764-108">示例</span><span class="sxs-lookup"><span data-stu-id="df764-108">Example</span></span>  
 <span data-ttu-id="df764-109">首先, 创建<xref:System.Windows.Documents.FlowDocument>一个来承载的<xref:System.Windows.Documents.Table>, 并创建一个新<xref:System.Windows.Documents.Table>的并将其添加到的<xref:System.Windows.Documents.FlowDocument>内容中。</span><span class="sxs-lookup"><span data-stu-id="df764-109">First, a <xref:System.Windows.Documents.FlowDocument> is created to host the <xref:System.Windows.Documents.Table>, and a new <xref:System.Windows.Documents.Table> is created and added to the contents of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
## <a name="example"></a><span data-ttu-id="df764-110">示例</span><span class="sxs-lookup"><span data-stu-id="df764-110">Example</span></span>  
 <span data-ttu-id="df764-111">接下来, <xref:System.Windows.Documents.TableColumn>将创建六个对象并将其添加<xref:System.Windows.Documents.Table.Columns%2A>到表的集合, 并应用某些格式设置。</span><span class="sxs-lookup"><span data-stu-id="df764-111">Next, six <xref:System.Windows.Documents.TableColumn> objects are created and added to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection, with some formatting applied.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="df764-112">请注意, 表的<xref:System.Windows.Documents.Table.Columns%2A>集合使用从零开始的标准索引。</span><span class="sxs-lookup"><span data-stu-id="df764-112">Note that the table's <xref:System.Windows.Documents.Table.Columns%2A> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
## <a name="example"></a><span data-ttu-id="df764-113">示例</span><span class="sxs-lookup"><span data-stu-id="df764-113">Example</span></span>  
 <span data-ttu-id="df764-114">接下来，创建一个标题行，并将其添加到表中，同时应用某些格式设置。</span><span class="sxs-lookup"><span data-stu-id="df764-114">Next, a title row is created and added to the table with some formatting applied.</span></span>  <span data-ttu-id="df764-115">标题行包含一个单元格，该单元格跨表中的全部六列。</span><span class="sxs-lookup"><span data-stu-id="df764-115">The title row happens to contain a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
## <a name="example"></a><span data-ttu-id="df764-116">示例</span><span class="sxs-lookup"><span data-stu-id="df764-116">Example</span></span>  
 <span data-ttu-id="df764-117">接下来，创建一个标头行并将其添加到表中，同时创建标头行中的单元格并填充其内容。</span><span class="sxs-lookup"><span data-stu-id="df764-117">Next, a header row is created and added to the table, and the cells in the header row are created and populated with content.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
## <a name="example"></a><span data-ttu-id="df764-118">示例</span><span class="sxs-lookup"><span data-stu-id="df764-118">Example</span></span>  
 <span data-ttu-id="df764-119">接下来，创建一个数据行并将其添加到表中，同时创建此行中的单元格并填充其内容。</span><span class="sxs-lookup"><span data-stu-id="df764-119">Next, a row for data is created and added to the table, and the cells in this row are created and populated with content.</span></span>  <span data-ttu-id="df764-120">生成此行的过程与生成标头行的过程类似，只是应用的格式设置略有不同。</span><span class="sxs-lookup"><span data-stu-id="df764-120">Building this row is similar to building the header row, with slightly different formatting applied.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
## <a name="example"></a><span data-ttu-id="df764-121">示例</span><span class="sxs-lookup"><span data-stu-id="df764-121">Example</span></span>  
 <span data-ttu-id="df764-122">最后，创建、添加脚注行并设置其格式。</span><span class="sxs-lookup"><span data-stu-id="df764-122">Finally, a footer row is created, added, and formatted.</span></span>  <span data-ttu-id="df764-123">与标题行类似，脚注包含的单元格的跨度为表中的全部六列。</span><span class="sxs-lookup"><span data-stu-id="df764-123">Like the title row, the footer contains a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a><span data-ttu-id="df764-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="df764-124">See also</span></span>

- [<span data-ttu-id="df764-125">表概述</span><span class="sxs-lookup"><span data-stu-id="df764-125">Table Overview</span></span>](table-overview.md)
