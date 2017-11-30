---
title: "线程与线程处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multiple threads
- threading [.NET Framework]
- threading [.NET Framework], multiple threads
ms.assetid: 5baac3aa-e603-4fa6-9f89-0f2c1084e6b1
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b57cac34009e13c27c6d34a0ab402f9ecbe08305
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="threads-and-threading"></a><span data-ttu-id="b5c93-102">线程与线程处理</span><span class="sxs-lookup"><span data-stu-id="b5c93-102">Threads and Threading</span></span>
<span data-ttu-id="b5c93-103">操作系统使用进程分隔一起执行的不同应用程序。</span><span class="sxs-lookup"><span data-stu-id="b5c93-103">Operating systems use processes to separate the different applications that they are executing.</span></span> <span data-ttu-id="b5c93-104">线程是操作系统向其分配处理器时间的基本单元和多个线程可执行该过程内的代码。</span><span class="sxs-lookup"><span data-stu-id="b5c93-104">Threads are the basic unit to which an operating system allocates processor time, and more than one thread can be executing code inside that process.</span></span> <span data-ttu-id="b5c93-105">每个线程都维持异常处理程序、 计划的优先级别和一组系统使用保存的线程上下文，直到为计划的结构。</span><span class="sxs-lookup"><span data-stu-id="b5c93-105">Each thread maintains exception handlers, a scheduling priority, and a set of structures the system uses to save the thread context until it is scheduled.</span></span> <span data-ttu-id="b5c93-106">线程上下文包括线程需要无缝地继续执行，包括 CPU 寄存器和堆栈的线程的一组线程的主机进程的地址空间中的所有信息。</span><span class="sxs-lookup"><span data-stu-id="b5c93-106">The thread context includes all the information the thread needs to seamlessly resume execution, including the thread's set of CPU registers and stack, in the address space of the thread's host process.</span></span>  
  
 <span data-ttu-id="b5c93-107">.NET Framework 进一步细分为轻量的托管子进程，调用应用程序域，由表示的操作系统进程<xref:System.AppDomain?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="b5c93-107">The .NET Framework further subdivides an operating system process into lightweight managed subprocesses, called application domains, represented by <xref:System.AppDomain?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b5c93-108">一个或多个托管的线程 (由表示<xref:System.Threading.Thread?displayProperty=nameWithType>) 可以在任何数目的相同的托管进程内的应用程序域中运行。</span><span class="sxs-lookup"><span data-stu-id="b5c93-108">One or more managed threads (represented by <xref:System.Threading.Thread?displayProperty=nameWithType>) can run in one or any number of application domains within the same managed process.</span></span> <span data-ttu-id="b5c93-109">尽管每个应用程序域开始使用单线程，该应用程序域中的代码可以创建其他应用程序域和其他线程。</span><span class="sxs-lookup"><span data-stu-id="b5c93-109">Although each application domain is started with a single thread, code in that application domain can create additional application domains and additional threads.</span></span> <span data-ttu-id="b5c93-110">结果是一个托管的线程可以自由移动在相同的托管过程; 的应用程序域之间你可能必须只有一个线程在多个应用程序域之间切换。</span><span class="sxs-lookup"><span data-stu-id="b5c93-110">The result is that a managed thread can move freely between application domains inside the same managed process; you might have only one thread moving among several application domains.</span></span>  
  
 <span data-ttu-id="b5c93-111">支持强占式多任务操作系统从多个进程创建的多个线程同时执行的效果。</span><span class="sxs-lookup"><span data-stu-id="b5c93-111">An operating system that supports preemptive multitasking creates the effect of simultaneous execution of multiple threads from multiple processes.</span></span> <span data-ttu-id="b5c93-112">此，它会将需要它在线程之间的可用的处理器时间、 依次分配到每个线程的处理器时间切片。</span><span class="sxs-lookup"><span data-stu-id="b5c93-112">It does this by dividing the available processor time among the threads that need it, allocating a processor time slice to each thread one after another.</span></span> <span data-ttu-id="b5c93-113">其时间片结束，而另一个线程继续运行时挂起当前正在执行的线程。</span><span class="sxs-lookup"><span data-stu-id="b5c93-113">The currently executing thread is suspended when its time slice elapses, and another thread resumes running.</span></span> <span data-ttu-id="b5c93-114">当系统从一个线程切换到另一个时，它将保存已抢占线程的线程上下文，并重新加载线程队列中的下一个线程的已保存的线程上下文。</span><span class="sxs-lookup"><span data-stu-id="b5c93-114">When the system switches from one thread to another, it saves the thread context of the preempted thread and reloads the saved thread context of the next thread in the thread queue.</span></span>  
  
 <span data-ttu-id="b5c93-115">时间段的长度取决于操作系统和处理器。</span><span class="sxs-lookup"><span data-stu-id="b5c93-115">The length of the time slice depends on the operating system and the processor.</span></span> <span data-ttu-id="b5c93-116">因为每个时间段很小，多个线程看起来似乎相同次执行即使只有一个处理器。</span><span class="sxs-lookup"><span data-stu-id="b5c93-116">Because each time slice is small, multiple threads appear to be executing at the same time, even if there is only one processor.</span></span> <span data-ttu-id="b5c93-117">这是实际在多处理器系统中，这种情况在可用的处理器之间分发可执行的线程的位置。</span><span class="sxs-lookup"><span data-stu-id="b5c93-117">This is actually the case on multiprocessor systems, where the executable threads are distributed among the available processors.</span></span>  
  
