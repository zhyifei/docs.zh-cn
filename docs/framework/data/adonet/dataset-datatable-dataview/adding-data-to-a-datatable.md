---
title: 将数据添加到数据表中
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
ms.openlocfilehash: 02d7f94259cc56513be404c5539ca7015d5f3533
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151528"
---
# <a name="adding-data-to-a-datatable"></a>将数据添加到数据表中
在创建 <xref:System.Data.DataTable> 并使用列和约束定义其结构之后，您可以将新的数据行添加到表中。 要添加新行，可将一个新变量声明为 <xref:System.Data.DataRow> 类型。 调用<xref:System.Data.DataTable.NewRow%2A>方法时将返回新的**DataRow**对象。 然后 **，DataTable**基于表的结构（由 定义）创建**DataRow**对象<xref:System.Data.DataColumnCollection>。  
  
 下面的示例演示如何通过调用**NewRow**方法创建新行。  
  
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
  
 将数据插入到新行后 **，Add**方法用于将行添加到 ，<xref:System.Data.DataRowCollection>如下所示。  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 还可以调用**Add**方法，通过传入值数组来添加新行，这些值键入为<xref:System.Object>，如以下示例所示。  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 将值数组（键入为**Object**）传递给**Add**方法会在表中创建一个新行，并将其列值设置到对象数组中的值。 请注意，数组中的值会根据它们在表中出现的顺序相继与各列匹配。  
  
 下面的示例将 10 行添加到新创建**的客户**表。  
  
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
  
## <a name="see-also"></a>另请参阅

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [操作数据表中的数据](manipulating-data-in-a-datatable.md)
- [ADO.NET 概述](../ado-net-overview.md)
