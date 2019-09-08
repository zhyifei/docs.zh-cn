---
title: 将数据添加到数据表中
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
ms.openlocfilehash: 2a001ac8b3d4b8cd9618b3ced7bdf578ebae2e22
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786591"
---
# <a name="adding-data-to-a-datatable"></a>将数据添加到数据表中
在创建 <xref:System.Data.DataTable> 并使用列和约束定义其结构之后，您可以将新的数据行添加到表中。 要添加新行，可将一个新变量声明为 <xref:System.Data.DataRow> 类型。 当调用 <xref:System.Data.DataTable.NewRow%2A>方法时，将返回新的 DataRow 对象。 然后， **DataTable**根据所 <xref:System.Data.DataColumnCollection>定义的表的结构创建 DataRow 对象。  
  
 下面的示例演示如何通过调用**NewRow**方法来创建新行。  
  
```vb  
Dim workRow As DataRow = workTable.NewRow()  
```  
  
```csharp  
DataRow workRow = workTable.NewRow();  
```  
  
 然后您可以使用索引或列名来处理新添加的行，如下例所示。  
  
```vb  
workRow("CustLName") = "Smith"  
workRow(1) = "Smith"  
```  
  
```csharp  
workRow["CustLName"] = "Smith";  
workRow[1] = "Smith";  
```  
  
 将数据插入新行后，**将使用 add**方法将行添加到<xref:System.Data.DataRowCollection>中，如下面的代码所示。  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 你还可以调用**add**方法来添加新行，方法是传入类型为<xref:System.Object>的值数组，如下面的示例中所示。  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 将类型化为**object**的值的数组传递到**Add**方法会在表中创建一个新行，并将其列值设置为对象数组中的值。 请注意，数组中的值会根据它们在表中出现的顺序相继与各列匹配。  
  
 下面的示例将10行添加到新创建的**Customers**表中。  
  
```vb  
Dim workRow As DataRow  
Dim i As Integer  
  
For i = 0 To 9  
  workRow = workTable.NewRow()  
  workRow(0) = i  
  workRow(1) = "CustName" & I.ToString()  
  workTable.Rows.Add(workRow)  
Next  
```  
  
```csharp  
DataRow workRow;  
  
for (int i = 0; i <= 9; i++)   
{  
  workRow = workTable.NewRow();  
  workRow[0] = i;  
  workRow[1] = "CustName" + i.ToString();  
  workTable.Rows.Add(workRow);  
}  
```  
  
## <a name="see-also"></a>请参阅

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [操作数据表中的数据](manipulating-data-in-a-datatable.md)
- [ADO.NET 概述](../ado-net-overview.md)
