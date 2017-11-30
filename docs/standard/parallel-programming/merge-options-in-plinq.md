---
title: "PLINQ 中的合并选项"
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
helpviewer_keywords: PLINQ queries, merge options
ms.assetid: e8f7be3b-88de-4f33-ab14-dc008e76c1ba
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e9bf586c1805fc5b5f1cc5f96f4e6b08d80c199a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="merge-options-in-plinq"></a>PLINQ 中的合并选项
当查询正在作为并行，PLINQ 分区的源序列，以便多个线程可以同时处理同一置于不同部分，通常在单独线程上。 如果结果为将使用上一个线程，例如，在`foreach`(`For Each`中[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) 循环，则来自每个线程的结果必须合并回一个序列。 PLINQ 执行 merge 的类型取决于查询中存在的运算符。 例如，应用于的结果新顺序的运算符必须缓冲的所有线程中的所有元素。 从使用它的线程 （这也是，应用程序用户） 的角度来看完全缓冲的查询可能会明显期运行之前它将生成其第一个结果的时间。 其他运算符，默认情况下，部分缓冲;它们会产生分批其结果。 运算符，<xref:System.Linq.ParallelEnumerable.ForAll%2A>默认情况下未缓冲。 它立即从所有线程中生成的所有元素。  
  
 通过使用<xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A>方法，如下面的示例中所示你可以提供一个提示 plinq，该值指示要执行的合并类型。  
  
 [!code-csharp[PLINQ#26](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#26)]
 [!code-vb[PLINQ#26](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#26)]  
  
 有关完整示例，请参阅[如何： 在 PLINQ 中指定合并选项](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)。  
  
 如果特定的查询不支持请求的选项，则只需忽略选项。 在大多数情况下，无需指定 PLINQ 查询的合并选项。 但是，在某些情况下你可能会发现通过测试和查询执行最在非默认模式下的测量。 此选项的一个常见用途是强制使用区块合并运算符流式以便提供更快地响应用户界面处理其结果。  
  
## <a name="parallelmergeoptions"></a>ParallelMergeOptions  
 <xref:System.Linq.ParallelMergeOptions>枚举包含以下选项，指定如何生成查询的最终输出了结果使用在一个线程上时，支持的查询形状：  
  
-   `Not Buffered`  
  
     <xref:System.Linq.ParallelMergeOptions.NotBuffered>选项将导致每个已处理的元素，返回从每个线程，就会立即生成它。 此行为是类似于"流式处理"输出。 如果<xref:System.Linq.ParallelEnumerable.AsOrdered%2A>运算符是在查询中，存在`NotBuffered`保留源元素的顺序。 尽管`NotBuffered`开始就立即可用，就产生结果、 的总时间以生成所有结果可能仍然能长于使用其他合并选项之一。  
  
-   `Auto Buffered`  
  
     通过 <xref:System.Linq.ParallelMergeOptions.AutoBuffered> 选项，查询将元素收集到缓冲区中，并定期一次性将所有缓冲内容生成到使用线程中。 这是类似于生成而不使用的"流式处理"行为"区块"中的源数据`NotBuffered`。 `AutoBuffered`可能需要超过`NotBuffered`以使第一个元素在使用它的线程上可用。 大小以及缓冲区准确的生成行为是不可配置的并可能会有所不同，具体取决于与查询相关的各种因素。  
  
-   `FullyBuffered`  
  
     <xref:System.Linq.ParallelMergeOptions.FullyBuffered>选项会导致整个查询之前的任何元素都生成缓存的输出。 当你使用此选项时，则可以较长时间之前的第一个元素上使用它的线程，可用，但可能仍然生成完整的结果比使用其他选项更快。  
  
## <a name="query-operators-that-support-merge-options"></a>支持合并选项的查询运算符  
 下表列出了支持所有的合并选项模式，根据指定的限制的运算符。  
  
|运算符|限制|  
|--------------|------------------|  
|<xref:System.Linq.ParallelEnumerable.AsEnumerable%2A>|无|  
|<xref:System.Linq.ParallelEnumerable.Cast%2A>|无|  
|<xref:System.Linq.ParallelEnumerable.Concat%2A>|有一个数组或列表源仅的非排序的查询。|  
|<xref:System.Linq.ParallelEnumerable.DefaultIfEmpty%2A>|无|  
|<xref:System.Linq.ParallelEnumerable.OfType%2A>|无|  
|<xref:System.Linq.ParallelEnumerable.Reverse%2A>|有一个数组或列表源仅的非排序的查询。|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>|无|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>|无|  
|<xref:System.Linq.ParallelEnumerable.Skip%2A>|无|  
|<xref:System.Linq.ParallelEnumerable.Take%2A>|无|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>|无|  
  
 所有其他 PLINQ 查询运算符可能会忽略用户提供的合并选项。 某些查询运算符，例如，<xref:System.Linq.ParallelEnumerable.Reverse%2A>和<xref:System.Linq.ParallelEnumerable.OrderBy%2A>，无法生成任何元素，直到所有已生成并重新排序。 因此，当<xref:System.Linq.ParallelMergeOptions>还包含操作员例如查询中使用<xref:System.Linq.ParallelEnumerable.Reverse%2A>，合并行为后该运算符生成其结果不会在查询中，直到应用。  
  
 有些运算符能够处理合并选项取决于源序列中的类型和是否<xref:System.Linq.ParallelEnumerable.AsOrdered%2A>运算符使用前面的查询。 <xref:System.Linq.ParallelEnumerable.ForAll%2A>始终<xref:System.Linq.ParallelMergeOptions.NotBuffered>; 它将立即生成它的元素。 <xref:System.Linq.ParallelEnumerable.OrderBy%2A>始终<xref:System.Linq.ParallelMergeOptions.FullyBuffered>; 它之前它将产生必须对整个列表进行排序。  
  
## <a name="see-also"></a>另请参阅  
 [并行 LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [如何：在 PLINQ 中指定合并选项](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)
