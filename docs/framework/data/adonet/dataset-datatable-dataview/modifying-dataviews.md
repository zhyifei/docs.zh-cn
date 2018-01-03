---
title: "修改 DataView"
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
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 921707b07f1e8c8a9208df7de74512325f3027d2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="modifying-dataviews"></a><span data-ttu-id="5d373-102">修改 DataView</span><span class="sxs-lookup"><span data-stu-id="5d373-102">Modifying DataViews</span></span>
<span data-ttu-id="5d373-103">可以使用 <xref:System.Data.DataView> 在基础表中添加、删除或修改数据行。</span><span class="sxs-lookup"><span data-stu-id="5d373-103">You can use the <xref:System.Data.DataView> to add, delete, or modify rows of data in the underlying table.</span></span> <span data-ttu-id="5d373-104">能够使用**DataView**修改基础表中的数据通过设置三个布尔值属性之一控制**DataView**。</span><span class="sxs-lookup"><span data-stu-id="5d373-104">The ability to use the **DataView** to modify data in the underlying table is controlled by setting one of three Boolean properties of the **DataView**.</span></span> <span data-ttu-id="5d373-105">这三个属性是 <xref:System.Data.DataView.AllowNew%2A>、<xref:System.Data.DataView.AllowEdit%2A> 和 <xref:System.Data.DataView.AllowDelete%2A>。</span><span class="sxs-lookup"><span data-stu-id="5d373-105">These properties are <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A>, and <xref:System.Data.DataView.AllowDelete%2A>.</span></span> <span data-ttu-id="5d373-106">它们将设置为**true**默认情况下。</span><span class="sxs-lookup"><span data-stu-id="5d373-106">They are set to **true** by default.</span></span>  
  
 <span data-ttu-id="5d373-107">如果**AllowNew**是**true**，你可以使用<xref:System.Data.DataView.AddNew%2A>方法**DataView**创建新<xref:System.Data.DataRowView>。</span><span class="sxs-lookup"><span data-stu-id="5d373-107">If **AllowNew** is **true**, you can use the <xref:System.Data.DataView.AddNew%2A> method of the **DataView** to create a new <xref:System.Data.DataRowView>.</span></span> <span data-ttu-id="5d373-108">请注意，新行不会实际添加到基础<xref:System.Data.DataTable>直到<xref:System.Data.DataRowView.EndEdit%2A>方法**DataRowView**调用。</span><span class="sxs-lookup"><span data-stu-id="5d373-108">Note that a new row is not actually added to the underlying <xref:System.Data.DataTable> until the <xref:System.Data.DataRowView.EndEdit%2A> method of the **DataRowView** is called.</span></span> <span data-ttu-id="5d373-109">如果<xref:System.Data.DataRowView.CancelEdit%2A>方法**DataRowView**是调用，将丢弃新行。</span><span class="sxs-lookup"><span data-stu-id="5d373-109">If the <xref:System.Data.DataRowView.CancelEdit%2A> method of the **DataRowView** is called, the new row is discarded.</span></span> <span data-ttu-id="5d373-110">还要注意，您可以编辑只有一个**DataRowView**一次。</span><span class="sxs-lookup"><span data-stu-id="5d373-110">Note also that you can edit only one **DataRowView** at a time.</span></span> <span data-ttu-id="5d373-111">如果调用**AddNew**或**BeginEdit**方法**DataRowView**虽然存在挂起行， **EndEdit**对隐式调用挂起的行。</span><span class="sxs-lookup"><span data-stu-id="5d373-111">If you call the **AddNew** or **BeginEdit** method of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="5d373-112">当**EndEdit**是调用，所做的更改应用于基础**DataTable**和更高版本可以提交或拒绝使用**AcceptChanges**或**RejectChanges**方法**DataTable**，**数据集**，或**DataRow**对象。</span><span class="sxs-lookup"><span data-stu-id="5d373-112">When **EndEdit** is called, the changes are applied to the underlying **DataTable** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="5d373-113">如果**AllowNew**是**false**，如果调用引发异常**AddNew**方法**DataRowView**。</span><span class="sxs-lookup"><span data-stu-id="5d373-113">If **AllowNew** is **false**, an exception is thrown if you call the **AddNew** method of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="5d373-114">如果**AllowEdit**是**true**，你可以修改的内容**DataRow**通过**DataRowView**。</span><span class="sxs-lookup"><span data-stu-id="5d373-114">If **AllowEdit** is **true**, you can modify the contents of a **DataRow** via the **DataRowView**.</span></span> <span data-ttu-id="5d373-115">你可以确认对基础行使用的更改**DataRowView.EndEdit**或拒绝更改使用**DataRowView.CancelEdit**。</span><span class="sxs-lookup"><span data-stu-id="5d373-115">You can confirm changes to the underlying row using **DataRowView.EndEdit** or reject the changes using **DataRowView.CancelEdit**.</span></span> <span data-ttu-id="5d373-116">注意，一次只能编辑一行。</span><span class="sxs-lookup"><span data-stu-id="5d373-116">Note that only one row can be edited at a time.</span></span> <span data-ttu-id="5d373-117">如果调用**AddNew**或**BeginEdit**方法**DataRowView**虽然存在挂起行， **EndEdit**对隐式调用挂起的行。</span><span class="sxs-lookup"><span data-stu-id="5d373-117">If you call the **AddNew** or **BeginEdit** methods of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="5d373-118">当**EndEdit**调用时，建议的更改都将置于**当前**的基础的行版本**DataRow**和更高版本可以提交或拒绝使用**AcceptChanges**或**RejectChanges**方法**DataTable**，**数据集**，或**DataRow**对象。</span><span class="sxs-lookup"><span data-stu-id="5d373-118">When **EndEdit** is called, proposed changes are placed in the **Current** row version of the underlying **DataRow** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="5d373-119">如果**AllowEdit**是**false**，如果您尝试修改中的值将引发异常**DataView**。</span><span class="sxs-lookup"><span data-stu-id="5d373-119">If **AllowEdit** is **false**, an exception is thrown if you attempt to modify a value in the **DataView**.</span></span>  
  
 <span data-ttu-id="5d373-120">如果现有**DataRowView**正在编辑的基础事件**DataTable**仍将引发与建议的更改。</span><span class="sxs-lookup"><span data-stu-id="5d373-120">When an existing **DataRowView** is being edited, events of the underlying **DataTable** will still be raised with the proposed changes.</span></span> <span data-ttu-id="5d373-121">请注意，如果你调用**EndEdit**或**CancelEdit**基础**DataRow**、 挂起的更改将应用或取消而不管是否**EndEdit**或**CancelEdit**上调用**DataRowView**。</span><span class="sxs-lookup"><span data-stu-id="5d373-121">Note that if you call **EndEdit** or **CancelEdit** on the underlying **DataRow**, pending changes will be applied or canceled regardless of whether **EndEdit** or **CancelEdit** is called on the **DataRowView**.</span></span>  
  
 <span data-ttu-id="5d373-122">如果**AllowDelete**是**true**，你可以删除行从**DataView**使用**删除**方法**DataView**或**DataRowView**从基础删除对象，并且行**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="5d373-122">If **AllowDelete** is **true**, you can delete rows from the **DataView** by using the **Delete** method of the **DataView** or **DataRowView** object, and the rows are deleted from the underlying **DataTable**.</span></span> <span data-ttu-id="5d373-123">以后可以提交或拒绝删除使用**AcceptChanges**或**RejectChanges**分别。</span><span class="sxs-lookup"><span data-stu-id="5d373-123">You can later commit or reject the deletes using **AcceptChanges** or **RejectChanges** respectively.</span></span> <span data-ttu-id="5d373-124">如果**AllowDelete**是**false**，如果调用引发异常**删除**方法**DataView**或**DataRowView**。</span><span class="sxs-lookup"><span data-stu-id="5d373-124">If **AllowDelete** is **false**, an exception is thrown if you call the **Delete** method of the **DataView** or **DataRowView**.</span></span>  
  
 <span data-ttu-id="5d373-125">下面的代码示例禁用通过**DataView**到删除的行，并将新行添加到基础表使用**DataView**。</span><span class="sxs-lookup"><span data-stu-id="5d373-125">The following code example disables using the **DataView** to delete rows  and adds a new row to the underlying table using the **DataView**.</span></span>  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custView As DataView = custTable.DefaultView  
custView.Sort = "CompanyName"  
  
custView.AllowDelete = False  
  
Dim newDRV As DataRowView = custView.AddNew()  
newDRV("CustomerID") = "ABCDE"  
newDRV("CompanyName") = "ABC Products"  
newDRV.EndEdit()  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
DataView custView = custTable.DefaultView;  
custView.Sort = "CompanyName";  
  
custView.AllowDelete = false;  
  
DataRowView newDRV = custView.AddNew();  
newDRV["CustomerID"] = "ABCDE";  
newDRV["CompanyName"] = "ABC Products";  
newDRV.EndEdit();  
```  
  
## <a name="see-also"></a><span data-ttu-id="5d373-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d373-126">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 <xref:System.Data.DataRowView>  
 [<span data-ttu-id="5d373-127">数据视图</span><span class="sxs-lookup"><span data-stu-id="5d373-127">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="5d373-128">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="5d373-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
