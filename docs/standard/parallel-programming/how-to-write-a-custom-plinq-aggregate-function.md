---
title: "如何：编写自定义 PLINQ 聚合函数"
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
helpviewer_keywords: PLINQ queries, how to create aggregate function
ms.assetid: 5a70dd49-ab2a-4798-b551-196ee7042b1a
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8b098f21e29d0d59cd99ddbb64af6246d9953a3a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-a-custom-plinq-aggregate-function"></a>如何：编写自定义 PLINQ 聚合函数
此示例演示如何使用<xref:System.Linq.ParallelEnumerable.Aggregate%2A>方法将自定义聚合函数应用于源序列。  
  
> [!WARNING]
>  本示例旨在演示用法，运行速度可能不如等效的顺序 LINQ to Objects 查询快。 有关加速的详细信息，请参阅[了解 PLINQ 中的加速](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)。  
  
## <a name="example"></a>示例  
 下面的示例计算整数的序列的标准偏差。  
  
 [!code-csharp[PLINQ#31](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#31)]
 [!code-vb[PLINQ#31](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#31)]  
  
 此示例使用是唯一的 PLINQ 聚合的标准查询运算符的重载。 此重载采用额外<xref:System.Func%603?displayProperty=nameWithType>作为第三个输入参数。 执行最终计算聚合结果之前，此委托将合并所有线程的结果。 在此示例中我们将添加在一起总和所有线程。  
  
 请注意，当 lambda 表达式主体包含单个表达式，返回值的<xref:System.Func%602?displayProperty=nameWithType>委托是表达式的值。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Linq.ParallelEnumerable>  
 [并行 LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
