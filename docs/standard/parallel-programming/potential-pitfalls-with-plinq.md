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
# <a name="potential-pitfalls-with-plinq"></a><span data-ttu-id="117da-102">PLINQ 的潜在缺陷</span><span class="sxs-lookup"><span data-stu-id="117da-102">Potential Pitfalls with PLINQ</span></span>
<span data-ttu-id="117da-103">在许多情况下，PLINQ 可以通过向对象查询的顺序 LINQ 提供显著的性能改进。</span><span class="sxs-lookup"><span data-stu-id="117da-103">In many cases, PLINQ can provide significant performance improvements over sequential LINQ to Objects queries.</span></span> <span data-ttu-id="117da-104">但是，并行查询执行的工作引入可能导致问题，在顺序代码中，一些不太常见或根本不会遇到的复杂性。</span><span class="sxs-lookup"><span data-stu-id="117da-104">However, the work of parallelizing the query execution introduces complexity that can lead to problems that, in sequential code, are not as common or are not encountered at all.</span></span> <span data-ttu-id="117da-105">本主题列出了一些要避免编写 PLINQ 查询时的做法。</span><span class="sxs-lookup"><span data-stu-id="117da-105">This topic lists some practices to avoid when you write PLINQ queries.</span></span>  
  
## <a name="do-not-assume-that-parallel-is-always-faster"></a><span data-ttu-id="117da-106">不要假定并行的速度始终更快</span><span class="sxs-lookup"><span data-stu-id="117da-106">Do Not Assume That Parallel Is Always Faster</span></span>  
 <span data-ttu-id="117da-107">并行化有时会导致 PLINQ 查询运行速度减慢比其 LINQ 为对象等效项。</span><span class="sxs-lookup"><span data-stu-id="117da-107">Parallelization sometimes causes a PLINQ query to run slower than its LINQ to Objects equivalent.</span></span> <span data-ttu-id="117da-108">基本的经验法则是，具有很少的源元素和快速用户委托的查询未必会快得多。</span><span class="sxs-lookup"><span data-stu-id="117da-108">The basic rule of thumb is that queries that have few source elements and fast user delegates are unlikely to speedup much.</span></span> <span data-ttu-id="117da-109">但是，由于性能涉及很多原因，我们建议你决定是否使用 PLINQ 之前，测量实际结果。</span><span class="sxs-lookup"><span data-stu-id="117da-109">However, because many factors are involved in performance, we recommend that you measure actual results before you decide whether to use PLINQ.</span></span> <span data-ttu-id="117da-110">有关详细信息，请参阅[了解 PLINQ 中的加速](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)。</span><span class="sxs-lookup"><span data-stu-id="117da-110">For more information, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="avoid-writing-to-shared-memory-locations"></a><span data-ttu-id="117da-111">避免写入共享内存位置</span><span class="sxs-lookup"><span data-stu-id="117da-111">Avoid Writing to Shared Memory Locations</span></span>  
 <span data-ttu-id="117da-112">在顺序代码中，从静态变量或类字段中读取或写入静态变量或类字段的情况很常见。</span><span class="sxs-lookup"><span data-stu-id="117da-112">In sequential code, it is not uncommon to read from or write to static variables or class fields.</span></span> <span data-ttu-id="117da-113">但是，每当多个线程同时访问此类变量时，则很有可能会出现争用条件。</span><span class="sxs-lookup"><span data-stu-id="117da-113">However, whenever multiple threads are accessing such variables concurrently, there is a big potential for race conditions.</span></span> <span data-ttu-id="117da-114">即使可以使用锁来同步对变量的访问，但同步开销可能会对性能造成损害。</span><span class="sxs-lookup"><span data-stu-id="117da-114">Even though you can use locks to synchronize access to the variable, the cost of synchronization can hurt performance.</span></span> <span data-ttu-id="117da-115">因此，我们建议您避免，或至少限制，访问为共享的尽可能多地 PLINQ 查询中的状态。</span><span class="sxs-lookup"><span data-stu-id="117da-115">Therefore, we recommend that you avoid, or at least limit, access to shared state in a PLINQ query as much as possible.</span></span>  
  
