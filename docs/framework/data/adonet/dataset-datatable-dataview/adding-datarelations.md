---
title: 添加 DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: fde1e2ace09e31234d199876ae7f063e01e7a7e4
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203979"
---
# <a name="adding-datarelations"></a>添加 DataRelation
在包含多个 <xref:System.Data.DataSet> 对象的 <xref:System.Data.DataTable> 中，可以使用 <xref:System.Data.DataRelation> 对象来使一个表与另一个表相关，在多个表之间导航，以及从相关表中返回子行或父行。  
  
 创建**datarelation**所需的参数是要创建的**datarelation**的名称以及对用作关系中父列和子列<xref:System.Data.DataColumn>的列的一个或多个引用的数组。 创建**DataRelation**后, 可以使用它在表之间导航和检索值。  
  
 默认<xref:System.Data.DataSet> <xref:System.Data.ForeignKeyConstraint> 情况下,将DataRelation添加到将向父表和子表<xref:System.Data.UniqueConstraint>添加。 有关这些默认约束的详细信息, 请参阅[DataTable 约束](datatable-constraints.md)。  
  
 下面的代码示例使用中的<xref:System.Data.DataSet>两个<xref:System.Data.DataTable>对象创建**DataRelation** 。 每<xref:System.Data.DataTable>个都包含一个名为**CustID**的列, 它用作两个<xref:System.Data.DataTable>对象之间的链接。 该示例将一个**DataRelation**添加到<xref:System.Data.DataSet>的**关系**集合。 该示例中的第一个参数指定所创建的**DataRelation**的名称。 第二个参数设置父**datacolumn** , 第三个参数设置子**datacolumn**。  
  
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
  
 **DataRelation**还具有一个**嵌套**属性, 当设置为**true**时, 将导致子表中的行嵌套在使用<xref:System.Data.DataSet.WriteXml%2A>编写为 XML 元素的父表中的关联行内。 有关详细信息，请参阅[在数据集中使用 XML](using-xml-in-a-dataset.md)。  
  
## <a name="see-also"></a>请参阅

- [数据集、数据表和数据视图](index.md)
- [ADO.NET 托管提供程序和数据集开发人员中心](https://go.microsoft.com/fwlink/?LinkId=217917)
