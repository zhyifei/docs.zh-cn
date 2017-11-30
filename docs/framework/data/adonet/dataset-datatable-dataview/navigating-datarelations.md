---
title: "导航 DataRelation"
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
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 5b90b58595c86fc3c4dcaf7fd453c517d6f14904
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="navigating-datarelations"></a>导航 DataRelation
<xref:System.Data.DataRelation> 的一项主要功能就是在 <xref:System.Data.DataTable> 中从一个 <xref:System.Data.DataSet> 浏览到另一个。 这允许您检索所有相关<xref:System.Data.DataRow>中一个对象**DataTable**在给定单个**DataRow**从相关**DataTable**。 例如，在建立后**DataRelation**之间客户表和订单表，你可以检索特定客户行使用的所有订单行**GetChildRows**。  
  
 下面的代码示例创建**DataRelation**之间**客户**表和**订单**表**数据集**并返回每个客户的所有订单。  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 下一示例以上例为基础，将四个表关联在一起，并浏览这些关系。 与前面的示例中， **CustomerID**相关**客户**表**订单**表。 对于中的每个客户**客户**表中的所有子行**订单**确定都表，以返回特定客户的订单数以及它们**OrderID**值。  
  
 该扩展的示例还返回的值从**OrderDetails**和**产品**表。 **订单**与相关表**OrderDetails**表使用**OrderID**以确定每个客户订单的产品及数量已经排序。 因为**OrderDetails**表仅包含**ProductID**已订购产品， **OrderDetails**与相关**产品**使用**ProductID**为了返回**ProductName**。 在这一关系，**产品**表为父表和**订单详细信息**表为子表。 因此，当循环访问**OrderDetails**表， **GetParentRow**调用来检索相关**ProductName**值。  
  
 请注意，当**DataRelation**为创建**客户**和**订单**表，为指定任何值**createConstraints**标志 (默认值是**true**)。 此操作假定所有中的行**订单**表具有**CustomerID**存在的父代中的值**客户**表。 如果**CustomerID**中存在**订单**中不存在的表**客户**表，<xref:System.Data.ForeignKeyConstraint>导致引发异常。  
  
 如果子列可能包含父列不包含的值，设置**createConstraints**标志切换为**false**添加时**DataRelation**。 在示例中， **createConstraints**标志设置为**false**为**DataRelation**之间**订单**表和**OrderDetails**表。 这使应用程序返回中的所有记录**OrderDetails**表和仅从记录的子集**订单**表而不会产生运行时异常。 该扩展示例生成以下格式的输出。  
  
```  
Customer ID: NORTS  
  Order ID: 10517  
        Order Date: 4/24/1997 12:00:00 AM  
           Product: Filo Mix  
          Quantity: 6  
           Product: Raclette Courdavault  
          Quantity: 4  
           Product: Outback Lager  
          Quantity: 6  
  Order ID: 11057  
        Order Date: 4/29/1998 12:00:00 AM  
           Product: Outback Lager  
          Quantity: 3  
```  
  
 下面的代码示例是展开的示例其中的值从**OrderDetails**和**产品**返回表，其中仅中记录的子集有**订单**所返回的表。  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## <a name="see-also"></a>另请参阅  
 [数据集、数据表和数据视图](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
