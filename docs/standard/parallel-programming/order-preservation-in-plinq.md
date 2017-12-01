---
title: "PLINQ 中的顺序保留"
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
helpviewer_keywords: PLINQ queries, order preservation
ms.assetid: 10d202bc-19e1-4b5c-bbf1-9a977322a9ca
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 060459cf8f408e40ddc394fbcda6a022ec6379de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="order-preservation-in-plinq"></a>PLINQ 中的顺序保留
在 PLINQ 中，目标是最大程度提高性能，同时保持正确性。 查询应运行尽可能快，但仍然生成正确的结果。 在某些情况下，正确性需要源序列中的顺序，将保留;但是，排序可以是计算开销很大。 因此，默认情况下，PLINQ 不保留源序列中的顺序。 在这一方面，类似于 PLINQ [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)]，但与 LINQ to Objects，其中未保留排序不同。  
  
 若要重写默认行为，你可以启用顺序保留使用<xref:System.Linq.ParallelEnumerable.AsOrdered%2A>对源序列的运算符。 然后可以通过将更高版本中查询的顺序保留关闭<xref:System.Linq.ParallelEnumerable.AsUnordered%2A>方法。 与这两种方法，在基于的试探方法确定是否执行并行形式的查询，或按顺序处理查询。 有关详细信息，请参阅[了解 PLINQ 中的加速](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)。  
  
 下面的示例显示未排序的并行查询在筛选的匹配条件，而不会尝试对结果进行排序以任何方式的所有元素。  
  
 [!code-csharp[PLINQ#8](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#8)]
 [!code-vb[PLINQ#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#8)]  
  
 此查询不一定会生成满足条件，而是某些组 1000年个城市中满足条件但源序列中的前 1000 个城市。 PLINQ 查询运算符分区源序列转换为并发任务处理的多个序列。 如果未指定顺序保留，则来自每个分区的结果被移交给查询按任意顺序的下一阶段。 此外，分区可能会产生其结果的子集，才能继续处理剩余的元素。 生成顺序可能不同每次。 你的应用程序不能控制此行为因为它依赖于操作系统如何调度线程。  
  
 下面的示例通过使用来重写默认行为<xref:System.Linq.ParallelEnumerable.AsOrdered%2A>对源序列的运算符。 这样可确保<xref:System.Linq.ParallelEnumerable.Take%2A>方法返回源序列中满足条件中的前 1000 个城市。  
  
 [!code-csharp[PLINQ#9](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#9)]
 [!code-vb[PLINQ#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#9)]  
  
 但是，此查询可能不运行尽可能快的无序版本因为它必须跟踪整个分区的原始排序的并在合并时确保的顺序一致。 因此，我们建议你使用<xref:System.Linq.ParallelEnumerable.AsOrdered%2A>仅时是必需的并且仅用于需要它的查询那些部分。 当不再需要顺序保留时，使用<xref:System.Linq.ParallelEnumerable.AsUnordered%2A>来将其关闭。 下面的示例来实现此编写两个查询。  
  
 [!code-csharp[PLINQ#6](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#6)]
 [!code-vb[PLINQ#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#6)]  
  
 请注意 PLINQ 保留由查询的其余部分的顺序不对运算符生成的序列的顺序。 换而言之，运算符，如<xref:System.Linq.ParallelEnumerable.OrderBy%2A>和<xref:System.Linq.ParallelEnumerable.ThenBy%2A>被视为好像在它们之后通过调用<xref:System.Linq.ParallelEnumerable.AsOrdered%2A>。  
  
## <a name="query-operators-and-ordering"></a>查询运算符和排序  
 下面的查询运算符将在查询中，或之前的所有后续操作顺序保留引入<xref:System.Linq.ParallelEnumerable.AsUnordered%2A>调用：  
  
-   <xref:System.Linq.ParallelEnumerable.OrderBy%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.OrderByDescending%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.ThenBy%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.ThenByDescending%2A>  
  
 下面的 PLINQ 查询运算符在某些情况下可能需要经过排序的源序列来生成正确的结果：  
  
-   <xref:System.Linq.ParallelEnumerable.Reverse%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.SequenceEqual%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.TakeWhile%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.SkipWhile%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.Zip%2A>  
  
 有些 PLINQ 查询运算符的行为不同，具体取决于是否其源序列是否已经过排序。 下表列出这些运算符。  
  
|运算符|源序列进行排序时，会发生|源序列为无序时的结果|  
|--------------|------------------------------------------------|--------------------------------------------------|  
|<xref:System.Linq.ParallelEnumerable.Aggregate%2A>|具有不确定性输出结合或不可交换操作|具有不确定性输出结合或不可交换操作|  
|<xref:System.Linq.ParallelEnumerable.All%2A>|不适用|不适用|  
|<xref:System.Linq.ParallelEnumerable.Any%2A>|不适用|不适用|  
|<xref:System.Linq.ParallelEnumerable.AsEnumerable%2A>|不适用|不适用|  
|<xref:System.Linq.ParallelEnumerable.Average%2A>|具有不确定性输出结合或不可交换操作|具有不确定性输出结合或不可交换操作|  
|<xref:System.Linq.ParallelEnumerable.Cast%2A>|结果按顺序排列|无序的结果|  
|<xref:System.Linq.ParallelEnumerable.Concat%2A>|结果按顺序排列|无序的结果|  
|<xref:System.Linq.ParallelEnumerable.Count%2A>|不适用|不适用|  
|<xref:System.Linq.ParallelEnumerable.DefaultIfEmpty%2A>|不适用|不适用|  
|<xref:System.Linq.ParallelEnumerable.Distinct%2A>|结果按顺序排列|无序的结果|  
|<xref:System.Linq.ParallelEnumerable.ElementAt%2A>|返回指定的元素|任意元素|  
|<xref:System.Linq.ParallelEnumerable.ElementAtOrDefault%2A>|返回指定的元素|任意元素|  
|<xref:System.Linq.ParallelEnumerable.Except%2A>|无序的结果|无序的结果|  
|<xref:System.Linq.ParallelEnumerable.First%2A>|返回指定的元素|任意元素|  
|<xref:System.Linq.ParallelEnumerable.FirstOrDefault%2A>|返回指定的元素|任意元素|  
|<xref:System.Linq.ParallelEnumerable.ForAll%2A>|不确定地以并行方式执行|不确定地以并行方式执行|  
|<xref:System.Linq.ParallelEnumerable.GroupBy%2A>|结果按顺序排列|无序的结果|  
|<xref:System.Linq.ParallelEnumerable.GroupJoin%2A>|结果按顺序排列|无序的结果|  
|<xref:System.Linq.ParallelEnumerable.Intersect%2A>|结果按顺序排列|无序的结果|  
|<xref:System.Linq.ParallelEnumerable.Join%2A>|结果按顺序排列|无序的结果|  
|<xref:System.Linq.ParallelEnumerable.Last%2A>|返回指定的元素|任意元素|  
|<xref:System.Linq.ParallelEnumerable.LastOrDefault%2A>|返回指定的元素|任意元素|  
|<xref:System.Linq.ParallelEnumerable.LongCount%2A>|不适用|不适用|  
|<xref:System.Linq.ParallelEnumerable.Min%2A>|不适用|不适用|  
|<xref:System.Linq.ParallelEnumerable.OrderBy%2A>|重新排序序列|启动新经过排序的节|  
|<xref:System.Linq.ParallelEnumerable.OrderByDescending%2A>|重新排序序列|启动新经过排序的节|  
|<xref:System.Linq.ParallelEnumerable.Range%2A>|不适用 (相同的默认值为<xref:System.Linq.ParallelEnumerable.AsParallel%2A>)|不适用|  
|<xref:System.Linq.ParallelEnumerable.Repeat%2A>|不适用 (相同的默认值为<xref:System.Linq.ParallelEnumerable.AsParallel%2A>)|不适用|  
|<xref:System.Linq.ParallelEnumerable.Reverse%2A>|反转|不执行任何操作|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>|结果按顺序排列|无序的结果|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>（索引）|结果按顺序排列|无序的结果。|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>|结果按顺序排列。|无序的结果|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>（索引）|结果按顺序排列。|无序的结果。|  
|<xref:System.Linq.ParallelEnumerable.SequenceEqual%2A>|经过排序的比较|无序的比较|  
|<xref:System.Linq.ParallelEnumerable.Single%2A>|不适用|不适用|  
|<xref:System.Linq.ParallelEnumerable.SingleOrDefault%2A>|不适用|不适用|  
|<xref:System.Linq.ParallelEnumerable.Skip%2A>|第一次跳过 *n* 元素|跳过任何 *n* 元素|  
|<xref:System.Linq.ParallelEnumerable.SkipWhile%2A>|结果按顺序排列。|具有不确定性。 对当前的任意顺序执行 SkipWhile|  
|<xref:System.Linq.ParallelEnumerable.Sum%2A>|具有不确定性输出结合或不可交换操作|具有不确定性输出结合或不可交换操作|  
|<xref:System.Linq.ParallelEnumerable.Take%2A>|采用第一个`n`元素|采用任何`n`元素|  
|<xref:System.Linq.ParallelEnumerable.TakeWhile%2A>|结果按顺序排列|具有不确定性。 对当前的任意顺序执行 TakeWhile|  
|<xref:System.Linq.ParallelEnumerable.ThenBy%2A>|补充`OrderBy`|补充`OrderBy`|  
|<xref:System.Linq.ParallelEnumerable.ThenByDescending%2A>|补充`OrderBy`|补充`OrderBy`|  
|<xref:System.Linq.ParallelEnumerable.ToArray%2A>|结果按顺序排列|无序的结果|  
|<xref:System.Linq.ParallelEnumerable.ToDictionary%2A>|不适用|不适用|  
|<xref:System.Linq.ParallelEnumerable.ToList%2A>|结果按顺序排列|无序的结果|  
|<xref:System.Linq.ParallelEnumerable.ToLookup%2A>|结果按顺序排列|无序的结果|  
|<xref:System.Linq.ParallelEnumerable.Union%2A>|结果按顺序排列|无序的结果|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>|结果按顺序排列|无序的结果|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>（索引）|结果按顺序排列|无序的结果|  
|<xref:System.Linq.ParallelEnumerable.Zip%2A>|结果按顺序排列|无序的结果|  
  
 无序的结果不主动随机排布;它们只不具有应用于它们的任何特殊的排序逻辑。 在某些情况下，未经排序的查询可能会保留对源序列的排序。 对于使用索引的 Select 运算符的查询，PLINQ 保证的输出元素将先行一顺序递增索引，但使哪个索引不能确保将分配给哪些元素。  
  
## <a name="see-also"></a>另请参阅  
 [并行 LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [并行编程](../../../docs/standard/parallel-programming/index.md)
