---
title: "PLINQ 介绍"
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
helpviewer_keywords: PLINQ queries, introduction to
ms.assetid: eaa720d8-8999-4eb7-8df5-3c19ca61cad0
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: db9c3e16d4a8073fbce636f37490f719dbd93e4d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="introduction-to-plinq"></a>PLINQ 介绍
## <a name="what-is-a-parallel-query"></a>什么是并行查询？  
 [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)] 中引入了语言集成查询 (LINQ)。  它提供了用于查询任何的统一的模型<xref:System.Collections.IEnumerable?displayProperty=nameWithType>或<xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>类型安全的方式的数据源。 LINQ to 对象是如运行针对内存中集合的 LINQ 查询的名称<xref:System.Collections.Generic.List%601>和数组。 本文假定你对 LINQ 有基本的了解。 有关详细信息，请参阅 [LINQ（语言集成查询）](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)。  
  
 并行 LINQ (PLINQ) 是 LINQ 模式的并行实现。 一个 PLINQ 查询的许多方面都类似于非并行的 LINQ to Objects 查询。 PLINQ 查询，就像顺序[!INCLUDE[vbteclinq](../../../includes/vbteclinq-md.md)]查询，是对任何在内存<xref:System.Collections.IEnumerable>或<xref:System.Collections.Generic.IEnumerable%601>数据源，并具有延迟执行，这意味着它们不开始执行，直至枚举查询。 主要区别在于，PLINQ 会尝试充分利用系统上的所有处理器。 方法是将数据源分区成片段，然后在多个处理器上针对单独工作线程上的每个片段执行并行查询。 在许多情况下，并行执行意味着查询运行速度显著提高。  
  
 通过并行执行，PLINQ 可以通过为某些种类的查询，通常只需添加的旧代码实现显著的性能改进<xref:System.Linq.ParallelEnumerable.AsParallel%2A>查询到数据源的操作。 但是，并行可能会引入其自身的复杂性，因此并非所有的查询操作的运行速度在 PLINQ 中都更快。 事实上，并行实际上会降低某些查询的速度。 因此，应了解排序等问题将如何对并行查询产生影响。 有关详细信息，请参阅[了解 PLINQ 中的加速](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)。  
  
> [!NOTE]
>  本文档使用 lambda 表达式在 PLINQ 中定义委托。 如果不熟悉 C# 或 Visual Basic 中的 lambda 表达式，请参阅 [PLINQ 和 TPL 中的 Lambda 表达式](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)。  
  
 本文的其余部分将概述主 PLINQ 类，并讨论如何创建 PLINQ 查询。 每部分包含指向更详细信息以及代码示例的链接。  
  
