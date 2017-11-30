---
title: "PLINQ 的潜在缺陷"
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
helpviewer_keywords: PLINQ queries, pitfalls
ms.assetid: 75a38b55-4bc4-488a-87d5-89dbdbdc76a2
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f7c971d2c039e6441669108e966eba472819fde5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="potential-pitfalls-with-plinq"></a>PLINQ 的潜在缺陷
在许多情况下，PLINQ 可以通过向对象查询的顺序 LINQ 提供显著的性能改进。 但是，并行查询执行的工作引入可能导致问题，在顺序代码中，一些不太常见或根本不会遇到的复杂性。 本主题列出了一些要避免编写 PLINQ 查询时的做法。  
  
## <a name="do-not-assume-that-parallel-is-always-faster"></a>不要假定并行的速度始终更快  
 并行化有时会导致 PLINQ 查询运行速度减慢比其 LINQ 为对象等效项。 基本的经验法则是，具有很少的源元素和快速用户委托的查询未必会快得多。 但是，由于性能涉及很多原因，我们建议你决定是否使用 PLINQ 之前，测量实际结果。 有关详细信息，请参阅[了解 PLINQ 中的加速](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)。  
  
## <a name="avoid-writing-to-shared-memory-locations"></a>避免写入共享内存位置  
 在顺序代码中，从静态变量或类字段中读取或写入静态变量或类字段的情况很常见。 但是，每当多个线程同时访问此类变量时，则很有可能会出现争用条件。 即使可以使用锁来同步对变量的访问，但同步开销可能会对性能造成损害。 因此，我们建议您避免，或至少限制，访问为共享的尽可能多地 PLINQ 查询中的状态。  
  
