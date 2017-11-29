---
title: "创建数据视图"
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
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 28a2f6f299d2f904dc3f842c0c778f30081240b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="creating-a-dataview"></a>创建数据视图
创建 <xref:System.Data.DataView> 的方法有两种。 你可以使用**DataView**构造函数，也可以创建对引用<xref:System.Data.DataTable.DefaultView%2A>属性<xref:System.Data.DataTable>。 **DataView**构造函数可以为空，或它可以采用**DataTable**作为单个参数，或**DataTable**与筛选条件、 排序条件和行状态筛选器。 有关用于与一起使用的其他参数的详细信息**DataView**，请参阅[排序和筛选数据](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)。  
  
 因为索引**DataView**这两个时，会生成**DataView**创建后，和任何**排序**， **RowFilter**，或**RowStateFilter**属性将被修改，通过提供任何初始排序顺序或筛选条件作为构造函数自变量，在创建时获得最佳性能**DataView**。 创建**DataView**而无需指定排序或筛选条件，然后设置**排序**， **RowFilter**，或**RowStateFilter**属性更高版本使索引生成至少两次： 一次时**DataView**创建后，并且任何排序或筛选器属性再次进行修改时。  
  
 请注意，如果你创建**DataView**使用不采用任何参数的构造函数，你将不能使用**DataView**设置之前**表**属性.  
  
 下面的代码示例演示如何创建**DataView**使用**DataView**构造函数。 A **RowFilter**，**排序**列中，和**DataViewRowState**连同提供**DataTable**。  
  
```vb  
Dim custDV As DataView = New DataView(custDS.Tables("Customers"), _  
    "Country = 'USA'", _  
    "ContactName", _  
    DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView custDV = new DataView(custDS.Tables["Customers"],   
    "Country = 'USA'",   
    "ContactName",   
    DataViewRowState.CurrentRows);  
```  
  
 下面的代码示例演示如何获取对默认值的引用**DataView**的**DataTable**使用**默认视图**的表的属性。  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [数据视图](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [排序和筛选数据](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 [数据表](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