## <a name="when-to-use-multiple-threads"></a><span data-ttu-id="b5c93-118">何时使用多个线程</span><span class="sxs-lookup"><span data-stu-id="b5c93-118">When To Use Multiple Threads</span></span>  
 <span data-ttu-id="b5c93-119">需要用户交互的软件必须尽可能提供丰富的用户体验最快响应用户的活动。</span><span class="sxs-lookup"><span data-stu-id="b5c93-119">Software that requires user interaction must react to the user's activities as rapidly as possible to provide a rich user experience.</span></span> <span data-ttu-id="b5c93-120">在同一时间，但是，它必须执行必要的计算来向用户尽可能快地显示数据。</span><span class="sxs-lookup"><span data-stu-id="b5c93-120">At the same time, however, it must do the calculations necessary to present data to the user as fast as possible.</span></span> <span data-ttu-id="b5c93-121">如果你的应用程序使用只有一个线程的执行，你可以组合[异步编程](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)与[.NET Framework 远程处理](http://msdn.microsoft.com/en-us/eccb1d31-0a22-417a-97fd-f4f1f3aa4462)或[XML Web services](http://msdn.microsoft.com/en-us/1e64af78-d705-4384-b08d-591a45f4379c)使用 ASP 创建若要使用的其他计算机的处理时间此外于给用户，并减少你的应用程序的数据处理时间你自己以提高响应能力的.NET。</span><span class="sxs-lookup"><span data-stu-id="b5c93-121">If your application uses only one thread of execution, you can combine [asynchronous programming](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md) with[.NET Framework remoting](http://msdn.microsoft.com/en-us/eccb1d31-0a22-417a-97fd-f4f1f3aa4462) or [XML Web services](http://msdn.microsoft.com/en-us/1e64af78-d705-4384-b08d-591a45f4379c) created using ASP.NET to use the processing time of other computers in addition to that of your own to increase responsiveness to the user and decrease the data processing time of your application.</span></span> <span data-ttu-id="b5c93-122">如果你正在密集型的输入/输出工作，你可以使用 I/O 完成端口以提高应用程序的响应能力。</span><span class="sxs-lookup"><span data-stu-id="b5c93-122">If you are doing intensive input/output work, you can also use I/O completion ports to increase your application's responsiveness.</span></span>  
  
### <a name="advantages-of-multiple-threads"></a><span data-ttu-id="b5c93-123">多个线程的优点</span><span class="sxs-lookup"><span data-stu-id="b5c93-123">Advantages of Multiple Threads</span></span>  
 <span data-ttu-id="b5c93-124">使用多个线程，但是，是最强大的技术可用于增加对用户的响应能力和处理几乎同时完成工作所必需的数据。</span><span class="sxs-lookup"><span data-stu-id="b5c93-124">Using more than one thread, however, is the most powerful technique available to increase responsiveness to the user and process the data necessary to get the job done at almost the same time.</span></span> <span data-ttu-id="b5c93-125">具有一个处理器的计算机，在多个线程可以创建此效果，请利用很小的用户事件，以处理在后台的数据之间的时间段。</span><span class="sxs-lookup"><span data-stu-id="b5c93-125">On a computer with one processor, multiple threads can create this effect, taking advantage of the small periods of time in between user events to process the data in the background.</span></span> <span data-ttu-id="b5c93-126">例如，用户可以编辑电子表格，而另一个线程正在重新计算同一个应用程序中的电子表格的其他部分。</span><span class="sxs-lookup"><span data-stu-id="b5c93-126">For example, a user can edit a spreadsheet while another thread is recalculating other parts of the spreadsheet within the same application.</span></span>  
  
 <span data-ttu-id="b5c93-127">而不进行修改，同一个应用程序任务会急剧增加用户满意度当在具有多个处理器的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="b5c93-127">Without modification, the same application would dramatically increase user satisfaction when run on a computer with more than one processor.</span></span> <span data-ttu-id="b5c93-128">单个应用程序域可以使用多个线程来完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="b5c93-128">Your single application domain could use multiple threads to accomplish the following tasks:</span></span>  
  
