---
title: 通过查询结果分页
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa360c46-e5f8-411e-a711-46997771133d
ms.openlocfilehash: 2e7fb97e5c0cb42deff43c411f47e8d30e2257ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149383"
---
# <a name="paging-through-a-query-result"></a>通过查询结果分页
查询结果分页是以较小数据子集（即页）的形式返回查询结果的过程。 它通常用于以易于管理的小块形式向用户显示结果。  
  
 **DataAdapter**提供了一个工具，用于通过**填充**方法的重载仅返回一页数据。 但是，这可能不是通过大型查询结果分页的最佳选择，因为尽管**DataAdapter**填充了目标<xref:System.Data.DataTable>或<xref:System.Data.DataSet>仅包含请求的记录，但仍使用返回整个查询的资源。 若要在从数据源中返回一页数据时不使用返回整个查询的资源，请为查询指定附加条件，使返回的行数减少到只返回所需的行。  
  
 要使用**Fill**方法返回数据页，请为数据页中的第一个记录指定**startRecord**参数，并为数据页中的记录数指定**maxRecord**参数。  
  
 以下代码示例演示如何使用**Fill**方法返回查询结果的第一页，其中页面大小为五条记录。  
  
```vb  
Dim currentIndex As Integer = 0  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT * FROM dbo.Orders ORDER BY OrderID"  
' Assumes that connection is a valid SqlConnection object.  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
int currentIndex = 0;  
int pageSize = 5;  
  
string orderSQL = "SELECT * FROM Orders ORDER BY OrderID";  
// Assumes that connection is a valid SqlConnection object.  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 在前面的示例中 **，DataSet**只填充五条记录，但返回整个**订单**表。 要用这五条记录填充**DataSet，** 但仅返回五条记录，请使用 SQL 语句中的 TOP 和 WHERE 子句，如以下代码示例所示。  
  
```vb  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT TOP " & pageSize & _  
  " * FROM Orders ORDER BY OrderID"  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, "Orders")
```  
  
```csharp  
int pageSize = 5;  
  
string orderSQL = "SELECT TOP " + pageSize +
  " * FROM Orders ORDER BY OrderID";  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "Orders");  
```  
  
 请注意，当以这种方式进行查询结果分页时，必须保留用于对行进行排序的唯一标识符，以便将唯一 ID 传递给用于返回下一页记录的命令，如以下代码示例所示。  
  
```vb  
Dim lastRecord As String = _  
  dataSet.Tables("Orders").Rows(pageSize - 1)("OrderID").ToString()  
```  
  
```csharp  
string lastRecord =
  dataSet.Tables["Orders"].Rows[pageSize - 1]["OrderID"].ToString();  
```  
  
 要使用取**startRecord**和**maxRecord**参数的**Fill**方法重载返回记录的下一页，请按页大小增加当前记录索引并填充表。 请记住，数据库服务器返回整个查询结果，即使只向**DataSet**添加了一页记录。 在以下代码示例中，先清除表行，然后再用下一页数据填充这些表行。 您可能需要在本地缓存中保留一定数量的返回行，以减少与数据库服务器的往返次数。  
  
```vb  
currentIndex = currentIndex + pageSize  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
currentIndex += pageSize;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 若要返回下一页记录而不让数据库服务器返回整个查询，请指定对 SQL SELECT 语句的限制条件。 由于上例保留了返回的最后一个记录，因此可以在 WHERE 子句中使用它来指定查询的起点，如以下代码示例所示。  
  
```vb  
orderSQL = "SELECT TOP " & pageSize & _  
  " * FROM Orders WHERE OrderID > " & lastRecord & " ORDER BY OrderID"  
adapter.SelectCommand.CommandText = orderSQL  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, "Orders")  
```  
  
```csharp  
orderSQL = "SELECT TOP " + pageSize +
  " * FROM Orders WHERE OrderID > " + lastRecord + " ORDER BY OrderID";  
adapter.SelectCommand.CommandText = orderSQL;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, "Orders");  
```  
  
## <a name="see-also"></a>另请参阅

- [DataAdapters 和 DataReaders](dataadapters-and-datareaders.md)
- [ADO.NET 概述](ado-net-overview.md)
