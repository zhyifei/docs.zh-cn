---
title: "对数据进行排序和筛选"
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
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 2411307623c714ae521d00dcffca05d3569a656e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="sorting-and-filtering-data"></a>对数据进行排序和筛选
<xref:System.Data.DataView> 为在 <xref:System.Data.DataTable> 中对数据排序和筛选提供了多种方法：  
  
-   可以使用 <xref:System.Data.DataView.Sort%2A> 属性指定单个或多个列排序顺序并包含 ASC（升序）和 DESC（降序）参数。  
  
-   可以使用 <xref:System.Data.DataView.ApplyDefaultSort%2A> 属性自动以升序创建基于表的一个或多个主键列的排序顺序。 <xref:System.Data.DataView.ApplyDefaultSort%2A>时，才适用**排序**属性为空引用或空字符串，并且在表已定义主键。  
  
-   可以使用 <xref:System.Data.DataView.RowFilter%2A> 属性根据行的列值来指定行的子集。 有关有效表达式的详细信息**RowFilter**属性，请参阅的引用信息<xref:System.Data.DataColumn.Expression%2A>属性<xref:System.Data.DataColumn>类。  
  
     如果你想要返回的数据，而不是提供的数据子集的动态视图上的特定查询结果，请使用<xref:System.Data.DataView.Find%2A>或<xref:System.Data.DataView.FindRows%2A>方法**DataView**以获得最佳性能而不是设置**RowFilter**属性。 设置**RowFilter**属性会重新生成数据，将添加到你的应用程序的系统开销并降低性能的索引。 **RowFilter**属性最适合用于数据绑定应用程序绑定的控件显示筛选的结果的位置。 **查找**和**FindRows**方法而无需重新生成索引利用当前的索引。 有关详细信息**查找**和**FindRows**方法，请参阅[查找行](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)。  
  
-   可以使用 <xref:System.Data.DataView.RowStateFilter%2A> 属性指定要查看的行版本。 **DataView**隐式地管理要公开具体取决于哪个行版本**RowState**基础行。 例如，如果**RowStateFilter**设置为**DataViewRowState.Deleted**、 **DataView**公开**原始**行版本所有**已删除**在于，存在的行没有**当前**行版本。 你可以确定通过公开任何行的哪个行版本**RowVersion**属性**DataRowView**。  
  
     下表显示的选项**DataViewRowState**。  
  
    |DataViewRowState 选项|描述|  
    |------------------------------|-----------------|  
    |**CurrentRows**|**当前**的所有行版本**Unchanged**， **Added**，和**已修改**行。 这是默认设置。|  
    |**添加**|**当前**的所有行版本**Added**行。|  
    |**删除**|**原始**的所有行版本**已删除**行。|  
    |**ModifiedCurrent**|**当前**的所有行版本**已修改**行。|  
    |**ModifiedOriginal**|**原始**的所有行版本**已修改**行。|  
    |**无**|没有行。|  
    |**OriginalRows**|**原始**的所有行版本**Unchanged**，**已修改**，和**已删除**行。|  
    |**保持不变**|**当前**的所有行版本**Unchanged**行。|  
  
 有关行状态和行版本的详细信息，请参阅[行状态和行版本](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)。  
  
 以下代码示例创建一个视图，该视图显示所有库存量小于或等于再订购量的产品，这些产品首先按供应商 ID 排序，然后按产品名称排序。  
  
```vb  
Dim prodView As DataView = New DataView(prodDS.Tables("Products"), _  
   "UnitsInStock <= ReorderLevel", _  
   "SupplierID, ProductName", _  
   DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView prodView = new DataView(prodDS.Tables["Products"],  
   "UnitsInStock <= ReorderLevel",  
   "SupplierID, ProductName",  
   DataViewRowState.CurrentRows);  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Data.DataViewRowState>  
 <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [数据视图](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
