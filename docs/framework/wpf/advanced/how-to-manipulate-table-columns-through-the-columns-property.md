---
title: "如何： 处理表 &#39; s 列通过列属性"
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
- documents [WPF], manipulating table columns
- properties [WPF], Columns [WPF], manipulating table columns
- tables [WPF], manipulating columns
- Columns property [WPF]
ms.assetid: 3f8884f4-7e1f-456b-be06-fbd3cf469bf3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8264e49b29f5a790e37c97c3683d7bf09e850c3e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-manipulate-a-table39s-columns-through-the-columns-property"></a><span data-ttu-id="be5be-102">如何： 处理表 &#39; s 列通过列属性</span><span class="sxs-lookup"><span data-stu-id="be5be-102">How to: Manipulate a Table&#39;s Columns through the Columns Property</span></span>
<span data-ttu-id="be5be-103">此示例演示一些较常见的操作，可以对表的列执行<xref:System.Windows.Documents.Table.Columns%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="be5be-103">This example demonstrates some of the more common operations that can be performed on a table's columns through the <xref:System.Windows.Documents.Table.Columns%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be5be-104">示例</span><span class="sxs-lookup"><span data-stu-id="be5be-104">Example</span></span>  
 <span data-ttu-id="be5be-105">下面的示例创建一个新表，然后使用<xref:System.Windows.Documents.TableColumnCollection.Add%2A>方法将列添加到表的<xref:System.Windows.Documents.Table.Columns%2A>集合。</span><span class="sxs-lookup"><span data-stu-id="be5be-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableColumnCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## <a name="example"></a><span data-ttu-id="be5be-106">示例</span><span class="sxs-lookup"><span data-stu-id="be5be-106">Example</span></span>  
 <span data-ttu-id="be5be-107">下面的示例将一个新<xref:System.Windows.Documents.TableColumn>。</span><span class="sxs-lookup"><span data-stu-id="be5be-107">The following example inserts a new <xref:System.Windows.Documents.TableColumn>.</span></span>  <span data-ttu-id="be5be-108">在索引位置 0，令其成为表中新的第一个列插入新列。</span><span class="sxs-lookup"><span data-stu-id="be5be-108">The new column is inserted at index position 0, making it the new first column in the table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be5be-109"><xref:System.Windows.Documents.TableColumnCollection>集合使用标准的从零开始索引。</span><span class="sxs-lookup"><span data-stu-id="be5be-109">The <xref:System.Windows.Documents.TableColumnCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## <a name="example"></a><span data-ttu-id="be5be-110">示例</span><span class="sxs-lookup"><span data-stu-id="be5be-110">Example</span></span>  
 <span data-ttu-id="be5be-111">以下示例访问中的列上的一些任意属性<xref:System.Windows.Documents.TableColumnCollection>集合，按索引引用特定的列。</span><span class="sxs-lookup"><span data-stu-id="be5be-111">The following example accesses some arbitrary properties on columns in the <xref:System.Windows.Documents.TableColumnCollection> collection, referring to particular columns by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## <a name="example"></a><span data-ttu-id="be5be-112">示例</span><span class="sxs-lookup"><span data-stu-id="be5be-112">Example</span></span>  
 <span data-ttu-id="be5be-113">下面的示例获取当前由表承载的列数。</span><span class="sxs-lookup"><span data-stu-id="be5be-113">The following example gets the number of columns currently hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## <a name="example"></a><span data-ttu-id="be5be-114">示例</span><span class="sxs-lookup"><span data-stu-id="be5be-114">Example</span></span>  
 <span data-ttu-id="be5be-115">下面的示例通过引用来消除特定列。</span><span class="sxs-lookup"><span data-stu-id="be5be-115">The following example removes a particular column by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## <a name="example"></a><span data-ttu-id="be5be-116">示例</span><span class="sxs-lookup"><span data-stu-id="be5be-116">Example</span></span>  
 <span data-ttu-id="be5be-117">下面的示例按索引删除特定的列。</span><span class="sxs-lookup"><span data-stu-id="be5be-117">The following example removes a particular column by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## <a name="example"></a><span data-ttu-id="be5be-118">示例</span><span class="sxs-lookup"><span data-stu-id="be5be-118">Example</span></span>  
 <span data-ttu-id="be5be-119">下面的示例从表的列集合中移除所有列。</span><span class="sxs-lookup"><span data-stu-id="be5be-119">The following example removes all columns from the table's columns collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="be5be-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="be5be-120">See Also</span></span>  
 [<span data-ttu-id="be5be-121">表概述</span><span class="sxs-lookup"><span data-stu-id="be5be-121">Table Overview</span></span>](../../../../docs/framework/wpf/advanced/table-overview.md)  
 [<span data-ttu-id="be5be-122">使用 XAML 定义表</span><span class="sxs-lookup"><span data-stu-id="be5be-122">Define a Table with XAML</span></span>](../../../../docs/framework/wpf/advanced/how-to-define-a-table-with-xaml.md)  
 [<span data-ttu-id="be5be-123">以编程方式生成表</span><span class="sxs-lookup"><span data-stu-id="be5be-123">Build a Table Programmatically</span></span>](../../../../docs/framework/wpf/advanced/how-to-build-a-table-programmatically.md)  
 [<span data-ttu-id="be5be-124">通过 RowGroups 属性操作表的行组</span><span class="sxs-lookup"><span data-stu-id="be5be-124">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)  
 [<span data-ttu-id="be5be-125">通过 Blocks 属性控制 FlowDocument</span><span class="sxs-lookup"><span data-stu-id="be5be-125">Manipulate a FlowDocument through the Blocks Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [<span data-ttu-id="be5be-126">通过 RowGroups 属性操作表的行组</span><span class="sxs-lookup"><span data-stu-id="be5be-126">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
