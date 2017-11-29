---
title: "将数据添加到数据表中"
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
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6e05e8cb0c7de638e0c4efe74ffd27ab0dc45508
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="adding-data-to-a-datatable"></a>将数据添加到数据表中
在创建 <xref:System.Data.DataTable> 并使用列和约束定义其结构之后，您可以将新的数据行添加到表中。 要添加新行，可将一个新变量声明为 <xref:System.Data.DataRow> 类型。 一个新**DataRow**在调用时返回对象<xref:System.Data.DataTable.NewRow%2A>方法。 **DataTable**然后创建**DataRow**对象基于在表中，该结构，由定义<xref:System.Data.DataColumnCollection>。  
  
 下面的示例演示如何通过调用创建一个新行**NewRow**方法。  
  
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
  
 数据插入新行中后,**添加**方法用于向其中添加行<xref:System.Data.DataRowCollection>，下面的代码所示。  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 你还可以调用**添加**方法来添加新行，通过传入的值，数组类型化为<xref:System.Object>，下面的示例中所示。  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 传递的值，类型化为数组**对象**到**添加**方法创建一个新表内部行，并将其列的值设置为对象数组中的值。 请注意，数组中的值会根据它们在表中出现的顺序相继与各列匹配。  
  
 下面的示例将添加到新创建的 10 行**客户**表。  
  
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
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataRowCollection>  
 <xref:System.Data.DataTable>  
 [操作数据表中的数据](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
