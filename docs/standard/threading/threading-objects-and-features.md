---
title: 线程处理对象和功能
ms.date: 10/01/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a355c2e996ddb00dad804dfeb22987923d91aa6
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144515"
---
# <a name="threading-objects-and-features"></a><span data-ttu-id="cc27b-102">线程处理对象和功能</span><span class="sxs-lookup"><span data-stu-id="cc27b-102">Threading objects and features</span></span>

<span data-ttu-id="cc27b-103">.NET 与 <xref:System.Threading.Thread?displayProperty=nameWithType> 类一起提供了许多可帮助开发多线程应用程序的类。</span><span class="sxs-lookup"><span data-stu-id="cc27b-103">Along with the <xref:System.Threading.Thread?displayProperty=nameWithType> class, .NET provides a number of classes that help you develop multithreaded applications.</span></span> <span data-ttu-id="cc27b-104">以下文章是对这些类的概述：</span><span class="sxs-lookup"><span data-stu-id="cc27b-104">The following articles provide overview of those classes:</span></span>

|<span data-ttu-id="cc27b-105">标题</span><span class="sxs-lookup"><span data-stu-id="cc27b-105">Title</span></span>|<span data-ttu-id="cc27b-106">说明</span><span class="sxs-lookup"><span data-stu-id="cc27b-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="cc27b-107">托管线程池</span><span class="sxs-lookup"><span data-stu-id="cc27b-107">The managed thread pool</span></span>](the-managed-thread-pool.md)|<span data-ttu-id="cc27b-108">描述 <xref:System.Threading.ThreadPool?displayProperty=nameWithType> 类，它提供由 .NET 托管的工作线程池。</span><span class="sxs-lookup"><span data-stu-id="cc27b-108">Describes the <xref:System.Threading.ThreadPool?displayProperty=nameWithType> class, which provides a pool of worker threads that are managed by .NET.</span></span>|  
|[<span data-ttu-id="cc27b-109">计时器</span><span class="sxs-lookup"><span data-stu-id="cc27b-109">Timers</span></span>](timers.md)|<span data-ttu-id="cc27b-110">介绍可在多线程环境中使用的 .NET 计时器。</span><span class="sxs-lookup"><span data-stu-id="cc27b-110">Describes .NET timers that can be used in a multithreaded environment.</span></span>|
|[<span data-ttu-id="cc27b-111">同步基元概述</span><span class="sxs-lookup"><span data-stu-id="cc27b-111">Overview of synchronization primitives</span></span>](overview-of-synchronization-primitives.md)|<span data-ttu-id="cc27b-112">描述可用于同步对共享资源的访问或控制线程交互的类型。</span><span class="sxs-lookup"><span data-stu-id="cc27b-112">Describes types that can be used to synchronize access to a shared resource or control thread interaction.</span></span>|
|[<span data-ttu-id="cc27b-113">EventWaitHandle、AutoResetEvent、CountdownEvent、ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="cc27b-113">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)|<span data-ttu-id="cc27b-114">描述用于通过发送和等待信号同步线程活动的托管事件等待句柄。</span><span class="sxs-lookup"><span data-stu-id="cc27b-114">Describes managed event wait handles, which are used to synchronize thread activities by signaling and waiting for signals.</span></span>|
|[<span data-ttu-id="cc27b-115">Mutex</span><span class="sxs-lookup"><span data-stu-id="cc27b-115">Mutexes</span></span>](mutexes.md)|<span data-ttu-id="cc27b-116">描述 <xref:System.Threading.Mutex?displayProperty=nameWithType>，它可授予对共享资源的独占访问权限。</span><span class="sxs-lookup"><span data-stu-id="cc27b-116">Describes <xref:System.Threading.Mutex?displayProperty=nameWithType>, which grants exclusive access to a shared resource.</span></span>|
|[<span data-ttu-id="cc27b-117">Semaphore 和 SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="cc27b-117">Semaphore and SemaphoreSlim</span></span>](semaphore-and-semaphoreslim.md)|<span data-ttu-id="cc27b-118">描述 <xref:System.Threading.Semaphore?displayProperty=nameWithType>，它用于限制可同时访问某一共享资源或资源池的线程数。</span><span class="sxs-lookup"><span data-stu-id="cc27b-118">Describes the <xref:System.Threading.Semaphore?displayProperty=nameWithType> class, which limits number of threads that can access a shared resource or a pool of resources concurrently.</span></span>|
|[<span data-ttu-id="cc27b-119">Barrier</span><span class="sxs-lookup"><span data-stu-id="cc27b-119">Barrier</span></span>](barrier.md)|<span data-ttu-id="cc27b-120">描述 <xref:System.Threading.Barrier?displayProperty=nameWithType> 类，它可实现分阶段操作中的线程协调屏障模式。</span><span class="sxs-lookup"><span data-stu-id="cc27b-120">Describes the <xref:System.Threading.Barrier?displayProperty=nameWithType> class that implements the barrier pattern for coordination of threads in phased operations.</span></span>|
|[<span data-ttu-id="cc27b-121">SpinLock</span><span class="sxs-lookup"><span data-stu-id="cc27b-121">SpinLock</span></span>](spinlock.md)|<span data-ttu-id="cc27b-122">描述 <xref:System.Threading.SpinLock?displayProperty=nameWithType> 结构，它是某些低级别锁定方案的 <xref:System.Threading.Monitor?displayProperty=nameWithType> 类的轻型替代项。</span><span class="sxs-lookup"><span data-stu-id="cc27b-122">Describes the <xref:System.Threading.SpinLock?displayProperty=nameWithType> structure, which is a lightweight alternative to the <xref:System.Threading.Monitor?displayProperty=nameWithType> class for certain low-level locking scenarios.</span></span>|
|[<span data-ttu-id="cc27b-123">SpinWait</span><span class="sxs-lookup"><span data-stu-id="cc27b-123">SpinWait</span></span>](spinwait.md)|<span data-ttu-id="cc27b-124">描述 <xref:System.Threading.SpinWait?displayProperty=nameWithType> 结构，它为基于调整的等待提供支持。</span><span class="sxs-lookup"><span data-stu-id="cc27b-124">Describes the <xref:System.Threading.SpinWait?displayProperty=nameWithType> structure, which provides support for spin-based waiting.</span></span>|

## <a name="see-also"></a><span data-ttu-id="cc27b-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc27b-125">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- [<span data-ttu-id="cc27b-126">使用线程和线程处理</span><span class="sxs-lookup"><span data-stu-id="cc27b-126">Using threads and threading</span></span>](using-threads-and-threading.md)
- [<span data-ttu-id="cc27b-127">Asynchronous File I/O</span><span class="sxs-lookup"><span data-stu-id="cc27b-127">Asynchronous File I/O</span></span>](../io/asynchronous-file-i-o.md)
- [<span data-ttu-id="cc27b-128">并行编程</span><span class="sxs-lookup"><span data-stu-id="cc27b-128">Parallel Programming</span></span>](../parallel-programming/index.md)
- [<span data-ttu-id="cc27b-129">任务并行库 (TPL)</span><span class="sxs-lookup"><span data-stu-id="cc27b-129">Task Parallel Library (TPL)</span></span>](../parallel-programming/task-parallel-library-tpl.md)
