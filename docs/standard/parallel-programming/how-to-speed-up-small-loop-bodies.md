---
title: 如何：加快小型循环体的速度
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to speed up
ms.assetid: c7a66677-cb59-4cbf-969a-d2e8fc61a6ce
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bff41416dd2263c185cc94de045b2c8a26ea194d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-speed-up-small-loop-bodies"></a>如何：加快小型循环体的速度
如果 <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> 循环的主体很小，它的执行速度可能慢于相当的顺序循环，如 C# 中的 [for](~/docs/csharp/language-reference/keywords/for.md) 循环和 Visual Basic 中的 [For](http://msdn.microsoft.com/library/c470a263-9b49-4308-8fd6-8592b84a7980) 循环。 性能下降是由数据分区中的开销和在每个循环迭代上调用委托的成本所引起的。 若要解决这种情况下，<xref:System.Collections.Concurrent.Partitioner> 类提供了 <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> 方法，使你能够为委托主体提供一个顺序循环，以便每个分区仅调用一次委托，而不是每个迭代调用一次委托。 有关详细信息，请参阅 [PLINQ 和 TPL 的自定义分区程序](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)。  
  
## <a name="example"></a>示例  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 在循环执行最少量的工作时，此示例中演示的方法很有用。 随着工作变得更占用计算资源，通过默认分区程序，使用 <xref:System.Threading.Tasks.Parallel.For%2A> 或 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 循环，很有可能会获得相同或更好的性能。  
  
## <a name="see-also"></a>请参阅  
 [数据并行](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [PLINQ 和 TPL 的自定义分区程序](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)  
 [迭代器](https://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)  
 [PLINQ 和 TPL 中的 Lambda 表达式](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
