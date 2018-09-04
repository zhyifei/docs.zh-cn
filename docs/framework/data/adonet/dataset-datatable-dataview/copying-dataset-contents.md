---
title: 复制数据集内容
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: b85fb6ebf56b110330be121c87d2492b0cfac536
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43535367"
---
# <a name="copying-dataset-contents"></a><span data-ttu-id="21f16-102">复制数据集内容</span><span class="sxs-lookup"><span data-stu-id="21f16-102">Copying DataSet Contents</span></span>
<span data-ttu-id="21f16-103">可以创建一份<xref:System.Data.DataSet>，以便可以处理的数据，而不会影响原始数据，或处理中的数据的子集**数据集**。</span><span class="sxs-lookup"><span data-stu-id="21f16-103">You can create a copy of a <xref:System.Data.DataSet> so that you can work with data without affecting the original data, or work with a subset of the data from a **DataSet**.</span></span> <span data-ttu-id="21f16-104">复制时**数据集**，你可以：</span><span class="sxs-lookup"><span data-stu-id="21f16-104">When copying a **DataSet**, you can:</span></span>  
  
-   <span data-ttu-id="21f16-105">创建的一个精确副本**数据集**，包括架构、 数据、 行状态信息和行版本。</span><span class="sxs-lookup"><span data-stu-id="21f16-105">Create an exact copy of the **DataSet**, including the schema, data, row state information, and row versions.</span></span>  
  
-   <span data-ttu-id="21f16-106">创建**数据集**，其中包含对现有的架构**数据集**，但已被修改的行。</span><span class="sxs-lookup"><span data-stu-id="21f16-106">Create a **DataSet** that contains the schema of an existing **DataSet**, but only rows that have been modified.</span></span> <span data-ttu-id="21f16-107">可以返回已修改的所有行，也可以指定特定**DataRowState**。</span><span class="sxs-lookup"><span data-stu-id="21f16-107">You can return all rows that have been modified, or specify a specific **DataRowState**.</span></span> <span data-ttu-id="21f16-108">有关行状态的详细信息，请参阅[行状态和行版本](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)。</span><span class="sxs-lookup"><span data-stu-id="21f16-108">For more information about row states, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
-   <span data-ttu-id="21f16-109">复制的架构，即关系结构**数据集**仅，而不复制任何行。</span><span class="sxs-lookup"><span data-stu-id="21f16-109">Copy the schema, or relational structure, of the **DataSet** only, without copying any rows.</span></span> <span data-ttu-id="21f16-110">可以使用 <xref:System.Data.DataTable> 将行导入现有 <xref:System.Data.DataTable.ImportRow%2A>。</span><span class="sxs-lookup"><span data-stu-id="21f16-110">Rows can be imported into an existing <xref:System.Data.DataTable> using <xref:System.Data.DataTable.ImportRow%2A>.</span></span>  
  
 <span data-ttu-id="21f16-111">若要创建的一个精确副本**数据集**其中包括架构和数据，请使用<xref:System.Data.DataSet.Copy%2A>方法**数据集**。</span><span class="sxs-lookup"><span data-stu-id="21f16-111">To create an exact copy of the **DataSet** that includes both schema and data, use the <xref:System.Data.DataSet.Copy%2A> method of the **DataSet**.</span></span> <span data-ttu-id="21f16-112">下面的代码示例演示如何创建完全相同的副本**数据集**。</span><span class="sxs-lookup"><span data-stu-id="21f16-112">The following code example shows how to create an exact copy of the **DataSet**.</span></span>  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 <span data-ttu-id="21f16-113">若要创建一份**数据集**其中包括架构和仅数据表示**Added**， **Modified**，或**已删除**行，请使用<xref:System.Data.DataSet.GetChanges%2A>方法**数据集**。</span><span class="sxs-lookup"><span data-stu-id="21f16-113">To create a copy of a **DataSet** that includes schema and only the data representing **Added**, **Modified**, or **Deleted** rows, use the <xref:System.Data.DataSet.GetChanges%2A> method of the **DataSet**.</span></span> <span data-ttu-id="21f16-114">此外可以使用**GetChanges**返回只有指定的行状态的行通过传递**DataRowState**值时调用**GetChanges**。</span><span class="sxs-lookup"><span data-stu-id="21f16-114">You can also use **GetChanges** to return only rows with a specified row state by passing a **DataRowState** value when calling **GetChanges**.</span></span> <span data-ttu-id="21f16-115">下面的代码示例演示如何传递**DataRowState**调用时**GetChanges**。</span><span class="sxs-lookup"><span data-stu-id="21f16-115">The following code example shows how to pass a **DataRowState** when calling **GetChanges**.</span></span>  
  
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
  
 <span data-ttu-id="21f16-116">若要创建一份**数据集**仅包含架构，请使用<xref:System.Data.DataSet.Clone%2A>方法**数据集**。</span><span class="sxs-lookup"><span data-stu-id="21f16-116">To create a copy of a **DataSet** that only includes schema, use the <xref:System.Data.DataSet.Clone%2A> method of the **DataSet**.</span></span> <span data-ttu-id="21f16-117">此外可以将现有行添加到克隆**数据集**使用**ImportRow**方法**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="21f16-117">You can also add existing rows to the cloned **DataSet** using the **ImportRow** method of the **DataTable**.</span></span> <span data-ttu-id="21f16-118">**ImportRow**将数据、 行状态和行版本信息添加到指定的表。</span><span class="sxs-lookup"><span data-stu-id="21f16-118">**ImportRow** adds data, row state, and row version information to the specified table.</span></span> <span data-ttu-id="21f16-119">只有当列名称匹配且数据类型兼容时，才会添加列值。</span><span class="sxs-lookup"><span data-stu-id="21f16-119">Column values are added only where the column name matches and the data type is compatible.</span></span>  
  
 <span data-ttu-id="21f16-120">下面的代码示例创建的克隆**数据集**然后将行添加从原始**数据集**到**客户**表中**数据集**克隆客户位置**国家 （地区)** 列具有"Germany"的值。</span><span class="sxs-lookup"><span data-stu-id="21f16-120">The following code example creates a clone of a **DataSet** and then adds the rows from the original **DataSet** to the **Customers** table in the **DataSet** clone for customers where the **CountryRegion** column has the value "Germany".</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="21f16-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="21f16-121">See Also</span></span>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="21f16-122">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="21f16-122">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="21f16-123">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="21f16-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