## <a name="avoid-over-parallelization"></a><span data-ttu-id="117da-116">避免过度并行化</span><span class="sxs-lookup"><span data-stu-id="117da-116">Avoid Over-Parallelization</span></span>  
 <span data-ttu-id="117da-117">通过使用`AsParallel`运算符，你会产生分区源集合和同步的工作线程的开销。</span><span class="sxs-lookup"><span data-stu-id="117da-117">By using the `AsParallel` operator, you incur the overhead costs of partitioning the source collection and synchronizing the worker threads.</span></span> <span data-ttu-id="117da-118">计算机上的处理器数量进一步限制了并行化的优点。</span><span class="sxs-lookup"><span data-stu-id="117da-118">The benefits of parallelization are further limited by the number of processors on the computer.</span></span> <span data-ttu-id="117da-119">仅在一个处理器上运行多个受计算限制的线程时，速度并不会得到提升。</span><span class="sxs-lookup"><span data-stu-id="117da-119">There is no speedup to be gained by running multiple compute-bound threads on just one processor.</span></span> <span data-ttu-id="117da-120">因此，你必须注意不要过度并行化查询。</span><span class="sxs-lookup"><span data-stu-id="117da-120">Therefore, you must be careful not to over-parallelize a query.</span></span>  
  
 <span data-ttu-id="117da-121">最常见的方案中可能发生的过度并行化是在嵌套查询中，如下面的代码段中所示。</span><span class="sxs-lookup"><span data-stu-id="117da-121">The most common scenario in which over-parallelization can occur is in nested queries, as shown in the following snippet.</span></span>  
  
 [!code-csharp[PLINQ#20](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#20)]
 [!code-vb[PLINQ#20](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#20)]  
  
 <span data-ttu-id="117da-122">在这种情况下，最好是并行化仅对外部数据源 （客户），除非一个或多个以下条件适用：</span><span class="sxs-lookup"><span data-stu-id="117da-122">In this case, it is best to parallelize only the outer data source (customers) unless one or more of the following conditions apply:</span></span>  
  
-   <span data-ttu-id="117da-123">内部数据源 （客户。Orders) 已知会很长。</span><span class="sxs-lookup"><span data-stu-id="117da-123">The inner data source (cust.Orders) is known to be very long.</span></span>  
  
-   <span data-ttu-id="117da-124">正在对每个订单执行开销极大的计算。</span><span class="sxs-lookup"><span data-stu-id="117da-124">You are performing an expensive computation on each order.</span></span> <span data-ttu-id="117da-125">（示例中所示的操作开销不大。）</span><span class="sxs-lookup"><span data-stu-id="117da-125">(The operation shown in the example is not expensive.)</span></span>  
  
-   <span data-ttu-id="117da-126">已知目标系统具有足够的处理器来处理通过对 `cust.Orders` 上的查询进行并行化所产生的线程数。</span><span class="sxs-lookup"><span data-stu-id="117da-126">The target system is known to have enough processors to handle the number of threads that will be produced by parallelizing the query on `cust.Orders`.</span></span>  
  
 <span data-ttu-id="117da-127">在所有情况下，确定最佳查询形式的最好方法是进行测试和测量。</span><span class="sxs-lookup"><span data-stu-id="117da-127">In all cases, the best way to determine the optimum query shape is to test and measure.</span></span> <span data-ttu-id="117da-128">有关详细信息，请参阅[How to： 度量值 PLINQ 查询性能](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="117da-128">For more information, see [How to: Measure PLINQ Query Performance](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).</span></span>  
  
## <a name="avoid-calls-to-non-thread-safe-methods"></a><span data-ttu-id="117da-129">避免调用非线程安全方法</span><span class="sxs-lookup"><span data-stu-id="117da-129">Avoid Calls to Non-Thread-Safe Methods</span></span>  
 <span data-ttu-id="117da-130">写入的非线程安全实例方法，从 PLINQ 查询可能会导致数据损坏可能或可能不会在程序中未检测到。</span><span class="sxs-lookup"><span data-stu-id="117da-130">Writing to non-thread-safe instance methods from a PLINQ query can lead to data corruption which may or may not go undetected in your program.</span></span> <span data-ttu-id="117da-131">还可能会导致异常。</span><span class="sxs-lookup"><span data-stu-id="117da-131">It can also lead to exceptions.</span></span> <span data-ttu-id="117da-132">在下面的示例中，将尝试多个线程进行调用`Filestream.Write`方法同时，这不受支持类。</span><span class="sxs-lookup"><span data-stu-id="117da-132">In the following example, multiple threads would be attempting to call the `Filestream.Write` method simultaneously, which is not supported by the class.</span></span>  
  
```vb  
Dim fs As FileStream = File.OpenWrite(…)  
a.Where(...).OrderBy(...).Select(...).ForAll(Sub(x) fs.Write(x))  
```  
  
```csharp  
FileStream fs = File.OpenWrite(...);  
a.Where(...).OrderBy(...).Select(...).ForAll(x => fs.Write(x));  
```  
  
## <a name="limit-calls-to-thread-safe-methods"></a><span data-ttu-id="117da-133">限制调用线程安全方法</span><span class="sxs-lookup"><span data-stu-id="117da-133">Limit Calls to Thread-Safe Methods</span></span>  
 <span data-ttu-id="117da-134">.NET Framework 中的大多数静态方法是线程安全的，并且可以同时从多个线程中调用。</span><span class="sxs-lookup"><span data-stu-id="117da-134">Most static methods in the .NET Framework are thread-safe and can be called from multiple threads concurrently.</span></span> <span data-ttu-id="117da-135">但是，即使在这些情况下，所涉及到的同步也可能会导致查询速度大幅度下降。</span><span class="sxs-lookup"><span data-stu-id="117da-135">However, even in these cases, the synchronization involved can lead to significant slowdown in the query.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="117da-136">你可以对此进行测试自己的方法是插入到一些调用<xref:System.Console.WriteLine%2A>在您的查询。</span><span class="sxs-lookup"><span data-stu-id="117da-136">You can test for this yourself by inserting some calls to <xref:System.Console.WriteLine%2A> in your queries.</span></span> <span data-ttu-id="117da-137">尽管此方法用于在文档的示例演示目的，不要使用它在 PLINQ 查询中。</span><span class="sxs-lookup"><span data-stu-id="117da-137">Although this method is used in the documentation examples for demonstration purposes, do not use it in PLINQ queries.</span></span>  
  
## <a name="avoid-unnecessary-ordering-operations"></a><span data-ttu-id="117da-138">避免不必要的排序操作</span><span class="sxs-lookup"><span data-stu-id="117da-138">Avoid Unnecessary Ordering Operations</span></span>  
 <span data-ttu-id="117da-139">当 PLINQ 并行执行查询时，它将源序列划分成可以处理同时在多个线程的分区。</span><span class="sxs-lookup"><span data-stu-id="117da-139">When PLINQ executes a query in parallel, it divides the source sequence into partitions that can be operated on concurrently on multiple threads.</span></span> <span data-ttu-id="117da-140">默认情况下，处理这些分区和提供结果时的顺序不是可预测 (除外运算符，如`OrderBy`)。</span><span class="sxs-lookup"><span data-stu-id="117da-140">By default, the order in which the partitions are processed and the results are delivered is not predictable (except for operators such as `OrderBy`).</span></span> <span data-ttu-id="117da-141">你可以指示 PLINQ 中保留的任何源序列中，排序，但这对性能有负面影响。</span><span class="sxs-lookup"><span data-stu-id="117da-141">You can instruct PLINQ to preserve the ordering of any source sequence, but this has a negative impact on performance.</span></span> <span data-ttu-id="117da-142">最佳做法，只要有可能，是结构查询，以便它们不依赖于顺序保留。</span><span class="sxs-lookup"><span data-stu-id="117da-142">The best practice, whenever possible, is to structure queries so that they do not rely on order preservation.</span></span> <span data-ttu-id="117da-143">有关详细信息，请参阅 [PLINQ 中的顺序保留](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md)。</span><span class="sxs-lookup"><span data-stu-id="117da-143">For more information, see [Order Preservation in PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).</span></span>  
  
## <a name="prefer-forall-to-foreach-when-it-is-possible"></a><span data-ttu-id="117da-144">ForEach 时很可能希望 ForAll</span><span class="sxs-lookup"><span data-stu-id="117da-144">Prefer ForAll to ForEach When It Is Possible</span></span>  
 <span data-ttu-id="117da-145">尽管 PLINQ 在如果你使用中的结果在多个线程上执行查询`foreach`循环 (`For Each`在 Visual Basic 中)，必须合并回一个线程查询结果，并将其按顺序访问枚举器。</span><span class="sxs-lookup"><span data-stu-id="117da-145">Although PLINQ executes a query on multiple threads, if you consume the results in a `foreach` loop (`For Each` in Visual Basic), then the query results must be merged back into one thread and accessed serially by the enumerator.</span></span> <span data-ttu-id="117da-146">在某些情况下，这是不可避免地;但是，只要可能，使用`ForAll`方法，以使每个线程输出其自己的结果，例如，通过将写入的线程安全集合，如<xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="117da-146">In some cases, this is unavoidable; however, whenever possible, use the `ForAll` method to enable each thread to output its own results, for example, by writing to a thread-safe collection such as <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="117da-147"><xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> 也有同样的问题。换言之，强烈建议应首选使用 `source.AsParallel().Where().ForAll(...)`</span><span class="sxs-lookup"><span data-stu-id="117da-147">The same issue applies to <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> In other words, `source.AsParallel().Where().ForAll(...)` should be strongly preferred to</span></span>  
  
 <span data-ttu-id="117da-148">`Parallel.ForEach(source.AsParallel().Where(), ...)`。</span><span class="sxs-lookup"><span data-stu-id="117da-148">`Parallel.ForEach(source.AsParallel().Where(), ...)`.</span></span>  
  
## <a name="be-aware-of-thread-affinity-issues"></a><span data-ttu-id="117da-149">注意线程关联问题</span><span class="sxs-lookup"><span data-stu-id="117da-149">Be Aware of Thread Affinity Issues</span></span>  
 <span data-ttu-id="117da-150">某些技术（例如，单线程单元 (STA) 组件的 COM 互操作性、Windows 窗体以及 Windows Presentation Foundation (WPF)）具有要求代码在特定线程上运行的线程关联限制。</span><span class="sxs-lookup"><span data-stu-id="117da-150">Some technologies, for example, COM interoperability for Single-Threaded Apartment (STA) components, Windows Forms, and Windows Presentation Foundation (WPF), impose thread affinity restrictions that require code to run on a specific thread.</span></span> <span data-ttu-id="117da-151">例如，在 Windows 窗体和 WPF 中，只能在创建控件的线程上访问该控件。</span><span class="sxs-lookup"><span data-stu-id="117da-151">For example, in both Windows Forms and WPF, a control can only be accessed on the thread on which it was created.</span></span> <span data-ttu-id="117da-152">如果你尝试访问的共享的状态的 PLINQ 查询中的 Windows 窗体控件，如果你正在运行在调试器中被引发异常。</span><span class="sxs-lookup"><span data-stu-id="117da-152">If you try to access the shared state of a Windows Forms control in a PLINQ query, an exception is raised if you are running in the debugger.</span></span> <span data-ttu-id="117da-153">（此设置可以关闭。）但是，如果 UI 线程上使用您的查询，然后你可以访问该控件从`foreach`枚举查询的循环会造成，因为该代码仅在一个线程上执行。</span><span class="sxs-lookup"><span data-stu-id="117da-153">(This setting can be turned off.) However, if your query is consumed on the UI thread, then you can access the control from the `foreach` loop that enumerates the query results because that code executes on just one thread.</span></span>  
  
## <a name="do-not-assume-that-iterations-of-foreach-for-and-forall-always-execute-in-parallel"></a><span data-ttu-id="117da-154">不要假定 ForEach、For 和 ForAll 的迭代始终并行执行</span><span class="sxs-lookup"><span data-stu-id="117da-154">Do Not Assume that Iterations of ForEach, For and ForAll Always Execute in Parallel</span></span>  
 <span data-ttu-id="117da-155">务必要记住该中的个别迭代<xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>，<xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>或<xref:System.Linq.ParallelEnumerable.ForAll%2A>循环可能但不是需要并行执行。</span><span class="sxs-lookup"><span data-stu-id="117da-155">It is important to keep in mind that individual iterations in a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> or <xref:System.Linq.ParallelEnumerable.ForAll%2A> loop may but do not have to execute in parallel.</span></span> <span data-ttu-id="117da-156">因此，应避免编写任何依赖于迭代并行执行的正确性或依赖于按任何特定顺序执行迭代的代码。</span><span class="sxs-lookup"><span data-stu-id="117da-156">Therefore, you should avoid writing any code that depends for correctness on parallel execution of iterations or on the execution of iterations in any particular order.</span></span>  
  
 <span data-ttu-id="117da-157">例如，此代码有可能会死锁：</span><span class="sxs-lookup"><span data-stu-id="117da-157">For example, this code is likely to deadlock:</span></span>  
  
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
  
 <span data-ttu-id="117da-158">在此示例中，一个迭代设置一个事件，而所有的其他迭代则等待该事件。</span><span class="sxs-lookup"><span data-stu-id="117da-158">In this example, one iteration sets an event, and all other iterations wait on the event.</span></span> <span data-ttu-id="117da-159">在设置事件的迭代完成之前，任何等待迭代均无法完成。</span><span class="sxs-lookup"><span data-stu-id="117da-159">None of the waiting iterations can complete until the event-setting iteration has completed.</span></span> <span data-ttu-id="117da-160">但是，在设置事件的迭代有机会执行之前，等待迭代可能会阻止用于执行并行循环的所有线程。</span><span class="sxs-lookup"><span data-stu-id="117da-160">However, it is possible that the waiting iterations block all threads that are used to execute the parallel loop, before the event-setting iteration has had a chance to execute.</span></span> <span data-ttu-id="117da-161">这将导致死锁 – 设置事件的迭代将永不会执行，并且等待迭代将永远不会醒来。</span><span class="sxs-lookup"><span data-stu-id="117da-161">This results in a deadlock – the event-setting iteration will never execute, and the waiting iterations will never wake up.</span></span>  
  
 <span data-ttu-id="117da-162">具体而言，并行循环的一个迭代绝不应该等待循环的另一个迭代来继续执行。</span><span class="sxs-lookup"><span data-stu-id="117da-162">In particular, one iteration of a parallel loop should never wait on another iteration of the loop to make progress.</span></span> <span data-ttu-id="117da-163">如果并行循环决定按相反的顺序安排迭代，则会发生死锁。</span><span class="sxs-lookup"><span data-stu-id="117da-163">If the parallel loop decides to schedule the iterations sequentially but in the opposite order, a deadlock will occur.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="117da-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="117da-164">See Also</span></span>  
 [<span data-ttu-id="117da-165">并行 LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="117da-165">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
