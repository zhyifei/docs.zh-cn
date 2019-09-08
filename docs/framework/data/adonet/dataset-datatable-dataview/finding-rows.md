---
title: 查找行
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
ms.openlocfilehash: ad10557a55b498fe004bff6ce89801e975e7138b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786328"
---
# <a name="finding-rows"></a><span data-ttu-id="0239d-102">查找行</span><span class="sxs-lookup"><span data-stu-id="0239d-102">Finding Rows</span></span>
<span data-ttu-id="0239d-103">可以使用 <xref:System.Data.DataView.Find%2A> 的 <xref:System.Data.DataView.FindRows%2A> 和 <xref:System.Data.DataView> 方法，根据排序关键字值搜索行。</span><span class="sxs-lookup"><span data-stu-id="0239d-103">You can search for rows according to their sort key values by using the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView>.</span></span> <span data-ttu-id="0239d-104">**Find**和**FindRows**方法中搜索值的区分大小写取决于基础<xref:System.Data.DataTable>的**CaseSensitive**属性。</span><span class="sxs-lookup"><span data-stu-id="0239d-104">The case sensitivity of search values in the **Find** and **FindRows** methods is determined by the **CaseSensitive** property of the underlying <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="0239d-105">搜索值必须完全匹配现有排序关键字值才能返回结果。</span><span class="sxs-lookup"><span data-stu-id="0239d-105">Search values must match existing sort key values in their entirety in order to return a result.</span></span>  
  
 <span data-ttu-id="0239d-106">**Find**方法返回一个整数，该整数包含与搜索<xref:System.Data.DataRowView>条件匹配的的索引。</span><span class="sxs-lookup"><span data-stu-id="0239d-106">The **Find** method returns an integer with the index of the <xref:System.Data.DataRowView> that matches the search criteria.</span></span> <span data-ttu-id="0239d-107">如果多行与搜索条件匹配，则仅返回第一个匹配**DataRowView**的索引。</span><span class="sxs-lookup"><span data-stu-id="0239d-107">If more than one row matches the search criteria, only the index of the first matching **DataRowView** is returned.</span></span> <span data-ttu-id="0239d-108">如果找不到匹配项， **Find**将返回-1。</span><span class="sxs-lookup"><span data-stu-id="0239d-108">If no matches are found, **Find** returns -1.</span></span>  
  
 <span data-ttu-id="0239d-109">若要返回与多个行匹配的搜索结果，请使用**FindRows**方法。</span><span class="sxs-lookup"><span data-stu-id="0239d-109">To return search results that match multiple rows, use the **FindRows** method.</span></span> <span data-ttu-id="0239d-110">**FindRows**的工作方式与**Find**方法相同，不同之处在于该方法返回的**DataRowView**数组引用**DataView**中的所有匹配行。</span><span class="sxs-lookup"><span data-stu-id="0239d-110">**FindRows** works just like the **Find** method, except that it returns a **DataRowView** array that references all matching rows in the **DataView**.</span></span> <span data-ttu-id="0239d-111">如果未找到匹配项， **DataRowView**数组将为空。</span><span class="sxs-lookup"><span data-stu-id="0239d-111">If no matches are found, the **DataRowView** array will be empty.</span></span>  
  
 <span data-ttu-id="0239d-112">若要使用**Find**或**FindRows**方法，必须通过将**ApplyDefaultSort**设置为**true**或使用**sort**属性来指定排序顺序。</span><span class="sxs-lookup"><span data-stu-id="0239d-112">To use the **Find** or **FindRows** methods you must specify a sort order either by setting **ApplyDefaultSort** to **true** or by using the **Sort** property.</span></span> <span data-ttu-id="0239d-113">如果未指定排序顺序，则将引发异常。</span><span class="sxs-lookup"><span data-stu-id="0239d-113">If no sort order is specified, an exception is thrown.</span></span>  
  
 <span data-ttu-id="0239d-114">**Find**和**FindRows**方法将值数组作为输入，其长度与排序顺序中的列数匹配。</span><span class="sxs-lookup"><span data-stu-id="0239d-114">The **Find** and **FindRows** methods take an array of values as input whose length matches the number of columns in the sort order.</span></span> <span data-ttu-id="0239d-115">在对单个列进行排序的情况下，可以传递单个值。</span><span class="sxs-lookup"><span data-stu-id="0239d-115">In the case of a sort on a single column, you can pass a single value.</span></span> <span data-ttu-id="0239d-116">对于包含多个列的排序顺序，可传递一个对象数组。</span><span class="sxs-lookup"><span data-stu-id="0239d-116">For sort orders containing multiple columns, you pass an array of objects.</span></span> <span data-ttu-id="0239d-117">请注意，对于多列排序，对象数组中的值必须与**DataView**的**sort**属性中指定的列顺序相匹配。</span><span class="sxs-lookup"><span data-stu-id="0239d-117">Note that for a sort on multiple columns, the values in the object array must match the order of the columns specified in the **Sort** property of the **DataView**.</span></span>  
  
 <span data-ttu-id="0239d-118">下面的代码示例演示了如何使用单列排序顺序对**DataView**调用**Find**方法。</span><span class="sxs-lookup"><span data-stu-id="0239d-118">The following code example shows the **Find** method being called against a **DataView** with a single column sort order.</span></span>  
  
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
  
 <span data-ttu-id="0239d-119">如果**Sort**属性指定了多个列，则必须按照**sort**属性指定的顺序为每个列的搜索值传递对象数组，如下面的代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="0239d-119">If your **Sort** property specifies multiple columns, you must pass an object array with the search values for each column in the order specified by the **Sort** property, as in the following code example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0239d-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="0239d-120">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="0239d-121">数据视图</span><span class="sxs-lookup"><span data-stu-id="0239d-121">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="0239d-122">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="0239d-122">ADO.NET Overview</span></span>](../ado-net-overview.md)
