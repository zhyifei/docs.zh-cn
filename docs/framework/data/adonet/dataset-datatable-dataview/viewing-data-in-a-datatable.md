---
title: 查看数据表中的数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
ms.openlocfilehash: ea92b8a5e46bdaa8e94756cd28a3fbcb2789d7b3
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204385"
---
# <a name="viewing-data-in-a-datatable"></a><span data-ttu-id="816b3-102">查看数据表中的数据</span><span class="sxs-lookup"><span data-stu-id="816b3-102">Viewing Data in a DataTable</span></span>

<span data-ttu-id="816b3-103">您可以使用**DataTable**的**Rows**和<xref:System.Data.DataTable> **Columns**集合来访问的内容。</span><span class="sxs-lookup"><span data-stu-id="816b3-103">You can access the contents of a <xref:System.Data.DataTable> by using the **Rows** and **Columns** collections of the **DataTable**.</span></span> <span data-ttu-id="816b3-104">你还可以使用<xref:System.Data.DataTable.Select%2A>方法, 根据包括搜索条件、排序顺序和行状态的条件, 返回**DataTable**中的数据子集。</span><span class="sxs-lookup"><span data-stu-id="816b3-104">You can also use the <xref:System.Data.DataTable.Select%2A> method to return subsets of the data in a **DataTable** according to criteria including search criteria, sort order, and row state.</span></span> <span data-ttu-id="816b3-105">此外, 在使用主键值<xref:System.Data.DataRowCollection.Find%2A>搜索特定行时, 可以使用**DataRowCollection**的方法。</span><span class="sxs-lookup"><span data-stu-id="816b3-105">Additionally, you can use the <xref:System.Data.DataRowCollection.Find%2A> method of the **DataRowCollection** when searching for a particular row using a primary key value.</span></span>

<span data-ttu-id="816b3-106">**DataTable**对象的<xref:System.Data.DataRow> **Select**方法返回一组与指定条件匹配的对象。</span><span class="sxs-lookup"><span data-stu-id="816b3-106">The **Select** method of the **DataTable** object returns a set of <xref:System.Data.DataRow> objects that match the specified criteria.</span></span> <span data-ttu-id="816b3-107">**Select**使用筛选表达式、排序表达式和**DataViewRowState**的可选参数。</span><span class="sxs-lookup"><span data-stu-id="816b3-107">**Select** takes optional arguments of a filter expression, sort expression, and **DataViewRowState**.</span></span> <span data-ttu-id="816b3-108">筛选表达式基于**DataColumn**值 (如`LastName = 'Smith'`) 标识要返回的行。</span><span class="sxs-lookup"><span data-stu-id="816b3-108">The filter expression identifies which rows to return based on **DataColumn** values, such as `LastName = 'Smith'`.</span></span> <span data-ttu-id="816b3-109">排序表达式遵循用于为列排序的标准 SQL 约定，例如 `LastName ASC, FirstName ASC`。</span><span class="sxs-lookup"><span data-stu-id="816b3-109">The sort expression follows standard SQL conventions for ordering columns, for example `LastName ASC, FirstName ASC`.</span></span> <span data-ttu-id="816b3-110">有关编写表达式的规则, 请参阅<xref:System.Data.DataColumn.Expression%2A> **DataColumn**类的属性。</span><span class="sxs-lookup"><span data-stu-id="816b3-110">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>

> [!TIP]
> <span data-ttu-id="816b3-111">如果要对**datatable** <xref:System.Data.DataView>的**Select**方法执行多个调用, 可以通过首先为**datatable**创建来提高性能。</span><span class="sxs-lookup"><span data-stu-id="816b3-111">If you are performing a number of calls to the **Select** method of a **DataTable**, you can increase performance by first creating a <xref:System.Data.DataView> for the **DataTable**.</span></span> <span data-ttu-id="816b3-112">创建**DataView**会索引表中的行。</span><span class="sxs-lookup"><span data-stu-id="816b3-112">Creating the **DataView** indexes the rows of the table.</span></span> <span data-ttu-id="816b3-113">然后, **Select**方法使用该索引, 大大减少了生成查询结果的时间。</span><span class="sxs-lookup"><span data-stu-id="816b3-113">The **Select** method then uses that index, significantly reducing the time to generate the query result.</span></span> <span data-ttu-id="816b3-114">有关为**DataTable**创建**DataView**的信息, 请参阅[dataview](dataviews.md)。</span><span class="sxs-lookup"><span data-stu-id="816b3-114">For information about creating a **DataView** for a **DataTable**, see [DataViews](dataviews.md).</span></span>

<span data-ttu-id="816b3-115">**Select**方法确定要基于<xref:System.Data.DataViewRowState>其查看或操作的行的版本。</span><span class="sxs-lookup"><span data-stu-id="816b3-115">The **Select** method determines which version of the rows to view or manipulate based on a <xref:System.Data.DataViewRowState>.</span></span> <span data-ttu-id="816b3-116">下表描述了可能的**DataViewRowState**枚举值。</span><span class="sxs-lookup"><span data-stu-id="816b3-116">The following table describes the possible **DataViewRowState** enumeration values.</span></span>

