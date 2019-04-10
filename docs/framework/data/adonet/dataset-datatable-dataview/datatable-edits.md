---
title: 数据表编辑
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
ms.openlocfilehash: 0300ceab16d9a94bd04468f7acd105e69d13e643
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150938"
---
# <a name="datatable-edits"></a><span data-ttu-id="0fed1-102">数据表编辑</span><span class="sxs-lookup"><span data-stu-id="0fed1-102">DataTable Edits</span></span>
<span data-ttu-id="0fed1-103">当您在 <xref:System.Data.DataRow> 中更改列值时，所做更改会立即置于行的当前状态中。</span><span class="sxs-lookup"><span data-stu-id="0fed1-103">When you make changes to column values in a <xref:System.Data.DataRow>, the changes are immediately placed in the current state of the row.</span></span> <span data-ttu-id="0fed1-104"><xref:System.Data.DataRowState>然后将设置为**Modified**，和所做的更改来接受或拒绝使用<xref:System.Data.DataRow.AcceptChanges%2A>或<xref:System.Data.DataRow.RejectChanges%2A>方法**DataRow**。</span><span class="sxs-lookup"><span data-stu-id="0fed1-104">The <xref:System.Data.DataRowState> is then set to **Modified**, and the changes are accepted or rejected using the <xref:System.Data.DataRow.AcceptChanges%2A> or <xref:System.Data.DataRow.RejectChanges%2A> methods of the **DataRow**.</span></span> <span data-ttu-id="0fed1-105">**DataRow**还提供了可用于在编辑时挂起行状态的三种方法。</span><span class="sxs-lookup"><span data-stu-id="0fed1-105">The **DataRow** also provides three methods that you can use to suspend the state of the row while you are editing it.</span></span> <span data-ttu-id="0fed1-106">这三个方法是 <xref:System.Data.DataRow.BeginEdit%2A>、<xref:System.Data.DataRow.EndEdit%2A> 和 <xref:System.Data.DataRow.CancelEdit%2A>。</span><span class="sxs-lookup"><span data-stu-id="0fed1-106">These methods are <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A>, and <xref:System.Data.DataRow.CancelEdit%2A>.</span></span>  
  
 <span data-ttu-id="0fed1-107">当修改列中的值**DataRow**直接**DataRow**管理使用的列的值**当前**，**默认**，和**原始**行版本。</span><span class="sxs-lookup"><span data-stu-id="0fed1-107">When you modify column values in a **DataRow** directly, the **DataRow** manages the column values using the **Current**, **Default**, and **Original** row versions.</span></span> <span data-ttu-id="0fed1-108">除了这些行版本，之外**BeginEdit**， **EndEdit**，并**CancelEdit**方法使用第四个行版本：**建议**。</span><span class="sxs-lookup"><span data-stu-id="0fed1-108">In addition to these row versions, the **BeginEdit**, **EndEdit**, and **CancelEdit** methods use a fourth row version: **Proposed**.</span></span> <span data-ttu-id="0fed1-109">有关行版本的详细信息，请参阅[行状态和行版本](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)。</span><span class="sxs-lookup"><span data-stu-id="0fed1-109">For more information about row versions, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="0fed1-110">**Proposed**编辑操作，首先会调用的过程中存在行版本**BeginEdit**结束通过使用**EndEdit**或**CancelEdit，** 或通过调用**AcceptChanges**或**RejectChanges**。</span><span class="sxs-lookup"><span data-stu-id="0fed1-110">The **Proposed** row version exists during an edit operation that begins by calling **BeginEdit** and that ends either by using **EndEdit** or **CancelEdit,** or by calling **AcceptChanges** or **RejectChanges**.</span></span>  
  
 <span data-ttu-id="0fed1-111">在编辑操作时，您可以将验证逻辑应用于单独的列通过评估**ProposedValue**中**ColumnChanged**的事件**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="0fed1-111">During the edit operation, you can apply validation logic to individual columns by evaluating the **ProposedValue** in the **ColumnChanged** event of the **DataTable**.</span></span> <span data-ttu-id="0fed1-112">**ColumnChanged**事件保存**DataColumnChangeEventArgs**的保留的引用，到正在更改的列和**ProposedValue**。</span><span class="sxs-lookup"><span data-stu-id="0fed1-112">The **ColumnChanged** event holds **DataColumnChangeEventArgs** that keep a reference to the column that is changing and to the **ProposedValue**.</span></span> <span data-ttu-id="0fed1-113">计算了建议值后，可以对其进行修改或取消编辑。</span><span class="sxs-lookup"><span data-stu-id="0fed1-113">After you evaluate the proposed value, you can either modify it or cancel the edit.</span></span> <span data-ttu-id="0fed1-114">在结束编辑后，将行移出**建议**状态。</span><span class="sxs-lookup"><span data-stu-id="0fed1-114">When the edit is ended, the row moves out of the **Proposed** state.</span></span>  
  
 <span data-ttu-id="0fed1-115">可以通过调用来确认编辑**EndEdit**，或通过调用取消**CancelEdit**。</span><span class="sxs-lookup"><span data-stu-id="0fed1-115">You can confirm edits by calling **EndEdit**, or you can cancel them by calling **CancelEdit**.</span></span> <span data-ttu-id="0fed1-116">请注意，当**EndEdit**确实已确认编辑，**数据集**没有实际接受更改直至**AcceptChanges**调用。</span><span class="sxs-lookup"><span data-stu-id="0fed1-116">Note that while **EndEdit** does confirm your edits, the **DataSet** does not actually accept the changes until **AcceptChanges** is called.</span></span> <span data-ttu-id="0fed1-117">另请注意，如果您调用**AcceptChanges**已结束编辑之前**EndEdit**或**CancelEdit**，编辑将会结束和**建议**行值接受两个**当前**并**原始**行版本。</span><span class="sxs-lookup"><span data-stu-id="0fed1-117">Note also that if you call **AcceptChanges** before you have ended the edit with **EndEdit** or **CancelEdit**, the edit is ended and the **Proposed** row values are accepted for both the **Current** and **Original** row versions.</span></span> <span data-ttu-id="0fed1-118">以相同的方式调用**RejectChanges**结束编辑，并放弃**当前**并**建议**行版本。</span><span class="sxs-lookup"><span data-stu-id="0fed1-118">In the same manner, calling **RejectChanges** ends the edit and discards the **Current** and **Proposed** row versions.</span></span> <span data-ttu-id="0fed1-119">调用**EndEdit**或**CancelEdit**后调用**AcceptChanges**或者**RejectChanges**不起任何作用，因为已经完成编辑已结束。</span><span class="sxs-lookup"><span data-stu-id="0fed1-119">Calling **EndEdit** or **CancelEdit** after calling **AcceptChanges** or **RejectChanges** has no effect because the edit has already ended.</span></span>  
  
 <span data-ttu-id="0fed1-120">下面的示例演示如何使用**BeginEdit**与**EndEdit**并**CancelEdit**。</span><span class="sxs-lookup"><span data-stu-id="0fed1-120">The following example demonstrates how to use **BeginEdit** with **EndEdit** and **CancelEdit**.</span></span> <span data-ttu-id="0fed1-121">该示例还会检查**ProposedValue**中**ColumnChanged**事件并决定是否要取消编辑。</span><span class="sxs-lookup"><span data-stu-id="0fed1-121">The example also checks the **ProposedValue** in the **ColumnChanged** event and decides whether to cancel the edit.</span></span>  
  
