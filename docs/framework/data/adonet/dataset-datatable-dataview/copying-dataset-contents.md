---
title: "复制数据集内容"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 69709fea628e6cb1d10a23f29b60911ab07e1111
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="copying-dataset-contents"></a>复制数据集内容
你可以创建一份<xref:System.Data.DataSet>，以便可以处理的数据不会影响原始数据，或工作中的数据的子集**数据集**。 在复制**数据集**，你可以：  
  
-   创建的一个精确副本**数据集**，包括架构、 数据、 行状态信息和行版本。  
  
-   创建**数据集**是否包含现有架构**数据集**，但已修改的行。 可以返回已修改的所有行，也可以指定特定**DataRowState**。 有关行状态的详细信息，请参阅[行状态和行版本](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)。  
  
-   副本的架构，即关系结构**数据集**仅，而不复制任何行。 可以使用 <xref:System.Data.DataTable> 将行导入现有 <xref:System.Data.DataTable.ImportRow%2A>。  
  
 若要创建的一个精确副本**数据集**包含架构和数据的则使用<xref:System.Data.DataSet.Copy%2A>方法**数据集**。 下面的代码示例演示如何创建的一个精确副本**数据集**。  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 若要创建一份**数据集**，包含架构和仅数据表示**Added**，**已修改**，或**已删除**行，使用<xref:System.Data.DataSet.GetChanges%2A>方法**数据集**。 你还可以使用**GetChanges**来仅返回行具有指定的行状态通过传递**DataRowState**值调用时**GetChanges**。 下面的代码示例演示如何将传递**DataRowState**调用时**GetChanges**。  
  
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
  
 若要创建一份**数据集**，仅包含架构，使用<xref:System.Data.DataSet.Clone%2A>方法**数据集**。 此外可以将现有行添加到克隆**数据集**使用**ImportRow**方法**DataTable**。 **ImportRow**将数据、 行状态和行版本信息添加到指定的表。 只有当列名称匹配且数据类型兼容时，才会添加列值。  
  
 下面的代码示例创建的克隆**数据集**，然后将行添加与原始**数据集**到**客户**表中**数据集**客户的克隆其中**CountryRegion**列具有值"Germany"。  
  
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
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [数据集、数据表和数据视图](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
