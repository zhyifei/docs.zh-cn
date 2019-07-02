---
title: 查询数据集 (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: ec4ee345835294499f7ac9f665a9b79e2efc0f64
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504666"
---
# <a name="querying-datasets-linq-to-dataset"></a>查询数据集 (LINQ to DataSet)
用数据填充 <xref:System.Data.DataSet> 对象后，您可以开始查询该对象。 系统地阐明使用 LINQ to DataSet 查询是类似于使用[!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]对其他[!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-启用数据源。 但请记住，在对 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 对象使用 <xref:System.Data.DataSet> 查询时，所查询的是 <xref:System.Data.DataRow> 对象的枚举，而不是自定义类型的枚举。 这意味着可以在 <xref:System.Data.DataRow> 查询中使用 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 类的任意成员。 这允许您创建丰富而复杂的查询。  
  
 其他实现一样[!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]，可以在两个不同的窗体中的数据集查询中创建 LINQ： 查询表达式语法和基于方法的查询语法。 您可以使用查询表达式语法或基于方法的查询语法对 <xref:System.Data.DataSet> 中的单个表、对 <xref:System.Data.DataSet> 中的多个表或对类型化 <xref:System.Data.DataSet> 中的表执行查询。  
  
## <a name="in-this-section"></a>本节内容  
 [单表查询](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)  
 说明如何执行单表查询。  
  
 [跨表查询](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 说明如何执行交叉表查询。  
  
 [查询类型化数据集](../../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 说明如何查询类型化 <xref:System.Data.DataSet> 对象。  
  
## <a name="see-also"></a>请参阅

- [LINQ to DataSet 示例](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [将数据加载到数据集中](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
