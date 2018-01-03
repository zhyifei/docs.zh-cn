---
title: "在 DataView 中查询 DataRowView 集合"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: b9070a12-1094-44d6-bb87-a23b50bcb0af
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 02b32157fe88bddfd9a777042f6da87aa48ca551
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="querying-the-datarowview-collection-in-a-dataview"></a><span data-ttu-id="87f04-102">在 DataView 中查询 DataRowView 集合</span><span class="sxs-lookup"><span data-stu-id="87f04-102">Querying the DataRowView Collection in a DataView</span></span>
<span data-ttu-id="87f04-103"><xref:System.Data.DataView> 公开了 <xref:System.Data.DataRowView> 对象的可枚举集合。</span><span class="sxs-lookup"><span data-stu-id="87f04-103">The <xref:System.Data.DataView> exposes an enumerable collection of <xref:System.Data.DataRowView> objects.</span></span> <span data-ttu-id="87f04-104"><xref:System.Data.DataRowView> 表示 <xref:System.Data.DataRow> 的自定义视图，并在控件中显示特定版本的 <xref:System.Data.DataRow>。</span><span class="sxs-lookup"><span data-stu-id="87f04-104"><xref:System.Data.DataRowView> represents a customized view of a <xref:System.Data.DataRow> and displays a specific version of that <xref:System.Data.DataRow> in a control.</span></span> <span data-ttu-id="87f04-105">只有一种版本的 <xref:System.Data.DataRow> 可通过控件显示，例如 <xref:System.Windows.Forms.DataGridView>。</span><span class="sxs-lookup"><span data-stu-id="87f04-105">Only one version of a <xref:System.Data.DataRow> can be displayed through a control, such as a <xref:System.Windows.Forms.DataGridView>.</span></span> <span data-ttu-id="87f04-106">您可以通过 <xref:System.Data.DataRow> 的 <xref:System.Data.DataRowView> 属性访问 <xref:System.Data.DataRowView.Row%2A> 公开的 <xref:System.Data.DataRowView>。</span><span class="sxs-lookup"><span data-stu-id="87f04-106">You can access the <xref:System.Data.DataRow> that is exposed by the <xref:System.Data.DataRowView> through the <xref:System.Data.DataRowView.Row%2A> property of the <xref:System.Data.DataRowView>.</span></span> <span data-ttu-id="87f04-107">当使用 <xref:System.Data.DataRowView> 查看值时，<xref:System.Data.DataView.RowStateFilter%2A> 属性决定公开基础 <xref:System.Data.DataRow> 的哪个行版本。</span><span class="sxs-lookup"><span data-stu-id="87f04-107">When you view values by using a <xref:System.Data.DataRowView>, the <xref:System.Data.DataView.RowStateFilter%2A> property determines which row version of the underlying <xref:System.Data.DataRow> is exposed.</span></span> <span data-ttu-id="87f04-108">有关访问使用不同的行版本信息<xref:System.Data.DataRow>，请参阅[行状态和行版本](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)。</span><span class="sxs-lookup"><span data-stu-id="87f04-108">For information about accessing different row versions using a <xref:System.Data.DataRow>, see [Row States and Row Versions](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span> <span data-ttu-id="87f04-109">因为 <xref:System.Data.DataRowView> 公开的 <xref:System.Data.DataView> 对象的集合是可枚举的，所以您可以使用 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 对它执行查询。</span><span class="sxs-lookup"><span data-stu-id="87f04-109">Because the collection of <xref:System.Data.DataRowView> objects exposed by the <xref:System.Data.DataView> is enumerable, you can use [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] to query over it.</span></span>  
  
 <span data-ttu-id="87f04-110">下面的示例对 `Product` 表执行查询查找红色的产品，并从该查询创建表。</span><span class="sxs-lookup"><span data-stu-id="87f04-110">The following example queries the `Product` table for red-colored products and creates a table from that query.</span></span> <span data-ttu-id="87f04-111">从该表创建 <xref:System.Data.DataView> 并将 <xref:System.Data.DataView.RowStateFilter%2A> 属性设置为筛选已删除和修改的行。</span><span class="sxs-lookup"><span data-stu-id="87f04-111">A <xref:System.Data.DataView> is created from the table and the <xref:System.Data.DataView.RowStateFilter%2A> property is set to filter on deleted and modified rows.</span></span> <span data-ttu-id="87f04-112">然后将 <xref:System.Data.DataView> 用作 LINQ 查询中的源，并将已修改和删除的 <xref:System.Data.DataRowView> 对象绑定到 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="87f04-112">The <xref:System.Data.DataView> is then used as a source in a LINQ query, and the <xref:System.Data.DataRowView> objects that have been modified and deleted are bound to a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[DP DataView Samples#QueryDataView2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#querydataview2)]
 [!code-vb[DP DataView Samples#QueryDataView2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#querydataview2)]  
  
 <span data-ttu-id="87f04-113">下面的示例从绑定到 <xref:System.Windows.Forms.DataGridView> 控件的视图创建了一个产品表。</span><span class="sxs-lookup"><span data-stu-id="87f04-113">The following example creates a table of products from a view that is bound to a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="87f04-114">对 <xref:System.Data.DataView> 进行查询查找红色的产品，并将排序的结果绑定到 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="87f04-114">The <xref:System.Data.DataView> is queried for red-colored products and the ordered results are bound to a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[DP DataView Samples#QueryDataView1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#querydataview1)]
 [!code-vb[DP DataView Samples#QueryDataView1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#querydataview1)]  
  
## <a name="see-also"></a><span data-ttu-id="87f04-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="87f04-115">See Also</span></span>  
 [<span data-ttu-id="87f04-116">数据绑定和 LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="87f04-116">Data Binding and LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)
