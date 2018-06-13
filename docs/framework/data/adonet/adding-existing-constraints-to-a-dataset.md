---
title: 将现有约束添加到数据集
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
ms.openlocfilehash: c3c28392a9e4bee0e2f9e0dcf553e13b67c378dd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758352"
---
# <a name="adding-existing-constraints-to-a-dataset"></a>将现有约束添加到数据集
**填充**方法**DataAdapter**填充<xref:System.Data.DataSet>只与表中的列和行从数据源; 但约束通常由设置数据源，**填充**方法不会添加到此架构信息**数据集**默认情况下。 若要填充**数据集**与现有主键约束信息从数据源，可以通过调用**FillSchema**方法**DataAdapter**，或设置**MissingSchemaAction**属性**DataAdapter**到**AddWithKey**之前调用**填充**。 这将确保该主键约束中的**数据集**反映数据源。 外键约束信息不包括，并且必须显式中所示创建[数据表约束](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)。  
  
 添加到的架构信息**数据集**使用数据填充它可确保中附带了主键约束之前<xref:System.Data.DataTable>中的对象**数据集**。 因此，当再次调用来填充**数据集**进行时，主键列信息用于匹配数据源的新行，和在每个当前行的**DataTable**，和中的当前数据数据源中的数据覆盖表。 如果没有架构信息中，来自数据源的新行将追加到**数据集**，这会导致重复的行中。  
  
> [!NOTE]
>  如果数据源中的列被标识为自动递增， **FillSchema**方法，或**填充**方法替换**MissingSchemaAction**的**AddWithKey**，创建**DataColumn**与**AutoIncrement**属性设置为`true`。 但是，你将需要设置**AutoIncrementStep**和**AutoIncrementSeed**值。 有关自动递增列的详细信息，请参阅[创建 AutoIncrement 列](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md)。  
  
 使用**FillSchema**或设置**MissingSchemaAction**到**AddWithKey**需要额外的处理，在数据源来确定主键列信息。 这一额外的处理可能会降低性能。 如果主键信息在设计时已知，为了实现最佳性能，建议显式指定一个或多个主键列。 有关显式设置表的主键信息的信息，请参阅[定义主键](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md)。  
  
 下面的代码示例演示如何添加到的架构信息**数据集**使用**FillSchema**。  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers")  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers");  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
 下面的代码示例演示如何添加到的架构信息**数据集**使用**MissingSchemaAction.AddWithKey**属性**填充**方法。  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
## <a name="handling-multiple-result-sets"></a>处理多个结果集  
 如果**DataAdapter**遇到从返回的多个结果集**SelectCommand**，它将创建多个表中的**数据集**。 这些表将提供的从零开始递增的默认名称**表** *N*，第一页为**表**而不是"Table0"。 如果作为参数传递表名称**FillSchema**方法，这些表将会提供的从零开始的递增的名称**TableName** *N*，第一页为**TableName**而不是从"tablename0"开始。  
  
> [!NOTE]
>  如果**FillSchema**方法**OleDbDataAdapter**对象称为返回多个结果集的命令，则返回的架构信息将从第一个结果集。 当过程返回多个结果的架构信息集使用**OleDbDataAdapter**，建议您指定**MissingSchemaAction**的**AddWithKey**并在调用时获取架构信息**填充**方法。  
  
## <a name="see-also"></a>请参阅  
 [DataAdapters 和 DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [数据集、数据表和数据视图](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [在 ADO.NET 中检索和修改数据](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
