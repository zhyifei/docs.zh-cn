---
title: 任务并行库 (TPL)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- .NET, concurrency in
- .NET, parallel programming in
- Parallel Programming
ms.assetid: b8f99f43-9104-45fd-9bff-385a20488a23
caps.latest.revision: 37
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8f63237e139e4be1d8cbb13e1534c894626fd72d
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="task-parallel-library-tpl"></a><span data-ttu-id="9c991-102">任务并行库 (TPL)</span><span class="sxs-lookup"><span data-stu-id="9c991-102">Task Parallel Library (TPL)</span></span>
<span data-ttu-id="9c991-103">任务并行库 (TPL) 是 <xref:System.Threading?displayProperty=nameWithType> 和 <xref:System.Threading.Tasks?displayProperty=nameWithType> 空间中的一组公共类型和 API。</span><span class="sxs-lookup"><span data-stu-id="9c991-103">The Task Parallel Library (TPL) is a set of public types and APIs in the <xref:System.Threading?displayProperty=nameWithType> and <xref:System.Threading.Tasks?displayProperty=nameWithType> namespaces.</span></span> <span data-ttu-id="9c991-104">TPL 的目的是通过简化将并行和并发添加到应用程序的过程来提高开发人员的工作效率。</span><span class="sxs-lookup"><span data-stu-id="9c991-104">The purpose of the TPL is to make developers more productive by simplifying the process of adding parallelism and concurrency to applications.</span></span> <span data-ttu-id="9c991-105">TPL 动态缩放并发的程度以最有效地使用所有可用的处理器。</span><span class="sxs-lookup"><span data-stu-id="9c991-105">The TPL scales the degree of concurrency dynamically to most efficiently use all the processors that are available.</span></span> <span data-ttu-id="9c991-106">此外，TPL 还处理工作分区、<xref:System.Threading.ThreadPool> 上的线程调度、取消支持、状态管理以及其他低级别的细节操作。</span><span class="sxs-lookup"><span data-stu-id="9c991-106">In addition, the TPL handles the partitioning of the work, the scheduling of threads on the <xref:System.Threading.ThreadPool>, cancellation support, state management, and other low-level details.</span></span> <span data-ttu-id="9c991-107">通过使用 TPL，你可以在将精力集中于程序要完成的工作，同时最大程度地提高代码的性能。</span><span class="sxs-lookup"><span data-stu-id="9c991-107">By using TPL, you can maximize the performance of your code while focusing on the work that your program is designed to accomplish.</span></span>  
  
 <span data-ttu-id="9c991-108">自 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 起，首选 TPL 编写多线程代码和并行代码。</span><span class="sxs-lookup"><span data-stu-id="9c991-108">Starting with the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], the TPL is the preferred way to write multithreaded and parallel code.</span></span> <span data-ttu-id="9c991-109">但是，并不是所有代码都适合并行化；例如，如果某个循环在每次迭代时只执行少量工作，或它在很多次迭代时都不运行，那么并行化的开销可能导致代码运行更慢。</span><span class="sxs-lookup"><span data-stu-id="9c991-109">However, not all code is suitable for parallelization; for example, if a loop performs only a small amount of work on each iteration, or it doesn't run for many iterations, then the overhead of parallelization can cause the code to run more slowly.</span></span> <span data-ttu-id="9c991-110">此外，像任何多线程代码一样，并行化会增加程序执行的复杂性。</span><span class="sxs-lookup"><span data-stu-id="9c991-110">Furthermore, parallelization like any multithreaded code adds complexity to your program execution.</span></span> <span data-ttu-id="9c991-111">尽管 TPL 简化了多线程方案，但我们建议你对线程处理概念（例如，锁、死锁和争用条件）进行基本的了解，以便能够有效地使用 TPL。</span><span class="sxs-lookup"><span data-stu-id="9c991-111">Although the TPL simplifies multithreaded scenarios, we recommend that you have a basic understanding of threading concepts, for example, locks, deadlocks, and race conditions, so that you can use the TPL effectively.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="9c991-112">相关主题</span><span class="sxs-lookup"><span data-stu-id="9c991-112">Related Topics</span></span>  
  
