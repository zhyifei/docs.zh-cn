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
# <a name="copying-dataset-contents"></a>复制数据集内容
您可以创建 from 的副本<xref:System.Data.DataSet>，以便可以在不影响原始数据的情况下处理数据，或者处理**DataSet**中数据的子集。 复制**数据集**时，您可以：  
  
- 创建**DataSet**的确切副本 ，包括架构、数据、行状态信息和行版本。  
  
- 创建包含现有 DataSet 的架构，但仅包含已修改的行**的 DataSet。** **DataSet** 您可以返回已修改的所有行，或指定特定的**DataRowState**。 有关行状态的详细信息，请参阅[行状态和行版本](row-states-and-row-versions.md)。  
  
- 仅复制**DataSet**的架构或关系结构，而不复制任何行。 可以使用 <xref:System.Data.DataTable> 将行导入现有 <xref:System.Data.DataTable.ImportRow%2A>。  
  
 要创建包含架构和数据的数据**集**的精确副本，<xref:System.Data.DataSet.Copy%2A>请使用**DataSet**的方法。 以下代码示例演示如何创建**DataSet**的确切副本。  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 要创建**包含**架构且仅表示**已添加**、**已修改**或**已删除**行的数据集的副本，请使用<xref:System.Data.DataSet.GetChanges%2A>**DataSet**的方法。 您还可以使用**GetChanges**在调用**GetChanges**时传递**DataRowState**值，仅返回具有指定行状态的行。 以下代码示例演示如何在调用**GetChanges**时传递**DataRowState。**  
  
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
  
 要创建仅包含架构**的 DataSet**的副本，<xref:System.Data.DataSet.Clone%2A>请使用**DataSet**的方法。 您还可以使用**DataTable**的**ImportRow**方法将现有行添加到克隆**的数据集**。 **ImportRow**将数据、行状态和行版本信息添加到指定的表。 只有当列名称匹配且数据类型兼容时，才会添加列值。  
  
 以下代码示例创建**DataSet**的克隆，然后将原始**DataSet**中的行添加到**DataSet**克隆中的 **"客户"** 表中，客户**国家区域**列的值为"德国"。  
  
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
  
## <a name="see-also"></a>另请参阅

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [数据集、数据表和数据视图](index.md)
- [ADO.NET 概述](../ado-net-overview.md)
