---
title: "托管线程池"
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
- cpp
helpviewer_keywords:
- thread pooling [.NET Framework]
- thread pools [.NET Framework]
- threading [.NET Framework], thread pool
- threading [.NET Framework], pooling
ms.assetid: 2be05b06-a42e-4c9d-a739-96c21d673927
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e50fd66096d6bd58fb7db692449e7f8654b5ca76
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="the-managed-thread-pool"></a><span data-ttu-id="57169-102">托管线程池</span><span class="sxs-lookup"><span data-stu-id="57169-102">The Managed Thread Pool</span></span>
<span data-ttu-id="57169-103"><xref:System.Threading.ThreadPool> 类为你的应用程序提供一个受系统管理的辅助线程池，从而使你能够专注于应用程序任务，而非线程管理。</span><span class="sxs-lookup"><span data-stu-id="57169-103">The <xref:System.Threading.ThreadPool> class provides your application with a pool of worker threads that are managed by the system, allowing you to concentrate on application tasks rather than thread management.</span></span> <span data-ttu-id="57169-104">如果有需要后台处理的短任务，托管的线程池则为利用多个线程的简便方法。</span><span class="sxs-lookup"><span data-stu-id="57169-104">If you have short tasks that require background processing, the managed thread pool is an easy way to take advantage of multiple threads.</span></span> <span data-ttu-id="57169-105">例如，从 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 开始，可以创建 <xref:System.Threading.Tasks.Task> 和 <xref:System.Threading.Tasks.Task%601> 对象，它们在线程池线程上执行异步任务。</span><span class="sxs-lookup"><span data-stu-id="57169-105">For example, beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] you can create <xref:System.Threading.Tasks.Task> and <xref:System.Threading.Tasks.Task%601> objects, which perform asynchronous tasks on thread pool threads.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57169-106">从 [!INCLUDE[net_v20SP1_long](../../../includes/net-v20sp1-long-md.md)] 开始，在早期版本 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 中被视为瓶颈的三个关键方面内线程池的吞吐量显著提高：队列任务、调度线程池线程和调度 I/O 完成线程。</span><span class="sxs-lookup"><span data-stu-id="57169-106">Starting with the [!INCLUDE[net_v20SP1_long](../../../includes/net-v20sp1-long-md.md)], the throughput of the thread pool is significantly improved in three key areas that were identified as bottlenecks in previous releases of the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]: queuing tasks, dispatching thread pool threads, and dispatching I/O completion threads.</span></span> <span data-ttu-id="57169-107">若要使用此功能，应用程序应为 [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)] 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="57169-107">To use this functionality, your application should target the [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)] or later.</span></span>  
  
 <span data-ttu-id="57169-108">对于与用户界面交互的后台任务，.NET Framework 2.0 版还提供 <xref:System.ComponentModel.BackgroundWorker> 类，该类使用用户界面线程上引发的事件进行通信。</span><span class="sxs-lookup"><span data-stu-id="57169-108">For background tasks that interact with the user interface, the .NET Framework version 2.0 also provides the <xref:System.ComponentModel.BackgroundWorker> class, which communicates using events raised on the user interface thread.</span></span>  
  
 <span data-ttu-id="57169-109">.NET Framework 将线程池线程用于多种用途，包括异步 I/O 完成、计时器回调、注册的等待操作、使用委托的异步方法调用和 <xref:System.Net> 套接字连接。</span><span class="sxs-lookup"><span data-stu-id="57169-109">The .NET Framework uses thread pool threads for many purposes, including asynchronous I/O completion, timer callbacks, registered wait operations, asynchronous method calls using delegates, and <xref:System.Net> socket connections.</span></span>  
  
## <a name="when-not-to-use-thread-pool-threads"></a><span data-ttu-id="57169-110">何时不使用线程池线程</span><span class="sxs-lookup"><span data-stu-id="57169-110">When Not to Use Thread Pool Threads</span></span>  
 <span data-ttu-id="57169-111">有几种应用场景，其中适合创建并管理自己的线程，而非使用线程池线程：</span><span class="sxs-lookup"><span data-stu-id="57169-111">There are several scenarios in which it is appropriate to create and manage your own threads instead of using thread pool threads:</span></span>  
  