|<span data-ttu-id="9c991-113">标题</span><span class="sxs-lookup"><span data-stu-id="9c991-113">Title</span></span>|<span data-ttu-id="9c991-114">描述</span><span class="sxs-lookup"><span data-stu-id="9c991-114">Description</span></span>|  
|-|-|  
|[<span data-ttu-id="9c991-115">数据并行</span><span class="sxs-lookup"><span data-stu-id="9c991-115">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)|<span data-ttu-id="9c991-116">描述如何创建并行的 `for` 和 `foreach` 循环（在 Visual Basic 中为 `For` 和 `For Each`）。</span><span class="sxs-lookup"><span data-stu-id="9c991-116">Describes how to create parallel `for` and `foreach` loops (`For` and `For Each` in Visual Basic).</span></span>|  
|[<span data-ttu-id="9c991-117">基于任务的异步编程</span><span class="sxs-lookup"><span data-stu-id="9c991-117">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)|<span data-ttu-id="9c991-118">描述如何通过使用 <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=nameWithType> 隐式创建和运行任务，或通过直接使用 <xref:System.Threading.Tasks.Task> 对象显式创建和运行任务。</span><span class="sxs-lookup"><span data-stu-id="9c991-118">Describes how to create and run tasks implicitly by using <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=nameWithType> or explicitly by using <xref:System.Threading.Tasks.Task> objects directly.</span></span>|  
|[<span data-ttu-id="9c991-119">数据流</span><span class="sxs-lookup"><span data-stu-id="9c991-119">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)|<span data-ttu-id="9c991-120">描述如何使用 TPL 数据流库中的数据流组件处理多项运算，这些运算必须彼此通信，或在数据可用时处理数据。</span><span class="sxs-lookup"><span data-stu-id="9c991-120">Describes how to use the dataflow components in the TPL Dataflow Library to handle multiple operations that must communicate with one another or to process data as it becomes available.</span></span>|  
|[<span data-ttu-id="9c991-121">将 TPL 和其他异步模式结合使用</span><span class="sxs-lookup"><span data-stu-id="9c991-121">Using TPL with Other Asynchronous Patterns</span></span>](../../../docs/standard/parallel-programming/using-tpl-with-other-asynchronous-patterns.md)|<span data-ttu-id="9c991-122">描述如何将 TPL 与 .NET 中的其他异步模式一起使用。</span><span class="sxs-lookup"><span data-stu-id="9c991-122">Describes how to use TPL with other asynchronous patterns in .NET</span></span>|  
|[<span data-ttu-id="9c991-123">数据和任务并行的潜在问题</span><span class="sxs-lookup"><span data-stu-id="9c991-123">Potential Pitfalls in Data and Task Parallelism</span></span>](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)|<span data-ttu-id="9c991-124">描述一些常见缺陷以及如何避免它们。</span><span class="sxs-lookup"><span data-stu-id="9c991-124">Describes some common pitfalls and how to avoid them.</span></span>|  
|[<span data-ttu-id="9c991-125">并行 LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="9c991-125">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)|<span data-ttu-id="9c991-126">描述如何使用 LINQ 查询实现数据并行化。</span><span class="sxs-lookup"><span data-stu-id="9c991-126">Describes how to achieve data parallelism with LINQ queries.</span></span>|  
|[<span data-ttu-id="9c991-127">并行编程</span><span class="sxs-lookup"><span data-stu-id="9c991-127">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)|<span data-ttu-id="9c991-128">.NET 并行编程的顶级节点。</span><span class="sxs-lookup"><span data-stu-id="9c991-128">Top level node for .NET parallel programming.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9c991-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="9c991-129">See Also</span></span>  
 [<span data-ttu-id="9c991-130">使用 .NET Framework 进行并行编程的示例</span><span class="sxs-lookup"><span data-stu-id="9c991-130">Samples for Parallel Programming with the .NET Framework</span></span>](https://code.msdn.microsoft.com/Samples-for-Parallel-b4b76364)
