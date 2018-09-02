---
title: 查找行
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
ms.openlocfilehash: daa8097bc5dfee203f988915b1e4a8bdcd2c50e0
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43408079"
---
# <a name="finding-rows"></a><span data-ttu-id="be126-102">查找行</span><span class="sxs-lookup"><span data-stu-id="be126-102">Finding Rows</span></span>
<span data-ttu-id="be126-103">可以使用 <xref:System.Data.DataView.Find%2A> 的 <xref:System.Data.DataView.FindRows%2A> 和 <xref:System.Data.DataView> 方法，根据排序关键字值搜索行。</span><span class="sxs-lookup"><span data-stu-id="be126-103">You can search for rows according to their sort key values by using the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView>.</span></span> <span data-ttu-id="be126-104">中的值以搜索是否区分大小写**查找**并**FindRows**方法由**CaseSensitive**属性的基础<xref:System.Data.DataTable>。</span><span class="sxs-lookup"><span data-stu-id="be126-104">The case sensitivity of search values in the **Find** and **FindRows** methods is determined by the **CaseSensitive** property of the underlying <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="be126-105">搜索值必须完全匹配现有排序关键字值才能返回结果。</span><span class="sxs-lookup"><span data-stu-id="be126-105">Search values must match existing sort key values in their entirety in order to return a result.</span></span>  
  
 <span data-ttu-id="be126-106">**查找**方法返回一个整数，其索引的<xref:System.Data.DataRowView>与搜索条件匹配的。</span><span class="sxs-lookup"><span data-stu-id="be126-106">The **Find** method returns an integer with the index of the <xref:System.Data.DataRowView> that matches the search criteria.</span></span> <span data-ttu-id="be126-107">如果多个行匹配搜索条件，仅第一个匹配的索引**DataRowView**返回。</span><span class="sxs-lookup"><span data-stu-id="be126-107">If more than one row matches the search criteria, only the index of the first matching **DataRowView** is returned.</span></span> <span data-ttu-id="be126-108">如果不找到任何匹配项，**查找**返回-1。</span><span class="sxs-lookup"><span data-stu-id="be126-108">If no matches are found, **Find** returns -1.</span></span>  
  
 <span data-ttu-id="be126-109">若要返回的多个行匹配的搜索结果，请使用**FindRows**方法。</span><span class="sxs-lookup"><span data-stu-id="be126-109">To return search results that match multiple rows, use the **FindRows** method.</span></span> <span data-ttu-id="be126-110">**FindRows**工作方式就类似于**查找**方法，前者返回**DataRowView**引用中的所有匹配行的数组**DataView**。</span><span class="sxs-lookup"><span data-stu-id="be126-110">**FindRows** works just like the **Find** method, except that it returns a **DataRowView** array that references all matching rows in the **DataView**.</span></span> <span data-ttu-id="be126-111">如果不找到任何匹配项， **DataRowView**数组将为空。</span><span class="sxs-lookup"><span data-stu-id="be126-111">If no matches are found, the **DataRowView** array will be empty.</span></span>  
  
 <span data-ttu-id="be126-112">若要使用**查找**或**FindRows**方法必须指定排序顺序设置**ApplyDefaultSort**到**true**或通过使用**排序**属性。</span><span class="sxs-lookup"><span data-stu-id="be126-112">To use the **Find** or **FindRows** methods you must specify a sort order either by setting **ApplyDefaultSort** to **true** or by using the **Sort** property.</span></span> <span data-ttu-id="be126-113">如果未指定排序顺序，则将引发异常。</span><span class="sxs-lookup"><span data-stu-id="be126-113">If no sort order is specified, an exception is thrown.</span></span>  
  
 <span data-ttu-id="be126-114">**查找**并**FindRows**方法采用一个值数组作为其长度与排序顺序中的列数相匹配的输入。</span><span class="sxs-lookup"><span data-stu-id="be126-114">The **Find** and **FindRows** methods take an array of values as input whose length matches the number of columns in the sort order.</span></span> <span data-ttu-id="be126-115">在对单个列进行排序的情况下，可以传递单个值。</span><span class="sxs-lookup"><span data-stu-id="be126-115">In the case of a sort on a single column, you can pass a single value.</span></span> <span data-ttu-id="be126-116">对于包含多个列的排序顺序，可传递一个对象数组。</span><span class="sxs-lookup"><span data-stu-id="be126-116">For sort orders containing multiple columns, you pass an array of objects.</span></span> <span data-ttu-id="be126-117">请注意，对多个列上进行排序，对象数组中的值必须匹配中指定的列的顺序**排序**的属性**DataView**。</span><span class="sxs-lookup"><span data-stu-id="be126-117">Note that for a sort on multiple columns, the values in the object array must match the order of the columns specified in the **Sort** property of the **DataView**.</span></span>  
  
 <span data-ttu-id="be126-118">下面的代码示例演示**查找**方法调用针对**DataView**使用单个列的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="be126-118">The following code example shows the **Find** method being called against a **DataView** with a single column sort order.</span></span>  
  
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
  
 <span data-ttu-id="be126-119">如果你**排序**属性指定多个列，则必须按指定顺序通过包含每个列的搜索值的对象数组**排序**属性，如以下代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="be126-119">If your **Sort** property specifies multiple columns, you must pass an object array with the search values for each column in the order specified by the **Sort** property, as in the following code example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="be126-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="be126-120">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [<span data-ttu-id="be126-121">数据视图</span><span class="sxs-lookup"><span data-stu-id="be126-121">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="be126-122">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="be126-122">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
