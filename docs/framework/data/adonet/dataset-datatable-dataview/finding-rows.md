---
title: "查找行"
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
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 43703ead9d38ea1cf02539f12479e9228d7eacd4
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="finding-rows"></a>查找行
可以使用 <xref:System.Data.DataView.Find%2A> 的 <xref:System.Data.DataView.FindRows%2A> 和 <xref:System.Data.DataView> 方法，根据排序关键字值搜索行。 中值的区分大小写的搜索**查找**和**FindRows**方法由**CaseSensitive**基础属性<xref:System.Data.DataTable>。 搜索值必须完全匹配现有排序关键字值才能返回结果。  
  
 **查找**方法返回一个整数，它的索引<xref:System.Data.DataRowView>匹配搜索条件。 如果多个行匹配搜索条件，仅第一个匹配的索引**DataRowView**返回。 如果不找到任何匹配项，**查找**返回-1。  
  
 若要返回匹配多个行的搜索结果，请使用**FindRows**方法。 **FindRows**工作方式就像**查找**方法，它返回不同**DataRowView**引用中的所有匹配行的数组**DataView**。 如果不找到任何匹配项， **DataRowView**数组将为空。  
  
 若要使用**查找**或**FindRows**方法必须指定排序顺序通过设置**ApplyDefaultSort**到**true**或通过使用**排序**属性。 如果未指定排序顺序，则将引发异常。  
  
 **查找**和**FindRows**方法将一个值数组作为输入长度与匹配的排序顺序中的列数。 在对单个列进行排序的情况下，可以传递单个值。 对于包含多个列的排序顺序，可传递一个对象数组。 请注意，对多个列进行排序，对象数组中的值必须匹配中指定的列的顺序**排序**属性**DataView**。  
  
 下面的代码示例演示**查找**针对正在调用的方法**DataView**具有单个列排序顺序。  
  
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
  
 如果你**排序**属性指定多个列，必须传递包含每个列的搜索值的对象数组中指定的顺序**排序**属性，如下面的代码示例所示。  
  
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
  
## <a name="see-also"></a>请参阅  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [数据视图](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
