---
title: 查找行
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
ms.openlocfilehash: cfd4587f0dde7687ecf88bf6b31c44b90a2287ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151138"
---
# <a name="finding-rows"></a>查找行
可以使用 <xref:System.Data.DataView.Find%2A> 的 <xref:System.Data.DataView.FindRows%2A> 和 <xref:System.Data.DataView> 方法，根据排序关键字值搜索行。 **Find**和**FindRows**方法中搜索值的区分度由基础<xref:System.Data.DataTable>的**Case敏感**属性确定。 搜索值必须完全匹配现有排序关键字值才能返回结果。  
  
 **Find**方法返回一个整数，该整数与<xref:System.Data.DataRowView>搜索条件匹配的索引。 如果多行与搜索条件匹配，则仅返回第一个匹配**DataRowView**的索引。 如果未找到匹配项，**则查找**返回 -1。  
  
 要返回与多行匹配的搜索结果，请使用**FindRows**方法。 **FindRows**的工作方式与**Find**方法类似，只不过它返回一个**数据罗视图**数组，该数组引用**DataView**中的所有匹配行。 如果未找到匹配项 **，DataRowView**阵列将为空。  
  
 要使用 **"查找**"**或"查找行"** 方法，必须通过将 **"应用默认排序"** 设置为**true**或使用**排序**属性来指定排序顺序。 如果未指定排序顺序，则将引发异常。  
  
 **Find**和**FindRows**方法采用一个值数组作为输入，其长度与排序顺序中的列数匹配。 在对单个列进行排序的情况下，可以传递单个值。 对于包含多个列的排序顺序，可传递一个对象数组。 请注意，对于对多个列的排序，对象数组中的值必须与**DataView**的**Sort**属性中指定的列的顺序匹配。  
  
 以下代码示例显示针对具有单个列排序顺序的**DataView**调用**的 Find**方法。  
  
```vb  
Dim custView As DataView = _  
  New DataView(custDS.Tables("Customers"), "", _  
  "CompanyName", DataViewRowState.CurrentRows)  
  
Dim rowIndex As Integer = custView.Find("The Cracker Box")  
  
If rowIndex = -1 Then  
  Console.WriteLine("No match found.")  
Else  
  Console.WriteLine("{0}, {1}", _  
    custView(rowIndex)("CustomerID").ToString(), _  
    custView(rowIndex)("CompanyName").ToString())  
End If  
```  
  
```csharp  
DataView custView = new DataView(custDS.Tables["Customers"], "",
  "CompanyName", DataViewRowState.CurrentRows);  
  
int rowIndex = custView.Find("The Cracker Box");  
  
if (rowIndex == -1)  
  Console.WriteLine("No match found.");  
else  
  Console.WriteLine("{0}, {1}",  
    custView[rowIndex]["CustomerID"].ToString(),  
    custView[rowIndex]["CompanyName"].ToString());  
```  
  
 如果**Sort**属性指定了多个列，则必须按照**Sort**属性指定的顺序传递具有每列搜索值的对象数组，如以下代码示例所示。  
  
```vb  
Dim custView As DataView = _  
  New DataView(custDS.Tables("Customers"), "", _  
  "CompanyName, ContactName", _  
  DataViewRowState.CurrentRows)  
  
Dim foundRows() As DataRowView = _  
  custView.FindRows(New object() {"The Cracker Box", "Liu Wong"})  
  
If foundRows.Length = 0 Then  
  Console.WriteLine("No match found.")  
Else  
  Dim myDRV As DataRowView  
  For Each myDRV In foundRows  
    Console.WriteLine("{0}, {1}", _  
      myDRV("CompanyName").ToString(), myDRV("ContactName").ToString())  
  Next  
End If  
```  
  
```csharp  
DataView custView = new DataView(custDS.Tables["Customers"], "",  
  "CompanyName, ContactName",  
  DataViewRowState.CurrentRows);  
  
DataRowView[] foundRows =
  custView.FindRows(new object[] {"The Cracker Box", "Liu Wong"});  
  
if (foundRows.Length == 0)  
  Console.WriteLine("No match found.");  
else  
  foreach (DataRowView myDRV in foundRows)  
    Console.WriteLine("{0}, {1}", myDRV["CompanyName"].ToString(),
      myDRV["ContactName"].ToString());  
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [DataView](dataviews.md)
- [ADO.NET 概述](../ado-net-overview.md)
