---
title: "如何：编写具有线程局部变量的 Parallel.ForEach 循环"
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
helpviewer_keywords: parallel foreach loop, how to use local state
ms.assetid: 24b10041-b30b-45cb-aa65-66cf568ca76d
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6102274f75d2fe66b89f917cf9095d3a6dfaa3e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-a-parallelforeach-loop-with-thread-local-variables"></a><span data-ttu-id="a1234-102">如何：编写具有线程局部变量的 Parallel.ForEach 循环</span><span class="sxs-lookup"><span data-stu-id="a1234-102">How to: Write a Parallel.ForEach Loop with Thread-Local Variables</span></span>
<span data-ttu-id="a1234-103">下面的示例演示如何编写使用线程本地变量的 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="a1234-103">The following example shows how to write a <xref:System.Threading.Tasks.Parallel.ForEach%2A> method that uses thread-local variables.</span></span> <span data-ttu-id="a1234-104">当 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 循环执行时，它会将其源集合划分为多个分区。</span><span class="sxs-lookup"><span data-stu-id="a1234-104">When a <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop executes, it divides its source collection into multiple partitions.</span></span> <span data-ttu-id="a1234-105">每个分区都将获得自己的“线程本地”变量的副本。</span><span class="sxs-lookup"><span data-stu-id="a1234-105">Each partition will get its own copy of the "thread-local" variable.</span></span> <span data-ttu-id="a1234-106">（术语“线程本地”在此处不太准确，因为在某些情况下两个分区可能在同一线程上运行。）</span><span class="sxs-lookup"><span data-stu-id="a1234-106">(The term "thread-local" is slightly inaccurate here, because in some cases two partitions may run on the same thread.)</span></span>  
  
 <span data-ttu-id="a1234-107">此示例中的代码和参数非常类似于对应的 <xref:System.Threading.Tasks.Parallel.For%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="a1234-107">The code and parameters in this example closely resemble the corresponding <xref:System.Threading.Tasks.Parallel.For%2A> method.</span></span> <span data-ttu-id="a1234-108">有关详细信息，请参阅[如何： 编写具有线程局部变量的 Parallel.For 循环](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md)。</span><span class="sxs-lookup"><span data-stu-id="a1234-108">For more information, see [How to: Write a Parallel.For Loop with Thread-Local Variables](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md).</span></span>  
  
 <span data-ttu-id="a1234-109">若要在 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 循环中使用线程本地变量，你必须调用采用两个类型参数的方法重载之一。</span><span class="sxs-lookup"><span data-stu-id="a1234-109">To use a thread-local variable in a <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop, you must call one of the method overloads that takes two type parameters.</span></span> <span data-ttu-id="a1234-110">第一个类型参数 `TSource` 指定源元素的类型，第二个类型参数 `TLocal` 指定线程本地变量的类型。</span><span class="sxs-lookup"><span data-stu-id="a1234-110">The first type parameter, `TSource`, specifies the type of the source element, and the second type parameter, `TLocal`, specifies the type of the thread-local variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1234-111">示例</span><span class="sxs-lookup"><span data-stu-id="a1234-111">Example</span></span>  
 <span data-ttu-id="a1234-112">以下示例调用 <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType> 重载以计算一百万个元素的数组的总和。</span><span class="sxs-lookup"><span data-stu-id="a1234-112">The following example calls <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType> overload to compute the sum of an array of one million elements.</span></span> <span data-ttu-id="a1234-113">此重载具有四个参数：</span><span class="sxs-lookup"><span data-stu-id="a1234-113">This overload has four parameters:</span></span>  
  
-   <span data-ttu-id="a1234-114">`source`，也就是数据源。</span><span class="sxs-lookup"><span data-stu-id="a1234-114">`source`, which is the data source.</span></span> <span data-ttu-id="a1234-115">它必须实现 <xref:System.Collections.Generic.IEnumerable%601>。</span><span class="sxs-lookup"><span data-stu-id="a1234-115">It must implement <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="a1234-116">在我们的示例中，数据源是由 `IEnumerable<Int32>` 方法返回的一百万个成员 <xref:System.Linq.Enumerable.Range%2A?displayProperty=nameWithType> 对象。</span><span class="sxs-lookup"><span data-stu-id="a1234-116">The data source in our example is the one million member `IEnumerable<Int32>` object returned by the <xref:System.Linq.Enumerable.Range%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="a1234-117">`localInit`，或初始化线程本地变量的函数。</span><span class="sxs-lookup"><span data-stu-id="a1234-117">`localInit`, or the function that initializes the thread-local variable.</span></span> <span data-ttu-id="a1234-118">为每个在其中执行 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> 操作的分区调用此函数一次。</span><span class="sxs-lookup"><span data-stu-id="a1234-118">This function is called once for each partition in which the <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> operation executes.</span></span> <span data-ttu-id="a1234-119">我们的示例将线程本地变量初始化为零。</span><span class="sxs-lookup"><span data-stu-id="a1234-119">Our example initializes the thread-local variable to zero.</span></span>  
  
