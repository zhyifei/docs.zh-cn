---
title: 创建数据视图
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 9d21b17068ff3ce5b0bd3990144383d7f9ded2f9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151333"
---
# <a name="creating-a-dataview"></a>创建数据视图
创建 <xref:System.Data.DataView> 的方法有两种。 您可以使用**DataView**构造函数，也可以创建对<xref:System.Data.DataTable.DefaultView%2A>属性<xref:System.Data.DataTable>的引用。 **DataView**构造函数可以是空的，也可以将**DataTable**作为单个参数，也可以将 DataTable 以及筛选器条件、排序条件和行状态筛选器视为 **"DataTable"。** 有关可用于**DataView**的其他参数的详细信息，请参阅[排序和筛选数据](sorting-and-filtering-data.md)。  
  
 由于**DataView**的索引是在创建**DataView**时构建的，并且当修改任何**排序**、**行筛选器**或**RowStateFilter**属性时，在创建**DataView**时，通过提供任何初始排序顺序或筛选条件作为构造函数参数来实现最佳性能。 创建**DataView**而不指定排序或筛选条件，然后设置**排序**、**行筛选器**或**RowStateFilter**属性，以后会导致索引至少生成两次：创建**DataView**时生成一次，在修改任何排序或筛选器属性时再次生成索引。  
  
 请注意，如果使用不采用任何参数的构造函数创建**DataView，** 则在设置**表**属性之前，您将无法使用**DataView。**  
  
 以下代码示例演示如何使用**DataView**构造函数创建**DataView。** 随**数据表**一起提供**行筛选器**、**排序**列和**DataViewRowState。**  
  
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
  
 以下代码示例演示如何使用表的**DefaultView**属性获取对**DataTable**的默认**DataView**的引用。  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [DataView](dataviews.md)
- [对数据进行排序和筛选](sorting-and-filtering-data.md)
- [DataTables](datatables.md)
- [ADO.NET 概述](../ado-net-overview.md)