-   <span data-ttu-id="57169-112">需要一个前台线程。</span><span class="sxs-lookup"><span data-stu-id="57169-112">You require a foreground thread.</span></span>  
  
-   <span data-ttu-id="57169-113">需要具有特定优先级的线程。</span><span class="sxs-lookup"><span data-stu-id="57169-113">You require a thread to have a particular priority.</span></span>  
  
-   <span data-ttu-id="57169-114">拥有会导致线程长时间阻塞的任务。</span><span class="sxs-lookup"><span data-stu-id="57169-114">You have tasks that cause the thread to block for long periods of time.</span></span> <span data-ttu-id="57169-115">线程池具有最大线程数，因此大量被阻塞的线程池线程可能会阻止任务启动。</span><span class="sxs-lookup"><span data-stu-id="57169-115">The thread pool has a maximum number of threads, so a large number of blocked thread pool threads might prevent tasks from starting.</span></span>  
  
-   <span data-ttu-id="57169-116">需将线程放入单线程单元。</span><span class="sxs-lookup"><span data-stu-id="57169-116">You need to place threads into a single-threaded apartment.</span></span> <span data-ttu-id="57169-117">所有 <xref:System.Threading.ThreadPool> 线程均位于多线程单元中。</span><span class="sxs-lookup"><span data-stu-id="57169-117">All <xref:System.Threading.ThreadPool> threads are in the multithreaded apartment.</span></span>  
  
-   <span data-ttu-id="57169-118">需具有与线程关联的稳定标识，或需将一个线程专用于一项任务。</span><span class="sxs-lookup"><span data-stu-id="57169-118">You need to have a stable identity associated with the thread, or to dedicate a thread to a task.</span></span>  
  
## <a name="thread-pool-characteristics"></a><span data-ttu-id="57169-119">线程池特征</span><span class="sxs-lookup"><span data-stu-id="57169-119">Thread Pool Characteristics</span></span>  
 <span data-ttu-id="57169-120">线程池线程是后台线程。</span><span class="sxs-lookup"><span data-stu-id="57169-120">Thread pool threads are background threads.</span></span> <span data-ttu-id="57169-121">请参阅[前台和后台线程](../../../docs/standard/threading/foreground-and-background-threads.md)。</span><span class="sxs-lookup"><span data-stu-id="57169-121">See [Foreground and Background Threads](../../../docs/standard/threading/foreground-and-background-threads.md).</span></span> <span data-ttu-id="57169-122">每个线程均使用默认的堆栈大小，以默认的优先级运行，并且位于多线程单元中。</span><span class="sxs-lookup"><span data-stu-id="57169-122">Each thread uses the default stack size, runs at the default priority, and is in the multithreaded apartment.</span></span>  
  
 <span data-ttu-id="57169-123">每个进程只有一个线程池。</span><span class="sxs-lookup"><span data-stu-id="57169-123">There is only one thread pool per process.</span></span>  
  
### <a name="exceptions-in-thread-pool-threads"></a><span data-ttu-id="57169-124">线程池线程中的异常</span><span class="sxs-lookup"><span data-stu-id="57169-124">Exceptions in Thread Pool Threads</span></span>  
 <span data-ttu-id="57169-125">线程池线程上未经处理的异常终止该进程。</span><span class="sxs-lookup"><span data-stu-id="57169-125">Unhandled exceptions on thread pool threads terminate the process.</span></span> <span data-ttu-id="57169-126">以下为此规则的三种例外情况：</span><span class="sxs-lookup"><span data-stu-id="57169-126">There are three exceptions to this rule:</span></span>  
  
-   <span data-ttu-id="57169-127"><xref:System.Threading.ThreadAbortException> 在线程池线程中引发，因为调用了 <xref:System.Threading.Thread.Abort%2A>。</span><span class="sxs-lookup"><span data-stu-id="57169-127">A <xref:System.Threading.ThreadAbortException> is thrown in a thread pool thread, because <xref:System.Threading.Thread.Abort%2A> was called.</span></span>  
  