|<span data-ttu-id="816b3-117">DataViewRowState 值</span><span class="sxs-lookup"><span data-stu-id="816b3-117">DataViewRowState value</span></span>|<span data-ttu-id="816b3-118">描述</span><span class="sxs-lookup"><span data-stu-id="816b3-118">Description</span></span>|
|----------------------------|-----------------|
|<span data-ttu-id="816b3-119">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="816b3-119">**CurrentRows**</span></span>|<span data-ttu-id="816b3-120">当前行，包括未更改的行、已添加的行和已修改的行。</span><span class="sxs-lookup"><span data-stu-id="816b3-120">Current rows including unchanged, added, and modified rows.</span></span>|
|<span data-ttu-id="816b3-121">**删除**</span><span class="sxs-lookup"><span data-stu-id="816b3-121">**Deleted**</span></span>|<span data-ttu-id="816b3-122">已删除的行。</span><span class="sxs-lookup"><span data-stu-id="816b3-122">A deleted row.</span></span>|
|<span data-ttu-id="816b3-123">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="816b3-123">**ModifiedCurrent**</span></span>|<span data-ttu-id="816b3-124">当前版本，它是原始数据的修改版本。</span><span class="sxs-lookup"><span data-stu-id="816b3-124">A current version, which is a modified version of original data.</span></span> <span data-ttu-id="816b3-125">(请参阅**ModifiedOriginal**。)</span><span class="sxs-lookup"><span data-stu-id="816b3-125">(See **ModifiedOriginal**.)</span></span>|
|<span data-ttu-id="816b3-126">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="816b3-126">**ModifiedOriginal**</span></span>|<span data-ttu-id="816b3-127">所有已修改行的原始版本。</span><span class="sxs-lookup"><span data-stu-id="816b3-127">The original version of all modified rows.</span></span> <span data-ttu-id="816b3-128">当前版本可用于**ModifiedCurrent**。</span><span class="sxs-lookup"><span data-stu-id="816b3-128">The current version is available using **ModifiedCurrent**.</span></span>|
|<span data-ttu-id="816b3-129">**已**</span><span class="sxs-lookup"><span data-stu-id="816b3-129">**Added**</span></span>|<span data-ttu-id="816b3-130">新行。</span><span class="sxs-lookup"><span data-stu-id="816b3-130">A new row.</span></span>|
|<span data-ttu-id="816b3-131">**无**</span><span class="sxs-lookup"><span data-stu-id="816b3-131">**None**</span></span>|<span data-ttu-id="816b3-132">无。</span><span class="sxs-lookup"><span data-stu-id="816b3-132">None.</span></span>|
|<span data-ttu-id="816b3-133">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="816b3-133">**OriginalRows**</span></span>|<span data-ttu-id="816b3-134">原始行，包括未更改的行和已删除的行。</span><span class="sxs-lookup"><span data-stu-id="816b3-134">Original rows, including unchanged and deleted rows.</span></span>|
|<span data-ttu-id="816b3-135">**变化**</span><span class="sxs-lookup"><span data-stu-id="816b3-135">**Unchanged**</span></span>|<span data-ttu-id="816b3-136">未更改的行。</span><span class="sxs-lookup"><span data-stu-id="816b3-136">An unchanged row.</span></span>|

<span data-ttu-id="816b3-137">在下面的示例中, 对**DataSet**对象进行了筛选, 以便您只使用其**DataViewRowState**设置为**CurrentRows**的行。</span><span class="sxs-lookup"><span data-stu-id="816b3-137">In the following example, the **DataSet** object is filtered so that you are only working with rows whose **DataViewRowState** is set to **CurrentRows**.</span></span>

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

<span data-ttu-id="816b3-138">**Select**方法可用于返回具有不同的**RowState**值或字段值的行。</span><span class="sxs-lookup"><span data-stu-id="816b3-138">The **Select** method can be used to return rows with differing **RowState** values or field values.</span></span> <span data-ttu-id="816b3-139">下面的示例返回引用所有已删除行的**datarow**数组, 并返回引用所有行的另一个**datarow**数组, 这些行由**custlname 排序 (** 排序, 其中**CustID**列大于5。</span><span class="sxs-lookup"><span data-stu-id="816b3-139">The following example returns a **DataRow** array that references all rows that have been deleted, and returns another **DataRow** array that references all rows, ordered by **CustLName**, where the **CustID** column is greater than 5.</span></span> <span data-ttu-id="816b3-140">浪中的信息**已删除**行中，请参阅[行状态和行版本](row-states-and-row-versions.md)。</span><span class="sxs-lookup"><span data-stu-id="816b3-140">For information about how to view the information in the **Deleted** row, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="816b3-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="816b3-141">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataViewRowState>
- [<span data-ttu-id="816b3-142">操作数据表中的数据</span><span class="sxs-lookup"><span data-stu-id="816b3-142">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="816b3-143">行状态和行版本</span><span class="sxs-lookup"><span data-stu-id="816b3-143">Row States and Row Versions</span></span>](row-states-and-row-versions.md)
- [<span data-ttu-id="816b3-144">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="816b3-144">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
