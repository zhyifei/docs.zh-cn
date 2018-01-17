---
title: "数据表编辑"
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
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 3d06fc3a82457972db94f82964942f446bb761be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="datatable-edits"></a>数据表编辑
当您在 <xref:System.Data.DataRow> 中更改列值时，所做更改会立即置于行的当前状态中。 <xref:System.Data.DataRowState>然后将设置为**已修改**，并接受或拒绝使用更改<xref:System.Data.DataRow.AcceptChanges%2A>或<xref:System.Data.DataRow.RejectChanges%2A>方法**DataRow**。 **DataRow**还提供了可用于进行编辑时挂起的行状态的三种方法。 这三个方法是 <xref:System.Data.DataRow.BeginEdit%2A>、<xref:System.Data.DataRow.EndEdit%2A> 和 <xref:System.Data.DataRow.CancelEdit%2A>。  
  
 当您修改列中的值**DataRow**直接， **DataRow**管理使用的列的值**当前**，**默认**，和**原始**行版本。 除了这些行版本中， **BeginEdit**， **EndEdit**，和**CancelEdit**方法使用第四个行版本：**建议**。 有关行版本的详细信息，请参阅[行状态和行版本](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)。  
  
 **建议**行版本在通过调用开始编辑操作过程中存在**BeginEdit**和用于结束通过使用**EndEdit**或**CancelEdit，**或通过调用**AcceptChanges**或**RejectChanges**。  
  
 在编辑操作时，你可以将验证逻辑应用于各列通过评估来评估**ProposedValue**中**ColumnChanged**事件**DataTable**。 **ColumnChanged**事件保存**DataColumnChangeEventArgs** ，保留的引用，到正在更改的列和**ProposedValue**。 计算了建议值后，可以对其进行修改或取消编辑。 当编辑结束时，行移出**建议**状态。  
  
 可以通过调用来确认编辑**EndEdit**，也可以通过调用取消它们**CancelEdit**。 请注意，当**EndEdit**确实已确认所做的编辑，**数据集**没有实际接受更改直至**AcceptChanges**调用。 另请注意，如果调用**AcceptChanges**已结束编辑之前**EndEdit**或**CancelEdit**，编辑将会结束和**建议**行值接受**当前**和**原始**行版本。 在同样的方式调用**RejectChanges**结束编辑并放弃**当前**和**建议**行版本。 调用**EndEdit**或**CancelEdit**之后调用**AcceptChanges**或**RejectChanges**不起任何作用，因为编辑已经结束。  
  
 下面的示例演示如何使用**BeginEdit**与**EndEdit**和**CancelEdit**。 该示例还将检查**ProposedValue**中**ColumnChanged**事件并决定是否取消编辑。  
  
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
  
## <a name="see-also"></a>请参阅  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataRowVersion>  
 [操作数据表中的数据](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [处理数据表事件](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