## <a name="avoid-over-parallelization"></a>避免过度并行化  
 通过使用`AsParallel`运算符，你会产生分区源集合和同步的工作线程的开销。 计算机上的处理器数量进一步限制了并行化的优点。 仅在一个处理器上运行多个受计算限制的线程时，速度并不会得到提升。 因此，你必须注意不要过度并行化查询。  
  
 最常见的方案中可能发生的过度并行化是在嵌套查询中，如下面的代码段中所示。  
  
 [!code-csharp[PLINQ#20](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#20)]
 [!code-vb[PLINQ#20](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#20)]  
  
 在这种情况下，最好是并行化仅对外部数据源 （客户），除非一个或多个以下条件适用：  
  
-   内部数据源 （客户。Orders) 已知会很长。  
  
-   正在对每个订单执行开销极大的计算。 （示例中所示的操作开销不大。）  
  
-   已知目标系统具有足够的处理器来处理通过对 `cust.Orders` 上的查询进行并行化所产生的线程数。  
  
 在所有情况下，确定最佳查询形式的最好方法是进行测试和测量。 有关详细信息，请参阅[How to： 度量值 PLINQ 查询性能](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md)。  
  
## <a name="avoid-calls-to-non-thread-safe-methods"></a>避免调用非线程安全方法  
 写入的非线程安全实例方法，从 PLINQ 查询可能会导致数据损坏可能或可能不会在程序中未检测到。 还可能会导致异常。 在下面的示例中，将尝试多个线程进行调用`Filestream.Write`方法同时，这不受支持类。  
  
```vb  
Dim fs As FileStream = File.OpenWrite(…)  
a.Where(...).OrderBy(...).Select(...).ForAll(Sub(x) fs.Write(x))  
```  
  
```csharp  
FileStream fs = File.OpenWrite(...);  
a.Where(...).OrderBy(...).Select(...).ForAll(x => fs.Write(x));  
```  
  
## <a name="limit-calls-to-thread-safe-methods"></a>限制调用线程安全方法  
 .NET Framework 中的大多数静态方法是线程安全的，并且可以同时从多个线程中调用。 但是，即使在这些情况下，所涉及到的同步也可能会导致查询速度大幅度下降。  
  
> [!NOTE]
>  你可以对此进行测试自己的方法是插入到一些调用<xref:System.Console.WriteLine%2A>在您的查询。 尽管此方法用于在文档的示例演示目的，不要使用它在 PLINQ 查询中。  
  
## <a name="avoid-unnecessary-ordering-operations"></a>避免不必要的排序操作  
 当 PLINQ 并行执行查询时，它将源序列划分成可以处理同时在多个线程的分区。 默认情况下，处理这些分区和提供结果时的顺序不是可预测 (除外运算符，如`OrderBy`)。 你可以指示 PLINQ 中保留的任何源序列中，排序，但这对性能有负面影响。 最佳做法，只要有可能，是结构查询，以便它们不依赖于顺序保留。 有关详细信息，请参阅 [PLINQ 中的顺序保留](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md)。  
  
## <a name="prefer-forall-to-foreach-when-it-is-possible"></a>ForEach 时很可能希望 ForAll  
 尽管 PLINQ 在如果你使用中的结果在多个线程上执行查询`foreach`循环 (`For Each`在 Visual Basic 中)，必须合并回一个线程查询结果，并将其按顺序访问枚举器。 在某些情况下，这是不可避免地;但是，只要可能，使用`ForAll`方法，以使每个线程输出其自己的结果，例如，通过将写入的线程安全集合，如<xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>。  
  
 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> 也有同样的问题。换言之，强烈建议应首选使用 `source.AsParallel().Where().ForAll(...)`  
  
 `Parallel.ForEach(source.AsParallel().Where(), ...)`。  
  
## <a name="be-aware-of-thread-affinity-issues"></a>注意线程关联问题  
 某些技术（例如，单线程单元 (STA) 组件的 COM 互操作性、Windows 窗体以及 Windows Presentation Foundation (WPF)）具有要求代码在特定线程上运行的线程关联限制。 例如，在 Windows 窗体和 WPF 中，只能在创建控件的线程上访问该控件。 如果你尝试访问的共享的状态的 PLINQ 查询中的 Windows 窗体控件，如果你正在运行在调试器中被引发异常。 （此设置可以关闭。）但是，如果 UI 线程上使用您的查询，然后你可以访问该控件从`foreach`枚举查询的循环会造成，因为该代码仅在一个线程上执行。  
  
## <a name="do-not-assume-that-iterations-of-foreach-for-and-forall-always-execute-in-parallel"></a>不要假定 ForEach、For 和 ForAll 的迭代始终并行执行  
 务必要记住该中的个别迭代<xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>，<xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>或<xref:System.Linq.ParallelEnumerable.ForAll%2A>循环可能但不是需要并行执行。 因此，应避免编写任何依赖于迭代并行执行的正确性或依赖于按任何特定顺序执行迭代的代码。  
  
 例如，此代码有可能会死锁：  
  
```vb  
Dim mre = New ManualResetEventSlim()  
    Enumerable.Range(0, ProcessorCount * 100).AsParallel().ForAll(Sub(j)   
  
                                                     If j = Environment.ProcessorCount Then  
  
                                                         Console.WriteLine("Set on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j)  
                                                         mre.Set()  
  
                                                     Else  
  
                                                         Console.WriteLine("Waiting on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j)  
                                                         mre.Wait()  
                                                     End If  
    End Sub) ' deadlocks  
```  
  
```csharp  
ManualResetEventSlim mre = new ManualResetEventSlim();  
            Enumerable.Range(0, ProcessorCount * 100).AsParallel().ForAll((j) =>  
            {  
                if (j == Environment.ProcessorCount)  
                {  
                    Console.WriteLine("Set on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j);  
                    mre.Set();  
                }  
                else  
                {  
                    Console.WriteLine("Waiting on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j);  
                    mre.Wait();  
                }  
            }); //deadlocks  
```  
  
 在此示例中，一个迭代设置一个事件，而所有的其他迭代则等待该事件。 在设置事件的迭代完成之前，任何等待迭代均无法完成。 但是，在设置事件的迭代有机会执行之前，等待迭代可能会阻止用于执行并行循环的所有线程。 这将导致死锁 – 设置事件的迭代将永不会执行，并且等待迭代将永远不会醒来。  
  
 具体而言，并行循环的一个迭代绝不应该等待循环的另一个迭代来继续执行。 如果并行循环决定按相反的顺序安排迭代，则会发生死锁。  
  
## <a name="see-also"></a>另请参阅  
 [并行 LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
