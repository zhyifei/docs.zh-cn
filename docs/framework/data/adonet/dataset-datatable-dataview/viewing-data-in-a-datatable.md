---
title: 查看数据表中的数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
ms.openlocfilehash: de745633060dd4f7b1610492d0ff57ec7a4f545b
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2018
ms.locfileid: "45615776"
---
# <a name="viewing-data-in-a-datatable"></a><span data-ttu-id="646c9-102">查看数据表中的数据</span><span class="sxs-lookup"><span data-stu-id="646c9-102">Viewing Data in a DataTable</span></span>
<span data-ttu-id="646c9-103">可以访问的内容<xref:System.Data.DataTable>通过使用**行**并**列**集合**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="646c9-103">You can access the contents of a <xref:System.Data.DataTable> by using the **Rows** and **Columns** collections of the **DataTable**.</span></span> <span data-ttu-id="646c9-104">此外可以使用<xref:System.Data.DataTable.Select%2A>方法来返回中的数据的子集**DataTable**根据包括搜索条件的条件，排序顺序和行状态。</span><span class="sxs-lookup"><span data-stu-id="646c9-104">You can also use the <xref:System.Data.DataTable.Select%2A> method to return subsets of the data in a **DataTable** according to criteria including search criteria, sort order, and row state.</span></span> <span data-ttu-id="646c9-105">此外，还可以使用<xref:System.Data.DataRowCollection.Find%2A>方法**DataRowCollection**搜索使用的主键值的特定行时。</span><span class="sxs-lookup"><span data-stu-id="646c9-105">Additionally, you can use the <xref:System.Data.DataRowCollection.Find%2A> method of the **DataRowCollection** when searching for a particular row using a primary key value.</span></span>  
  
 <span data-ttu-id="646c9-106">**选择**方法**DataTable**对象返回的一组<xref:System.Data.DataRow>符合指定的条件的对象。</span><span class="sxs-lookup"><span data-stu-id="646c9-106">The **Select** method of the **DataTable** object returns a set of <xref:System.Data.DataRow> objects that match the specified criteria.</span></span> <span data-ttu-id="646c9-107">**选择**采用的筛选表达式、 排序表达式的可选参数和**DataViewRowState**。</span><span class="sxs-lookup"><span data-stu-id="646c9-107">**Select** takes optional arguments of a filter expression, sort expression, and **DataViewRowState**.</span></span> <span data-ttu-id="646c9-108">筛选器表达式标识要返回基于的行**DataColumn**值，例如`LastName = 'Smith'`。</span><span class="sxs-lookup"><span data-stu-id="646c9-108">The filter expression identifies which rows to return based on **DataColumn** values, such as `LastName = 'Smith'`.</span></span> <span data-ttu-id="646c9-109">排序表达式遵循用于为列排序的标准 SQL 约定，例如 `LastName ASC, FirstName ASC`。</span><span class="sxs-lookup"><span data-stu-id="646c9-109">The sort expression follows standard SQL conventions for ordering columns, for example `LastName ASC, FirstName ASC`.</span></span> <span data-ttu-id="646c9-110">有关编写表达式的规则，请参阅<xref:System.Data.DataColumn.Expression%2A>的属性**DataColumn**类。</span><span class="sxs-lookup"><span data-stu-id="646c9-110">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="646c9-111">如果您正在执行对的调用次数**选择**方法**DataTable**，您可以提高性能，方法是首先创建<xref:System.Data.DataView>有关**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="646c9-111">If you are performing a number of calls to the **Select** method of a **DataTable**, you can increase performance by first creating a <xref:System.Data.DataView> for the **DataTable**.</span></span> <span data-ttu-id="646c9-112">创建**DataView**表的行编制索引。</span><span class="sxs-lookup"><span data-stu-id="646c9-112">Creating the **DataView** indexes the rows of the table.</span></span> <span data-ttu-id="646c9-113">**选择**方法则会使用该索引，显著缩短生成查询结果的时间。</span><span class="sxs-lookup"><span data-stu-id="646c9-113">The **Select** method then usees that index, significantly reducing the time to generate the query result.</span></span> <span data-ttu-id="646c9-114">有关创建信息**DataView**有关**DataTable**，请参阅[Dataview](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)。</span><span class="sxs-lookup"><span data-stu-id="646c9-114">For information about creating a **DataView** for a **DataTable**, see [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).</span></span>  
  
 <span data-ttu-id="646c9-115">**选择**方法确定要查看或操作的行的版本根据<xref:System.Data.DataViewRowState>。</span><span class="sxs-lookup"><span data-stu-id="646c9-115">The **Select** method determines which version of the rows to view or manipulate based on a <xref:System.Data.DataViewRowState>.</span></span> <span data-ttu-id="646c9-116">下表描述了可能**DataViewRowState**枚举值。</span><span class="sxs-lookup"><span data-stu-id="646c9-116">The following table describes the possible **DataViewRowState** enumeration values.</span></span>  
  
