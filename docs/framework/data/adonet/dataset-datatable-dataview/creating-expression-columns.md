---
title: "创建表达式列"
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
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: c1b0b7be8be6bec0c5a8850029bd3336d107f0a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="creating-expression-columns"></a>创建表达式列
您可以为列定义表达式，让它能够包含根据同一行中其他列值或根据表中多行的列值计算而得的值。 要定义要计算的表达式，可使用目标列的 <xref:System.Data.DataColumn.Expression%2A> 属性，并使用 <xref:System.Data.DataColumn.ColumnName%2A> 属性在表达式中引用其他列。 用于表达式列的 <xref:System.Data.DataColumn.DataType%2A> 必须适合于表达式将返回的值。  
  
 下表列出了表中表达式列的几种可能用法。  
  
|表达式类型|示例|  
|---------------------|-------------|  
|比较|"Total >= 500"|  
|计算|"UnitPrice * Quantity"|  
|聚合|Sum(Price)|  
  
 你可以设置**表达式**在现有的属性**DataColumn**对象，也可以将该属性用作第三个自变量传递给<xref:System.Data.DataColumn>构造函数，如下面的示例中所示。  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 表达式可以引用其他表达式列，但循环引用（其中两个表达式相互引用）将产生异常。 有关编写表达式的规则，请参阅<xref:System.Data.DataColumn.Expression%2A>属性**DataColumn**类。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Data.DataColumn>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [数据表架构定义](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [数据表](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
