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
# <a name="datatable-edits"></a>数据表编辑
当您在 <xref:System.Data.DataRow> 中更改列值时，所做更改会立即置于行的当前状态中。 然后<xref:System.Data.DataRowState>设置为 **"已修改 "，** 并使用<xref:System.Data.DataRow.AcceptChanges%2A>**DataRow**的 或<xref:System.Data.DataRow.RejectChanges%2A>方法接受或拒绝更改。 **DataRow**还提供三种方法，可用于在编辑行时挂起行的状态。 这三个方法是 <xref:System.Data.DataRow.BeginEdit%2A>、<xref:System.Data.DataRow.EndEdit%2A> 和 <xref:System.Data.DataRow.CancelEdit%2A>。  
  
 直接修改**DataRow**中的列值时 **，DataRow**将使用 **"当前**"、"**默认**"和 **"原始**行"版本管理列值。 除了这些行版本外，"**开始编辑**"、"**结束编辑****"和"取消编辑"** 方法使用第四行版本：**建议**。 有关行版本的详细信息，请参阅[行状态和行版本](row-states-and-row-versions.md)。  
  
 **建议的**行版本存在于编辑操作中，该操作以调用**BeginEdit**开始，最后使用 **"结束编辑"** 或 **"取消编辑"，** 或调用 **"接受更改**"或 **"拒绝更改**"。  
  
 在编辑操作期间，您可以通过在**DataTable**的**列更改**事件中评估 **"建议值**"来将验证逻辑应用于各个列。 **"列更改"** 事件保存**DataColumnChangeEventArgs，该事件**保留对正在更改的列和**建议值**的引用。 计算了建议值后，可以对其进行修改或取消编辑。 编辑结束时，行将移出 **"建议"** 状态。  
  
 您可以通过调用**EndEdit**来确认编辑，也可以通过调用**CancelEdit**来取消编辑。 请注意，虽然**EndEdit**确实确认您的编辑，但**DataSet**在调用 **"接受更改**"之前实际上不会接受更改。 另请注意，如果在结束编辑或**取消编辑**之前调用 **"接受更改**"，则编辑将结束，**并且"当前**"行版本和**原始**行版本均接受 **"建议**行"值。 **EndEdit** 以同样的方式，调用**拒绝更改**结束编辑并丢弃**当前**和**建议的**行版本。 调用"**接受更改**"或 **"拒绝更改**"后调用 **"结束编辑**"或 **"取消编辑"** 不起作用，因为编辑已结束。  
  
 下面的示例演示如何使用 **"开始编辑**"与**结束编辑**和**取消编辑**。 该示例还检查 **"列更改"** 事件中**的"建议值**"，并决定是否取消编辑。  
  
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
  
## <a name="see-also"></a>另请参阅

- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataRowVersion>
- [操作数据表中的数据](manipulating-data-in-a-datatable.md)
- [处理数据表事件](handling-datatable-events.md)
- [ADO.NET 概述](../ado-net-overview.md)
