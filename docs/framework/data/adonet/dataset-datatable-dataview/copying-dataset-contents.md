---
title: 复制数据集内容
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: f60ef817773b6234b19856bfc0727eedb67e113e
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205172"
---
# <a name="copying-dataset-contents"></a>复制数据集内容
您可以创建的副本<xref:System.Data.DataSet> , 以便在不影响原始数据的情况下处理数据, 或使用数据**集中**的数据的子集。 复制**数据集**时, 可以:  
  
- 创建**数据集**的精确副本, 包括架构、数据、行状态信息和行版本。  
  
- 创建一个**数据集, 该数据集**包含现有**数据集**的架构, 而只包含已修改的行。 可以返回所有已修改的行, 也可以指定特定的**DataRowState**。 有关行状态的详细信息, 请参阅[行状态和行版本](row-states-and-row-versions.md)。  
  
- 仅复制**数据集**的架构或关系结构, 而不复制任何行。 可以使用 <xref:System.Data.DataTable> 将行导入现有 <xref:System.Data.DataTable.ImportRow%2A>。  
  
 若要创建包含架构和数据的**数据集**的完全相同的副本, 请<xref:System.Data.DataSet.Copy%2A>使用**dataset**的方法。 下面的代码示例演示如何创建**数据集**的精确副本。  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 若要创建包含架构的数据**集**的副本, 并且仅创建表示**已添加**、**已修改**或**已删除**行的<xref:System.Data.DataSet.GetChanges%2A>数据, 请使用**数据集**的方法。 调用**GetChanges**时, 还可以使用**GetChanges**来仅返回具有指定行状态的行 。 下面的代码示例演示如何在调用**GetChanges**时传递**DataRowState** 。  
  
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
  
 若要创建仅包含架构的**数据集**的副本, 请使用<xref:System.Data.DataSet.Clone%2A> **dataset**的方法。 还可以使用**DataTable**的**ImportRow**方法将现有行添加到克隆的**数据集**。 **ImportRow**将数据、行状态和行版本信息添加到指定的表中。 只有当列名称匹配且数据类型兼容时，才会添加列值。  
  
 下面的代码示例创建一个**数据集**的克隆, 然后将原始**数据集中**的行添加到 "国家/地区"克隆的 " **Customers** " 表中, 其中 "**国家/地区**" 列的值为 "德国".  
  
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
  
## <a name="see-also"></a>请参阅

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [数据集、数据表和数据视图](index.md)
- [ADO.NET 托管提供程序和数据集开发人员中心](https://go.microsoft.com/fwlink/?LinkId=217917)
