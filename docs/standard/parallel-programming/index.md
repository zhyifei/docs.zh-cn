---
title: ".NET 中的并行编程"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parallel programming
ms.assetid: 4d83c690-ad2d-489e-a2e0-b85b898a672d
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 554de5d65929afc03b57bdc604ceeb6ac35362d4
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="parallel-programming-in-net"></a><span data-ttu-id="bea19-102">.NET 中的并行编程</span><span class="sxs-lookup"><span data-stu-id="bea19-102">Parallel Programming in .NET</span></span>
<span data-ttu-id="bea19-103">许多个人计算机和工作站都有两个或四个内核（即 CPU），使多个线程能够同时执行。</span><span class="sxs-lookup"><span data-stu-id="bea19-103">Many personal computers and workstations have two or four cores (that is, CPUs) that enable multiple threads to be executed simultaneously.</span></span> <span data-ttu-id="bea19-104">在不久的将来，计算机预期会有更多的内核。</span><span class="sxs-lookup"><span data-stu-id="bea19-104">Computers in the near future are expected to have significantly more cores.</span></span> <span data-ttu-id="bea19-105">为了利用当今和未来的硬件，您可以对代码进行并行化，以将工作分摊在多个处理器上。</span><span class="sxs-lookup"><span data-stu-id="bea19-105">To take advantage of the hardware of today and tomorrow, you can parallelize your code to distribute work across multiple processors.</span></span> <span data-ttu-id="bea19-106">过去，并行化需要线程和锁的低级操作。</span><span class="sxs-lookup"><span data-stu-id="bea19-106">In the past, parallelization required low-level manipulation of threads and locks.</span></span> [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="bea19-107"> 和 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 新增了运行时、类库类型和诊断工具，增强了对并行编程的支持。</span><span class="sxs-lookup"><span data-stu-id="bea19-107"> and the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] enhance support for parallel programming by providing a new runtime, new class library types, and new diagnostic tools.</span></span> <span data-ttu-id="bea19-108">这些功能简化了并行开发，使您能够通过固有方法编写高效、细化且可伸缩的并行代码，而不必直接处理线程或线程池。</span><span class="sxs-lookup"><span data-stu-id="bea19-108">These features simplify parallel development so that you can write efficient, fine-grained, and scalable parallel code in a natural idiom without having to work directly with threads or the thread pool.</span></span> <span data-ttu-id="bea19-109">下图从较高层面上概述了 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 中的并行编程体系结构。</span><span class="sxs-lookup"><span data-stu-id="bea19-109">The following illustration provides a high-level overview of the parallel programming architecture in the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].</span></span>  
  
 <span data-ttu-id="bea19-110">![.NET 并行编程体系结构](../../../docs/standard/parallel-programming/media/tpl-architecture.png "TPL_Architecture")</span><span class="sxs-lookup"><span data-stu-id="bea19-110">![.NET Parallel Programming Architecture](../../../docs/standard/parallel-programming/media/tpl-architecture.png "TPL_Architecture")</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="bea19-111">相关主题</span><span class="sxs-lookup"><span data-stu-id="bea19-111">Related Topics</span></span>  
  
