---
title: 通过查询结果分页
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa360c46-e5f8-411e-a711-46997771133d
ms.openlocfilehash: 023efcc15d7080afc1583f4ad8984e152b86cf23
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59140317"
---
# <a name="paging-through-a-query-result"></a><span data-ttu-id="67073-102">通过查询结果分页</span><span class="sxs-lookup"><span data-stu-id="67073-102">Paging Through a Query Result</span></span>
<span data-ttu-id="67073-103">查询结果分页是以较小数据子集（即页）的形式返回查询结果的过程。</span><span class="sxs-lookup"><span data-stu-id="67073-103">Paging through a query result is the process of returning the results of a query in smaller subsets of data, or pages.</span></span> <span data-ttu-id="67073-104">它通常用于以易于管理的小块形式向用户显示结果。</span><span class="sxs-lookup"><span data-stu-id="67073-104">This is a common practice for displaying results to a user in small, easy-to-manage chunks.</span></span>  
  
 <span data-ttu-id="67073-105">**DataAdapter**提供的工具，用于仅返回一页的数据，通过重载**填充**方法。</span><span class="sxs-lookup"><span data-stu-id="67073-105">The **DataAdapter** provides a facility for returning only a page of data, through overloads of the **Fill** method.</span></span> <span data-ttu-id="67073-106">但是，这可能不是因为，通过大量的查询结果分页的最佳选择尽管**DataAdapter**填充目标<xref:System.Data.DataTable>或<xref:System.Data.DataSet>仅请求记录，若要返回的资源仍使用整个查询。</span><span class="sxs-lookup"><span data-stu-id="67073-106">However, this might not be the best choice for paging through large query results because, although the **DataAdapter** fills the target <xref:System.Data.DataTable> or <xref:System.Data.DataSet> with only the requested records, the resources to return the entire query are still used.</span></span> <span data-ttu-id="67073-107">若要在从数据源中返回一页数据时不使用返回整个查询的资源，请为查询指定附加条件，使返回的行数减少到只返回所需的行。</span><span class="sxs-lookup"><span data-stu-id="67073-107">To return a page of data from a data source without using the resources to return the entire query, specify additional criteria for your query that reduce the rows returned to only those required.</span></span>  
  
 <span data-ttu-id="67073-108">若要使用**填充**方法以返回一页数据，指定**startRecord**参数，第一个记录的页中的数据，和一个**maxRecords**参数的数目在数据页中的记录。</span><span class="sxs-lookup"><span data-stu-id="67073-108">To use the **Fill** method to return a page of data, specify a **startRecord** parameter, for the first record in the page of data, and a **maxRecords** parameter, for the number of records in the page of data.</span></span>  
  
 <span data-ttu-id="67073-109">下面的代码示例演示如何使用**填充**方法以返回查询结果的第一页的页大小为 5 个记录的位置。</span><span class="sxs-lookup"><span data-stu-id="67073-109">The following code example shows how to use the **Fill** method to return the first page of a query result where the page size is five records.</span></span>  
  
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
  
 <span data-ttu-id="67073-110">在上一示例中，**数据集**只填充了 5 个记录，但整个**订单**返回表。</span><span class="sxs-lookup"><span data-stu-id="67073-110">In the previous example, the **DataSet** is only filled with five records, but the entire **Orders** table is returned.</span></span> <span data-ttu-id="67073-111">若要填充**数据集**这些相同的五个记录，但仅返回 5 个记录，同时使用 TOP 和 WHERE 子句中 SQL 语句，如以下代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="67073-111">To fill the **DataSet** with those same five records, but only return five records, use the TOP and WHERE clauses in your SQL statement, as in the following code example.</span></span>  
  
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
  
 <span data-ttu-id="67073-112">请注意，当以这种方式进行查询结果分页时，必须保留用于对行进行排序的唯一标识符，以便将唯一 ID 传递给用于返回下一页记录的命令，如以下代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="67073-112">Note that, when paging through the query results in this way, you must preserve the unique identifier that orders the rows, in order to pass the unique ID to the command to return the next page of records, as shown in the following code example.</span></span>  
  
```vb  
Dim lastRecord As String = _  
  dataSet.Tables("Orders").Rows(pageSize - 1)("OrderID").ToString()  
```  
  
```csharp  
string lastRecord =   
  dataSet.Tables["Orders"].Rows[pageSize - 1]["OrderID"].ToString();  
```  
  
 <span data-ttu-id="67073-113">若要返回下一页记录使用的重载**填充**采用的方法**startRecord**并**maxRecords**参数，递增的当前记录索引页大小和填充在表中。</span><span class="sxs-lookup"><span data-stu-id="67073-113">To return the next page of records using the overload of the **Fill** method that takes the **startRecord** and **maxRecords** parameters, increment the current record index by the page size and fill the table.</span></span> <span data-ttu-id="67073-114">请记住，数据库服务器将返回整个查询结果，即使只有一页的记录添加到**数据集**。</span><span class="sxs-lookup"><span data-stu-id="67073-114">Remember that the database server returns the entire query results even though only one page of records is added to the **DataSet**.</span></span> <span data-ttu-id="67073-115">在以下代码示例中，先清除表行，然后再用下一页数据填充这些表行。</span><span class="sxs-lookup"><span data-stu-id="67073-115">In the following code example, the table rows are cleared before they are filled with the next page of data.</span></span> <span data-ttu-id="67073-116">您可能需要在本地缓存中保留一定数量的返回行，以减少与数据库服务器的往返次数。</span><span class="sxs-lookup"><span data-stu-id="67073-116">You might want to preserve a certain number of returned rows in a local cache to reduce trips to the database server.</span></span>  
  
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
  
 <span data-ttu-id="67073-117">若要返回下一页记录而不让数据库服务器返回整个查询，请指定对 SQL SELECT 语句的限制条件。</span><span class="sxs-lookup"><span data-stu-id="67073-117">To return the next page of records without having the database server return the entire query, specify restrictive criteria to the SELECT statement.</span></span> <span data-ttu-id="67073-118">由于上例保留了返回的最后一个记录，因此可以在 WHERE 子句中使用它来指定查询的起点，如以下代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="67073-118">Because the preceding example preserved the last record returned, you can use it in the WHERE clause to specify a starting point for the query, as shown in the following code example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="67073-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="67073-119">See also</span></span>

- [<span data-ttu-id="67073-120">DataAdapters 和 DataReaders</span><span class="sxs-lookup"><span data-stu-id="67073-120">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="67073-121">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="67073-121">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