-   <span data-ttu-id="b5c93-129">通过网络，到 Web 服务器和数据库进行通信。</span><span class="sxs-lookup"><span data-stu-id="b5c93-129">Communicate over a network, to a Web server, and to a database.</span></span>  
  
-   <span data-ttu-id="b5c93-130">执行需要大量的时间的操作。</span><span class="sxs-lookup"><span data-stu-id="b5c93-130">Perform operations that take a large amount of time.</span></span>  
  
-   <span data-ttu-id="b5c93-131">区分具有不同优先级的任务。</span><span class="sxs-lookup"><span data-stu-id="b5c93-131">Distinguish tasks of varying priority.</span></span> <span data-ttu-id="b5c93-132">例如，优先级较高的线程管理时间关键任务，而低优先级的线程执行其他任务。</span><span class="sxs-lookup"><span data-stu-id="b5c93-132">For example, a high-priority thread manages time-critical tasks, and a low-priority thread performs other tasks.</span></span>  
  
-   <span data-ttu-id="b5c93-133">允许用户界面以保持响应度，分配到的后台任务的时间时。</span><span class="sxs-lookup"><span data-stu-id="b5c93-133">Allow the user interface to remain responsive, while allocating time to background tasks.</span></span>  
  
### <a name="disadvantages-of-multiple-threads"></a><span data-ttu-id="b5c93-134">多个线程的缺点</span><span class="sxs-lookup"><span data-stu-id="b5c93-134">Disadvantages of Multiple Threads</span></span>  
 <span data-ttu-id="b5c93-135">建议你使用尽可能少的线程，从而最小化操作系统资源的使用和提高性能。</span><span class="sxs-lookup"><span data-stu-id="b5c93-135">It is recommended that you use as few threads as possible, thereby minimizing the use of operating-system resources and improving performance.</span></span> <span data-ttu-id="b5c93-136">线程处理还具有要设计你的应用程序时考虑的资源要求和潜在的冲突。</span><span class="sxs-lookup"><span data-stu-id="b5c93-136">Threading also has resource requirements and potential conflicts to be considered when designing your application.</span></span> <span data-ttu-id="b5c93-137">资源要求如下所示：</span><span class="sxs-lookup"><span data-stu-id="b5c93-137">The resource requirements are as follows:</span></span>  
  
-   <span data-ttu-id="b5c93-138">系统使用的内存的进程，所需的上下文信息**AppDomain**对象和线程。</span><span class="sxs-lookup"><span data-stu-id="b5c93-138">The system consumes memory for the context information required by processes, **AppDomain** objects, and threads.</span></span> <span data-ttu-id="b5c93-139">因此，进程，数**AppDomain**对象和可以创建的线程受可用内存的限制。</span><span class="sxs-lookup"><span data-stu-id="b5c93-139">Therefore, the number of processes, **AppDomain** objects, and threads that can be created is limited by available memory.</span></span>  
  
-   <span data-ttu-id="b5c93-140">跟踪的大量的线程将占用大量的处理器时间。</span><span class="sxs-lookup"><span data-stu-id="b5c93-140">Keeping track of a large number of threads consumes significant processor time.</span></span> <span data-ttu-id="b5c93-141">如果有线程过多，其中大多数都不会明显的进度。</span><span class="sxs-lookup"><span data-stu-id="b5c93-141">If there are too many threads, most of them will not make significant progress.</span></span> <span data-ttu-id="b5c93-142">如果当前线程的大多数都在一个进程，其他进程中的线程计划频率较低。</span><span class="sxs-lookup"><span data-stu-id="b5c93-142">If most of the current threads are in one process, threads in other processes are scheduled less frequently.</span></span>  
  
-   <span data-ttu-id="b5c93-143">控制使用多线程代码执行复杂，并且可以是多个 bug 的源。</span><span class="sxs-lookup"><span data-stu-id="b5c93-143">Controlling code execution with many threads is complex, and can be a source of many bugs.</span></span>  
  
