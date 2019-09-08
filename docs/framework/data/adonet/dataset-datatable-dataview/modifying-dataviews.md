---
title: 修改 DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
ms.openlocfilehash: 3e811410ea9fdd4be0cbd84b895483f69f58b0d0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786053"
---
# <a name="modifying-dataviews"></a><span data-ttu-id="aa25a-102">修改 DataView</span><span class="sxs-lookup"><span data-stu-id="aa25a-102">Modifying DataViews</span></span>
<span data-ttu-id="aa25a-103">可以使用 <xref:System.Data.DataView> 在基础表中添加、删除或修改数据行。</span><span class="sxs-lookup"><span data-stu-id="aa25a-103">You can use the <xref:System.Data.DataView> to add, delete, or modify rows of data in the underlying table.</span></span> <span data-ttu-id="aa25a-104">使用**dataview**修改基础表中数据的功能是通过设置**dataview**的三个布尔属性之一来控制的。</span><span class="sxs-lookup"><span data-stu-id="aa25a-104">The ability to use the **DataView** to modify data in the underlying table is controlled by setting one of three Boolean properties of the **DataView**.</span></span> <span data-ttu-id="aa25a-105">这三个属性是 <xref:System.Data.DataView.AllowNew%2A>、<xref:System.Data.DataView.AllowEdit%2A> 和 <xref:System.Data.DataView.AllowDelete%2A>。</span><span class="sxs-lookup"><span data-stu-id="aa25a-105">These properties are <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A>, and <xref:System.Data.DataView.AllowDelete%2A>.</span></span> <span data-ttu-id="aa25a-106">默认情况下，它们设置为**true** 。</span><span class="sxs-lookup"><span data-stu-id="aa25a-106">They are set to **true** by default.</span></span>  
  
 <span data-ttu-id="aa25a-107">如果**AllowNew**为**true**，则<xref:System.Data.DataView.AddNew%2A>可以使用**DataView**的方法来创建新<xref:System.Data.DataRowView>的。</span><span class="sxs-lookup"><span data-stu-id="aa25a-107">If **AllowNew** is **true**, you can use the <xref:System.Data.DataView.AddNew%2A> method of the **DataView** to create a new <xref:System.Data.DataRowView>.</span></span> <span data-ttu-id="aa25a-108">请注意，在调用<xref:System.Data.DataTable> **DataRowView**的<xref:System.Data.DataRowView.EndEdit%2A>方法之前，新行实际上不会添加到基础中。</span><span class="sxs-lookup"><span data-stu-id="aa25a-108">Note that a new row is not actually added to the underlying <xref:System.Data.DataTable> until the <xref:System.Data.DataRowView.EndEdit%2A> method of the **DataRowView** is called.</span></span> <span data-ttu-id="aa25a-109">如果调用**DataRowView**的方法，则将丢弃新行。<xref:System.Data.DataRowView.CancelEdit%2A></span><span class="sxs-lookup"><span data-stu-id="aa25a-109">If the <xref:System.Data.DataRowView.CancelEdit%2A> method of the **DataRowView** is called, the new row is discarded.</span></span> <span data-ttu-id="aa25a-110">另请注意，一次只能编辑一个**DataRowView** 。</span><span class="sxs-lookup"><span data-stu-id="aa25a-110">Note also that you can edit only one **DataRowView** at a time.</span></span> <span data-ttu-id="aa25a-111">如果在存在挂起行时调用**DataRowView**的**AddNew**或**BeginEdit**方法，则会对挂起行隐式调用**EndEdit** 。</span><span class="sxs-lookup"><span data-stu-id="aa25a-111">If you call the **AddNew** or **BeginEdit** method of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="aa25a-112">调用**EndEdit**时，所做的更改将应用于基础**DataTable** ，以后可以使用**DataTable**、 **DataSet** **或的 AcceptChanges 或 RejectChanges 方法来提交或拒绝这些更改。DataRow**对象。</span><span class="sxs-lookup"><span data-stu-id="aa25a-112">When **EndEdit** is called, the changes are applied to the underlying **DataTable** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="aa25a-113">如果**AllowNew**为**false**，则当调用**DataRowView**的**AddNew**方法时，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="aa25a-113">If **AllowNew** is **false**, an exception is thrown if you call the **AddNew** method of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="aa25a-114">如果**AllowEdit**为**true**，则可以通过**DataRowView**修改**DataRow**的内容。</span><span class="sxs-lookup"><span data-stu-id="aa25a-114">If **AllowEdit** is **true**, you can modify the contents of a **DataRow** via the **DataRowView**.</span></span> <span data-ttu-id="aa25a-115">您可以使用**DataRowView**确认对基础行所做的更改，或使用**DataRowView**拒绝更改。</span><span class="sxs-lookup"><span data-stu-id="aa25a-115">You can confirm changes to the underlying row using **DataRowView.EndEdit** or reject the changes using **DataRowView.CancelEdit**.</span></span> <span data-ttu-id="aa25a-116">注意，一次只能编辑一行。</span><span class="sxs-lookup"><span data-stu-id="aa25a-116">Note that only one row can be edited at a time.</span></span> <span data-ttu-id="aa25a-117">如果在存在挂起行时调用**DataRowView**的**AddNew**或**BeginEdit**方法，则会对挂起行隐式调用**EndEdit** 。</span><span class="sxs-lookup"><span data-stu-id="aa25a-117">If you call the **AddNew** or **BeginEdit** methods of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="aa25a-118">调用**EndEdit**时，建议的更改将放置在基础**DataRow**的**当前**行版本中，以后可以使用的**AcceptChanges**或**RejectChanges**方法来提交或拒绝这些**更改。DataTable**、 **DataSet**或**DataRow**对象。</span><span class="sxs-lookup"><span data-stu-id="aa25a-118">When **EndEdit** is called, proposed changes are placed in the **Current** row version of the underlying **DataRow** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="aa25a-119">如果**AllowEdit**为**false**，则当你尝试修改**DataView**中的值时，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="aa25a-119">If **AllowEdit** is **false**, an exception is thrown if you attempt to modify a value in the **DataView**.</span></span>  
  
 <span data-ttu-id="aa25a-120">正在编辑现有的**DataRowView**时，仍将使用建议的更改引发基础**DataTable**的事件。</span><span class="sxs-lookup"><span data-stu-id="aa25a-120">When an existing **DataRowView** is being edited, events of the underlying **DataTable** will still be raised with the proposed changes.</span></span> <span data-ttu-id="aa25a-121">请注意，如果对基础**DataRow**调用**EndEdit**或**CancelEdit** ，则将应用或取消挂起的更改，而不考虑是否在**DataRowView**上调用**EndEdit**或**CancelEdit** 。</span><span class="sxs-lookup"><span data-stu-id="aa25a-121">Note that if you call **EndEdit** or **CancelEdit** on the underlying **DataRow**, pending changes will be applied or canceled regardless of whether **EndEdit** or **CancelEdit** is called on the **DataRowView**.</span></span>  
  
 <span data-ttu-id="aa25a-122">如果**AllowDelete**为**true**，则可以使用**Dataview**或**DataRowView**对象的**delete**方法从**dataview**删除行，并从基础**DataTable**中删除这些行。</span><span class="sxs-lookup"><span data-stu-id="aa25a-122">If **AllowDelete** is **true**, you can delete rows from the **DataView** by using the **Delete** method of the **DataView** or **DataRowView** object, and the rows are deleted from the underlying **DataTable**.</span></span> <span data-ttu-id="aa25a-123">稍后可以分别使用**AcceptChanges**或**RejectChanges**提交或拒绝删除。</span><span class="sxs-lookup"><span data-stu-id="aa25a-123">You can later commit or reject the deletes using **AcceptChanges** or **RejectChanges** respectively.</span></span> <span data-ttu-id="aa25a-124">如果**AllowDelete**为**false**，则在调用**DataView**或**DataRowView**的**Delete**方法时，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="aa25a-124">If **AllowDelete** is **false**, an exception is thrown if you call the **Delete** method of the **DataView** or **DataRowView**.</span></span>  
  
 <span data-ttu-id="aa25a-125">下面的代码示例禁止使用**dataview**删除行并使用**dataview**向基础表中添加新行。</span><span class="sxs-lookup"><span data-stu-id="aa25a-125">The following code example disables using the **DataView** to delete rows  and adds a new row to the underlying table using the **DataView**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="aa25a-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="aa25a-126">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [<span data-ttu-id="aa25a-127">数据视图</span><span class="sxs-lookup"><span data-stu-id="aa25a-127">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="aa25a-128">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="aa25a-128">ADO.NET Overview</span></span>](../ado-net-overview.md)
