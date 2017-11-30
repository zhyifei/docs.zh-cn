---
title: "PLINQ 和 TPL 的自定义分区程序"
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
helpviewer_keywords: tasks, partitioners
ms.assetid: 96153688-9a01-47c4-8430-909cee9a2887
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 12d234b86b0067178d54d2fdcb5d37ceaee6109d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="custom-partitioners-for-plinq-and-tpl"></a>PLINQ 和 TPL 的自定义分区程序
并行执行对数据源的操作，其中一个重要步骤是到*分区*到可由多个线程同时访问的多个部分的源。 PLINQ 和任务并行库 (TPL) 提供了当你编写并行查询以透明方式工作的默认分区程序或<xref:System.Threading.Tasks.Parallel.ForEach%2A>循环。 对于更高级方案，您可以插入您自己的分区程序。  
  
## <a name="kinds-of-partitioning"></a>类型的分区  
 有多种方法进行分区的数据源。 最有效方法，在多个线程之间相互协作过程原始的源序列中，而不是以物理方式将源分离到多个序列。 对于数组和其他索引源如<xref:System.Collections.IList>集合长度提前，知道*范围分区*是最简单的分区类型。 每个线程都接收唯一的开头和结尾的索引，以便它可以处理其范围的源，而无需覆盖或其他任何线程被覆盖。 范围分区所涉及的唯一开销是创建范围; 的初始工作在此之后，没有其他同步是必需的。 因此，它可提供良好的性能，只要均匀划分工作负荷。 范围分区的缺点是，如果一个线程提前完成，它不能帮助其他线程完成其工作。  
  
 对于链接的表或其长度不知道其他集合，你可以使用*区块分区*。 在按区块分区，每个线程或任务并行循环或查询中的使用一定数量的一个块区中的源元素，处理它们，然后再次要从中检索其他元素。 分发的所有元素，且没有没有重复项，可确保分区程序。 块可为任意大小。 例如，分区程序中所示[如何： 实现动态分区](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md)创建只包含一个元素的区块。 只要消息块不太大，这种类型的分区是本质上负载平衡因为分配给线程的元素不预先确定。 但是，分区程序确实会引致同步开销线程需要获取另一个区块每次。 在这些情况下产生的同步量为反比区块的大小成正比。  
  
 一般情况下，范围分区时才是更快委托的执行时间是小到中等程度，并且源有大量的元素，和每个分区的总工作量大致相当。 块区分区是因此在大多数情况下通常更快。 少量的元素或委托执行时间较长的源，则文本块和范围分区的性能是大致相等。  
  
 TPL 分区程序还支持动态数量的分区。 这意味着它们可以创建分区上的即时，例如，当<xref:System.Threading.Tasks.Parallel.ForEach%2A>循环生成新的任务。 此功能使分区程序循环本身以及缩放。 动态分区程序也是本质上负载平衡。 当你创建自定义分区程序时，你必须支持动态的分区，若要通过<xref:System.Threading.Tasks.Parallel.ForEach%2A>循环。  
  
