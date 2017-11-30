---
title: "托管线程处理基本知识"
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
- threading [.NET Framework], multiple threads
- threading [.NET Framework], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 62c207f6074e33813887c6903f5285ee72d14e85
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="managed-threading-basics"></a><span data-ttu-id="50ee2-102">托管线程处理基本知识</span><span class="sxs-lookup"><span data-stu-id="50ee2-102">Managed Threading Basics</span></span>
<span data-ttu-id="50ee2-103">本部分的前五个主题旨在帮助你确定何时使用托管线程处理，并介绍一些基本功能。</span><span class="sxs-lookup"><span data-stu-id="50ee2-103">The first five topics of this section are designed to help you determine when to use managed threading, and to explain some basic features.</span></span> <span data-ttu-id="50ee2-104">提供其他功能的类的信息，请参阅[线程处理对象和功能](../../../docs/standard/threading/threading-objects-and-features.md)和[同步基元概述](../../../docs/standard/threading/overview-of-synchronization-primitives.md)。</span><span class="sxs-lookup"><span data-stu-id="50ee2-104">For information on classes that provide additional features, see [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) and [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="50ee2-105">在此部分涵盖的主题的其余部分高级主题，包括托管线程处理与 Windows 操作系统的系统的交互。</span><span class="sxs-lookup"><span data-stu-id="50ee2-105">The rest of the topics in this section cover advanced topics, including the interaction of managed threading with the Windows operating system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50ee2-106">在[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]，任务并行库和 PLINQ 提供的 Api 来多线程程序中的任务和数据并行。</span><span class="sxs-lookup"><span data-stu-id="50ee2-106">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the Task Parallel Library and PLINQ provide APIs for task and data parallelism in multi-threaded programs.</span></span> <span data-ttu-id="50ee2-107">有关详细信息，请参阅[并行编程](../../../docs/standard/parallel-programming/index.md)。</span><span class="sxs-lookup"><span data-stu-id="50ee2-107">For more information, see [Parallel Programming](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="50ee2-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="50ee2-108">In This Section</span></span>  
 [<span data-ttu-id="50ee2-109">线程与线程处理</span><span class="sxs-lookup"><span data-stu-id="50ee2-109">Threads and Threading</span></span>](../../../docs/standard/threading/threads-and-threading.md)  
 <span data-ttu-id="50ee2-110">讨论的优点和缺点的多个线程，并概述了你可能创建线程或使用线程池线程的方案。</span><span class="sxs-lookup"><span data-stu-id="50ee2-110">Discusses the advantages and drawbacks of multiple threads, and outlines the scenarios in which you might create threads or use thread pool threads.</span></span>  
  
 [<span data-ttu-id="50ee2-111">托管线程中的异常</span><span class="sxs-lookup"><span data-stu-id="50ee2-111">Exceptions in Managed Threads</span></span>](../../../docs/standard/threading/exceptions-in-managed-threads.md)  
 <span data-ttu-id="50ee2-112">描述针对不同版本的.NET Framework 中，线程中的未处理异常的行为尤其情况中它们可以导致应用终止。</span><span class="sxs-lookup"><span data-stu-id="50ee2-112">Describes the behavior of unhandled exceptions in threads for different versions of the .NET Framework, in particular the situations in which they result in termination of the application.</span></span>  
  
 [<span data-ttu-id="50ee2-113">为多线程处理同步数据</span><span class="sxs-lookup"><span data-stu-id="50ee2-113">Synchronizing Data for Multithreading</span></span>](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 <span data-ttu-id="50ee2-114">介绍了同步用于多个线程的类中的数据的策略。</span><span class="sxs-lookup"><span data-stu-id="50ee2-114">Describes strategies for synchronizing data in classes that will be used with multiple threads.</span></span>  
  
 [<span data-ttu-id="50ee2-115">托管线程状态</span><span class="sxs-lookup"><span data-stu-id="50ee2-115">Managed Thread States</span></span>](../../../docs/standard/threading/managed-thread-states.md)  
 <span data-ttu-id="50ee2-116">介绍基本的线程状态，并说明如何检测是否正在运行一个线程。</span><span class="sxs-lookup"><span data-stu-id="50ee2-116">Describes the basic thread states, and explains how to detect whether a thread is running.</span></span>  
  
 [<span data-ttu-id="50ee2-117">前台和后台线程</span><span class="sxs-lookup"><span data-stu-id="50ee2-117">Foreground and Background Threads</span></span>](../../../docs/standard/threading/foreground-and-background-threads.md)  
 <span data-ttu-id="50ee2-118">介绍前景色和背景线程之间的差异。</span><span class="sxs-lookup"><span data-stu-id="50ee2-118">Explains the differences between foreground and background threads.</span></span>  
  
 [<span data-ttu-id="50ee2-119">Windows 中的托管和非托管线程</span><span class="sxs-lookup"><span data-stu-id="50ee2-119">Managed and Unmanaged Threading in Windows</span></span>](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)  
 <span data-ttu-id="50ee2-120">讨论托管和非托管线程处理之间的关系、 windows 线程处理 Api，列出托管等效项和讨论 COM 单元和托管的线程的交互。</span><span class="sxs-lookup"><span data-stu-id="50ee2-120">Discusses the relationship between managed and unmanaged threading, lists managed equivalents for Windows threading APIs, and discusses the interaction of COM apartments and managed threads.</span></span>  
  
 [<span data-ttu-id="50ee2-121">Thread.Suspend、垃圾回收和安全点</span><span class="sxs-lookup"><span data-stu-id="50ee2-121">Thread.Suspend, Garbage Collection, and Safe Points</span></span>](../../../docs/standard/threading/thread-suspend-garbage-collection-and-safe-points.md)  
 <span data-ttu-id="50ee2-122">描述线程挂起和垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="50ee2-122">Describes thread suspension and garbage collection.</span></span>  
  
 [<span data-ttu-id="50ee2-123">线程本地存储：线程相关的静态字段和数据槽</span><span class="sxs-lookup"><span data-stu-id="50ee2-123">Thread Local Storage: Thread-Relative Static Fields and Data Slots</span></span>](../../../docs/standard/threading/thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 <span data-ttu-id="50ee2-124">介绍线程相关的存储机制。</span><span class="sxs-lookup"><span data-stu-id="50ee2-124">Describes thread-relative storage mechanisms.</span></span>  
  
 [<span data-ttu-id="50ee2-125">托管线程中的取消</span><span class="sxs-lookup"><span data-stu-id="50ee2-125">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)  
 <span data-ttu-id="50ee2-126">描述如何异步操作或长时间运行的同步操作可通过使用取消标记被取消。</span><span class="sxs-lookup"><span data-stu-id="50ee2-126">Describes how asynchronous or long-running synchronous operations can be canceled by using a cancellation token.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="50ee2-127">参考</span><span class="sxs-lookup"><span data-stu-id="50ee2-127">Reference</span></span>  
 <xref:System.Threading.Thread>  
 <span data-ttu-id="50ee2-128">提供**线程**类的参考文档，无论该类是来自托管代码还是在托管应用程序中创建的，它都表示一个托管线程。</span><span class="sxs-lookup"><span data-stu-id="50ee2-128">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="50ee2-129">提供一种安全的方法，以实现多线程处理与用户界面对象结合使用。</span><span class="sxs-lookup"><span data-stu-id="50ee2-129">Provides a safe way to implement multithreading in conjunction with user-interface objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="50ee2-130">相关章节</span><span class="sxs-lookup"><span data-stu-id="50ee2-130">Related Sections</span></span>  
 [<span data-ttu-id="50ee2-131">同步基元概述</span><span class="sxs-lookup"><span data-stu-id="50ee2-131">Overview of Synchronization Primitives</span></span>](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 <span data-ttu-id="50ee2-132">介绍用于同步多个线程的活动的托管的类。</span><span class="sxs-lookup"><span data-stu-id="50ee2-132">Describes the managed classes used to synchronize the activities of multiple threads.</span></span>  
  
 [<span data-ttu-id="50ee2-133">托管线程处理的最佳做法</span><span class="sxs-lookup"><span data-stu-id="50ee2-133">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 <span data-ttu-id="50ee2-134">描述常见的问题的多线程处理的避免出现的问题和策略。</span><span class="sxs-lookup"><span data-stu-id="50ee2-134">Describes common problems with multithreading and strategies for avoiding problems.</span></span>  
  
 [<span data-ttu-id="50ee2-135">并行编程</span><span class="sxs-lookup"><span data-stu-id="50ee2-135">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 <span data-ttu-id="50ee2-136">描述任务并行库和 PLINQ 中，极大地简化了创建异步和多线程的.NET Framework 应用程序的工作。</span><span class="sxs-lookup"><span data-stu-id="50ee2-136">Describes the Task Parallel Library and PLINQ, which greatly simplify the work of creating asynchronous and multi-threaded .NET Framework applications.</span></span>
