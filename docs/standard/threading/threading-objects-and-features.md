---
title: 线程处理对象和功能
ms.date: 08/16/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d56d962279120a03a6e4b89154ac1429ea5479e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43483653"
---
# <a name="threading-objects-and-features"></a><span data-ttu-id="3bb91-102">线程处理对象和功能</span><span class="sxs-lookup"><span data-stu-id="3bb91-102">Threading objects and features</span></span>

<span data-ttu-id="3bb91-103">.NET 与 <xref:System.Threading.Thread?displayProperty=nameWithType> 类一起提供了许多可帮助开发多线程应用程序的类。</span><span class="sxs-lookup"><span data-stu-id="3bb91-103">Along with the <xref:System.Threading.Thread?displayProperty=nameWithType> class, .NET provides a number of classes that help you develop multithreaded applications.</span></span> <span data-ttu-id="3bb91-104">以下文章是对这些类的概述：</span><span class="sxs-lookup"><span data-stu-id="3bb91-104">The following articles provide overview of those classes:</span></span>

|<span data-ttu-id="3bb91-105">标题</span><span class="sxs-lookup"><span data-stu-id="3bb91-105">Title</span></span>|<span data-ttu-id="3bb91-106">描述</span><span class="sxs-lookup"><span data-stu-id="3bb91-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="3bb91-107">托管线程池</span><span class="sxs-lookup"><span data-stu-id="3bb91-107">The managed thread pool</span></span>](the-managed-thread-pool.md)|<span data-ttu-id="3bb91-108">描述 <xref:System.Threading.ThreadPool?displayProperty=nameWithType> 类，它提供由 .NET 托管的工作线程池。</span><span class="sxs-lookup"><span data-stu-id="3bb91-108">Describes the <xref:System.Threading.ThreadPool?displayProperty=nameWithType> class, which provides a pool of worker threads that are managed by .NET.</span></span>|  
|[<span data-ttu-id="3bb91-109">计时器</span><span class="sxs-lookup"><span data-stu-id="3bb91-109">Timers</span></span>](timers.md)|<span data-ttu-id="3bb91-110">介绍可在多线程环境中使用的计时器。</span><span class="sxs-lookup"><span data-stu-id="3bb91-110">Describes timers that can be used in a multithreaded environment.</span></span>|
|[<span data-ttu-id="3bb91-111">同步基元概述</span><span class="sxs-lookup"><span data-stu-id="3bb91-111">Overview of synchronization primitives</span></span>](overview-of-synchronization-primitives.md)|<span data-ttu-id="3bb91-112">描述可用于同步对数据的访问或控制线程交互的类。</span><span class="sxs-lookup"><span data-stu-id="3bb91-112">Describes classes that can be used to synchronize access to data or control thread interaction.</span></span>|
|[<span data-ttu-id="3bb91-113">EventWaitHandle、AutoResetEvent、CountdownEvent、ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="3bb91-113">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)|<span data-ttu-id="3bb91-114">描述用于通过发送和等待信号同步线程活动的托管事件等待句柄。</span><span class="sxs-lookup"><span data-stu-id="3bb91-114">Describes managed event wait handles, which are used to synchronize thread activities by signaling and waiting for signals.</span></span>|
|[<span data-ttu-id="3bb91-115">Mutex</span><span class="sxs-lookup"><span data-stu-id="3bb91-115">Mutexes</span></span>](mutexes.md)|<span data-ttu-id="3bb91-116">描述如何使用 <xref:System.Threading.Mutex?displayProperty=nameWithType> 同步访问对象或生成自己的同步机制。</span><span class="sxs-lookup"><span data-stu-id="3bb91-116">Describes how to use a <xref:System.Threading.Mutex?displayProperty=nameWithType> to synchronize access to an object or to build your own synchronization mechanisms.</span></span>|
|[<span data-ttu-id="3bb91-117">互锁操作</span><span class="sxs-lookup"><span data-stu-id="3bb91-117">Interlocked operations</span></span>](interlocked-operations.md)|<span data-ttu-id="3bb91-118">描述 <xref:System.Threading.Interlocked?displayProperty=nameWithType> 类，它为多个线程共享的变量提供原子操作。</span><span class="sxs-lookup"><span data-stu-id="3bb91-118">Describes the <xref:System.Threading.Interlocked?displayProperty=nameWithType> class, which provides atomic operations for variables that are shared by multiple threads.</span></span>|
|[<span data-ttu-id="3bb91-119">读取器-编写器锁</span><span class="sxs-lookup"><span data-stu-id="3bb91-119">Reader-Writer Locks</span></span>](reader-writer-locks.md)|<span data-ttu-id="3bb91-120">描述 <xref:System.Threading.ReaderWriterLockSlim?displayProperty=nameWithType> 类，它提供单编写器/多读取器语义。</span><span class="sxs-lookup"><span data-stu-id="3bb91-120">Describes the <xref:System.Threading.ReaderWriterLockSlim?displayProperty=nameWithType> class, which provides single-writer/multiple-reader semantics.</span></span>|
|[<span data-ttu-id="3bb91-121">Semaphore 和 SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="3bb91-121">Semaphore and SemaphoreSlim</span></span>](semaphore-and-semaphoreslim.md)|<span data-ttu-id="3bb91-122">描述 <xref:System.Threading.Semaphore?displayProperty=nameWithType> 类并说明如何使用它控制对有限资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="3bb91-122">Describes the <xref:System.Threading.Semaphore?displayProperty=nameWithType> class and explains how to use it to control access to limited resources.</span></span>|
|[<span data-ttu-id="3bb91-123">Barrier</span><span class="sxs-lookup"><span data-stu-id="3bb91-123">Barrier</span></span>](barrier.md)|<span data-ttu-id="3bb91-124">描述 <xref:System.Threading.Barrier?displayProperty=nameWithType> 类，它可实现分阶段操作中的线程协调屏障模式。</span><span class="sxs-lookup"><span data-stu-id="3bb91-124">Describes the <xref:System.Threading.Barrier?displayProperty=nameWithType> class that implements the barrier pattern for coordination of threads in phased operations.</span></span>|
|[<span data-ttu-id="3bb91-125">SpinLock</span><span class="sxs-lookup"><span data-stu-id="3bb91-125">SpinLock</span></span>](spinlock.md)|<span data-ttu-id="3bb91-126">描述 <xref:System.Threading.SpinLock?displayProperty=nameWithType> 类，它是某些低级别方案的 <xref:System.Threading.Monitor?displayProperty=nameWithType> 类的轻型替代项。</span><span class="sxs-lookup"><span data-stu-id="3bb91-126">Describes the <xref:System.Threading.SpinLock?displayProperty=nameWithType> class, which is a lightweight alternative to the <xref:System.Threading.Monitor?displayProperty=nameWithType> class for certain low-level scenarios.</span></span>|
|[<span data-ttu-id="3bb91-127">SpinWait</span><span class="sxs-lookup"><span data-stu-id="3bb91-127">SpinWait</span></span>](spinwait.md)|<span data-ttu-id="3bb91-128">描述 <xref:System.Threading.SpinWait?displayProperty=nameWithType> 类，它是一个级别较低的同步基元，可在启动基于内核的等待之前执行忙碌的旋转。</span><span class="sxs-lookup"><span data-stu-id="3bb91-128">Describes the <xref:System.Threading.SpinWait?displayProperty=nameWithType> class, which is a low-level synchronization primitive that performs busy spinning prior to initiating a kernel-based wait.</span></span>|

## <a name="see-also"></a><span data-ttu-id="3bb91-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="3bb91-129">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- [<span data-ttu-id="3bb91-130">使用线程和线程处理</span><span class="sxs-lookup"><span data-stu-id="3bb91-130">Using threads and threading</span></span>](using-threads-and-threading.md)
- [<span data-ttu-id="3bb91-131">异步文件 I/O</span><span class="sxs-lookup"><span data-stu-id="3bb91-131">Asynchronous File I/O</span></span>](../io/asynchronous-file-i-o.md)
- [<span data-ttu-id="3bb91-132">并行编程</span><span class="sxs-lookup"><span data-stu-id="3bb91-132">Parallel Programming</span></span>](../parallel-programming/index.md)
- [<span data-ttu-id="3bb91-133">任务并行库 (TPL)</span><span class="sxs-lookup"><span data-stu-id="3bb91-133">Task Parallel Library (TPL)</span></span>](../parallel-programming/task-parallel-library-tpl.md)