-   <span data-ttu-id="b5c93-144">销毁线程需要了解可能发生和处理这些问题。</span><span class="sxs-lookup"><span data-stu-id="b5c93-144">Destroying threads requires knowing what could happen and handling those issues.</span></span>  
  
 <span data-ttu-id="b5c93-145">提供对资源的共享访问权限会造成冲突。</span><span class="sxs-lookup"><span data-stu-id="b5c93-145">Providing shared access to resources can create conflicts.</span></span> <span data-ttu-id="b5c93-146">若要避免冲突，你必须同步，或控制对共享资源的访问。</span><span class="sxs-lookup"><span data-stu-id="b5c93-146">To avoid conflicts, you must synchronize, or control the access to, shared resources.</span></span> <span data-ttu-id="b5c93-147">正确 （在相同或不同的应用程序域中） 的访问进行同步的失败可能导致问题，例如死锁 （中的两个线程停止响应每个等待另一个用于完成时） 和 （异常结果发生时争用条件意外严重依赖于两个事件的计时）。</span><span class="sxs-lookup"><span data-stu-id="b5c93-147">Failure to synchronize access properly (in the same or different application domains) can lead to problems such as deadlocks (in which two threads stop responding while each waits for the other to complete) and race conditions (when an anomalous result occurs due to an unexpected critical dependence on the timing of two events).</span></span> <span data-ttu-id="b5c93-148">系统提供了可用于协调多个线程间共享的资源的同步对象。</span><span class="sxs-lookup"><span data-stu-id="b5c93-148">The system provides synchronization objects that can be used to coordinate resource sharing among multiple threads.</span></span> <span data-ttu-id="b5c93-149">减少的线程数，使更轻松地将资源同步。</span><span class="sxs-lookup"><span data-stu-id="b5c93-149">Reducing the number of threads makes it easier to synchronize resources.</span></span>  
  
 <span data-ttu-id="b5c93-150">需要同步的资源包括：</span><span class="sxs-lookup"><span data-stu-id="b5c93-150">Resources that require synchronization include:</span></span>  
  
-   <span data-ttu-id="b5c93-151">系统资源 （如通信的端口）。</span><span class="sxs-lookup"><span data-stu-id="b5c93-151">System resources (such as communications ports).</span></span>  
  
-   <span data-ttu-id="b5c93-152">由 （如文件句柄） 的多个进程共享的资源。</span><span class="sxs-lookup"><span data-stu-id="b5c93-152">Resources shared by multiple processes (such as file handles).</span></span>  
  
-   <span data-ttu-id="b5c93-153">单个应用程序域的资源 (如全局、 静态和实例字段) 多个线程访问。</span><span class="sxs-lookup"><span data-stu-id="b5c93-153">The resources of a single application domain (such as global, static, and instance fields) accessed by multiple threads.</span></span>  
  
### <a name="threading-and-application-design"></a><span data-ttu-id="b5c93-154">线程处理和应用程序设计</span><span class="sxs-lookup"><span data-stu-id="b5c93-154">Threading and Application Design</span></span>  
 <span data-ttu-id="b5c93-155">一般情况下，使用<xref:System.Threading.ThreadPool>类是最简单的方法来处理多个线程相对较短的任务不会阻止其他线程，并且当你不期待的任务的任何特定的计划。</span><span class="sxs-lookup"><span data-stu-id="b5c93-155">In general, using the <xref:System.Threading.ThreadPool> class is the easiest way to handle multiple threads for relatively short tasks that will not block other threads and when you do not expect any particular scheduling of the tasks.</span></span> <span data-ttu-id="b5c93-156">但是，有多种原因需要创建您自己的线程：</span><span class="sxs-lookup"><span data-stu-id="b5c93-156">However, there are a number of reasons to create your own threads:</span></span>  
  
-   <span data-ttu-id="b5c93-157">如果你需要具有特定优先级的任务。</span><span class="sxs-lookup"><span data-stu-id="b5c93-157">If you need a task to have a particular priority.</span></span>  
  
-   <span data-ttu-id="b5c93-158">如果你有一个任务，它可能运行较长时间 （并因此阻止其他任务）。</span><span class="sxs-lookup"><span data-stu-id="b5c93-158">If you have a task that might run a long time (and therefore block other tasks).</span></span>  
  
-   <span data-ttu-id="b5c93-159">如果你需要将线程放入单线程单元 (所有**线程池**线程处于多线程单元)。</span><span class="sxs-lookup"><span data-stu-id="b5c93-159">If you need to place threads into a single-threaded apartment (all **ThreadPool** threads are in the multithreaded apartment).</span></span>  
  
