---
title: 如何：通过 RowGroups 属性操作表的行组
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- row groups [WPF], manipulating through RowGroups property
- RowGroups property [WPF], manipulating row groups
- documents [WPF], manipulating row groups through RowGroups property
- properties [WPF], RowGroups [WPF], manipulating row groups
ms.assetid: ea61440f-08ae-44ed-b314-5716aaaae3ed
ms.openlocfilehash: edc5fbe552a04387fc3f152cb53444605d142624
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209965"
---
# <a name="how-to-manipulate-a-tables-row-groups-through-the-rowgroups-property"></a><span data-ttu-id="3638b-102">如何：通过 RowGroups 属性操作表的行组</span><span class="sxs-lookup"><span data-stu-id="3638b-102">How to: Manipulate a Table's Row Groups through the RowGroups Property</span></span>
<span data-ttu-id="3638b-103">此示例演示了一些较常见的操作可通过表的行组上执行<xref:System.Windows.Documents.Table.RowGroups%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="3638b-103">This example demonstrates some of the more common operations that can be performed on a table's row groups through the <xref:System.Windows.Documents.Table.RowGroups%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3638b-104">示例</span><span class="sxs-lookup"><span data-stu-id="3638b-104">Example</span></span>  
 <span data-ttu-id="3638b-105">下面的示例创建一个新表，然后使用<xref:System.Windows.Documents.TableRowGroupCollection.Add%2A>方法将列添加到表的<xref:System.Windows.Documents.Table.RowGroups%2A>集合。</span><span class="sxs-lookup"><span data-stu-id="3638b-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.RowGroups%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Add](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_add)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Add](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_add)]  
  
## <a name="example"></a><span data-ttu-id="3638b-106">示例</span><span class="sxs-lookup"><span data-stu-id="3638b-106">Example</span></span>  
 <span data-ttu-id="3638b-107">下面的示例插入一个新<xref:System.Windows.Documents.TableRowGroup>。</span><span class="sxs-lookup"><span data-stu-id="3638b-107">The following example inserts a new <xref:System.Windows.Documents.TableRowGroup>.</span></span>  <span data-ttu-id="3638b-108">新列插入到索引位置 0，使其新的第一个行组中的表。</span><span class="sxs-lookup"><span data-stu-id="3638b-108">The new column is inserted at index position 0, making it the new first row group in the table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3638b-109"><xref:System.Windows.Documents.TableRowGroupCollection>集合使用标准的从零开始索引。</span><span class="sxs-lookup"><span data-stu-id="3638b-109">The <xref:System.Windows.Documents.TableRowGroupCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Insert](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_insert)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Insert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_insert)]  
  
## <a name="example"></a><span data-ttu-id="3638b-110">示例</span><span class="sxs-lookup"><span data-stu-id="3638b-110">Example</span></span>  
 <span data-ttu-id="3638b-111">以下示例将多个行添加到特定<xref:System.Windows.Documents.TableRowGroup>（由索引指定） 的表中。</span><span class="sxs-lookup"><span data-stu-id="3638b-111">The following example adds several rows to a particular <xref:System.Windows.Documents.TableRowGroup> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddRows](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addrows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddRows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addrows)]  
  
## <a name="example"></a><span data-ttu-id="3638b-112">示例</span><span class="sxs-lookup"><span data-stu-id="3638b-112">Example</span></span>  
 <span data-ttu-id="3638b-113">以下示例将访问某些表中的第一个行组中的行的任意属性。</span><span class="sxs-lookup"><span data-stu-id="3638b-113">The following example accesses some arbitrary properties on rows in the first row group in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipRows](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_maniprows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipRows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_maniprows)]  
  
## <a name="example"></a><span data-ttu-id="3638b-114">示例</span><span class="sxs-lookup"><span data-stu-id="3638b-114">Example</span></span>  
 <span data-ttu-id="3638b-115">以下示例将多个单元格添加到特定<xref:System.Windows.Documents.TableRow>（由索引指定） 的表中。</span><span class="sxs-lookup"><span data-stu-id="3638b-115">The following example adds several cells to a particular <xref:System.Windows.Documents.TableRow> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddCells](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddCells](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addcells)]  
  
## <a name="example"></a><span data-ttu-id="3638b-116">示例</span><span class="sxs-lookup"><span data-stu-id="3638b-116">Example</span></span>  
 <span data-ttu-id="3638b-117">下面的示例访问一些任意方法和属性中的第一个行组中的第一行的单元格。</span><span class="sxs-lookup"><span data-stu-id="3638b-117">The following example access some arbitrary methods and properties on cells in the first row in the first row group.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipCells](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_manipcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipCells](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_manipcells)]  
  
## <a name="example"></a><span data-ttu-id="3638b-118">示例</span><span class="sxs-lookup"><span data-stu-id="3638b-118">Example</span></span>  
 <span data-ttu-id="3638b-119">下面的示例返回的数<xref:System.Windows.Documents.TableRowGroup>由表承载的元素。</span><span class="sxs-lookup"><span data-stu-id="3638b-119">The following example returns the number of <xref:System.Windows.Documents.TableRowGroup> elements hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Count](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_count)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Count](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_count)]  
  
## <a name="example"></a><span data-ttu-id="3638b-120">示例</span><span class="sxs-lookup"><span data-stu-id="3638b-120">Example</span></span>  
 <span data-ttu-id="3638b-121">下面的示例通过引用中删除特定行组。</span><span class="sxs-lookup"><span data-stu-id="3638b-121">The following example removes a particular row group by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelRef](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delref)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelRef](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delref)]  
  
## <a name="example"></a><span data-ttu-id="3638b-122">示例</span><span class="sxs-lookup"><span data-stu-id="3638b-122">Example</span></span>  
 <span data-ttu-id="3638b-123">下面的示例通过索引中删除特定行组。</span><span class="sxs-lookup"><span data-stu-id="3638b-123">The following example removes a particular row group by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delindex)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelIndex](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delindex)]  
  
## <a name="example"></a><span data-ttu-id="3638b-124">示例</span><span class="sxs-lookup"><span data-stu-id="3638b-124">Example</span></span>  
 <span data-ttu-id="3638b-125">下面的示例从表的行组集合中移除所有行组。</span><span class="sxs-lookup"><span data-stu-id="3638b-125">The following example removes all row groups from the table's row groups collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Clear](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_clear)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Clear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="3638b-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="3638b-126">See also</span></span>

- [<span data-ttu-id="3638b-127">操作说明：通过 Inlines 属性操作流内容元素</span><span class="sxs-lookup"><span data-stu-id="3638b-127">How-to: Manipulate Flow Content Elements through the Inlines Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="3638b-128">通过 Blocks 属性操作 FlowDocument</span><span class="sxs-lookup"><span data-stu-id="3638b-128">Manipulate a FlowDocument through the Blocks Property</span></span>](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="3638b-129">通过 Columns 属性操作表的列</span><span class="sxs-lookup"><span data-stu-id="3638b-129">Manipulate a Table's Columns through the Columns Property</span></span>](how-to-manipulate-table-columns-through-the-columns-property.md)
