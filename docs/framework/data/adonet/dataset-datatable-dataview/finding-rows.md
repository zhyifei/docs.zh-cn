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
# <a name="finding-rows"></a><span data-ttu-id="c033d-102">查找行</span><span class="sxs-lookup"><span data-stu-id="c033d-102">Finding Rows</span></span>
<span data-ttu-id="c033d-103">可以使用 <xref:System.Data.DataView.Find%2A> 的 <xref:System.Data.DataView.FindRows%2A> 和 <xref:System.Data.DataView> 方法，根据排序关键字值搜索行。</span><span class="sxs-lookup"><span data-stu-id="c033d-103">You can search for rows according to their sort key values by using the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView>.</span></span> <span data-ttu-id="c033d-104">中值的区分大小写的搜索**查找**和**FindRows**方法由**CaseSensitive**基础属性<xref:System.Data.DataTable>。</span><span class="sxs-lookup"><span data-stu-id="c033d-104">The case sensitivity of search values in the **Find** and **FindRows** methods is determined by the **CaseSensitive** property of the underlying <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="c033d-105">搜索值必须完全匹配现有排序关键字值才能返回结果。</span><span class="sxs-lookup"><span data-stu-id="c033d-105">Search values must match existing sort key values in their entirety in order to return a result.</span></span>  
  
 <span data-ttu-id="c033d-106">**查找**方法返回一个整数，它的索引<xref:System.Data.DataRowView>匹配搜索条件。</span><span class="sxs-lookup"><span data-stu-id="c033d-106">The **Find** method returns an integer with the index of the <xref:System.Data.DataRowView> that matches the search criteria.</span></span> <span data-ttu-id="c033d-107">如果多个行匹配搜索条件，仅第一个匹配的索引**DataRowView**返回。</span><span class="sxs-lookup"><span data-stu-id="c033d-107">If more than one row matches the search criteria, only the index of the first matching **DataRowView** is returned.</span></span> <span data-ttu-id="c033d-108">如果不找到任何匹配项，**查找**返回-1。</span><span class="sxs-lookup"><span data-stu-id="c033d-108">If no matches are found, **Find** returns -1.</span></span>  
  
 <span data-ttu-id="c033d-109">若要返回匹配多个行的搜索结果，请使用**FindRows**方法。</span><span class="sxs-lookup"><span data-stu-id="c033d-109">To return search results that match multiple rows, use the **FindRows** method.</span></span> <span data-ttu-id="c033d-110">**FindRows**工作方式就像**查找**方法，它返回不同**DataRowView**引用中的所有匹配行的数组**DataView**。</span><span class="sxs-lookup"><span data-stu-id="c033d-110">**FindRows** works just like the **Find** method, except that it returns a **DataRowView** array that references all matching rows in the **DataView**.</span></span> <span data-ttu-id="c033d-111">如果不找到任何匹配项， **DataRowView**数组将为空。</span><span class="sxs-lookup"><span data-stu-id="c033d-111">If no matches are found, the **DataRowView** array will be empty.</span></span>  
  
 <span data-ttu-id="c033d-112">若要使用**查找**或**FindRows**方法必须指定排序顺序通过设置**ApplyDefaultSort**到**true**或通过使用**排序**属性。</span><span class="sxs-lookup"><span data-stu-id="c033d-112">To use the **Find** or **FindRows** methods you must specify a sort order either by setting **ApplyDefaultSort** to **true** or by using the **Sort** property.</span></span> <span data-ttu-id="c033d-113">如果未指定排序顺序，则将引发异常。</span><span class="sxs-lookup"><span data-stu-id="c033d-113">If no sort order is specified, an exception is thrown.</span></span>  
  
 <span data-ttu-id="c033d-114">**查找**和**FindRows**方法将一个值数组作为输入长度与匹配的排序顺序中的列数。</span><span class="sxs-lookup"><span data-stu-id="c033d-114">The **Find** and **FindRows** methods take an array of values as input whose length matches the number of columns in the sort order.</span></span> <span data-ttu-id="c033d-115">在对单个列进行排序的情况下，可以传递单个值。</span><span class="sxs-lookup"><span data-stu-id="c033d-115">In the case of a sort on a single column, you can pass a single value.</span></span> <span data-ttu-id="c033d-116">对于包含多个列的排序顺序，可传递一个对象数组。</span><span class="sxs-lookup"><span data-stu-id="c033d-116">For sort orders containing multiple columns, you pass an array of objects.</span></span> <span data-ttu-id="c033d-117">请注意，对多个列进行排序，对象数组中的值必须匹配中指定的列的顺序**排序**属性**DataView**。</span><span class="sxs-lookup"><span data-stu-id="c033d-117">Note that for a sort on multiple columns, the values in the object array must match the order of the columns specified in the **Sort** property of the **DataView**.</span></span>  
  
 <span data-ttu-id="c033d-118">下面的代码示例演示**查找**针对正在调用的方法**DataView**具有单个列排序顺序。</span><span class="sxs-lookup"><span data-stu-id="c033d-118">The following code example shows the **Find** method being called against a **DataView** with a single column sort order.</span></span>  
  
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
  
 <span data-ttu-id="c033d-119">如果你**排序**属性指定多个列，必须传递包含每个列的搜索值的对象数组中指定的顺序**排序**属性，如下面的代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="c033d-119">If your **Sort** property specifies multiple columns, you must pass an object array with the search values for each column in the order specified by the **Sort** property, as in the following code example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c033d-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="c033d-120">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [<span data-ttu-id="c033d-121">数据视图</span><span class="sxs-lookup"><span data-stu-id="c033d-121">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="c033d-122">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="c033d-122">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