|<span data-ttu-id="646c9-117">DataViewRowState 值</span><span class="sxs-lookup"><span data-stu-id="646c9-117">DataViewRowState value</span></span>|<span data-ttu-id="646c9-118">描述</span><span class="sxs-lookup"><span data-stu-id="646c9-118">Description</span></span>|  
|----------------------------|-----------------|  
|<span data-ttu-id="646c9-119">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="646c9-119">**CurrentRows**</span></span>|<span data-ttu-id="646c9-120">当前行，包括未更改的行、已添加的行和已修改的行。</span><span class="sxs-lookup"><span data-stu-id="646c9-120">Current rows including unchanged, added, and modified rows.</span></span>|  
|<span data-ttu-id="646c9-121">**已删除**</span><span class="sxs-lookup"><span data-stu-id="646c9-121">**Deleted**</span></span>|<span data-ttu-id="646c9-122">已删除的行。</span><span class="sxs-lookup"><span data-stu-id="646c9-122">A deleted row.</span></span>|  
|<span data-ttu-id="646c9-123">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="646c9-123">**ModifiedCurrent**</span></span>|<span data-ttu-id="646c9-124">当前版本，它是原始数据的修改版本。</span><span class="sxs-lookup"><span data-stu-id="646c9-124">A current version, which is a modified version of original data.</span></span> <span data-ttu-id="646c9-125">(请参阅**ModifiedOriginal**。)</span><span class="sxs-lookup"><span data-stu-id="646c9-125">(See **ModifiedOriginal**.)</span></span>|  
|<span data-ttu-id="646c9-126">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="646c9-126">**ModifiedOriginal**</span></span>|<span data-ttu-id="646c9-127">所有已修改行的原始版本。</span><span class="sxs-lookup"><span data-stu-id="646c9-127">The original version of all modified rows.</span></span> <span data-ttu-id="646c9-128">当前版本是可以使用**ModifiedCurrent**。</span><span class="sxs-lookup"><span data-stu-id="646c9-128">The current version is available using **ModifiedCurrent**.</span></span>|  
|<span data-ttu-id="646c9-129">**添加**</span><span class="sxs-lookup"><span data-stu-id="646c9-129">**Added**</span></span>|<span data-ttu-id="646c9-130">新行。</span><span class="sxs-lookup"><span data-stu-id="646c9-130">A new row.</span></span>|  
|<span data-ttu-id="646c9-131">**无**</span><span class="sxs-lookup"><span data-stu-id="646c9-131">**None**</span></span>|<span data-ttu-id="646c9-132">无。</span><span class="sxs-lookup"><span data-stu-id="646c9-132">None.</span></span>|  
|<span data-ttu-id="646c9-133">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="646c9-133">**OriginalRows**</span></span>|<span data-ttu-id="646c9-134">原始行，包括未更改的行和已删除的行。</span><span class="sxs-lookup"><span data-stu-id="646c9-134">Original rows, including unchanged and deleted rows.</span></span>|  
|<span data-ttu-id="646c9-135">**保持不变**</span><span class="sxs-lookup"><span data-stu-id="646c9-135">**Unchanged**</span></span>|<span data-ttu-id="646c9-136">未更改的行。</span><span class="sxs-lookup"><span data-stu-id="646c9-136">An unchanged row.</span></span>|  
  
 <span data-ttu-id="646c9-137">在以下示例中，**数据集**对象进行筛选，以便仅使用行其**DataViewRowState**设置为**CurrentRows**。</span><span class="sxs-lookup"><span data-stu-id="646c9-137">In the following example, the **DataSet** object is filtered so that you are only working with rows whose **DataViewRowState** is set to **CurrentRows**.</span></span>  
  
