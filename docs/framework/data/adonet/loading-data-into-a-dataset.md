---
title: 将数据加载到数据集中
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: 26b77269b21e1b365f81746ba2df66d7df91677e
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504326"
---
# <a name="loading-data-into-a-dataset"></a>将数据加载到数据集中
一个<xref:System.Data.DataSet>之前您可以对其进行查询使用 LINQ to DataSet，首先必须填充对象。 填充 <xref:System.Data.DataSet> 有多种不同的方式。 例如，您可以使用 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] 来查询数据库并将结果加载到 <xref:System.Data.DataSet> 中。 有关详细信息，请参阅 [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)。  
  
 另一种将数据加载到 <xref:System.Data.DataSet> 中的常见方式是使用 <xref:System.Data.Common.DataAdapter> 类从数据库中检索数据。 下列示例对此进行了阐释。  
  
## <a name="example"></a>示例  
 此示例使用 <xref:System.Data.Common.DataAdapter> 查询 AdventureWorks 数据库中从 2002 年起的销售信息，并将结果加载到 <xref:System.Data.DataSet> 中。 之后<xref:System.Data.DataSet>已填充，您可以通过使用 LINQ to DataSet 编写针对它的查询。 `FillDataSet`中的示例查询中使用在此示例中的方法[LINQ to DataSet 示例](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)。 有关详细信息，请参阅[查询数据集](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)。  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a>请参阅

- [LINQ to DataSet 概述](../../../../docs/framework/data/adonet/linq-to-dataset-overview.md)
- [查询数据集](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [LINQ to DataSet 示例](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
