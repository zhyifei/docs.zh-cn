---
title: 将数据加载到数据集中
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: 53f0f5a589a0033c9612f0465dff090ab04e3fc4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794954"
---
# <a name="loading-data-into-a-dataset"></a>将数据加载到数据集中
必须先填充对象，然后才能使用 LINQ to DataSet 进行查询。 <xref:System.Data.DataSet> 填充 <xref:System.Data.DataSet> 有多种不同的方式。 例如，您可以使用 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] 来查询数据库并将结果加载到 <xref:System.Data.DataSet> 中。 有关详细信息，请参阅 [LINQ to SQL](./sql/linq/index.md)。  
  
 另一种将数据加载到 <xref:System.Data.DataSet> 中的常见方式是使用 <xref:System.Data.Common.DataAdapter> 类从数据库中检索数据。 下列示例对此进行了阐释。  
  
## <a name="example"></a>示例  
 此示例使用 <xref:System.Data.Common.DataAdapter> 查询 AdventureWorks 数据库中从 2002 年起的销售信息，并将结果加载到 <xref:System.Data.DataSet> 中。 <xref:System.Data.DataSet>填充后，可以使用 LINQ to DataSet 来编写查询。 本`FillDataSet`示例中的方法用于[LINQ to DataSet 示例](linq-to-dataset-examples.md)中的示例查询。 有关详细信息，请参阅[查询数据集](querying-datasets-linq-to-dataset.md)。  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a>请参阅

- [LINQ to DataSet 概述](linq-to-dataset-overview.md)
- [查询数据集](querying-datasets-linq-to-dataset.md)
- [LINQ to DataSet 示例](linq-to-dataset-examples.md)