-   <span data-ttu-id="57169-128"><xref:System.AppDomainUnloadedException> 在线程池线程中引发，因为正在卸载应用程序域。</span><span class="sxs-lookup"><span data-stu-id="57169-128">An <xref:System.AppDomainUnloadedException> is thrown in a thread pool thread, because the application domain is being unloaded.</span></span>  
  
-   <span data-ttu-id="57169-129">公共语言运行时或主机进程将终止该线程。</span><span class="sxs-lookup"><span data-stu-id="57169-129">The common language runtime or a host process terminates the thread.</span></span>  
  
 <span data-ttu-id="57169-130">有关详细信息，请参阅[托管线程异常](../../../docs/standard/threading/exceptions-in-managed-threads.md)。</span><span class="sxs-lookup"><span data-stu-id="57169-130">For more information, see [Exceptions in Managed Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57169-131">在 .NET framework 1.0 和 1.1 版中，公共语言运行时以无提示方式捕获线程池线程中未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="57169-131">In the .NET Framework versions 1.0 and 1.1, the common language runtime silently traps unhandled exceptions in thread pool threads.</span></span> <span data-ttu-id="57169-132">这可能会损坏应用程序状态并最终导致应用程序挂起，可能很难对此进行调试。</span><span class="sxs-lookup"><span data-stu-id="57169-132">This might corrupt application state and eventually cause applications to hang, which might be very difficult to debug.</span></span>  
  
### <a name="maximum-number-of-thread-pool-threads"></a><span data-ttu-id="57169-133">最大线程池线程数</span><span class="sxs-lookup"><span data-stu-id="57169-133">Maximum Number of Thread Pool Threads</span></span>  
 <span data-ttu-id="57169-134">可排入线程池的操作的数量仅受可用内存限制；但是，线程池会限制可同时在进程中处于活动状态的线程数。</span><span class="sxs-lookup"><span data-stu-id="57169-134">The number of operations that can be queued to the thread pool is limited only by available memory; however, the thread pool limits the number of threads that can be active in the process simultaneously.</span></span> <span data-ttu-id="57169-135">从 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 开始，进程的线程池的默认大小取决于若干因素，例如虚拟地址空间的大小。</span><span class="sxs-lookup"><span data-stu-id="57169-135">Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the default size of the thread pool for a process depends on several factors, such as the size of the virtual address space.</span></span> <span data-ttu-id="57169-136">进程可以调用 <xref:System.Threading.ThreadPool.GetMaxThreads%2A> 方法，以确定线程数。</span><span class="sxs-lookup"><span data-stu-id="57169-136">A process can call the <xref:System.Threading.ThreadPool.GetMaxThreads%2A> method to determine the number of threads.</span></span>  
  
 <span data-ttu-id="57169-137">可以使用 <xref:System.Threading.ThreadPool.GetMaxThreads%2A> 和 <xref:System.Threading.ThreadPool.SetMaxThreads%2A> 方法来控制最大线程数。</span><span class="sxs-lookup"><span data-stu-id="57169-137">You can control the maximum number of threads by using the <xref:System.Threading.ThreadPool.GetMaxThreads%2A> and <xref:System.Threading.ThreadPool.SetMaxThreads%2A> methods.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57169-138">在 .NET framework 1.0 和 1.1 版中，不能在托管代码中设置线程池大小。</span><span class="sxs-lookup"><span data-stu-id="57169-138">In the .NET Framework versions 1.0 and 1.1, the size of the thread pool cannot be set from managed code.</span></span> <span data-ttu-id="57169-139">承载公共语言运行时的代码可使用 mscoree.h 中定义的 `CorSetMaxThreads` 来设置线程池大小。</span><span class="sxs-lookup"><span data-stu-id="57169-139">Code that hosts the common language runtime can set the size using `CorSetMaxThreads`, defined in mscoree.h.</span></span>  
  
### <a name="thread-pool-minimums"></a><span data-ttu-id="57169-140">线程池最小值</span><span class="sxs-lookup"><span data-stu-id="57169-140">Thread Pool Minimums</span></span>  
 <span data-ttu-id="57169-141">线程池根据需要提供新的工作线程或 I/O 完成线程，直到它达到每个类别的指定最小值。</span><span class="sxs-lookup"><span data-stu-id="57169-141">The thread pool provides new worker threads or I/O completion threads on demand until it reaches a specified minimum for each category.</span></span> <span data-ttu-id="57169-142">可以使用 <xref:System.Threading.ThreadPool.GetMinThreads%2A> 方法来获取这些最小值。</span><span class="sxs-lookup"><span data-stu-id="57169-142">You can use the <xref:System.Threading.ThreadPool.GetMinThreads%2A> method to obtain these minimum values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57169-143">需求较低时，线程池线程的实际数量可以低于最小值。</span><span class="sxs-lookup"><span data-stu-id="57169-143">When demand is low, the actual number of thread pool threads can fall below the minimum values.</span></span>  
  
 <span data-ttu-id="57169-144">达到最小值时，线程池可以创建其他线程或等待，直到一些任务完成。</span><span class="sxs-lookup"><span data-stu-id="57169-144">When a minimum is reached, the thread pool can create additional threads or wait until some tasks complete.</span></span> <span data-ttu-id="57169-145">从 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 开始，线程池创建和销毁工作线程以优化吞吐量，吞吐量被定义为每个单位时间完成的任务数。</span><span class="sxs-lookup"><span data-stu-id="57169-145">Beginning with the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], the thread pool creates and destroys worker threads in order to optimize throughput, which is defined as the number of tasks that complete per unit of time.</span></span> <span data-ttu-id="57169-146">线程过少可能无法实现可用资源的最优利用，而线程过多则可能增加资源争用。</span><span class="sxs-lookup"><span data-stu-id="57169-146">Too few threads might not make optimal use of available resources, whereas too many threads could increase resource contention.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="57169-147">可以使用 <xref:System.Threading.ThreadPool.SetMinThreads%2A> 方法来增加最小空闲线程数。</span><span class="sxs-lookup"><span data-stu-id="57169-147">You can use the <xref:System.Threading.ThreadPool.SetMinThreads%2A> method to increase the minimum number of idle threads.</span></span> <span data-ttu-id="57169-148">但是，不必要地增加这些值可能导致性能问题。</span><span class="sxs-lookup"><span data-stu-id="57169-148">However, unnecessarily increasing these values can cause performance problems.</span></span> <span data-ttu-id="57169-149">如果在同一时间开始太多的任务，则所有任务均可能会很慢。</span><span class="sxs-lookup"><span data-stu-id="57169-149">If too many tasks start at the same time, all of them might appear to be slow.</span></span> <span data-ttu-id="57169-150">大多数情况下，使用自己的分配线程算法，线程池将更好地执行任务。</span><span class="sxs-lookup"><span data-stu-id="57169-150">In most cases the thread pool will perform better with its own algorithm for allocating threads.</span></span>  
  
