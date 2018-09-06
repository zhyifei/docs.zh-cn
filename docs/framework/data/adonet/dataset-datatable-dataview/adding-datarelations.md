---
title: 添加 DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: d0f481979ead7af775d462a2624ec43080e2c5a9
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43749952"
---
# <a name="adding-datarelations"></a>添加 DataRelation
在包含多个 <xref:System.Data.DataSet> 对象的 <xref:System.Data.DataTable> 中，可以使用 <xref:System.Data.DataRelation> 对象来使一个表与另一个表相关，在多个表之间导航，以及从相关表中返回子行或父行。  
  
 若要创建所需的参数**DataRelation**是一个名为**DataRelation**正在创建和的一个或多个数组<xref:System.Data.DataColumn>对用作父和子列的引用关系中的列。 创建后**DataRelation**，表之间导航和检索值，可以使用它。  
  
 添加**DataRelation**到<xref:System.Data.DataSet>道，默认情况下，通过<xref:System.Data.UniqueConstraint>到父表和一个<xref:System.Data.ForeignKeyConstraint>表到子表。 有关这些默认约束的详细信息，请参阅[数据表约束](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)。  
  
 下面的代码示例将创建**DataRelation**使用两个<xref:System.Data.DataTable>中的对象<xref:System.Data.DataSet>。 每个<xref:System.Data.DataTable>包含名为的列**CustID**，它可作为这两者之间的链接<xref:System.Data.DataTable>对象。 该示例将添加单个**DataRelation**到**关系**的集合<xref:System.Data.DataSet>。 在示例中的第一个参数指定的名称**DataRelation**正在创建。 第二个参数设置父级**DataColumn**和第三个参数设置子**DataColumn**。  
  
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
  
 一个**DataRelation**还有**嵌套**属性，如果设置为**true**，导致从嵌套在父表中的相关行的子表的行作为使用的 XML 元素写入时<xref:System.Data.DataSet.WriteXml%2A>。 有关详细信息，请参阅[在数据集中使用 XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)。  
  
## <a name="see-also"></a>请参阅  
 [数据集、数据表和数据视图](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](https://go.microsoft.com/fwlink/?LinkId=217917)