|<span data-ttu-id="bea19-112">技术</span><span class="sxs-lookup"><span data-stu-id="bea19-112">Technology</span></span>|<span data-ttu-id="bea19-113">描述</span><span class="sxs-lookup"><span data-stu-id="bea19-113">Description</span></span>|  
|----------------|-----------------|  
|[<span data-ttu-id="bea19-114">任务并行库 (TPL)</span><span class="sxs-lookup"><span data-stu-id="bea19-114">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)|<span data-ttu-id="bea19-115">提供针对 <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> 类的文档（包括 `For` 和 `ForEach` 循环的并行版本），还提供了针对 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 类的文档（描绘了表示异步操作的首选方式）。</span><span class="sxs-lookup"><span data-stu-id="bea19-115">Provides documentation for the <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> class, which includes parallel versions of `For` and `ForEach` loops, and also for the <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> class, which represents the preferred way to express asynchronous operations.</span></span>|  
|[<span data-ttu-id="bea19-116">并行 LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="bea19-116">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)|<span data-ttu-id="bea19-117">LINQ to Objects 的并行实现，该实现显著提高了许多情况下的性能。</span><span class="sxs-lookup"><span data-stu-id="bea19-117">A parallel implementation of LINQ to Objects that significantly improves performance in many scenarios.</span></span>|  
|[<span data-ttu-id="bea19-118">用于并行编程的数据结构</span><span class="sxs-lookup"><span data-stu-id="bea19-118">Data Structures for Parallel Programming</span></span>](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)|<span data-ttu-id="bea19-119">提供一些链接，这些链接指向有关线程安全集合类、轻量同步类型以及延迟初始化类型的文档。</span><span class="sxs-lookup"><span data-stu-id="bea19-119">Provides links to documentation for thread-safe collection classes, lightweight synchronization types, and types for lazy initialization.</span></span>|  
|[<span data-ttu-id="bea19-120">并行诊断工具</span><span class="sxs-lookup"><span data-stu-id="bea19-120">Parallel Diagnostic Tools</span></span>](../../../docs/standard/parallel-programming/parallel-diagnostic-tools.md)|<span data-ttu-id="bea19-121">收录了有关 Visual Studio 任务和并行堆栈调试器窗口以及[并发可视化工具](/visualstudio/profiling/concurrency-visualizer)的文档链接，其中包含 [!INCLUDE[vsprvsts](../../../includes/vsprvsts-md.md)] 探查器中的一组视图，可以使用这些视图来调试和调整并行代码的性能。</span><span class="sxs-lookup"><span data-stu-id="bea19-121">Provides links to documentation for Visual Studio debugger windows for tasks and parallel stacks, and the [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer), which consists of a set of views in the [!INCLUDE[vsprvsts](../../../includes/vsprvsts-md.md)] Profiler that you can use to debug and to tune the performance of parallel code.</span></span>|  
|[<span data-ttu-id="bea19-122">PLINQ 和 TPL 的自定义分区程序</span><span class="sxs-lookup"><span data-stu-id="bea19-122">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)|<span data-ttu-id="bea19-123">描述分区程序的工作方式，以及如何配置默认分区程序或创建新的分区程序。</span><span class="sxs-lookup"><span data-stu-id="bea19-123">Describes how partitioners work and how to configure the default partitioners or create a new partitioner.</span></span>|  
|[<span data-ttu-id="bea19-124">任务计划程序</span><span class="sxs-lookup"><span data-stu-id="bea19-124">Task Schedulers</span></span>](http://msdn.microsoft.com/library/638f8ea5-21db-47a2-a934-86e1e961bf65)|<span data-ttu-id="bea19-125">描述计划程序的工作方式，以及如何配置默认计划程序。</span><span class="sxs-lookup"><span data-stu-id="bea19-125">Describes how schedulers work and how the default schedulers may be configured.</span></span>|  
|[<span data-ttu-id="bea19-126">PLINQ 和 TPL 中的 Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="bea19-126">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)|<span data-ttu-id="bea19-127">简要概述 C# 和 Visual Basic 中的 Lambda 表达式，并演示如何在 PLINQ 和任务并行库中使用这些表达式。</span><span class="sxs-lookup"><span data-stu-id="bea19-127">Provides a brief overview of lambda expressions in C# and Visual Basic, and shows how they are used in PLINQ and the Task Parallel Library.</span></span>|  
|[<span data-ttu-id="bea19-128">其他阅读材料</span><span class="sxs-lookup"><span data-stu-id="bea19-128">For Further Reading</span></span>](../../../docs/standard/parallel-programming/for-further-reading-parallel-programming.md)|<span data-ttu-id="bea19-129">提供一些链接，这些链接指向其他文档以及在 .NET Framework 中进行并行编程的示例资源。</span><span class="sxs-lookup"><span data-stu-id="bea19-129">Provides links to additional documentation and sample resources for parallel programming in the .NET Framework.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bea19-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="bea19-130">See Also</span></span>  
 [<span data-ttu-id="bea19-131">并行编程模式：了解并使用 .NET Framework 4 应用并行模式</span><span class="sxs-lookup"><span data-stu-id="bea19-131">Patterns for Parallel Programming: Understanding and Applying Parallel Patterns with the .NET Framework 4</span></span>](http://go.microsoft.com/fwlink/?LinkID=185142)  
 [<span data-ttu-id="bea19-132">使用 .NET Framework 进行并行编程的示例</span><span class="sxs-lookup"><span data-stu-id="bea19-132">Samples for Parallel Programming with the .NET Framework</span></span>](http://code.msdn.microsoft.com/Samples-for-Parallel-b4b76364)
