---
title: 复制数据集内容
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: de13e07eb5c19b8beffa724fec4a128c418a4fed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151359"
---
# <a name="copying-dataset-contents"></a><span data-ttu-id="b5b79-102">复制数据集内容</span><span class="sxs-lookup"><span data-stu-id="b5b79-102">Copying DataSet Contents</span></span>
<span data-ttu-id="b5b79-103">您可以创建 from 的副本<xref:System.Data.DataSet>，以便可以在不影响原始数据的情况下处理数据，或者处理**DataSet**中数据的子集。</span><span class="sxs-lookup"><span data-stu-id="b5b79-103">You can create a copy of a <xref:System.Data.DataSet> so that you can work with data without affecting the original data, or work with a subset of the data from a **DataSet**.</span></span> <span data-ttu-id="b5b79-104">复制**数据集**时，您可以：</span><span class="sxs-lookup"><span data-stu-id="b5b79-104">When copying a **DataSet**, you can:</span></span>  
  
- <span data-ttu-id="b5b79-105">创建**DataSet**的确切副本 ，包括架构、数据、行状态信息和行版本。</span><span class="sxs-lookup"><span data-stu-id="b5b79-105">Create an exact copy of the **DataSet**, including the schema, data, row state information, and row versions.</span></span>  
  
- <span data-ttu-id="b5b79-106">创建包含现有 DataSet 的架构，但仅包含已修改的行**的 DataSet。** **DataSet**</span><span class="sxs-lookup"><span data-stu-id="b5b79-106">Create a **DataSet** that contains the schema of an existing **DataSet**, but only rows that have been modified.</span></span> <span data-ttu-id="b5b79-107">您可以返回已修改的所有行，或指定特定的**DataRowState**。</span><span class="sxs-lookup"><span data-stu-id="b5b79-107">You can return all rows that have been modified, or specify a specific **DataRowState**.</span></span> <span data-ttu-id="b5b79-108">有关行状态的详细信息，请参阅[行状态和行版本](row-states-and-row-versions.md)。</span><span class="sxs-lookup"><span data-stu-id="b5b79-108">For more information about row states, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
- <span data-ttu-id="b5b79-109">仅复制**DataSet**的架构或关系结构，而不复制任何行。</span><span class="sxs-lookup"><span data-stu-id="b5b79-109">Copy the schema, or relational structure, of the **DataSet** only, without copying any rows.</span></span> <span data-ttu-id="b5b79-110">可以使用 <xref:System.Data.DataTable> 将行导入现有 <xref:System.Data.DataTable.ImportRow%2A>。</span><span class="sxs-lookup"><span data-stu-id="b5b79-110">Rows can be imported into an existing <xref:System.Data.DataTable> using <xref:System.Data.DataTable.ImportRow%2A>.</span></span>  
  
 <span data-ttu-id="b5b79-111">要创建包含架构和数据的数据**集**的精确副本，<xref:System.Data.DataSet.Copy%2A>请使用**DataSet**的方法。</span><span class="sxs-lookup"><span data-stu-id="b5b79-111">To create an exact copy of the **DataSet** that includes both schema and data, use the <xref:System.Data.DataSet.Copy%2A> method of the **DataSet**.</span></span> <span data-ttu-id="b5b79-112">以下代码示例演示如何创建**DataSet**的确切副本。</span><span class="sxs-lookup"><span data-stu-id="b5b79-112">The following code example shows how to create an exact copy of the **DataSet**.</span></span>  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 <span data-ttu-id="b5b79-113">要创建**包含**架构且仅表示**已添加**、**已修改**或**已删除**行的数据集的副本，请使用<xref:System.Data.DataSet.GetChanges%2A>**DataSet**的方法。</span><span class="sxs-lookup"><span data-stu-id="b5b79-113">To create a copy of a **DataSet** that includes schema and only the data representing **Added**, **Modified**, or **Deleted** rows, use the <xref:System.Data.DataSet.GetChanges%2A> method of the **DataSet**.</span></span> <span data-ttu-id="b5b79-114">您还可以使用**GetChanges**在调用**GetChanges**时传递**DataRowState**值，仅返回具有指定行状态的行。</span><span class="sxs-lookup"><span data-stu-id="b5b79-114">You can also use **GetChanges** to return only rows with a specified row state by passing a **DataRowState** value when calling **GetChanges**.</span></span> <span data-ttu-id="b5b79-115">以下代码示例演示如何在调用**GetChanges**时传递**DataRowState。**</span><span class="sxs-lookup"><span data-stu-id="b5b79-115">The following code example shows how to pass a **DataRowState** when calling **GetChanges**.</span></span>  
  