## <a name="skipping-security-checks"></a><span data-ttu-id="57169-151">跳过安全检查</span><span class="sxs-lookup"><span data-stu-id="57169-151">Skipping Security Checks</span></span>  
 <span data-ttu-id="57169-152">线程池还提供 <xref:System.Threading.ThreadPool.UnsafeQueueUserWorkItem%2A?displayProperty=nameWithType> 和 <xref:System.Threading.ThreadPool.UnsafeRegisterWaitForSingleObject%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="57169-152">The thread pool also provides the <xref:System.Threading.ThreadPool.UnsafeQueueUserWorkItem%2A?displayProperty=nameWithType> and <xref:System.Threading.ThreadPool.UnsafeRegisterWaitForSingleObject%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="57169-153">仅当确定调用方的堆栈与执行排队的任务期间进行的任何安全检查无关时，方可使用这些方法。</span><span class="sxs-lookup"><span data-stu-id="57169-153">Use these methods only when you are certain that the caller's stack is irrelevant to any security checks performed during the execution of the queued task.</span></span> <span data-ttu-id="57169-154"><xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> 和 <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> 均捕获调用方堆栈，当线程开始执行任务时，调用方的堆栈被合并到线程池线程的堆栈中。</span><span class="sxs-lookup"><span data-stu-id="57169-154"><xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> and <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> both capture the caller's stack, which is merged into the stack of the thread pool thread when the thread begins to execute a task.</span></span> <span data-ttu-id="57169-155">如果安全检查是必需的，则必须检查整个堆栈。</span><span class="sxs-lookup"><span data-stu-id="57169-155">If a security check is required, the entire stack must be checked.</span></span> <span data-ttu-id="57169-156">尽管此检查提供了安全性，但它也具有性能成本。</span><span class="sxs-lookup"><span data-stu-id="57169-156">Although the check provides safety, it also has a performance cost.</span></span>  
  