-   <span data-ttu-id="a1234-120">`body`，由并行循环对循环的每个迭代调用的 <xref:System.Func%604>。</span><span class="sxs-lookup"><span data-stu-id="a1234-120">`body`, a <xref:System.Func%604> that is invoked by the parallel loop on each iteration of the loop.</span></span> <span data-ttu-id="a1234-121">其签名为 `Func\<TSource, ParallelLoopState, TLocal, TLocal>`。</span><span class="sxs-lookup"><span data-stu-id="a1234-121">Its signature is `Func\<TSource, ParallelLoopState, TLocal, TLocal>`.</span></span> <span data-ttu-id="a1234-122">你为委托提供代码，并且循环将传入输入参数，它们是：</span><span class="sxs-lookup"><span data-stu-id="a1234-122">You supply the code for the delegate, and the loop passes in the input parameters, which are:</span></span>  
  
    -   <span data-ttu-id="a1234-123"><xref:System.Collections.Generic.IEnumerable%601> 的当前元素。</span><span class="sxs-lookup"><span data-stu-id="a1234-123">The current element of the <xref:System.Collections.Generic.IEnumerable%601>.</span></span>  
  
    -   <span data-ttu-id="a1234-124">你可以在委托的代码中用来检查循环状态的 <xref:System.Threading.Tasks.ParallelLoopState> 变量。</span><span class="sxs-lookup"><span data-stu-id="a1234-124">A <xref:System.Threading.Tasks.ParallelLoopState> variable that you can use in your delegate's code to examine the state of the loop.</span></span>  
  
    -   <span data-ttu-id="a1234-125">线程本地变量。</span><span class="sxs-lookup"><span data-stu-id="a1234-125">The thread-local variable.</span></span>  
  
     <span data-ttu-id="a1234-126">你的委托返回线程本地变量，然后将此变量传递到在该特定分区中执行的循环的下一次迭代。</span><span class="sxs-lookup"><span data-stu-id="a1234-126">Your delegate returns the thread-local variable, which is then passed to the next iteration of the loop that executes in that particular partition.</span></span> <span data-ttu-id="a1234-127">每个循环分区维护此变量的一个单独实例。</span><span class="sxs-lookup"><span data-stu-id="a1234-127">Each loop partition maintains a separate instance of this variable.</span></span>  
  
     <span data-ttu-id="a1234-128">在该示例中，委托将每个整数的值添加到线程本地变量，该变量维护在该分区中整数元素的值的运行总数。</span><span class="sxs-lookup"><span data-stu-id="a1234-128">In the example, the delegate adds the value of each integer to the thread-local variable, which maintains a running total of the values of the integer elements in that partition.</span></span>  
  
-   <span data-ttu-id="a1234-129">`localFinally`，当在每个分区中的循环操作完成时，`Action<TLocal>` 调用的 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> 委托。</span><span class="sxs-lookup"><span data-stu-id="a1234-129">`localFinally`, an `Action<TLocal>` delegate that the <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> invokes when the looping operations in each partition have completed.</span></span> <span data-ttu-id="a1234-130"><xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> 方法将为此线程（或循环分区）的线程本地变量的最终值传递给你的 `Action<TLocal>` 委托，并且你提供代码，这些代码执行将来自此分区的结果与其他分区的结果组合所需的操作。</span><span class="sxs-lookup"><span data-stu-id="a1234-130">The <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> method passes your `Action<TLocal>` delegate the final value of the thread-local variable for this thread (or loop partition), and you provide the code that performs the required action for combining the result from this partition with the results from the other partitions.</span></span> <span data-ttu-id="a1234-131">此委托可以由多个任务并行调用。</span><span class="sxs-lookup"><span data-stu-id="a1234-131">This delegate can be invoked concurrently by multiple tasks.</span></span> <span data-ttu-id="a1234-132">因此，该示例使用 <xref:System.Threading.Interlocked.Add%28System.Int32%40%2CSystem.Int32%29?displayProperty=nameWithType> 方法以同步对 `total` 变量的访问。</span><span class="sxs-lookup"><span data-stu-id="a1234-132">Because of this, the example uses the <xref:System.Threading.Interlocked.Add%28System.Int32%40%2CSystem.Int32%29?displayProperty=nameWithType> method to synchronize access to the `total` variable.</span></span> <span data-ttu-id="a1234-133">由于委托类型为 <xref:System.Action%601>，因此不存在返回值。</span><span class="sxs-lookup"><span data-stu-id="a1234-133">Because the delegate type is an <xref:System.Action%601>, there is no return value.</span></span>  
  
 [!code-csharp[TPL_Parallel#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/foreachthreadlocal.cs#04)]
 [!code-vb[TPL_Parallel#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/foreachthreadlocal.vb#04)]  
  
## <a name="see-also"></a><span data-ttu-id="a1234-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1234-134">See Also</span></span>  
 [<span data-ttu-id="a1234-135">数据并行</span><span class="sxs-lookup"><span data-stu-id="a1234-135">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [<span data-ttu-id="a1234-136">如何：编写具有线程局部变量的 Parallel.For 循环</span><span class="sxs-lookup"><span data-stu-id="a1234-136">How to: Write a Parallel.For Loop with Thread-Local Variables</span></span>](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md)  
 [<span data-ttu-id="a1234-137">PLINQ 和 TPL 中的 Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="a1234-137">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
