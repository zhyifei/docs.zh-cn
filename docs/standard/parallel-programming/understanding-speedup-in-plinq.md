---
title: "了解 PLINQ 中的加速"
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
helpviewer_keywords: PLINQ queries, performance tuning
ms.assetid: 53706c7e-397d-467a-98cd-c0d1fd63ba5e
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c3373cb6a2c535bd7d42eb062e1f9727952f7cfb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="understanding-speedup-in-plinq"></a>了解 PLINQ 中的加速
PLINQ 的主要目的是为了加快执行 LINQ 对对象查询通过在多核计算机上的并行执行查询委托。 PLINQ 的性能最佳时源集合中每个元素的处理是独立的不涉及各个委托之间的共享状态。 此类操作在 LINQ to Objects 与 PLINQ 中, 很常见和通常称为"*适合并行*"因为它们有助于使自身轻松地在多个线程上执行计划。 但是，并非所有查询都包含完全适合并行操作;在大多数情况下，查询涉及到或者无法并行化，或的速度变慢并行执行某些运算符。 和完全适合并行的查询，即使使用 PLINQ 必须仍分区的数据源，并在上计划工作线程，并通常合并结果，查询完成时。 所有这些操作将添加到并行化; 的计算成本添加并行化的这些成本称为*开销*。 若要实现最佳性能 PLINQ 查询中的，目标是最大化适合并行的部分并最大程度减少需要开销的部分。 本文提供了将帮助你编写时仍然能产生正确的结果会尽可能高效的 PLINQ 查询的信息。  
  
## <a name="factors-that-impact-plinq-query-performance"></a>影响 PLINQ 查询性能的因素  
 下列各节列出了一些最重要的因素影响并行查询性能。 这些是常规的语句，仅凭不足以预测在所有情况下的查询性能。 与往常一样，它进行测量非常重要的计算机上的特定查询的代表性配置和负载的一系列的实际性能。  
  
1.  整体工作的计算成本。  
  
     若要实现加速，PLINQ 查询必须具有足够的适合并行工作来弥补开销。 工作可以表示为每个委托的源集合中的元素数的乘积的计算成本。 假设操作可以并行化，更占用计算开销很，较大的一个加速的可能性。 例如，如果函数采用一个毫秒执行，超过 1000 个元素将只采用一个秒的时间来执行该操作，而四个核心的计算机上进行的并行查询的顺序查询可能需要仅 250 毫秒。 这会生成 750 毫秒的加速。 如果该函数需要一个秒的时间来执行的每个元素，则加速将为 750 秒。 如果委托代价很高，PLINQ 可能会提供与只有几项源集合中的明显加快。 相反，使用普通的委托的小源集合通常不是最适合 PLINQ。  
  
     在下面的示例中，queryA 可能是很适合 PLINQ 中，假定其选择的功能，包括大量工作。 queryB 可能并不是很好的候选项，因为没有足够的 Select 语句中的工作和并行化的开销将偏移量的速度提高大部分或全部。  
  
    ```vb  
    Dim queryA = From num In numberList.AsParallel()  
                 Select ExpensiveFunction(num); 'good for PLINQ  
  
    Dim queryB = From num In numberList.AsParallel()  
                 Where num Mod 2 > 0  
                 Select num; 'not as good for PLINQ  
    ```  
  
    ```csharp  
    var queryA = from num in numberList.AsParallel()  
                 select ExpensiveFunction(num); //good for PLINQ  
  
    var queryB = from num in numberList.AsParallel()  
                 where num % 2 > 0  
                 select num; //not as good for PLINQ  
    ```  
  
2.  系统 （并行度） 上的逻辑内核数。  
  
     此点是上一节显而易见的必然结果，适合并行的查询更快地在计算机上运行具有更多内核因为更多的并发线程间设置可划分工作。 加速整体量取决于查询的整体工作的百分比是可并行化。 但是，不会假定两次作为将运行所有查询快速上四核计算机八核计算机。 当优化查询以获得最佳性能，务必衡量具有多个内核的计算机上的实际结果。 此点与相关点 #1： 大型数据集所需利用更多的计算资源。  
  
3.  数量和类型的操作。  
  
     PLINQ 提供 AsOrdered 运算符的情况下它有必要保留源序列中的元素的顺序。 排序，会带来开销，但此开销通常是适度。 GroupBy 和联接操作同样会产生开销。 它允许处理按任意顺序，对源集合中的元素并将它们传递到下一步的运算符，只要准备好时，PLINQ 的性能最佳。 有关详细信息，请参阅 [PLINQ 中的顺序保留](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md)。  
  
4.  查询执行的窗体。  
  
     如果你要通过调用 ToArray 或 ToList 存储查询的结果，所有并行线程的结果必须合并到单个数据结构。 这涉及到不可避免的计算成本。 同样，如果通过使用 （用于在 Visual Basic 中的每个） 的 foreach 循环中循环结果，则需要从工作线程的结果在枚举器线程序列化。 但如果你只是想要执行一些操作基于每个线程的结果，你可以使用 ForAll 方法以在多个线程上执行此工作。  
  
5.  合并选项的类型。  
  
     PLINQ 可以配置为缓冲其输出，并生成它小区块中或在一次后整个结果集生成，或者到流单个结果产生。 以前的结果是降低总执行时间，而后者生成元素之间的降低延迟。  虽然的合并选项并不总是有重大影响总体查询性能，它们可以影响感知的性能，因为它们控制多长时间的用户必须等待以查看结果。 有关详细信息，请参阅 [PLINQ 中的合并选项](../../../docs/standard/parallel-programming/merge-options-in-plinq.md)。  
  
6.  分区的种类。  
  
     在某些情况下，可建立索引的源集合的 PLINQ 查询可能会导致不平衡的工作负载。 当发生这种情况时，你可以通过创建自定义分区程序来提高查询性能。 有关详细信息，请参阅 [PLINQ 和 TPL 的自定义分区程序](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)。  
  
## <a name="when-plinq-chooses-sequential-mode"></a>当 PLINQ 选择顺序模式  
 PLINQ 将始终尝试执行至少速度一样快查询将按顺序运行查询。 尽管 PLINQ 不会计算查找如何昂贵的用户委托，或者如何大输入的源，它看起来一查询"形状"。 具体而言，它查找查询运算符或通常会导致要在并行模式下执行速度更慢的查询运算符的组合。 当它找到此类形状时，默认情况下的 PLINQ 回退到顺序模式。  
  
 但是，在衡量特定查询的性能，可能会确定，它实际上更快地在并行模式下运行。 在这种情况下可以使用<xref:System.Linq.ParallelExecutionMode.ForceParallelism?displayProperty=nameWithType>标志通过<xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A>方法以指示 PLINQ 并行执行查询。 有关详细信息，请参阅[如何：在 PLINQ 中指定执行模式](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md)。  
  
 以下列表描述 PLINQ 默认情况下的会在顺序模式中执行的查询形状：  
  
-   包含 Select、 查询，其中，索引索引的 SelectMany，或已删除或重新排列原始索引的排序或筛选运算符后的 ElementAt 子句。  
  
-   查询包含的 Take、 TakeWhile，跳过，SkipWhile 运算符和源序列中的索引不按原始顺序。  
  
-   包含 Zip 或 SequenceEquals 的查询，除非其中一个数据源具有按原始顺序排列的索引，并且另一个数据源是可索引的（即，数组或 IList(T)）。  
  
-   包含 Concat，除非将其应用到可索引数据源的查询。  
  
-   包含反向，除非应用到可索引数据源的查询。  
  
## <a name="see-also"></a>另请参阅  
 [并行 LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
