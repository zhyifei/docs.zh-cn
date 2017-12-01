---
title: "如何：在 PLINQ 中指定执行模式"
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
helpviewer_keywords: PLINQ queries, how to use execution mode
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 745ceae9832582c7b66a56075d128f9cf1c8ff69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-execution-mode-in-plinq"></a>如何：在 PLINQ 中指定执行模式
此示例演示如何强制 PLINQ 跳过其默认试探法并并行执行的查询而不考虑查询的形状。  
  
> [!WARNING]
>  本示例旨在演示用法，运行速度可能不如等效的顺序 LINQ to Objects 查询快。 有关加速的详细信息，请参阅[了解 PLINQ 中的加速](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)。  
  
## <a name="example"></a>示例  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 PLINQ 旨在利用并行化的机会。 但是，并非所有查询都受益于并行执行。 例如，当查询包含很少执行工作的单个用户委托，该查询通常将更快地按顺序运行。 这是因为启用并行化执行所涉及的开销是比速度提高获取开销更大。 因此，PLINQ 不自动并行化的每个查询。 它首先检查查询和包含它的各种运算符的形状。 基于此分析，PLINQ 中的默认执行模式可能决定按顺序执行部分或所有查询。 但是，在某些情况下你可能知道更多有关您的查询比 PLINQ 能够从其分析确定。 例如，你可能知道委托是代价很高，并查询将一定受益于并行化。 在这种情况下，你可以使用<xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A>方法并指定<xref:System.Linq.ParallelExecutionMode.ForceParallelism>值，以指示 PLINQ 为始终以并行运行查询。  
  
## <a name="compiling-the-code"></a>编译代码  
 到此代码剪切并粘贴[PLINQ 数据示例](../../../docs/standard/parallel-programming/plinq-data-sample.md)调用该方法从`Main`。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Linq.ParallelEnumerable.AsSequential%2A>  
 [并行 LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
