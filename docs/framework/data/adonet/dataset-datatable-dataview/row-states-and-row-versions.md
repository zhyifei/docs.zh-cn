---
title: 行状态和行版本
ms.date: 07/19/2018
dev_langs:
- csharp
- vb
ms.assetid: 2e6642c9-bfc6-425c-b3a7-e4912ffa6c1f
ms.openlocfilehash: 629e8b0bea1cd5c1dd80409acd7c03e0e033b5bc
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43880569"
---
# <a name="row-states-and-row-versions"></a><span data-ttu-id="fd9b1-102">行状态和行版本</span><span class="sxs-lookup"><span data-stu-id="fd9b1-102">Row States and Row Versions</span></span>
<span data-ttu-id="fd9b1-103">ADO.NET 用行状态和行版本管理表中的行。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-103">ADO.NET manages rows in tables using row states and versions.</span></span> <span data-ttu-id="fd9b1-104">行状态指示行的状态；行版本在修改行中存储的值时维护各个阶段的值，包括当前值、原始值和默认值。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-104">A row state indicates the status of a row; row versions maintain the values stored in a row as it is modified, including current, original, and default values.</span></span> <span data-ttu-id="fd9b1-105">例如，在修改了行中的某列后，该行的行状态将为 `Modified`，并且有两个行版本：`Current`（包含行的当前值）和 `Original`（包含列修改前行的值）。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-105">For example, after you have made a modification to a column in a row, the row will have a row state of `Modified`, and two row versions: `Current`, which contains the current row values, and `Original`, which contains the row values before the column was modified.</span></span>  
  
 <span data-ttu-id="fd9b1-106">每个 <xref:System.Data.DataRow> 对象都具有 <xref:System.Data.DataRow.RowState%2A> 属性，您可以检查此属性来确定行的当前状态。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-106">Each <xref:System.Data.DataRow> object has a <xref:System.Data.DataRow.RowState%2A> property that you can examine to determine the current state of the row.</span></span> <span data-ttu-id="fd9b1-107">下表提供了对每个 `RowState` 枚举值的简短说明。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-107">The following table gives a brief description of each `RowState` enumeration value.</span></span>  
  