-   <span data-ttu-id="b5c93-160">如果你需要与线程关联的稳定标识。</span><span class="sxs-lookup"><span data-stu-id="b5c93-160">If you need a stable identity associated with the thread.</span></span> <span data-ttu-id="b5c93-161">例如，应使用的专用的线程中止该线程，挂起，或按名称发现它。</span><span class="sxs-lookup"><span data-stu-id="b5c93-161">For example, you should use a dedicated thread to abort that thread, suspend it, or discover it by name.</span></span>  
  
-   <span data-ttu-id="b5c93-162">如果你需要运行与用户界面交互的后台线程，.NET Framework 2.0 版提供了<xref:System.ComponentModel.BackgroundWorker>与跨线程封送到的用户界面线程中使用事件，进行通信的组件。</span><span class="sxs-lookup"><span data-stu-id="b5c93-162">If you need to run background threads that interact with the user interface, the .NET Framework version 2.0 provides a <xref:System.ComponentModel.BackgroundWorker> component that communicates using events, with cross-thread marshaling to the user-interface thread.</span></span>  
  
### <a name="threading-and-exceptions"></a><span data-ttu-id="b5c93-163">线程处理和异常</span><span class="sxs-lookup"><span data-stu-id="b5c93-163">Threading and Exceptions</span></span>  
 <span data-ttu-id="b5c93-164">不要处理线程中的异常。</span><span class="sxs-lookup"><span data-stu-id="b5c93-164">Do handle exceptions in threads.</span></span> <span data-ttu-id="b5c93-165">中的线程，甚至是后台线程中未经处理的异常通常会终止进程。</span><span class="sxs-lookup"><span data-stu-id="b5c93-165">Unhandled exceptions in threads, even background threads, generally terminate the process.</span></span> <span data-ttu-id="b5c93-166">以下为此规则的三种例外情况：</span><span class="sxs-lookup"><span data-stu-id="b5c93-166">There are three exceptions to this rule:</span></span>  
  
-   <span data-ttu-id="b5c93-167">A<xref:System.Threading.ThreadAbortException>线程中引发，因为<xref:System.Threading.Thread.Abort%2A>调用。</span><span class="sxs-lookup"><span data-stu-id="b5c93-167">A <xref:System.Threading.ThreadAbortException> is thrown in a thread because <xref:System.Threading.Thread.Abort%2A> was called.</span></span>  
  
-   <span data-ttu-id="b5c93-168"><xref:System.AppDomainUnloadedException>线程中引发，因为应用程序域是否正在卸载。</span><span class="sxs-lookup"><span data-stu-id="b5c93-168">An <xref:System.AppDomainUnloadedException> is thrown in a thread because the application domain is being unloaded.</span></span>  
  
-   <span data-ttu-id="b5c93-169">公共语言运行时或主机进程将终止该线程。</span><span class="sxs-lookup"><span data-stu-id="b5c93-169">The common language runtime or a host process terminates the thread.</span></span>  
  
 <span data-ttu-id="b5c93-170">有关详细信息，请参阅[托管线程中的异常](../../../docs/standard/threading/exceptions-in-managed-threads.md)。</span><span class="sxs-lookup"><span data-stu-id="b5c93-170">For more information, see [Exceptions in Managed Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b5c93-171">在.NET framework 1.0 和 1.1 版中，公共语言运行时将以无提示方式捕获一些例外情况，例如在线程池线程。</span><span class="sxs-lookup"><span data-stu-id="b5c93-171">In the .NET Framework versions 1.0 and 1.1, the common language runtime silently traps some exceptions, for example in thread pool threads.</span></span> <span data-ttu-id="b5c93-172">这可能会损坏应用程序状态并最终导致应用程序挂起，这可能是很难进行调试。</span><span class="sxs-lookup"><span data-stu-id="b5c93-172">This may corrupt application state and eventually cause applications to hang, which might be very difficult to debug.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5c93-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5c93-173">See Also</span></span>  
 <xref:System.Threading.ThreadPool>  
 <xref:System.ComponentModel.BackgroundWorker>  
 [<span data-ttu-id="b5c93-174">为多线程处理同步数据</span><span class="sxs-lookup"><span data-stu-id="b5c93-174">Synchronizing Data for Multithreading</span></span>](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 [<span data-ttu-id="b5c93-175">托管线程池</span><span class="sxs-lookup"><span data-stu-id="b5c93-175">The Managed Thread Pool</span></span>](../../../docs/standard/threading/the-managed-thread-pool.md)
