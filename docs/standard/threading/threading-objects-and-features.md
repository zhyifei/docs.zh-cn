---
title: 线程处理对象和功能
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02f88faab6ddbaa026e73ad61bc63fbe8e5e00ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591320"
---
# <a name="threading-objects-and-features"></a><span data-ttu-id="d92cf-102">线程处理对象和功能</span><span class="sxs-lookup"><span data-stu-id="d92cf-102">Threading Objects and Features</span></span>
<span data-ttu-id="d92cf-103">.NET Framework 提供许多对象，有助于你创建和管理多线程应用程序。</span><span class="sxs-lookup"><span data-stu-id="d92cf-103">The .NET Framework provides a number of objects that help you create and manage multithreaded applications.</span></span> <span data-ttu-id="d92cf-104">托管线程通过 <xref:System.Threading.Thread> 类表示。</span><span class="sxs-lookup"><span data-stu-id="d92cf-104">Managed threads are represented by the <xref:System.Threading.Thread> class.</span></span> <span data-ttu-id="d92cf-105"><xref:System.Threading.ThreadPool> 类可以轻松创建和管理多线程后台任务。</span><span class="sxs-lookup"><span data-stu-id="d92cf-105">The <xref:System.Threading.ThreadPool> class provides easy creation and management of multithreaded background tasks.</span></span> <span data-ttu-id="d92cf-106"><xref:System.ComponentModel.BackgroundWorker> 类执行的任务和与用户界面交互的任务相同。</span><span class="sxs-lookup"><span data-stu-id="d92cf-106">The <xref:System.ComponentModel.BackgroundWorker> class does the same for tasks that interact with the user interface.</span></span> <span data-ttu-id="d92cf-107"><xref:System.Threading.Timer> 类可在指定的时间间隔内执行后台任务。</span><span class="sxs-lookup"><span data-stu-id="d92cf-107">The <xref:System.Threading.Timer> class executes background tasks at timed intervals.</span></span>  
  
 <span data-ttu-id="d92cf-108">此外，还有许多类可同步激活线程，包括 .NET Framework 2.0 版中引入的 <xref:System.Threading.Semaphore> 和 <xref:System.Threading.EventWaitHandle> 类。</span><span class="sxs-lookup"><span data-stu-id="d92cf-108">In addition, there are a number of classes that synchronize activities of threads, including the <xref:System.Threading.Semaphore> and <xref:System.Threading.EventWaitHandle> classes introduced in the .NET Framework version 2.0.</span></span> <span data-ttu-id="d92cf-109">[同步基元概述](../../../docs/standard/threading/overview-of-synchronization-primitives.md)中对这些类的功能进行了比较。</span><span class="sxs-lookup"><span data-stu-id="d92cf-109">The features of these classes are compared in [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d92cf-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="d92cf-110">In This Section</span></span>  
 [<span data-ttu-id="d92cf-111">托管线程池</span><span class="sxs-lookup"><span data-stu-id="d92cf-111">The Managed Thread Pool</span></span>](../../../docs/standard/threading/the-managed-thread-pool.md)  
 <span data-ttu-id="d92cf-112">介绍 **ThreadPool** 类，可以通过该类请求线程执行任务，而无须自行执行任何线程管理。</span><span class="sxs-lookup"><span data-stu-id="d92cf-112">Explains the **ThreadPool** class, which enables you to request a thread to execute a task without having to do any thread management yourself.</span></span>  
  
 [<span data-ttu-id="d92cf-113">计时器</span><span class="sxs-lookup"><span data-stu-id="d92cf-113">Timers</span></span>](../../../docs/standard/threading/timers.md)  
 <span data-ttu-id="d92cf-114">介绍如何使用**计时器**指定在指定的时间调用委派。</span><span class="sxs-lookup"><span data-stu-id="d92cf-114">Explains how to use a **Timer** to specify a delegate to be called at a specified time.</span></span>  
  
 [<span data-ttu-id="d92cf-115">监视器</span><span class="sxs-lookup"><span data-stu-id="d92cf-115">Monitors</span></span>](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)  
 <span data-ttu-id="d92cf-116">介绍如何使用**监视器**类同步访问成员或创建自己的线程管理类型。</span><span class="sxs-lookup"><span data-stu-id="d92cf-116">Explains how to use the **Monitor** class to synchronize access to a member or to build your own thread management types.</span></span>  
  
 [<span data-ttu-id="d92cf-117">等待句柄</span><span class="sxs-lookup"><span data-stu-id="d92cf-117">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 <span data-ttu-id="d92cf-118">描述 <xref:System.Threading.WaitHandle> 类、事件等待句柄的抽象基类、互斥体和可以等待多个同步事件的信号量。</span><span class="sxs-lookup"><span data-stu-id="d92cf-118">Describes the <xref:System.Threading.WaitHandle> class, the abstract base class for event wait handles, mutexes, and semaphores, which enables waiting for multiple synchronization events.</span></span>  
  
 [<span data-ttu-id="d92cf-119">EventWaitHandle、AutoResetEvent、CountdownEvent、ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="d92cf-119">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 <span data-ttu-id="d92cf-120">描述用于通过发送和等待信号同步线程活动的托管事件等待句柄。</span><span class="sxs-lookup"><span data-stu-id="d92cf-120">Describes managed event wait handles, which are used to synchronize thread activities by signaling and waiting for signals.</span></span>  
  
 [<span data-ttu-id="d92cf-121">Mutex</span><span class="sxs-lookup"><span data-stu-id="d92cf-121">Mutexes</span></span>](../../../docs/standard/threading/mutexes.md)  
 <span data-ttu-id="d92cf-122">介绍了如何使用 <xref:System.Threading.Mutex> 同步访问对象或生成自己的同步机制。</span><span class="sxs-lookup"><span data-stu-id="d92cf-122">Explains how to use a <xref:System.Threading.Mutex> to synchronize access to an object or to build your own synchronization mechanisms.</span></span>  
  
 [<span data-ttu-id="d92cf-123">互锁操作</span><span class="sxs-lookup"><span data-stu-id="d92cf-123">Interlocked Operations</span></span>](../../../docs/standard/threading/interlocked-operations.md)  
 <span data-ttu-id="d92cf-124">说明如何使用 <xref:System.Threading.Interlocked> 类递增或递减值和以单原子操作存储值。</span><span class="sxs-lookup"><span data-stu-id="d92cf-124">Explains how to use the <xref:System.Threading.Interlocked> class to increment or decrement a value and store the value in a single atomic operation.</span></span>  
  
 [<span data-ttu-id="d92cf-125">读取器-编写器锁</span><span class="sxs-lookup"><span data-stu-id="d92cf-125">Reader-Writer Locks</span></span>](../../../docs/standard/threading/reader-writer-locks.md)  
 <span data-ttu-id="d92cf-126">定义可实现单个编写器/多个读取器语义的锁。</span><span class="sxs-lookup"><span data-stu-id="d92cf-126">Defines a lock that implements single-writer/multiple-reader semantics.</span></span>  
  
 [<span data-ttu-id="d92cf-127">Semaphore 和 SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="d92cf-127">Semaphore and SemaphoreSlim</span></span>](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)  
 <span data-ttu-id="d92cf-128">描述 <xref:System.Threading.Semaphore> 对象并说明如何使用这些对象控制对有限资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="d92cf-128">Describes <xref:System.Threading.Semaphore> objects and explains how to use them to control access to limited resources.</span></span>  
  
 [<span data-ttu-id="d92cf-129">同步基元概述</span><span class="sxs-lookup"><span data-stu-id="d92cf-129">Overview of Synchronization Primitives</span></span>](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 <span data-ttu-id="d92cf-130">比较提供用于锁定和同步托管线程的 .NET Framework 类的功能。</span><span class="sxs-lookup"><span data-stu-id="d92cf-130">Compares the features of the .NET Framework classes provided for locking and synchronizing managed threads.</span></span>  
  
 [<span data-ttu-id="d92cf-131">Barrier</span><span class="sxs-lookup"><span data-stu-id="d92cf-131">Barrier</span></span>](../../../docs/standard/threading/barrier.md)  
 <span data-ttu-id="d92cf-132">描述 <xref:System.Threading.Barrier> 对象，这些对象可实现分阶段操作中的线程协调屏障模式。</span><span class="sxs-lookup"><span data-stu-id="d92cf-132">Describes <xref:System.Threading.Barrier> objects that implement the barrier pattern for coordination of threads in phased operations.</span></span>  
  
 [<span data-ttu-id="d92cf-133">SpinLock</span><span class="sxs-lookup"><span data-stu-id="d92cf-133">SpinLock</span></span>](../../../docs/standard/threading/spinlock.md)  
 <span data-ttu-id="d92cf-134">描述 <xref:System.Threading.SpinLock>，某些低级别方案的监视器类的轻型替代项。</span><span class="sxs-lookup"><span data-stu-id="d92cf-134">Describes <xref:System.Threading.SpinLock>, a lightweight alternative to the Monitor class for certain low-level scenarios.</span></span>  
  
 [<span data-ttu-id="d92cf-135">SpinWait</span><span class="sxs-lookup"><span data-stu-id="d92cf-135">SpinWait</span></span>](../../../docs/standard/threading/spinwait.md)  
 <span data-ttu-id="d92cf-136">描述 <xref:System.Threading.SpinWait>，一个级别较低的同步基元，可在启动基于内核的等待之前执行忙碌的旋转。</span><span class="sxs-lookup"><span data-stu-id="d92cf-136">Describes <xref:System.Threading.SpinWait>, a low level synchronization primitive that performs busy spinning prior to initiating a kernel-based wait.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d92cf-137">参考</span><span class="sxs-lookup"><span data-stu-id="d92cf-137">Reference</span></span>  
 <xref:System.Threading.Thread>  
 <span data-ttu-id="d92cf-138">提供**线程**类的参考文档，无论该类是来自托管代码还是在托管应用程序中创建的，它都表示一个托管线程。</span><span class="sxs-lookup"><span data-stu-id="d92cf-138">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="d92cf-139">启用与用户界面交互的后台任务，通过用户界面线程上引发的事件进行通信。</span><span class="sxs-lookup"><span data-stu-id="d92cf-139">Enables background tasks that interact with the user interface, communicating via events raised on the user-interface thread.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d92cf-140">相关章节</span><span class="sxs-lookup"><span data-stu-id="d92cf-140">Related Sections</span></span>  
 [<span data-ttu-id="d92cf-141">异步文件 I/O</span><span class="sxs-lookup"><span data-stu-id="d92cf-141">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
 <span data-ttu-id="d92cf-142">描述 I/O 异步完成端口如何使用线程池处理（仅在输入/输出操作完成时，才需要）。</span><span class="sxs-lookup"><span data-stu-id="d92cf-142">Describes how I/O asynchronous completion ports use the thread pool to require processing only when an input/output operation completes.</span></span>  
  
 [<span data-ttu-id="d92cf-143">任务并行库 (TPL)</span><span class="sxs-lookup"><span data-stu-id="d92cf-143">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 <span data-ttu-id="d92cf-144">描述 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 及更高版本中建议的多线程编程的方法。</span><span class="sxs-lookup"><span data-stu-id="d92cf-144">Describes the recommended approach for multithreaded programming in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] and later.</span></span>