|<span data-ttu-id="fd9b1-108">RowState 值</span><span class="sxs-lookup"><span data-stu-id="fd9b1-108">RowState value</span></span>|<span data-ttu-id="fd9b1-109">描述</span><span class="sxs-lookup"><span data-stu-id="fd9b1-109">Description</span></span>|  
|--------------------|-----------------|  
|<xref:System.Data.DataRowState.Unchanged>|<span data-ttu-id="fd9b1-110">自上次调用 `AcceptChanges` 以来或由 `DataAdapter.Fill` 创建该行以来，没有进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-110">No changes have been made since the last call to `AcceptChanges` or since the row was created by `DataAdapter.Fill`.</span></span>|  
|<xref:System.Data.DataRowState.Added>|<span data-ttu-id="fd9b1-111">已将该行添加到表中，但尚未调用 `AcceptChanges`。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-111">The row has been added to the table, but `AcceptChanges` has not been called.</span></span>|  
|<xref:System.Data.DataRowState.Modified>|<span data-ttu-id="fd9b1-112">已更改了行的某个元素。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-112">Some element of the row has been changed.</span></span>|  
|<xref:System.Data.DataRowState.Deleted>|<span data-ttu-id="fd9b1-113">已从表中删除该行，并且尚未调用 `AcceptChanges`。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-113">The row has been deleted from a table, and `AcceptChanges` has not been called.</span></span>|  
|<xref:System.Data.DataRowState.Detached>|<span data-ttu-id="fd9b1-114">该行不是任何 `DataRowCollection` 的一部分。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-114">The row is not part of any `DataRowCollection`.</span></span> <span data-ttu-id="fd9b1-115">新创建的行的 `RowState` 设置为 `Detached`。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-115">The `RowState` of a newly created row is set to `Detached`.</span></span> <span data-ttu-id="fd9b1-116">通过调用 `DataRow` 方法将新的 `DataRowCollection` 添加到 `Add` 后，`RowState` 属性的值设置为 `Added`。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-116">After the new `DataRow` is added to the `DataRowCollection` by calling the `Add` method, the value of the `RowState` property is set to `Added`.</span></span><br /><br /> <span data-ttu-id="fd9b1-117">将使用 `Detached` 方法，或使用 `DataRowCollection` 方法接着使用 `Remove` 方法从 `Delete` 中移除的行也设置为 `AcceptChanges`。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-117">`Detached` is also set for a row that has been removed from a `DataRowCollection` using the `Remove` method, or by the `Delete` method followed by the `AcceptChanges` method.</span></span>|  
  
 <span data-ttu-id="fd9b1-118">对 `AcceptChanges`、<xref:System.Data.DataSet> 或 <xref:System.Data.DataTable> 调用 <xref:System.Data.DataRow> 时，会移除行状态为 `Deleted` 的所有行。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-118">When `AcceptChanges` is called on a <xref:System.Data.DataSet>, <xref:System.Data.DataTable> , or <xref:System.Data.DataRow>, all rows with a row state of `Deleted` are removed.</span></span> <span data-ttu-id="fd9b1-119">剩余行的行状态为 `Unchanged`，并且 `Original` 行版本中的值将被 `Current` 行版本值覆盖。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-119">The remaining rows are given a row state of `Unchanged`, and the values in the `Original` row version are overwritten with the `Current` row version values.</span></span> <span data-ttu-id="fd9b1-120">调用 `RejectChanges` 时，会移除行状态为 `Added` 的所有行。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-120">When `RejectChanges` is called, all rows with a row state of `Added` are removed.</span></span> <span data-ttu-id="fd9b1-121">剩余行的行状态为 `Unchanged`，并且 `Current` 行版本中的值将被 `Original` 行版本值覆盖。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-121">The remaining rows are given a row state of `Unchanged`, and the values in the `Current` row version are overwritten with the `Original` row version values.</span></span>  
  
 <span data-ttu-id="fd9b1-122">通过列引用来传递 <xref:System.Data.DataRowVersion> 参数，您可以查看行的不同行版本，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-122">You can view the different row versions of a row by passing a <xref:System.Data.DataRowVersion> parameter with the column reference, as shown in the following example.</span></span>  
  
```vb  
Dim custRow As DataRow = custTable.Rows(0)  
Dim custID As String = custRow("CustomerID", DataRowVersion.Original).ToString()  
```  
  
```csharp  
DataRow custRow = custTable.Rows[0];  
string custID = custRow["CustomerID", DataRowVersion.Original].ToString();  
```  
  
 <span data-ttu-id="fd9b1-123">下表提供了对每个 `DataRowVersion` 枚举值的简短说明。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-123">The following table gives a brief description of each `DataRowVersion` enumeration value.</span></span>  
  
