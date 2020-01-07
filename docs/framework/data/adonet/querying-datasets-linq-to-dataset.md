---
title: 查询数据集 (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: bb64abcffdbbcd46dfb11b2564619c565e461436
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634776"
---
# <a name="querying-datasets-linq-to-dataset"></a>查询数据集 (LINQ to DataSet)
用数据填充 <xref:System.Data.DataSet> 对象后，您可以开始查询该对象。 使用 LINQ to DataSet 来构建查询类似于对其他启用 LINQ 的数据源使用语言集成查询（LINQ）。 但请记住，在对 <xref:System.Data.DataSet> 对象使用 LINQ 查询时，将查询 <xref:System.Data.DataRow> 对象的枚举，而不是自定义类型的枚举。 这意味着你可以在 LINQ 查询中使用 <xref:System.Data.DataRow> 类的任何成员。 这使您可以创建丰富复杂的查询。  
  
 与 LINQ 的其他实现一样，您可以通过两种不同的形式创建 LINQ to DataSet 查询：查询表达式语法和基于方法的查询语法。 您可以使用查询表达式语法或基于方法的查询语法对 <xref:System.Data.DataSet> 中的单个表、对 <xref:System.Data.DataSet> 中的多个表或对类型化 <xref:System.Data.DataSet> 中的表执行查询。  
  
## <a name="in-this-section"></a>本节内容  
 [单表查询](single-table-queries-linq-to-dataset.md)  
 说明如何执行单表查询。  
  
 [跨表查询](cross-table-queries-linq-to-dataset.md)  
 说明如何执行交叉表查询。  
  
 [查询类型化数据集](querying-typed-datasets.md)  
 说明如何查询类型化 <xref:System.Data.DataSet> 对象。  
  
## <a name="see-also"></a>另请参阅

- [LINQ to DataSet 示例](linq-to-dataset-examples.md)
- [将数据加载到数据集中](loading-data-into-a-dataset.md)
