---
title: 托管线程处理基本知识
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- multiple threads
- threading [.NET Framework], multiple threads
- threading [.NET Framework], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fa91bb22de6492815f79bfd50e1fefc800c6047
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586508"
---
# <a name="managed-threading-basics"></a><span data-ttu-id="856d8-102">托管线程处理基本知识</span><span class="sxs-lookup"><span data-stu-id="856d8-102">Managed Threading Basics</span></span>
<span data-ttu-id="856d8-103">本节的前五个主题有助于确定何时使用托管线程，并介绍一些基本功能。</span><span class="sxs-lookup"><span data-stu-id="856d8-103">The first five topics of this section are designed to help you determine when to use managed threading, and to explain some basic features.</span></span> <span data-ttu-id="856d8-104">若要了解提供附加功能的类，请参阅[线程处理对象和功能](../../../docs/standard/threading/threading-objects-and-features.md)和[同步基元概述](../../../docs/standard/threading/overview-of-synchronization-primitives.md)。</span><span class="sxs-lookup"><span data-stu-id="856d8-104">For information on classes that provide additional features, see [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) and [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="856d8-105">本节中的剩余主题涵盖了高级主题，其中包括托管线程与 Windows 操作系统的交互。</span><span class="sxs-lookup"><span data-stu-id="856d8-105">The rest of the topics in this section cover advanced topics, including the interaction of managed threading with the Windows operating system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="856d8-106">在 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 中，任务并行库和 PLINQ 提供了多线程程序中的任务并行和数据并行 API。</span><span class="sxs-lookup"><span data-stu-id="856d8-106">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the Task Parallel Library and PLINQ provide APIs for task and data parallelism in multi-threaded programs.</span></span> <span data-ttu-id="856d8-107">有关详细信息，请参阅[并行编程](../../../docs/standard/parallel-programming/index.md)。</span><span class="sxs-lookup"><span data-stu-id="856d8-107">For more information, see [Parallel Programming](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="856d8-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="856d8-108">In This Section</span></span>  
 [<span data-ttu-id="856d8-109">线程与线程处理</span><span class="sxs-lookup"><span data-stu-id="856d8-109">Threads and Threading</span></span>](../../../docs/standard/threading/threads-and-threading.md)  
 <span data-ttu-id="856d8-110">介绍了多个线程的优缺点，并概述了可能创建线程或使用线程池线程的方案。</span><span class="sxs-lookup"><span data-stu-id="856d8-110">Discusses the advantages and drawbacks of multiple threads, and outlines the scenarios in which you might create threads or use thread pool threads.</span></span>  
  
 [<span data-ttu-id="856d8-111">托管线程中的异常</span><span class="sxs-lookup"><span data-stu-id="856d8-111">Exceptions in Managed Threads</span></span>](../../../docs/standard/threading/exceptions-in-managed-threads.md)  
 <span data-ttu-id="856d8-112">介绍了对于不同版本的 .NET Framework，线程中未经处理的异常行为，特别是导致应用终止的情况。</span><span class="sxs-lookup"><span data-stu-id="856d8-112">Describes the behavior of unhandled exceptions in threads for different versions of the .NET Framework, in particular the situations in which they result in termination of the application.</span></span>  
  
 [<span data-ttu-id="856d8-113">为多线程处理同步数据</span><span class="sxs-lookup"><span data-stu-id="856d8-113">Synchronizing Data for Multithreading</span></span>](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 <span data-ttu-id="856d8-114">介绍了在用于多个线程的类中同步数据的策略。</span><span class="sxs-lookup"><span data-stu-id="856d8-114">Describes strategies for synchronizing data in classes that will be used with multiple threads.</span></span>  
  
 [<span data-ttu-id="856d8-115">托管线程状态</span><span class="sxs-lookup"><span data-stu-id="856d8-115">Managed Thread States</span></span>](../../../docs/standard/threading/managed-thread-states.md)  
 <span data-ttu-id="856d8-116">介绍了基本线程状态，以及如何检测线程是否正在运行。</span><span class="sxs-lookup"><span data-stu-id="856d8-116">Describes the basic thread states, and explains how to detect whether a thread is running.</span></span>  
  
 [<span data-ttu-id="856d8-117">前台和后台线程</span><span class="sxs-lookup"><span data-stu-id="856d8-117">Foreground and Background Threads</span></span>](../../../docs/standard/threading/foreground-and-background-threads.md)  
 <span data-ttu-id="856d8-118">介绍了前台和后台线程的区别。</span><span class="sxs-lookup"><span data-stu-id="856d8-118">Explains the differences between foreground and background threads.</span></span>  
  
 [<span data-ttu-id="856d8-119">Windows 中的托管和非托管线程</span><span class="sxs-lookup"><span data-stu-id="856d8-119">Managed and Unmanaged Threading in Windows</span></span>](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)  
 <span data-ttu-id="856d8-120">介绍了托管和非托管线程的关系，列出了 Windows 线程 API 的相当托管版本，并讨论了 COM 单元和托管线程的交互。</span><span class="sxs-lookup"><span data-stu-id="856d8-120">Discusses the relationship between managed and unmanaged threading, lists managed equivalents for Windows threading APIs, and discusses the interaction of COM apartments and managed threads.</span></span>  
  
 [<span data-ttu-id="856d8-121">Thread.Suspend、垃圾回收和安全点</span><span class="sxs-lookup"><span data-stu-id="856d8-121">Thread.Suspend, Garbage Collection, and Safe Points</span></span>](../../../docs/standard/threading/thread-suspend-garbage-collection-and-safe-points.md)  
 <span data-ttu-id="856d8-122">介绍了线程暂停和垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="856d8-122">Describes thread suspension and garbage collection.</span></span>  
  
 [<span data-ttu-id="856d8-123">线程本地存储：线程相关的静态字段和数据槽</span><span class="sxs-lookup"><span data-stu-id="856d8-123">Thread Local Storage: Thread-Relative Static Fields and Data Slots</span></span>](../../../docs/standard/threading/thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 <span data-ttu-id="856d8-124">介绍了线程相对存储机制。</span><span class="sxs-lookup"><span data-stu-id="856d8-124">Describes thread-relative storage mechanisms.</span></span>  
  
 [<span data-ttu-id="856d8-125">托管线程中的取消</span><span class="sxs-lookup"><span data-stu-id="856d8-125">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)  
 <span data-ttu-id="856d8-126">介绍了如何使用取消令牌取消异步操作或长时间运行的同步操作。</span><span class="sxs-lookup"><span data-stu-id="856d8-126">Describes how asynchronous or long-running synchronous operations can be canceled by using a cancellation token.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="856d8-127">参考</span><span class="sxs-lookup"><span data-stu-id="856d8-127">Reference</span></span>  
 <xref:System.Threading.Thread>  
 <span data-ttu-id="856d8-128">提供**线程**类的参考文档，无论该类是来自托管代码还是在托管应用程序中创建的，它都表示一个托管线程。</span><span class="sxs-lookup"><span data-stu-id="856d8-128">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="856d8-129">提供了一种安全实现多线程处理与用户界面对象的方式。</span><span class="sxs-lookup"><span data-stu-id="856d8-129">Provides a safe way to implement multithreading in conjunction with user-interface objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="856d8-130">相关章节</span><span class="sxs-lookup"><span data-stu-id="856d8-130">Related Sections</span></span>  
 [<span data-ttu-id="856d8-131">同步基元概述</span><span class="sxs-lookup"><span data-stu-id="856d8-131">Overview of Synchronization Primitives</span></span>](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 <span data-ttu-id="856d8-132">介绍了用于同步多个线程活动的托管类。</span><span class="sxs-lookup"><span data-stu-id="856d8-132">Describes the managed classes used to synchronize the activities of multiple threads.</span></span>  
  
 [<span data-ttu-id="856d8-133">托管线程处理的最佳做法</span><span class="sxs-lookup"><span data-stu-id="856d8-133">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 <span data-ttu-id="856d8-134">介绍了常见的多线程处理问题，以及避免这些问题发生的策略。</span><span class="sxs-lookup"><span data-stu-id="856d8-134">Describes common problems with multithreading and strategies for avoiding problems.</span></span>  
  
 [<span data-ttu-id="856d8-135">并行编程</span><span class="sxs-lookup"><span data-stu-id="856d8-135">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 <span data-ttu-id="856d8-136">介绍了任务并行库和 PLINQ，它们极大地简化了创建异步和多线程 .NET Framework 应用的工作。</span><span class="sxs-lookup"><span data-stu-id="856d8-136">Describes the Task Parallel Library and PLINQ, which greatly simplify the work of creating asynchronous and multi-threaded .NET Framework applications.</span></span>
