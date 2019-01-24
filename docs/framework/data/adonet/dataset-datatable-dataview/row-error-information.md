---
title: 行错误信息
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b1f9070-d032-48c7-b030-bd8fbb2ca59a
ms.openlocfilehash: bc3e4517e0bb194508ccb0598920a3bdd1299e5c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573278"
---
# <a name="row-error-information"></a><span data-ttu-id="0fc5e-102">行错误信息</span><span class="sxs-lookup"><span data-stu-id="0fc5e-102">Row Error Information</span></span>
<span data-ttu-id="0fc5e-103">为了避免在编辑 <xref:System.Data.DataTable> 中的值时对行错误做出响应，可以将错误信息添加到该行，供以后使用。</span><span class="sxs-lookup"><span data-stu-id="0fc5e-103">To avoid having to respond to row errors while editing values in a <xref:System.Data.DataTable>, you can add the error information to the row for later use.</span></span> <span data-ttu-id="0fc5e-104">因此，<xref:System.Data.DataRow> 对象在每行上提供 <xref:System.Data.DataRow.RowError%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="0fc5e-104">The <xref:System.Data.DataRow> object provides a <xref:System.Data.DataRow.RowError%2A> property on each row for this purpose.</span></span> <span data-ttu-id="0fc5e-105">将数据添加到**RowError**的属性**DataRow**设置<xref:System.Data.DataRow.HasErrors%2A>属性的**DataRow**到**true**。</span><span class="sxs-lookup"><span data-stu-id="0fc5e-105">Adding data to the **RowError** property of a **DataRow** sets the <xref:System.Data.DataRow.HasErrors%2A> property of the **DataRow** to **true**.</span></span> <span data-ttu-id="0fc5e-106">如果**DataRow**属于**DataTable**，并**DataRow.HasErrors**是**true**，则**DataTable.HasErrors**属性也是**true**。</span><span class="sxs-lookup"><span data-stu-id="0fc5e-106">If the **DataRow** is part of a **DataTable**, and **DataRow.HasErrors** is **true**, the **DataTable.HasErrors** property is also **true**.</span></span> <span data-ttu-id="0fc5e-107">这也适用于**数据集**所属**DataTable**所属。</span><span class="sxs-lookup"><span data-stu-id="0fc5e-107">This applies as well to the **DataSet** to which the **DataTable** belongs.</span></span> <span data-ttu-id="0fc5e-108">当测试是否有错误，您可以检查**HasErrors**属性来确定是否已添加任何行错误信息。</span><span class="sxs-lookup"><span data-stu-id="0fc5e-108">When testing for errors, you can check the **HasErrors** property to determine if error information has been added to any rows.</span></span> <span data-ttu-id="0fc5e-109">如果**HasErrors**是**true**，可以使用<xref:System.Data.DataTable.GetErrors%2A>方法**DataTable**返回和检查仅有错误的行，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="0fc5e-109">If **HasErrors** is **true**, you can use the <xref:System.Data.DataTable.GetErrors%2A> method of the **DataTable** to return and examine only the rows with errors, as shown in the following example.</span></span>  
  
```vb  
Dim workTable As DataTable = New DataTable("Customers")  
workTable.Columns.Add("CustID", Type.GetType("System.Int32"))  
workTable.Columns.Add("Total", Type.GetType("System.Double"))  
  
AddHandler workTable.RowChanged, New DataRowChangeEventHandler(AddressOf OnRowChanged)  
  
Dim i  As Int32  
  
For i  = 0 To 10  
  workTable.Rows.Add(New Object() {i , i *100})  
Next  
  
If workTable.HasErrors Then  
  Console.WriteLine("Errors in Table " & workTable.TableName)  
  
  Dim myRow As DataRow  
  
  For Each myRow In workTable.GetErrors()  
    Console.WriteLine("CustID = " & myRow("CustID").ToString())  
    Console.WriteLine(" Error = " & myRow.RowError & vbCrLf)  
  Next  
End If  
  
Private Shared Sub OnRowChanged( _  
    sender As Object, args As DataRowChangeEventArgs)  
  ' Check for zero values.  
  If CDbl(args.Row("Total")) = 0 Then args.Row.RowError = _  
      "Total cannot be 0."  
End Sub  
```  
  
```csharp  
DataTable  workTable = new DataTable("Customers");  
workTable.Columns.Add("CustID", typeof(Int32));  
workTable.Columns.Add("Total", typeof(Double));  
  
workTable.RowChanged += new DataRowChangeEventHandler(OnRowChanged);  
  
for (int i = 0; i < 10; i++)  
  workTable.Rows.Add(new Object[] {i, i*100});  
  
if (workTable.HasErrors)  
{  
  Console.WriteLine("Errors in Table " + workTable.TableName);  
  
  foreach (DataRow myRow in workTable.GetErrors())  
  {  
    Console.WriteLine("CustID = " + myRow["CustID"]);  
    Console.WriteLine(" Error = " + myRow.RowError + "\n");  
  }  
}  
  
protected static void OnRowChanged(  
    Object sender, DataRowChangeEventArgs args)  
{  
  // Check for zero values.  
  if (args.Row["Total"].Equals(0D))  
    args.Row.RowError = "Total cannot be 0.";  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="0fc5e-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="0fc5e-110">See also</span></span>
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="0fc5e-111">操作数据表中的数据</span><span class="sxs-lookup"><span data-stu-id="0fc5e-111">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="0fc5e-112">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="0fc5e-112">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