## <a name="using-the-thread-pool"></a><span data-ttu-id="57169-157">使用线程池</span><span class="sxs-lookup"><span data-stu-id="57169-157">Using the Thread Pool</span></span>  
 <span data-ttu-id="57169-158">自 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 起，使用线程池的最简单方法是使用[任务并行库 (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)。</span><span class="sxs-lookup"><span data-stu-id="57169-158">Beginning with the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], the easiest way to use the thread pool is to use the [Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md).</span></span> <span data-ttu-id="57169-159">默认情况下，并行库类型（例如 <xref:System.Threading.Tasks.Task> 和 <xref:System.Threading.Tasks.Task%601>）使用线程池线程来运行任务。</span><span class="sxs-lookup"><span data-stu-id="57169-159">By default, parallel library types like <xref:System.Threading.Tasks.Task> and <xref:System.Threading.Tasks.Task%601> use thread pool threads to run tasks.</span></span> <span data-ttu-id="57169-160">也可以通过从托管代码调用 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType>（或从非托管代码调用 `CorQueueUserWorkItem`）并传递表示执行任务的方法的 <xref:System.Threading.WaitCallback> 委托来使用线程池。</span><span class="sxs-lookup"><span data-stu-id="57169-160">You can also use the thread pool by calling <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> from managed code (or `CorQueueUserWorkItem` from unmanaged code) and passing a <xref:System.Threading.WaitCallback> delegate representing the method that performs the task.</span></span> <span data-ttu-id="57169-161">使用线程池的另一种方法是通过使用 <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> 方法并传递在发出信号或超时的时候调用 <xref:System.Threading.WaitOrTimerCallback> 委托所表示的方法的 <xref:System.Threading.WaitHandle>，从而对与等待操作相关的工作项排队。</span><span class="sxs-lookup"><span data-stu-id="57169-161">Another way to use the thread pool is to queue work items that are related to a wait operation by using the <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> method and passing a <xref:System.Threading.WaitHandle> that, when signaled or when timed out, calls the method represented by the <xref:System.Threading.WaitOrTimerCallback> delegate.</span></span> <span data-ttu-id="57169-162">线程池线程用于调用回调方法。</span><span class="sxs-lookup"><span data-stu-id="57169-162">Thread pool threads are used to invoke callback methods.</span></span>  
  
## <a name="threadpool-examples"></a><span data-ttu-id="57169-163">线程池示例</span><span class="sxs-lookup"><span data-stu-id="57169-163">ThreadPool Examples</span></span>  
 <span data-ttu-id="57169-164">本节中的代码示例通过使用 <xref:System.Threading.Tasks.Task> 类、<xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> 方法和 <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> 方法来演示线程池。</span><span class="sxs-lookup"><span data-stu-id="57169-164">The code examples in this section demonstrate the thread pool by using the <xref:System.Threading.Tasks.Task> class, the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> method, and the <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> method.</span></span>  
  