```vb  
Dim column As DataColumn  
Dim row As DataRow  
  
Dim currentRows() As DataRow = _  
    workTable.Select(Nothing, Nothing, DataViewRowState.CurrentRows)  
  
If (currentRows.Length < 1 ) Then  
  Console.WriteLine("No Current Rows Found")  
Else  
  For Each column in workTable.Columns  
    Console.Write(vbTab & column.ColumnName)  
  Next  
  
  Console.WriteLine(vbTab & "RowState")  
  
  For Each row In currentRows  
    For Each column In workTable.Columns  
      Console.Write(vbTab & row(column).ToString())  
    Next  
  
    Dim rowState As String = _  
        System.Enum.GetName(row.RowState.GetType(), row.RowState)  
    Console.WriteLine(vbTab & rowState)  
  Next  
End If  
```  
  
```csharp  
DataRow[] currentRows = workTable.Select(  
    null, null, DataViewRowState.CurrentRows);  
  
if (currentRows.Length < 1 )  
  Console.WriteLine("No Current Rows Found");  
else  
{  
  foreach (DataColumn column in workTable.Columns)  
    Console.Write("\t{0}", column.ColumnName);  
  
  Console.WriteLine("\tRowState");  
  
  foreach (DataRow row in currentRows)  
  {  
    foreach (DataColumn column in workTable.Columns)  
      Console.Write("\t{0}", row[column]);  
  
    Console.WriteLine("\t" + row.RowState);  
  }  
}  
```  
  
 <span data-ttu-id="646c9-138">**选择**方法可用于返回具有不同的行**RowState**值或字段值。</span><span class="sxs-lookup"><span data-stu-id="646c9-138">The **Select** method can be used to return rows with differing **RowState** values or field values.</span></span> <span data-ttu-id="646c9-139">下面的示例返回**DataRow**引用已被删除，并返回另一个的所有行的数组**DataRow**按排序的数组，它都引用的所有行， **CustLName**，其中**CustID**列大于 5。</span><span class="sxs-lookup"><span data-stu-id="646c9-139">The following example returns a **DataRow** array that references all rows that have been deleted, and returns another **DataRow** array that references all rows, ordered by **CustLName**, where the **CustID** column is greater than 5.</span></span> <span data-ttu-id="646c9-140">浪中的信息**已删除**行中，请参阅[行状态和行版本](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)。</span><span class="sxs-lookup"><span data-stu-id="646c9-140">For information about how to view the information in the **Deleted** row, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
```vb  
' Retrieve all deleted rows.  
Dim deletedRows() As DataRow = workTable.Select(Nothing, Nothing, DataViewRowState.Deleted)  
  
' Retrieve rows where CustID > 5, and order by CustLName.  
Dim custRows() As DataRow = workTable.Select( _  
    "CustID > 5", "CustLName ASC")  
```  
  
```csharp  
// Retrieve all deleted rows.  
DataRow[] deletedRows = workTable.Select(  
    null, null, DataViewRowState.Deleted);  
  
// Retrieve rows where CustID > 5, and order by CustLName.  
DataRow[] custRows = workTable.Select("CustID > 5", "CustLName ASC");  
```  
  
## <a name="see-also"></a><span data-ttu-id="646c9-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="646c9-141">See Also</span></span>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataViewRowState>  
 [<span data-ttu-id="646c9-142">操作数据表中的数据</span><span class="sxs-lookup"><span data-stu-id="646c9-142">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="646c9-143">行状态和行版本</span><span class="sxs-lookup"><span data-stu-id="646c9-143">Row States and Row Versions</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)  
 [<span data-ttu-id="646c9-144">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="646c9-144">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
