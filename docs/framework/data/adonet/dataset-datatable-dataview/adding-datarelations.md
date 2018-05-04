---
title: 添加 DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: 451ee0eee466efca86345ea7112e9b178a2c66e2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="adding-datarelations"></a>添加 DataRelation
在包含多个 <xref:System.Data.DataSet> 对象的 <xref:System.Data.DataTable> 中，可以使用 <xref:System.Data.DataRelation> 对象来使一个表与另一个表相关，在多个表之间导航，以及从相关表中返回子行或父行。  
  
 若要创建所需的参数**DataRelation**是一个名为**DataRelation**正在创建，并且一个或多个数组<xref:System.Data.DataColumn>对充当父和子列的引用对关系中的列。 创建后**DataRelation**，您可以使用它，表之间导航，并检索值。  
  
 添加**DataRelation**到<xref:System.Data.DataSet>添加时，默认情况下，<xref:System.Data.UniqueConstraint>到父表和<xref:System.Data.ForeignKeyConstraint>到子表。 有关这些默认约束的详细信息，请参阅[数据表约束](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)。  
  
 下面的代码示例创建**DataRelation**使用两个<xref:System.Data.DataTable>中的对象<xref:System.Data.DataSet>。 每个<xref:System.Data.DataTable>包含一个名为列**CustID**，它用作这两者之间的链接<xref:System.Data.DataTable>对象。 该示例将添加一个**DataRelation**到**关系**集合<xref:System.Data.DataSet>。 在示例中的第一个参数指定的名称**DataRelation**正在创建。 第二个参数设置父**DataColumn** ，第三个参数设置子**DataColumn**。  
  
```vb  
customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustID"), _  
  customerOrders.Tables("Orders").Columns("CustID"))  
```  
  
```csharp  
customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustID"],  
  customerOrders.Tables["Orders"].Columns["CustID"]);  
```  
  
 A **DataRelation**还有**嵌套**属性，当设置为**true**，使行从子表嵌套在来自父表的关联行在使用的 XML 元素作为写入时<xref:System.Data.DataSet.WriteXml%2A>。 有关详细信息，请参阅[在数据集中使用 XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)。  
  
## <a name="see-also"></a>请参阅  
 [数据集、数据表和数据视图](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