|<span data-ttu-id="fd9b1-124">DataRowVersion 值</span><span class="sxs-lookup"><span data-stu-id="fd9b1-124">DataRowVersion value</span></span>|<span data-ttu-id="fd9b1-125">描述</span><span class="sxs-lookup"><span data-stu-id="fd9b1-125">Description</span></span>|  
|--------------------------|-----------------|  
|<xref:System.Data.DataRowVersion.Current>|<span data-ttu-id="fd9b1-126">行的当前值。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-126">The current values for the row.</span></span> <span data-ttu-id="fd9b1-127">如果行的 `RowState` 为 `Deleted`，则不存在此行版本。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-127">This row version does not exist for rows with a `RowState` of `Deleted`.</span></span>|  
|<xref:System.Data.DataRowVersion.Default>|<span data-ttu-id="fd9b1-128">特定行的默认行版本。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-128">The default row version for a particular row.</span></span> <span data-ttu-id="fd9b1-129">`Added`、`Modified` 或 `Deleted` 行的默认行版本是 `Current`。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-129">The default row version for an `Added`, `Modified`, or `Deleted` row is `Current`.</span></span> <span data-ttu-id="fd9b1-130">`Detached` 行的默认行版本是 `Proposed`。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-130">The default row version for a `Detached` row is `Proposed`.</span></span>|  
|<xref:System.Data.DataRowVersion.Original>|<span data-ttu-id="fd9b1-131">行的原始值。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-131">The original values for the row.</span></span> <span data-ttu-id="fd9b1-132">如果行的 `RowState` 为 `Added`，则不存在此行版本。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-132">This row version does not exist for rows with a `RowState` of `Added`.</span></span>|  
|<xref:System.Data.DataRowVersion.Proposed>|<span data-ttu-id="fd9b1-133">行的建议值。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-133">The proposed values for the row.</span></span> <span data-ttu-id="fd9b1-134">在对行进行编辑操作的过程中，或者对于不属于 `DataRowCollection` 的行，存在此行版本。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-134">This row version exists during an edit operation on a row, or for a row that is not part of a `DataRowCollection`.</span></span>|  
  
 <span data-ttu-id="fd9b1-135">通过调用 `DataRow` 方法并将 <xref:System.Data.DataRow.HasVersion%2A> 作为参数传递，您可以测试 `DataRowVersion` 是否具有特定的行版本。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-135">You can test whether a `DataRow` has a particular row version by calling the <xref:System.Data.DataRow.HasVersion%2A> method and passing a `DataRowVersion` as an argument.</span></span> <span data-ttu-id="fd9b1-136">例如，在调用 `DataRow.HasVersion(DataRowVersion.Original)` 之前，`false` 对新添加的行将返回 `AcceptChanges`。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-136">For example, `DataRow.HasVersion(DataRowVersion.Original)` will return `false` for newly added rows before `AcceptChanges` has been called.</span></span>  
  
 <span data-ttu-id="fd9b1-137">下面的代码示例演示表中所有已删除行中的值。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-137">The following code example displays the values in all the deleted rows of a table.</span></span> <span data-ttu-id="fd9b1-138">`Deleted` 行没有 `Current` 行版本，因此在访问列值时必须传递 `DataRowVersion.Original`。</span><span class="sxs-lookup"><span data-stu-id="fd9b1-138">`Deleted` rows do not have a `Current` row version, so you must pass `DataRowVersion.Original` when accessing the column values.</span></span>  
  
```vb  
Dim catTable As DataTable = catDS.Tables("Categories")  
  
Dim delRows() As DataRow = catTable.Select(Nothing, Nothing, DataViewRowState.Deleted)  
  
Console.WriteLine("Deleted rows:" & vbCrLf)  
  
Dim catCol As DataColumn  
Dim delRow As DataRow  
  
For Each catCol In catTable.Columns  
  Console.Write(catCol.ColumnName & vbTab)  
Next  
Console.WriteLine()  
  
For Each delRow In delRows  
  For Each catCol In catTable.Columns  
    Console.Write(delRow(catCol, DataRowVersion.Original) & vbTab)  
  Next  
  Console.WriteLine()  
Next  
```  
  
```csharp  
DataTable catTable = catDS.Tables["Categories"];  
  
DataRow[] delRows = catTable.Select(null, null, DataViewRowState.Deleted);  
  
Console.WriteLine("Deleted rows:\n");  
  
foreach (DataColumn catCol in catTable.Columns)  
  Console.Write(catCol.ColumnName + "\t");  
Console.WriteLine();  
  
foreach (DataRow delRow in delRows)  
{  
  foreach (DataColumn catCol in catTable.Columns)  
    Console.Write(delRow[catCol, DataRowVersion.Original] + "\t");  
  Console.WriteLine();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="fd9b1-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd9b1-139">See Also</span></span>  
 [<span data-ttu-id="fd9b1-140">操作数据表中的数据</span><span class="sxs-lookup"><span data-stu-id="fd9b1-140">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="fd9b1-141">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="fd9b1-141">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="fd9b1-142">DataAdapters 和 DataReaders</span><span class="sxs-lookup"><span data-stu-id="fd9b1-142">DataAdapters and DataReaders</span></span>](../../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="fd9b1-143">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="fd9b1-143">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