```vb  
' Copy all changes.  
Dim changeDataSet As DataSet = customerDataSet.GetChanges()  
' Copy only new rows.  
Dim addedDataSetAs DataSet = _  
    customerDataSet.GetChanges(DataRowState.Added)  
```  
  
```csharp  
// Copy all changes.  
DataSet changeDataSet = customerDataSet.GetChanges();  
// Copy only new rows.  
DataSet addedDataSet= customerDataSet.GetChanges(DataRowState.Added);  
```  
  
 <span data-ttu-id="b5b79-116">要创建仅包含架构**的 DataSet**的副本，<xref:System.Data.DataSet.Clone%2A>请使用**DataSet**的方法。</span><span class="sxs-lookup"><span data-stu-id="b5b79-116">To create a copy of a **DataSet** that only includes schema, use the <xref:System.Data.DataSet.Clone%2A> method of the **DataSet**.</span></span> <span data-ttu-id="b5b79-117">您还可以使用**DataTable**的**ImportRow**方法将现有行添加到克隆**的数据集**。</span><span class="sxs-lookup"><span data-stu-id="b5b79-117">You can also add existing rows to the cloned **DataSet** using the **ImportRow** method of the **DataTable**.</span></span> <span data-ttu-id="b5b79-118">**ImportRow**将数据、行状态和行版本信息添加到指定的表。</span><span class="sxs-lookup"><span data-stu-id="b5b79-118">**ImportRow** adds data, row state, and row version information to the specified table.</span></span> <span data-ttu-id="b5b79-119">只有当列名称匹配且数据类型兼容时，才会添加列值。</span><span class="sxs-lookup"><span data-stu-id="b5b79-119">Column values are added only where the column name matches and the data type is compatible.</span></span>  
  
 <span data-ttu-id="b5b79-120">以下代码示例创建**DataSet**的克隆，然后将原始**DataSet**中的行添加到**DataSet**克隆中的 **"客户"** 表中，客户**国家区域**列的值为"德国"。</span><span class="sxs-lookup"><span data-stu-id="b5b79-120">The following code example creates a clone of a **DataSet** and then adds the rows from the original **DataSet** to the **Customers** table in the **DataSet** clone for customers where the **CountryRegion** column has the value "Germany".</span></span>  
  
```vb  
Dim customerDataSet As New DataSet  
        customerDataSet.Tables.Add(New DataTable("Customers"))  
        customerDataSet.Tables("Customers").Columns.Add("Name", GetType(String))  
        customerDataSet.Tables("Customers").Columns.Add("CountryRegion", GetType(String))  
        customerDataSet.Tables("Customers").Rows.Add("Juan", "Spain")  
        customerDataSet.Tables("Customers").Rows.Add("Johann", "Germany")  
        customerDataSet.Tables("Customers").Rows.Add("John", "UK")  
  
Dim germanyCustomers As DataSet = customerDataSet.Clone()  
  
Dim copyRows() As DataRow = _  
  customerDataSet.Tables("Customers").Select("CountryRegion = 'Germany'")  
  
Dim customerTable As DataTable = germanyCustomers.Tables("Customers")  
Dim copyRow As DataRow  
  
For Each copyRow In copyRows  
  customerTable.ImportRow(copyRow)  
Next  
```  
  
```csharp  
DataSet customerDataSet = new DataSet();  
customerDataSet.Tables.Add(new DataTable("Customers"));  
customerDataSet.Tables["Customers"].Columns.Add("Name", typeof(string));  
customerDataSet.Tables["Customers"].Columns.Add("CountryRegion", typeof(string));  
customerDataSet.Tables["Customers"].Rows.Add("Juan", "Spain");  
customerDataSet.Tables["Customers"].Rows.Add("Johann", "Germany");  
customerDataSet.Tables["Customers"].Rows.Add("John", "UK");  
  
DataSet germanyCustomers = customerDataSet.Clone();  
  
DataRow[] copyRows =
  customerDataSet.Tables["Customers"].Select("CountryRegion = 'Germany'");  
  
DataTable customerTable = germanyCustomers.Tables["Customers"];  
  
foreach (DataRow copyRow in copyRows)  
  customerTable.ImportRow(copyRow);  
```  
  
## <a name="see-also"></a><span data-ttu-id="b5b79-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5b79-121">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="b5b79-122">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="b5b79-122">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="b5b79-123">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="b5b79-123">ADO.NET Overview</span></span>](../ado-net-overview.md)
