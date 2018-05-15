---
title: DataRow 删除
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
ms.openlocfilehash: 128c41e1906b17e7f42458e8a5f1b3d3ec9cc449
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="datarow-deletion"></a><span data-ttu-id="5a9a6-102">DataRow 删除</span><span class="sxs-lookup"><span data-stu-id="5a9a6-102">DataRow Deletion</span></span>
<span data-ttu-id="5a9a6-103">有两种方法可用于删除<xref:System.Data.DataRow>对象<xref:System.Data.DataTable>对象：**删除**方法<xref:System.Data.DataRowCollection>对象，与<xref:System.Data.DataRow.Delete%2A>方法**DataRow**对象。</span><span class="sxs-lookup"><span data-stu-id="5a9a6-103">There are two methods you can use to delete a <xref:System.Data.DataRow> object from a <xref:System.Data.DataTable> object: the **Remove** method of the <xref:System.Data.DataRowCollection> object, and the <xref:System.Data.DataRow.Delete%2A> method of the **DataRow** object.</span></span> <span data-ttu-id="5a9a6-104">而<xref:System.Data.DataRowCollection.Remove%2A>方法删除**DataRow**从**DataRowCollection**、<xref:System.Data.DataRow.Delete%2A>方法仅标记要删除的行。</span><span class="sxs-lookup"><span data-stu-id="5a9a6-104">Whereas the <xref:System.Data.DataRowCollection.Remove%2A> method deletes a **DataRow** from the **DataRowCollection**, the <xref:System.Data.DataRow.Delete%2A> method only marks the row for deletion.</span></span> <span data-ttu-id="5a9a6-105">当应用程序调用时，会发生实际移除**AcceptChanges**方法。</span><span class="sxs-lookup"><span data-stu-id="5a9a6-105">The actual removal occurs when the application calls the **AcceptChanges** method.</span></span> <span data-ttu-id="5a9a6-106">通过使用 <xref:System.Data.DataRow.Delete%2A>，您可以在实际删除行之前，先以编程方式来检查哪些行已标记为删除。</span><span class="sxs-lookup"><span data-stu-id="5a9a6-106">By using <xref:System.Data.DataRow.Delete%2A>, you can programmatically check which rows are marked for deletion before actually removing them.</span></span> <span data-ttu-id="5a9a6-107">如果将行标记为删除，则该行的 <xref:System.Data.DataRow.RowState%2A> 属性会设置为 <xref:System.Data.DataRow.Delete%2A>。</span><span class="sxs-lookup"><span data-stu-id="5a9a6-107">When a row is marked for deletion, its <xref:System.Data.DataRow.RowState%2A> property is set to <xref:System.Data.DataRow.Delete%2A>.</span></span>  
  
 <span data-ttu-id="5a9a6-108">在 foreach 循环中，不会调用 <xref:System.Data.DataRow.Delete%2A> 和 <xref:System.Data.DataRowCollection.Remove%2A>，而是循环访问 <xref:System.Data.DataRowCollection> 对象。</span><span class="sxs-lookup"><span data-stu-id="5a9a6-108">Neither <xref:System.Data.DataRow.Delete%2A> nor <xref:System.Data.DataRowCollection.Remove%2A> should be called in a foreach loop while iterating through a <xref:System.Data.DataRowCollection> object.</span></span> <span data-ttu-id="5a9a6-109"><xref:System.Data.DataRow.Delete%2A> 和 <xref:System.Data.DataRowCollection.Remove%2A> 不会修改该集合的状态。</span><span class="sxs-lookup"><span data-stu-id="5a9a6-109"><xref:System.Data.DataRow.Delete%2A> nor <xref:System.Data.DataRowCollection.Remove%2A> modify the state of the collection.</span></span>  
  
 <span data-ttu-id="5a9a6-110">使用时<xref:System.Data.DataSet>或**DataTable**结合**DataAdapter**和关系数据源，使用**删除**方法**DataRow**以删除的行。</span><span class="sxs-lookup"><span data-stu-id="5a9a6-110">When using a <xref:System.Data.DataSet> or **DataTable** in conjunction with a **DataAdapter** and a relational data source, use the **Delete** method of the **DataRow** to remove the row.</span></span> <span data-ttu-id="5a9a6-111">**删除**方法将行标记为**已删除**中**数据集**或**DataTable**但不会删除它。</span><span class="sxs-lookup"><span data-stu-id="5a9a6-111">The **Delete** method marks the row as **Deleted** in the **DataSet** or **DataTable** but does not remove it.</span></span> <span data-ttu-id="5a9a6-112">相反，当**DataAdapter**遇到标记为**已删除**，它会执行其**DeleteCommand**方法来删除数据源处的行。</span><span class="sxs-lookup"><span data-stu-id="5a9a6-112">Instead, when the **DataAdapter** encounters a row marked as **Deleted**, it executes its **DeleteCommand** method to delete the row at the data source.</span></span> <span data-ttu-id="5a9a6-113">行可以永久删除使用**AcceptChanges**方法。</span><span class="sxs-lookup"><span data-stu-id="5a9a6-113">The row can then be permanently removed using the **AcceptChanges** method.</span></span> <span data-ttu-id="5a9a6-114">如果你使用**删除**若要删除的行，该行是完全从表中删除，但**DataAdapter**不会删除数据源处的行。</span><span class="sxs-lookup"><span data-stu-id="5a9a6-114">If you use **Remove** to delete the row, the row is removed entirely from the table, but the **DataAdapter** will not delete the row at the data source.</span></span>  
  
 <span data-ttu-id="5a9a6-115">**删除**方法**DataRowCollection**采用**DataRow**作为自变量并将其删除集合中的属性，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="5a9a6-115">The **Remove** method of the **DataRowCollection** takes a **DataRow** as an argument and removes it from the collection, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 <span data-ttu-id="5a9a6-116">与此相反，下面的示例演示如何调用**删除**方法**DataRow**若要更改其**RowState**到**已删除**.</span><span class="sxs-lookup"><span data-stu-id="5a9a6-116">In contrast, the following example demonstrates how to call the **Delete** method on a **DataRow** to change its **RowState** to **Deleted**.</span></span>  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 <span data-ttu-id="5a9a6-117">如果某行标记为删除，并且你调用**AcceptChanges**方法**DataTable**对象，则该行移除从**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="5a9a6-117">If a row is marked for deletion and you call the **AcceptChanges** method of the **DataTable** object, the row is removed from the **DataTable**.</span></span> <span data-ttu-id="5a9a6-118">相反，如果调用**RejectChanges**、 **RowState**的行将恢复为之前被标记为**已删除**。</span><span class="sxs-lookup"><span data-stu-id="5a9a6-118">In contrast, if you call **RejectChanges**, the **RowState** of the row reverts to what it was before being marked as **Deleted**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a9a6-119">如果**RowState**的**DataRow**是**Added**，这意味着它刚添加到表中，然后将其标记为**已删除**，它是从表中删除。</span><span class="sxs-lookup"><span data-stu-id="5a9a6-119">If the **RowState** of a **DataRow** is **Added**, meaning it has just been added to the table, and it is then marked as **Deleted**, it is removed from the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a9a6-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a9a6-120">See Also</span></span>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataRowCollection>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="5a9a6-121">操作数据表中的数据</span><span class="sxs-lookup"><span data-stu-id="5a9a6-121">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="5a9a6-122">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="5a9a6-122">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
