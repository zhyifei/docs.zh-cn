---
title: "如何：在 PLINQ 查询中控制排序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: PLINQ queries, how to control ordering
ms.assetid: c67eccc7-004d-4b2f-987e-919cbbd62ef7
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9e29aa825a68154e32a34a23ca170258092b88a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-ordering-in-a-plinq-query"></a>如何：在 PLINQ 查询中控制排序
这些示例演示如何控制排序 PLINQ 查询中使用<xref:System.Linq.ParallelEnumerable.AsOrdered%2A>扩展方法。  
  
> [!WARNING]
>  这些示例主要是为了演示用法，并可能或可能不运行速度不如等效的顺序 LINQ to 对象查询。  
  
## <a name="example"></a>示例  
 下面的示例将保留源序列的排序。 有时这是必要的;例如，有些查询运算符需要经过排序的源序列生成正确的结果。  
  
 [!code-csharp[PLINQ#12](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#12)]
 [!code-vb[PLINQ#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#12)]  
  
## <a name="example"></a>示例  
 下面的示例演示某些查询可能需要对其源序列进行排序的运算符。 这些运算符将适用于无序序列，但它们可能会产生意外的结果。  
  
 [!code-csharp[PLINQ#14](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#14)]
 [!code-vb[PLINQ#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#14)]  
  
 若要运行此方法，请将其粘贴到中的 PLINQDataSample 类[PLINQ 数据示例](../../../docs/standard/parallel-programming/plinq-data-sample.md)项目，然后按 F5。  
  
## <a name="example"></a>示例  
 下面的示例演示如何保留排序的第一个部分的查询，然后删除排序可提高性能的 join 子句中，然后重新应用的最终结果序列的排序。  
  
 [!code-csharp[PLINQ#15](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#15)]
 [!code-vb[PLINQ#15](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#15)]  
  
 若要运行此方法，请将其粘贴到中的 PLINQDataSample 类[PLINQ 数据示例](../../../docs/standard/parallel-programming/plinq-data-sample.md)项目，然后按 F5。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Linq.ParallelEnumerable>  
 [并行 LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
