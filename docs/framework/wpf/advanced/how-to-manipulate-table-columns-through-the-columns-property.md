---
title: 如何：通过 Columns 属性操作表列
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], manipulating table columns
- properties [WPF], Columns [WPF], manipulating table columns
- tables [WPF], manipulating columns
- Columns property [WPF]
ms.assetid: 3f8884f4-7e1f-456b-be06-fbd3cf469bf3
ms.openlocfilehash: e7b2c1923f7262417f44cb5ac2ea057ef6c83690
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358504"
---
# <a name="how-to-manipulate-a-tables-columns-through-the-columns-property"></a><span data-ttu-id="11f9c-102">如何：通过 Columns 属性操作表列</span><span class="sxs-lookup"><span data-stu-id="11f9c-102">How to: Manipulate a Table's Columns through the Columns Property</span></span>
<span data-ttu-id="11f9c-103">此示例演示了一些较常见的操作可通过表的列上执行<xref:System.Windows.Documents.Table.Columns%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="11f9c-103">This example demonstrates some of the more common operations that can be performed on a table's columns through the <xref:System.Windows.Documents.Table.Columns%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11f9c-104">示例</span><span class="sxs-lookup"><span data-stu-id="11f9c-104">Example</span></span>  
 <span data-ttu-id="11f9c-105">下面的示例创建一个新表，然后使用<xref:System.Windows.Documents.TableColumnCollection.Add%2A>方法将列添加到表的<xref:System.Windows.Documents.Table.Columns%2A>集合。</span><span class="sxs-lookup"><span data-stu-id="11f9c-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableColumnCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## <a name="example"></a><span data-ttu-id="11f9c-106">示例</span><span class="sxs-lookup"><span data-stu-id="11f9c-106">Example</span></span>  
 <span data-ttu-id="11f9c-107">下面的示例插入一个新<xref:System.Windows.Documents.TableColumn>。</span><span class="sxs-lookup"><span data-stu-id="11f9c-107">The following example inserts a new <xref:System.Windows.Documents.TableColumn>.</span></span>  <span data-ttu-id="11f9c-108">在索引位置 0，使之成为新的第一列在表中插入新列。</span><span class="sxs-lookup"><span data-stu-id="11f9c-108">The new column is inserted at index position 0, making it the new first column in the table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11f9c-109"><xref:System.Windows.Documents.TableColumnCollection>集合使用标准的从零开始索引。</span><span class="sxs-lookup"><span data-stu-id="11f9c-109">The <xref:System.Windows.Documents.TableColumnCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## <a name="example"></a><span data-ttu-id="11f9c-110">示例</span><span class="sxs-lookup"><span data-stu-id="11f9c-110">Example</span></span>  
 <span data-ttu-id="11f9c-111">以下示例将访问某些列中的任意属性<xref:System.Windows.Documents.TableColumnCollection>集合，通过索引来引用特定列。</span><span class="sxs-lookup"><span data-stu-id="11f9c-111">The following example accesses some arbitrary properties on columns in the <xref:System.Windows.Documents.TableColumnCollection> collection, referring to particular columns by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## <a name="example"></a><span data-ttu-id="11f9c-112">示例</span><span class="sxs-lookup"><span data-stu-id="11f9c-112">Example</span></span>  
 <span data-ttu-id="11f9c-113">下面的示例获取当前由表承载的列数。</span><span class="sxs-lookup"><span data-stu-id="11f9c-113">The following example gets the number of columns currently hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## <a name="example"></a><span data-ttu-id="11f9c-114">示例</span><span class="sxs-lookup"><span data-stu-id="11f9c-114">Example</span></span>  
 <span data-ttu-id="11f9c-115">下面的示例通过引用来消除特定列。</span><span class="sxs-lookup"><span data-stu-id="11f9c-115">The following example removes a particular column by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## <a name="example"></a><span data-ttu-id="11f9c-116">示例</span><span class="sxs-lookup"><span data-stu-id="11f9c-116">Example</span></span>  
 <span data-ttu-id="11f9c-117">下面的示例通过索引来消除特定列。</span><span class="sxs-lookup"><span data-stu-id="11f9c-117">The following example removes a particular column by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## <a name="example"></a><span data-ttu-id="11f9c-118">示例</span><span class="sxs-lookup"><span data-stu-id="11f9c-118">Example</span></span>  
 <span data-ttu-id="11f9c-119">下面的示例从表的列集合中移除所有列。</span><span class="sxs-lookup"><span data-stu-id="11f9c-119">The following example removes all columns from the table's columns collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="11f9c-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="11f9c-120">See also</span></span>
- [<span data-ttu-id="11f9c-121">表概述</span><span class="sxs-lookup"><span data-stu-id="11f9c-121">Table Overview</span></span>](table-overview.md)
- [<span data-ttu-id="11f9c-122">使用 XAML 定义表</span><span class="sxs-lookup"><span data-stu-id="11f9c-122">Define a Table with XAML</span></span>](how-to-define-a-table-with-xaml.md)
- [<span data-ttu-id="11f9c-123">以编程方式生成表</span><span class="sxs-lookup"><span data-stu-id="11f9c-123">Build a Table Programmatically</span></span>](how-to-build-a-table-programmatically.md)
- [<span data-ttu-id="11f9c-124">通过 RowGroups 属性操作表的行组</span><span class="sxs-lookup"><span data-stu-id="11f9c-124">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="11f9c-125">通过 Blocks 属性控制 FlowDocument</span><span class="sxs-lookup"><span data-stu-id="11f9c-125">Manipulate a FlowDocument through the Blocks Property</span></span>](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="11f9c-126">通过 RowGroups 属性操作表的行组</span><span class="sxs-lookup"><span data-stu-id="11f9c-126">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
