---
title: 基于方法的查询语法示例：集合运算符 (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa93af15-28af-4b5e-846b-897308410edb
ms.openlocfilehash: 481c0ed7e39b8f958ccdae01e4589d54b3ff2446
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783573"
---
# <a name="method-based-query-syntax-examples-set-operators-linq-to-dataset"></a>基于方法的查询语法示例：集合运算符 (LINQ to DataSet)
本主题中的示例演示如何<xref:System.Linq.Enumerable.Distinct%2A>使用、 <xref:System.Linq.Enumerable.Except%2A>、 <xref:System.Linq.Enumerable.Intersect%2A>和<xref:System.Linq.Enumerable.Union%2A>运算符对数据行集执行基于值的比较运算。[将数据加载到数据集](loading-data-into-a-dataset.md) <xref:System.Data.DataRowComparer>。有关的详细信息，请参阅[比较 datarow](comparing-datarows-linq-to-dataset.md) 。  
  
 在`FillDataSet`这些示例中使用的方法是在将[数据加载到数据集](loading-data-into-a-dataset.md)时指定的。  
  
 本主题中的示例使用 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 表。  
  
 本主题中的示例使用以下`using` / `Imports`语句：  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 有关详细信息，请参阅[如何：在 Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md)中创建 LINQ to DataSet 项目。  
  
## <a name="distinct"></a>Distinct  
  
### <a name="example"></a>示例  
 此示例使用 <xref:System.Linq.Enumerable.Distinct%2A> 方法移除序列中的重复元素。  
  
 [!code-csharp[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#distinctrows)]
 [!code-vb[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#distinctrows)]  
  
## <a name="except"></a>Except  
  
### <a name="example"></a>示例  
 此示例使用 <xref:System.Linq.Enumerable.Except%2A> 方法返回出现在第一个表中但不出现在第二个表中的联系人。  
  
 [!code-csharp[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#except2)]
 [!code-vb[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#except2)]  
  
## <a name="intersect"></a>相交  
  
### <a name="example"></a>示例  
 此示例使用 <xref:System.Linq.Enumerable.Intersect%2A> 方法返回同时出现在两个表中的联系人。  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
## <a name="union"></a>联合  
  
### <a name="example"></a>示例  
 此示例使用 <xref:System.Linq.Enumerable.Union%2A> 方法返回这两个表的任一表中特有的联系人。  
  
 [!code-csharp[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#union2)]
 [!code-vb[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#union2)]  
  
## <a name="see-also"></a>请参阅

- [将数据加载到数据集中](loading-data-into-a-dataset.md)
- [LINQ to DataSet 示例](linq-to-dataset-examples.md)
- [标准查询运算符概述 (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [标准查询运算符概述 (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
