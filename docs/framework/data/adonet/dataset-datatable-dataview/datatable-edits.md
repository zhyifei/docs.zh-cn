---
title: 数据表编辑
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
ms.openlocfilehash: 9e8c4204b51121b147fc7614066d9b849a687574
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151255"
---
# <a name="datatable-edits"></a><span data-ttu-id="17406-102">数据表编辑</span><span class="sxs-lookup"><span data-stu-id="17406-102">DataTable Edits</span></span>
<span data-ttu-id="17406-103">当您在 <xref:System.Data.DataRow> 中更改列值时，所做更改会立即置于行的当前状态中。</span><span class="sxs-lookup"><span data-stu-id="17406-103">When you make changes to column values in a <xref:System.Data.DataRow>, the changes are immediately placed in the current state of the row.</span></span> <span data-ttu-id="17406-104">然后<xref:System.Data.DataRowState>设置为 **"已修改 "，** 并使用<xref:System.Data.DataRow.AcceptChanges%2A>**DataRow**的 或<xref:System.Data.DataRow.RejectChanges%2A>方法接受或拒绝更改。</span><span class="sxs-lookup"><span data-stu-id="17406-104">The <xref:System.Data.DataRowState> is then set to **Modified**, and the changes are accepted or rejected using the <xref:System.Data.DataRow.AcceptChanges%2A> or <xref:System.Data.DataRow.RejectChanges%2A> methods of the **DataRow**.</span></span> <span data-ttu-id="17406-105">**DataRow**还提供三种方法，可用于在编辑行时挂起行的状态。</span><span class="sxs-lookup"><span data-stu-id="17406-105">The **DataRow** also provides three methods that you can use to suspend the state of the row while you are editing it.</span></span> <span data-ttu-id="17406-106">这三个方法是 <xref:System.Data.DataRow.BeginEdit%2A>、<xref:System.Data.DataRow.EndEdit%2A> 和 <xref:System.Data.DataRow.CancelEdit%2A>。</span><span class="sxs-lookup"><span data-stu-id="17406-106">These methods are <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A>, and <xref:System.Data.DataRow.CancelEdit%2A>.</span></span>  
  
 <span data-ttu-id="17406-107">直接修改**DataRow**中的列值时 **，DataRow**将使用 **"当前**"、"**默认**"和 **"原始**行"版本管理列值。</span><span class="sxs-lookup"><span data-stu-id="17406-107">When you modify column values in a **DataRow** directly, the **DataRow** manages the column values using the **Current**, **Default**, and **Original** row versions.</span></span> <span data-ttu-id="17406-108">除了这些行版本外，"**开始编辑**"、"**结束编辑\*\*\*\*"和"取消编辑"** 方法使用第四行版本：**建议**。</span><span class="sxs-lookup"><span data-stu-id="17406-108">In addition to these row versions, the **BeginEdit**, **EndEdit**, and **CancelEdit** methods use a fourth row version: **Proposed**.</span></span> <span data-ttu-id="17406-109">有关行版本的详细信息，请参阅[行状态和行版本](row-states-and-row-versions.md)。</span><span class="sxs-lookup"><span data-stu-id="17406-109">For more information about row versions, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="17406-110">**建议的**行版本存在于编辑操作中，该操作以调用**BeginEdit**开始，最后使用 **"结束编辑"** 或 **"取消编辑"，** 或调用 **"接受更改**"或 **"拒绝更改**"。</span><span class="sxs-lookup"><span data-stu-id="17406-110">The **Proposed** row version exists during an edit operation that begins by calling **BeginEdit** and that ends either by using **EndEdit** or **CancelEdit,** or by calling **AcceptChanges** or **RejectChanges**.</span></span>  
  
 <span data-ttu-id="17406-111">在编辑操作期间，您可以通过在**DataTable**的**列更改**事件中评估 **"建议值**"来将验证逻辑应用于各个列。</span><span class="sxs-lookup"><span data-stu-id="17406-111">During the edit operation, you can apply validation logic to individual columns by evaluating the **ProposedValue** in the **ColumnChanged** event of the **DataTable**.</span></span> <span data-ttu-id="17406-112">**"列更改"** 事件保存**DataColumnChangeEventArgs，该事件**保留对正在更改的列和**建议值**的引用。</span><span class="sxs-lookup"><span data-stu-id="17406-112">The **ColumnChanged** event holds **DataColumnChangeEventArgs** that keep a reference to the column that is changing and to the **ProposedValue**.</span></span> <span data-ttu-id="17406-113">计算了建议值后，可以对其进行修改或取消编辑。</span><span class="sxs-lookup"><span data-stu-id="17406-113">After you evaluate the proposed value, you can either modify it or cancel the edit.</span></span> <span data-ttu-id="17406-114">编辑结束时，行将移出 **"建议"** 状态。</span><span class="sxs-lookup"><span data-stu-id="17406-114">When the edit is ended, the row moves out of the **Proposed** state.</span></span>  
  
 <span data-ttu-id="17406-115">您可以通过调用**EndEdit**来确认编辑，也可以通过调用**CancelEdit**来取消编辑。</span><span class="sxs-lookup"><span data-stu-id="17406-115">You can confirm edits by calling **EndEdit**, or you can cancel them by calling **CancelEdit**.</span></span> <span data-ttu-id="17406-116">请注意，虽然**EndEdit**确实确认您的编辑，但**DataSet**在调用 **"接受更改**"之前实际上不会接受更改。</span><span class="sxs-lookup"><span data-stu-id="17406-116">Note that while **EndEdit** does confirm your edits, the **DataSet** does not actually accept the changes until **AcceptChanges** is called.</span></span> <span data-ttu-id="17406-117">另请注意，如果在结束编辑或**取消编辑**之前调用 **"接受更改**"，则编辑将结束，**并且"当前**"行版本和**原始**行版本均接受 **"建议**行"值。 **EndEdit**</span><span class="sxs-lookup"><span data-stu-id="17406-117">Note also that if you call **AcceptChanges** before you have ended the edit with **EndEdit** or **CancelEdit**, the edit is ended and the **Proposed** row values are accepted for both the **Current** and **Original** row versions.</span></span> <span data-ttu-id="17406-118">以同样的方式，调用**拒绝更改**结束编辑并丢弃**当前**和**建议的**行版本。</span><span class="sxs-lookup"><span data-stu-id="17406-118">In the same manner, calling **RejectChanges** ends the edit and discards the **Current** and **Proposed** row versions.</span></span> <span data-ttu-id="17406-119">调用"**接受更改**"或 **"拒绝更改**"后调用 **"结束编辑**"或 **"取消编辑"** 不起作用，因为编辑已结束。</span><span class="sxs-lookup"><span data-stu-id="17406-119">Calling **EndEdit** or **CancelEdit** after calling **AcceptChanges** or **RejectChanges** has no effect because the edit has already ended.</span></span>  
  
 <span data-ttu-id="17406-120">下面的示例演示如何使用 **"开始编辑**"与**结束编辑**和**取消编辑**。</span><span class="sxs-lookup"><span data-stu-id="17406-120">The following example demonstrates how to use **BeginEdit** with **EndEdit** and **CancelEdit**.</span></span> <span data-ttu-id="17406-121">该示例还检查 **"列更改"** 事件中**的"建议值**"，并决定是否取消编辑。</span><span class="sxs-lookup"><span data-stu-id="17406-121">The example also checks the **ProposedValue** in the **ColumnChanged** event and decides whether to cancel the edit.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="17406-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17406-122">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataRowVersion>
- [<span data-ttu-id="17406-123">操作数据表中的数据</span><span class="sxs-lookup"><span data-stu-id="17406-123">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="17406-124">处理数据表事件</span><span class="sxs-lookup"><span data-stu-id="17406-124">Handling DataTable Events</span></span>](handling-datatable-events.md)
- [<span data-ttu-id="17406-125">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="17406-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