-   [<span data-ttu-id="57169-165">使用任务并行库执行异步任务</span><span class="sxs-lookup"><span data-stu-id="57169-165">Executing Asynchronous Tasks with the Task Parallel Library</span></span>](#TaskParallelLibrary)  
  
-   [<span data-ttu-id="57169-166">使用 QueueUserWorkItem 异步执行代码</span><span class="sxs-lookup"><span data-stu-id="57169-166">Executing Code Asynchronously with QueueUserWorkItem</span></span>](#ExecuteCodeWithQUWI)  
  
-   [<span data-ttu-id="57169-167">为 QueueUserWorkItem 提供任务数据</span><span class="sxs-lookup"><span data-stu-id="57169-167">Supplying Task Data for QueueUserWorkItem</span></span>](#TaskDataForQUWI)  
  
-   [<span data-ttu-id="57169-168">使用 RegisterWaitForSingleObject</span><span class="sxs-lookup"><span data-stu-id="57169-168">Using RegisterWaitForSingleObject</span></span>](#RegisterWaitForSingleObject)  
  
<a name="TaskParallelLibrary"></a>   
### <a name="executing-asynchronous-tasks-with-the-task-parallel-library"></a><span data-ttu-id="57169-169">使用任务并行库执行异步任务</span><span class="sxs-lookup"><span data-stu-id="57169-169">Executing Asynchronous Tasks with the Task Parallel Library</span></span>  
 <span data-ttu-id="57169-170">下面的示例演示如何通过调用 <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> 方法来创建并使用 <xref:System.Threading.Tasks.Task> 对象。</span><span class="sxs-lookup"><span data-stu-id="57169-170">The following example shows how to create and use a <xref:System.Threading.Tasks.Task> object by calling the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="57169-171">有关使用 <xref:System.Threading.Tasks.Task%601> 类返回异步任务值的示例，请参阅[如何：返回任务值](../../../docs/standard/parallel-programming/how-to-return-a-value-from-a-task.md)。</span><span class="sxs-lookup"><span data-stu-id="57169-171">For an example that uses the <xref:System.Threading.Tasks.Task%601> class to return a value from an asynchronous task, see [How to: Return a Value from a Task](../../../docs/standard/parallel-programming/how-to-return-a-value-from-a-task.md).</span></span>  
  
 [!code-csharp[System.Threading.Tasks.Task#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.threading.tasks.task/cs/startnew.cs#01)]
 [!code-vb[System.Threading.Tasks.Task#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.threading.tasks.task/vb/startnew.vb#01)]  
  
<a name="ExecuteCodeWithQUWI"></a>   
### <a name="executing-code-asynchronously-with-queueuserworkitem"></a><span data-ttu-id="57169-172">使用 QueueUserWorkItem 以异步方式执行代码</span><span class="sxs-lookup"><span data-stu-id="57169-172">Executing Code Asynchronously with QueueUserWorkItem</span></span>  
 <span data-ttu-id="57169-173">下面的示例使用 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> 方法将非常简单的任务排入队列，由 `ThreadProc` 方法表示。</span><span class="sxs-lookup"><span data-stu-id="57169-173">The following example queues a very simple task, represented by the `ThreadProc` method, using the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span>  
  
 [!code-cpp[Conceptual.ThreadPool#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.threadpool/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.ThreadPool#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.threadpool/cs/source1.cs#1)]
 [!code-vb[Conceptual.ThreadPool#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.threadpool/vb/source1.vb#1)]  
  
<a name="TaskDataForQUWI"></a>   
### <a name="supplying-task-data-for-queueuserworkitem"></a><span data-ttu-id="57169-174">为 QueueUserWorkItem 提供任务数据</span><span class="sxs-lookup"><span data-stu-id="57169-174">Supplying Task Data for QueueUserWorkItem</span></span>  
 <span data-ttu-id="57169-175">下面的代码示例使用 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> 方法将任务排入队列，并为该任务提供数据。</span><span class="sxs-lookup"><span data-stu-id="57169-175">The following code example uses the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method to queue a task and supply the data for the task.</span></span>  
  
 [!code-cpp[Conceptual.ThreadPool#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.threadpool/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.ThreadPool#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.threadpool/cs/source2.cs#2)]
 [!code-vb[Conceptual.ThreadPool#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.threadpool/vb/source2.vb#2)]  
  
<a name="RegisterWaitForSingleObject"></a>   
### <a name="using-registerwaitforsingleobject"></a><span data-ttu-id="57169-176">使用 RegisterWaitForSingleObject</span><span class="sxs-lookup"><span data-stu-id="57169-176">Using RegisterWaitForSingleObject</span></span>  
 <span data-ttu-id="57169-177">下面的示例展示多种线程处理功能。</span><span class="sxs-lookup"><span data-stu-id="57169-177">The following example demonstrates several threading features.</span></span>  
  
-   <span data-ttu-id="57169-178">使用 <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> 方法，将任务排入队列，以便由 <xref:System.Threading.ThreadPool> 线程执行。</span><span class="sxs-lookup"><span data-stu-id="57169-178">Queuing a task for execution by <xref:System.Threading.ThreadPool> threads, with the <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> method.</span></span>  
  
-   <span data-ttu-id="57169-179">使用 <xref:System.Threading.AutoResetEvent> 发出要执行的任务的信号。</span><span class="sxs-lookup"><span data-stu-id="57169-179">Signaling a task to execute, with <xref:System.Threading.AutoResetEvent>.</span></span> <span data-ttu-id="57169-180">请参阅 [EventWaitHandle、AutoResetEvent、CountdownEvent、ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)。</span><span class="sxs-lookup"><span data-stu-id="57169-180">See [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md).</span></span>  
  
-   <span data-ttu-id="57169-181">使用 <xref:System.Threading.WaitOrTimerCallback> 委托处理超时和信号。</span><span class="sxs-lookup"><span data-stu-id="57169-181">Handling both time-outs and signals with a <xref:System.Threading.WaitOrTimerCallback> delegate.</span></span>  
  
-   <span data-ttu-id="57169-182">使用 <xref:System.Threading.RegisteredWaitHandle> 取消排队的任务。</span><span class="sxs-lookup"><span data-stu-id="57169-182">Canceling a queued task with <xref:System.Threading.RegisteredWaitHandle>.</span></span>  
  
 [!code-cpp[Conceptual.ThreadPool#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.threadpool/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.ThreadPool#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.threadpool/cs/source3.cs#3)]
 [!code-vb[Conceptual.ThreadPool#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.threadpool/vb/source3.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="57169-183">请参阅</span><span class="sxs-lookup"><span data-stu-id="57169-183">See Also</span></span>  
 <xref:System.Threading.ThreadPool>  
 <xref:System.Threading.Tasks.Task>  
 <xref:System.Threading.Tasks.Task%601>  
 [<span data-ttu-id="57169-184">任务并行库 (TPL)</span><span class="sxs-lookup"><span data-stu-id="57169-184">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 [<span data-ttu-id="57169-185">任务并行库 (TPL)</span><span class="sxs-lookup"><span data-stu-id="57169-185">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 [<span data-ttu-id="57169-186">如何：从任务中返回值</span><span class="sxs-lookup"><span data-stu-id="57169-186">How to: Return a Value from a Task</span></span>](../../../docs/standard/parallel-programming/how-to-return-a-value-from-a-task.md)  
 [<span data-ttu-id="57169-187">线程处理对象和功能</span><span class="sxs-lookup"><span data-stu-id="57169-187">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 [<span data-ttu-id="57169-188">线程与线程处理</span><span class="sxs-lookup"><span data-stu-id="57169-188">Threads and Threading</span></span>](../../../docs/standard/threading/threads-and-threading.md)  
 [<span data-ttu-id="57169-189">异步文件 I/O</span><span class="sxs-lookup"><span data-stu-id="57169-189">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [<span data-ttu-id="57169-190">计时器</span><span class="sxs-lookup"><span data-stu-id="57169-190">Timers</span></span>](../../../docs/standard/threading/timers.md)