## <a name="the-parallelenumerable-class"></a>ParallelEnumerable 类  
 <xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType>类会公开几乎所有 PLINQ 的功能。  它与其余<xref:System.Linq?displayProperty=nameWithType>命名空间类型被编译到 System.Core.dll 程序集。 Visual Studio 中默认的 C# 和 Visual Basic 项目均会引用该程序集并导入该命名空间。  
  
 <xref:System.Linq.ParallelEnumerable>尽管它不会尝试并行化每个包括 LINQ to Objects 支持中的所有标准查询运算符的实现。 如果不熟悉 [!INCLUDE[vbteclinq](../../../includes/vbteclinq-md.md)]，请参阅 [LINQ 简介](http://msdn.microsoft.com/library/24dddf19-12a0-4707-a4bc-eba4fa7f219e)。  
  
 除了标准查询运算符，<xref:System.Linq.ParallelEnumerable>类包含一组启用特定于并行执行的行为的方法。 下表中列出了这些特定于 PLINQ 的方法。  
  
|ParallelEnumerable 运算符|描述|  
|---------------------------------|-----------------|  
|<xref:System.Linq.ParallelEnumerable.AsParallel%2A>|PLINQ 的入口点。 指定如果可能，应并行化查询的其余部分。|  
|<xref:System.Linq.ParallelEnumerable.AsSequential%2A>|指定查询的其余部分应像非并行的 LINQ 查询一样按顺序运行。|  
|<xref:System.Linq.ParallelEnumerable.AsOrdered%2A>|指定 PLINQ 应为查询的其余部分保留源序列的排序，或直到例如通过使用 orderby（在 Visual Basic 中为 Order By）子句更改排序为止。|  
|<xref:System.Linq.ParallelEnumerable.AsUnordered%2A>|指定保留源序列的排序不需要查询其余部分的 PLINQ。|  
|<xref:System.Linq.ParallelEnumerable.WithCancellation%2A>|指定 PLINQ 应定期监视请求取消时所提供的取消标记的状态以及取消执行。|  
|<xref:System.Linq.ParallelEnumerable.WithDegreeOfParallelism%2A>|指定 PLINQ 应用于并行化查询的处理器的最大数量。|  
|<xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A>|提供有关 PLINQ 应如何（如果可能）将并行结果合并回使用线程上的一个序列的提示。|  
|<xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A>|指定 PLINQ 应如何并行化查询（即使是当默认行为是按顺序运行查询时）。|  
|<xref:System.Linq.ParallelEnumerable.ForAll%2A>|一种多线程枚举方法，与循环访问查询结果不同，它允许在不首先合并回使用者线程的情况下并行处理结果。|  
|<xref:System.Linq.ParallelEnumerable.Aggregate%2A>重载|对于 PLINQ 唯一的重载，它启用对线程本地分区的中间聚合以及一个用于合并所有分区结果的最终聚合函数。|  
  
## <a name="the-opt-in-model"></a>选择使用模型  
 当你编写查询时，来选择使用 PLINQ 通过调用<xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=nameWithType>上数据源，如下面的示例中所示的扩展方法。  
  
 [!code-csharp[PLINQ#1](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#1)]
 [!code-vb[PLINQ#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#1)]  
  
 <xref:System.Linq.ParallelEnumerable.AsParallel%2A>扩展方法将在此情况下，绑定的后续查询运算符，`where`和`select`到<xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType>实现。  
  
## <a name="execution-modes"></a>执行模式  
 默认情况下，PLINQ 是保守的。 在运行时，PLINQ 基础结构将分析查询的总体结构。 如果通过并行可能会提高查询速度，PLINQ 则将源序列分区为可以同时运行的任务。 如果并行化查询不安全，PLINQ 则只会按顺序运行查询。 如果 PLINQ 可以在可能会较昂贵的并行算法或成本较低的顺序算法之间进行选择，它会默认选择顺序算法。 你可以使用<xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A>方法和<xref:System.Linq.ParallelExecutionMode?displayProperty=nameWithType>枚举，以指示 PLINQ 选择的并行算法。 如果你通过测试和测量知道特定查询以并行方式执行得更快时，此做法非常有用。 有关详细信息，请参阅[如何：在 PLINQ 中指定执行模式](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md)。  
  
## <a name="degree-of-parallelism"></a>并行度  
 默认情况下，PLINQ 使用所有处理器的主机计算机上。 你可以指示 PLINQ 用于不能超过指定数目的处理器使用<xref:System.Linq.ParallelEnumerable.WithDegreeOfParallelism%2A>方法。 当你要确保计算机上运行的其他进程收到一定的 CPU 时间量时，此做法将非常有用。 下面的片段将查询限制为最多使用两个处理器。  
  
 [!code-csharp[PLINQ#5](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#5)]
 [!code-vb[PLINQ#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#5)]  
  
 在查询要执行大量非受计算限制的工作（如文件 I/O）的情况下，最好指定比计算机上的内核数要大的并行度。  
  
## <a name="ordered-versus-unordered-parallel-queries"></a>已排序和未排序的并行查询  
 在某些查询中，一个查询运算符必须产生保留源序列排序的结果。 PLINQ 提供<xref:System.Linq.ParallelEnumerable.AsOrdered%2A>为此目的的运算符。 <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>不同于<xref:System.Linq.ParallelEnumerable.AsSequential%2A>。 <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>序列仍并行处理的但其结果进行缓冲和排序。 顺序保留通常包含额外工作，因为<xref:System.Linq.ParallelEnumerable.AsOrdered%2A>序列可能会更慢于默认处理<xref:System.Linq.ParallelEnumerable.AsUnordered%2A>序列。 特定的已排序并行操作是否比操作的顺序版本更快取决于许多因素。  
  
 下面的代码示例演示了如何选择使用顺序保留。  
  
 [!code-csharp[PLINQ#3](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#3)]
 [!code-vb[PLINQ#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#3)]  
  
 有关详细信息，请参阅 [PLINQ 中的顺序保留](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md)。  
  
## <a name="parallel-vs-sequential-queries"></a>并行和顺序查询  
 某些操作要求按顺序提供源数据。 <xref:System.Linq.ParallelEnumerable>查询运算符转换为顺序模式自动需要时。 对于用户定义的查询运算符，需要顺序执行的用户委托 PLINQ 提供<xref:System.Linq.ParallelEnumerable.AsSequential%2A>方法。 当你使用<xref:System.Linq.ParallelEnumerable.AsSequential%2A>，在查询中的所有后续运算符按顺序执行，直到<xref:System.Linq.ParallelEnumerable.AsParallel%2A>会再次调用。 有关详细信息，请参阅[如何：合并并行和顺序 LINQ 查询](../../../docs/standard/parallel-programming/how-to-combine-parallel-and-sequential-linq-queries.md)。  
  
## <a name="options-for-merging-query-results"></a>合并查询结果的选项  
 当一个 PLINQ 查询并行执行时，它从每个工作线程得到的结果必须合并回到主线程上，以便由 `foreach` 循环（在 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 中为 `For Each`）使用或插入到列表或数组中。 例如在某些情况下，指定一个特定类型的合并操作可能会有好处，以更快地开始产生结果。 PLINQ 支持用于此目的，<xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A>方法，与<xref:System.Linq.ParallelMergeOptions>枚举。 有关详细信息，请参阅 [PLINQ 中的合并选项](../../../docs/standard/parallel-programming/merge-options-in-plinq.md)。  
  
## <a name="the-forall-operator"></a>ForAll 运算符  
 在顺序[!INCLUDE[vbteclinq](../../../includes/vbteclinq-md.md)]查询中，执行将推迟，直到枚举查询在`foreach`(`For Each`中[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) 循环，或通过调用方法如<xref:System.Linq.ParallelEnumerable.ToList%2A>， <xref:System.Linq.ParallelEnumerable.ToArray%2A> ，或<xref:System.Linq.ParallelEnumerable.ToDictionary%2A>。 在 PLINQ 中，还可以使用 `foreach` 执行查询以及循环访问结果。 但是，`foreach` 本身不会并行运行，因此，它要求将所有并行任务的输出合并回该循环正在上面运行的线程中。 在 PLINQ 中，在必须保留查询结果的最终排序，以及以按串行方式处理结果时，例如当为每个元素调用 `Console.WriteLine` 时，则可以使用 `foreach`。 对于更快地不需要顺序保留时查询执行并时结果的处理本身可并行化，使用<xref:System.Linq.ParallelEnumerable.ForAll%2A>方法来执行 PLINQ 查询。 <xref:System.Linq.ParallelEnumerable.ForAll%2A>不执行此最终合并步骤。 下面的代码示例说明如何使用 <xref:System.Linq.ParallelEnumerable.ForAll%2A> 方法。 <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>此处之所以使用，因为它非常适合而不会尝试删除任何项同时添加多个线程。  
  
 [!code-csharp[PLINQ#4](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#4)]
 [!code-vb[PLINQ#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#4)]  
  
 下图显示之间的差异`foreach`和<xref:System.Linq.ParallelEnumerable.ForAll%2A>在查询执行方面。  
  
 ![ForAll 与ForEach](../../../docs/standard/parallel-programming/media/vs-isvnt-allvseach.png "VS_ISVNT_ALLvsEACH")  
  
## <a name="cancellation"></a>取消  
 PLINQ 在 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 中与取消类型集成在一起。 （有关详细信息，请参阅[托管线程中的取消](../../../docs/standard/threading/cancellation-in-managed-threads.md)。）因此，与顺序 LINQ to Objects 查询不同，可以取消 PLINQ 查询。 若要创建可取消 PLINQ 查询，使用<xref:System.Linq.ParallelEnumerable.WithCancellation%2A>查询运算符，并提供<xref:System.Threading.CancellationToken>作为自变量的实例。 当<xref:System.Threading.CancellationToken.IsCancellationRequested%2A>令牌上的属性设置为 true，PLINQ 将注意到它、 停止在所有线程上处理和引发<xref:System.OperationCanceledException>。  
  
 在设置取消标记后，PLINQ 查询还可能会继续处理一些元素。  
  
 为了提高响应速度，还可以在长时间运行的用户委托中响应取消请求。 有关详细信息，请参阅[如何：取消 PLINQ 查询](../../../docs/standard/parallel-programming/how-to-cancel-a-plinq-query.md)。  
  
## <a name="exceptions"></a>异常  
 当一个 PLINQ 查询执行时，可能会同时从不同的线程引发多个异常。 此外，处理异常的代码可能与引发异常的代码处于不同的线程上。 PLINQ 使用<xref:System.AggregateException>要类型封装由一个查询，引发的所有异常，因此封送回调用线程这些异常。 在调用线程上，只需要一个 try-catch 块。 但是，你可以循环访问的所有异常的封装在<xref:System.AggregateException>和捕获任何可以安全地从中恢复。 在极少数情况下，一些例外情况可能会引发未包装在<xref:System.AggregateException>，和<xref:System.Threading.ThreadAbortException>s 也不包装。  
  
 如果允许异常向上冒泡回到联接线程，则查询也许可以在引发异常后继续处理一些项。  
  
 有关详细信息，请参阅[如何：处理 PLINQ 查询中的异常](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md)。  
  
## <a name="custom-partitioners"></a>自定义分区程序  
 在某些情况下，可以通过编写利用源数据的某些特征的自定义分区程序来提高查询性能。 在查询中，自定义分区程序本身是被查询的可枚举对象。  
  
 [!code-csharp[PLINQ#2](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#2)]
 [!code-vb[PLINQ#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq3.vb#2)]  
  
 PLINQ 支持固定数量的分区（尽管在运行时期间为了负载均衡可能会将数据重新动态分配到这些分区）。 <xref:System.Threading.Tasks.Parallel.For%2A>和<xref:System.Threading.Tasks.Parallel.ForEach%2A>支持仅动态分区，这意味着分区更改的数量在运行时。 有关详细信息，请参阅 [PLINQ 和 TPL 的自定义分区程序](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)。  
  
## <a name="measuring-plinq-performance"></a>衡量 PLINQ 性能  
 在很多情况下，可以并行化查询，但是设置并行查询的开销可能会超出获得的性能收益。 如果查询不执行大量的计算，或者如果数据源较小，则 PLINQ 查询的速度可能比顺序 LINQ to Objects 查询的速度慢。 可以在 Visual Studio Team Server 中使用并行性能分析器比较各种查询的性能，查找处理瓶颈，以及确定查询是并行运行还是按顺序运行。 有关详细信息，请参阅[并发可视化工具](/visualstudio/profiling/concurrency-visualizer)和[如何：衡量 PLINQ 查询性能](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md)。  
  
## <a name="see-also"></a>另请参阅  
 [并行 LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [了解 PLINQ 中的加速](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)