```vb  
Dim workTable As DataTable = New DataTable  
workTable.Columns.Add("LastName", Type.GetType("System.String"))  
  
AddHandler workTable.ColumnChanged, _  
  New DataColumnChangeEventHandler(AddressOf OnColumnChanged)  
  
Dim workRow As DataRow = workTable.NewRow()  
workRow(0) = "Smith"  
workTable.Rows.Add(workRow)  
  
workRow.BeginEdit()  
' Causes the ColumnChanged event to write a message and cancel the edit.  
workRow(0) = ""       
workRow.EndEdit()  
  
' Displays "Smith, New".  
Console.WriteLine("{0}, {1}", workRow(0), workRow.RowState)  
  
Private Shared Sub OnColumnChanged( _  
  sender As Object, args As DataColumnChangeEventArgs)  
  If args.Column.ColumnName = "LastName" Then  
    If args.ProposedValue.ToString() = "" Then  
      Console.WriteLine("Last Name cannot be blank.  Edit canceled.")  
      args.Row.CancelEdit()  
    End If  
  End If  
End Sub  
```  
  
```csharp  
DataTable workTable  = new DataTable();  
workTable.Columns.Add("LastName", typeof(String));  
  
workTable.ColumnChanged +=   
  new DataColumnChangeEventHandler(OnColumnChanged);  
  
DataRow workRow = workTable.NewRow();  
workRow[0] = "Smith";  
workTable.Rows.Add(workRow);  
  
workRow.BeginEdit();  
// Causes the ColumnChanged event to write a message and cancel the edit.  
workRow[0] = "";       
workRow.EndEdit();  
  
// Displays "Smith, New".  
Console.WriteLine("{0}, {1}", workRow[0], workRow.RowState);    
  
protected static void OnColumnChanged(  
  Object sender, DataColumnChangeEventArgs args)  
{  
  if (args.Column.ColumnName == "LastName")  
    if (args.ProposedValue.ToString() == "")  
    {  
      Console.WriteLine("Last Name cannot be blank. Edit canceled.");  
      args.Row.CancelEdit();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="0fed1-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="0fed1-122">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataRowVersion>
- [<span data-ttu-id="0fed1-123">操作数据表中的数据</span><span class="sxs-lookup"><span data-stu-id="0fed1-123">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="0fed1-124">处理数据表事件</span><span class="sxs-lookup"><span data-stu-id="0fed1-124">Handling DataTable Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)
- [<span data-ttu-id="0fed1-125">ADO.NET 托管提供程序和 DataSet 开发人员中心</span><span class="sxs-lookup"><span data-stu-id="0fed1-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