### <a name="configuring-load-balancing-partitioners-for-plinq"></a>配置负载平衡的 PLINQ 分区程序  
 某些重载<xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType>方法让你创建数组分区程序或<xref:System.Collections.IList>源，并指定是否应尝试平衡在线程间的工作负荷。 当分区程序配置负载平衡，使用块区分区，并元素会被移交给小区块中的每个分区会请求。 此方法可帮助确保所有分区都具有元素才能整个循环之前，处理或查询已完成。 可以使用另一个重载，以提供负载平衡分区的任何<xref:System.Collections.IEnumerable>源。  
  
 通常情况下，负载平衡要求请求元素相对频繁从分区程序的分区。 与此相反，分区程序执行静态分区可以通过将指定元素给每个分区程序在一次范围或块区分区。 这要求更少的开销不是负载平衡，但可能需要更长时间才能执行如果一个线程结束时，其比其他更多工作。 默认情况下是 IList 或数组，传递时 PLINQ 始终使用范围分区而不负载平衡。 若要启用负载平衡 PLINQ，使用`Partitioner.Create`方法，如下面的示例中所示。  
  
 [!code-csharp[TPL_Partitioners#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#02)]
 [!code-vb[TPL_Partitioners#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionsnippets_vb.vb#02)]  
  
 确定是否使用负载平衡在任何给定方案中是体验并度量时间操作在代表性的负载和计算机配置下完成的最佳方式。 例如，静态分区可能会有仅几个核心的多核计算机上的明显加快，但它可能会导致具有相对较多的内核的计算机上的系统速度变慢。  
  
 下表列出了可用的重载的<xref:System.Collections.Concurrent.Partitioner.Create%2A>方法。 这些分区程序不受限制，将仅用于 PLINQ 或<xref:System.Threading.Tasks.Task>。 它们还可以用于任何自定义的并行构造。  
  
|重载|使用负载平衡|  
|--------------|-------------------------|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>|Always|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28%60%600%5B%5D%2CSystem.Boolean%29>|当为 true，则指定的布尔型参数|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IList%7B%60%600%7D%2CSystem.Boolean%29>|当为 true，则指定的布尔型参数|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%29>|Never|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%2CSystem.Int32%29>|Never|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%29>|Never|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%2CSystem.Int64%29>|Never|  
  
### <a name="configuring-static-range-partitioners-for-parallelforeach"></a>配置静态范围的 Parallel.ForEach 的分区程序  
 在<xref:System.Threading.Tasks.Parallel.For%2A>循环，循环的正文提供给视为的委托方法。 调用该委托的成本是关于虚方法调用相同的。 在某些情况下，并行循环主体可能是足够小，每个循环迭代上的委托调用的成本变得很大。 在这种情况下，你可以使用其中一个<xref:System.Collections.Concurrent.Partitioner.Create%2A>重载创建<xref:System.Collections.Generic.IEnumerable%601>针对源元素的范围分区。 然后，将传递到此集合<xref:System.Threading.Tasks.Parallel.ForEach%2A>方法的正文包含正则表达式`for`循环。 此方法的好处是委托调用成本发生一次每个范围，而不是一次每个元素。 下面的示例演示了基本模式。  
  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 在循环中的每个线程都接收其自己<xref:System.Tuple%602>，其中包含起始和结束中指定的子范围的索引值。 内部`for`循环使用`fromInclusive`和`toExclusive`值循环访问数组或<xref:System.Collections.IList>直接。  
  
 之一<xref:System.Collections.Concurrent.Partitioner.Create%2A>重载允许您指定的大小以及这两个分区的分区数。 此重载可以在其中每个元素的工作是因此低甚至一个虚方法调用每个元素对性能产生显著影响在方案中使用。  
  
## <a name="custom-partitioners"></a>自定义分区程序  
 在某些情况下，它可能是值得或甚至需要实现自己的分区程序。 例如，您可能可以与默认分区程序可以基于你的类的内部结构知识更有效地进行分区的自定义集合类。 或者，你可能想要创建基于你的需要多长时间它到源集合中的不同位置的过程元素知识的不同大小的范围分区。  
  
 若要创建基本的自定义分区程序，从派生类<xref:System.Collections.Concurrent.Partitioner%601?displayProperty=nameWithType>和重写虚拟方法下, 表中所述。  
  
|||  
|-|-|  
|<xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>|此方法由主线程调用一次，并返回 IList(IEnumerator(TSource))。 循环或查询中的每个工作线程可以调用`GetEnumerator`上要检索的列表<xref:System.Collections.Generic.IEnumerator%601>针对不同的分区。|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|返回`true`如果实现<xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>，否则为`false`。|  
|<xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>|如果<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>是`true`，可以根据需要调用此方法，而不是<xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>。|  
  
 如果结果必须是可排序，或者您需要到的元素的索引的访问，派生自<xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType>并重写其虚拟方法下, 表中所述。  
  
|||  
|-|-|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetPartitions%2A>|此方法由主线程调用一次，并返回`IList(IEnumerator(TSource))`。 循环或查询中的每个工作线程可以调用`GetEnumerator`上要检索的列表<xref:System.Collections.Generic.IEnumerator%601>针对不同的分区。|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|返回`true`如果实现<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>; 否则为 false。|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>|通常情况下，这只调用<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>。|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>|如果<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>是`true`，可以根据需要调用此方法，而不是<xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>。|  
  
 下表提供了其他详细介绍三种类型的负载平衡分区程序实现<xref:System.Collections.Concurrent.OrderablePartitioner%601>类。  
  
|方法/属性|IList / 数组而不负载平衡|IList / 数组与负载平衡|IEnumerable|  
|----------------------|-------------------------------------------|----------------------------------------|-----------------|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>|使用范围分区|使用块区分区指定 partitionCount 针对列表优化|通过创建静态分区数使用块区分区。|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A?displayProperty=nameWithType>|不支持将引发异常|使用块区分区优化列表和动态分区|通过创建动态分区数使用块区分区。|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedInEachPartition%2A>|返回 `true`|返回 `true`|返回 `true`|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedAcrossPartitions%2A>|返回 `true`|返回 `false`|返回 `false`|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysNormalized%2A>|返回 `true`|返回 `true`|返回 `true`|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|返回 `false`|返回 `true`|返回 `true`|  
  
### <a name="dynamic-partitions"></a>动态分区  
 如果你想要在中使用的分区<xref:System.Threading.Tasks.Parallel.ForEach%2A>方法，你必须能够返回动态数量的分区。 这意味着分区程序可以在循环执行期间随时提供新分区的点播的枚举数。 基本上，只要循环添加新的并行任务，它会请求该任务的新分区。 如果你需要以可排序数据，然后派生自<xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType>，以便每个分区中的每个项分配一个唯一索引。  
  
 有关详细信息及示例，请参阅[如何： 实现动态分区](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md)。  
  
### <a name="contract-for-partitioners"></a>协定分区程序  
 当您实现自定义分区程序时，请遵循以下准则来帮助确保与 PLINQ 的正确交互和<xref:System.Threading.Tasks.Parallel.ForEach%2A>TPL 中：  
  
-   如果<xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>调用参数为零或更短`partitionsCount`，引发<xref:System.ArgumentOutOfRangeException>。 虽然 PLINQ 和 TPL 将永远不会传递中`partitionCount`等于 0，我们仍然建议抵御可能会出现。  
  
-   <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>和<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>应始终返回`partitionsCount`的分区数。 如果分区程序用完了数据，并且无法创建请求的所有分区，该方法应返回一个空枚举器的每个剩余的分区。 否则，PLINQ 和 TPL 会引发<xref:System.InvalidOperationException>。  
  
-   <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A><xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>， <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>，和<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>永远不应返回`null`(`Nothing`在 Visual Basic 中)。 如果他们这样做，PLINQ / TPL 将引发<xref:System.InvalidOperationException>。  
  
-   返回分区的方法应始终返回可以完全并唯一地枚举数据源的分区。 除非特别需要程序设计的分区程序，应为数据源或跳过的项目中没有重复。 如果未遵循此规则，则输出顺序可能会混乱。  
  
-   以便不会输出顺序混乱，以下布尔 getter 必须始终准确地返回以下值：  
  
    -   `KeysOrderedInEachPartition`： 每个分区返回不断增加的键索引的元素。  
  
    -   `KeysOrderedAcrossPartitions`： 适用于将返回分区中的密钥索引的所有分区*我*高于中分区的键索引*我*-1。  
  
    -   `KeysNormalized`： 所有键索引单调递增没有间隔，从零开始。  
  
-   所有索引必须都是唯一的。 不可能重复的索引。 如果未遵循此规则，则输出顺序可能会混乱。  
  
-   所有索引必须都为非负数。 如果未遵循此规则，则 PLINQ/TPL 可能会引发异常。  
  
## <a name="see-also"></a>另请参阅  
 [并行编程](../../../docs/standard/parallel-programming/index.md)  
 [如何：实现动态分区](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md)  
 [如何：实现静态分区程序](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
