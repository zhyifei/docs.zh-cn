---
title: Mutexes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wait handles
- threading [.NET Framework], Mutex class
- Mutex class, about Mutex class
- threading [.NET Framework], cross-process synchronization
ms.assetid: 9dd06e25-12c0-4a9e-855a-452dc83803e2
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a1d69c1b943d15b9ad8c80b4d7dbafebc54990ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="mutexes"></a><span data-ttu-id="86d73-102">Mutexes</span><span class="sxs-lookup"><span data-stu-id="86d73-102">Mutexes</span></span>
<span data-ttu-id="86d73-103">你可以使用<xref:System.Threading.Mutex>来提供对资源的独占访问的对象。</span><span class="sxs-lookup"><span data-stu-id="86d73-103">You can use a <xref:System.Threading.Mutex> object to provide exclusive access to a resource.</span></span> <span data-ttu-id="86d73-104"><xref:System.Threading.Mutex>类使用的详细的系统资源比<xref:System.Threading.Monitor>类，但它可以封送跨应用程序域边界，它可以用于多个等待，并且它可以用于同步不同的进程中的线程。</span><span class="sxs-lookup"><span data-stu-id="86d73-104">The <xref:System.Threading.Mutex> class uses more system resources than the <xref:System.Threading.Monitor> class, but it can be marshaled across application domain boundaries, it can be used with multiple waits, and it can be used to synchronize threads in different processes.</span></span> <span data-ttu-id="86d73-105">有关托管同步机制的比较，请参阅[同步基元概述](../../../docs/standard/threading/overview-of-synchronization-primitives.md)。</span><span class="sxs-lookup"><span data-stu-id="86d73-105">For a comparison of managed synchronization mechanisms, see [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="86d73-106">有关代码示例，请参阅的参考文档<xref:System.Threading.Mutex.%23ctor%2A>构造函数。</span><span class="sxs-lookup"><span data-stu-id="86d73-106">For code examples, see the reference documentation for the <xref:System.Threading.Mutex.%23ctor%2A> constructors.</span></span>  
  
## <a name="using-mutexes"></a><span data-ttu-id="86d73-107">使用 Mutex</span><span class="sxs-lookup"><span data-stu-id="86d73-107">Using Mutexes</span></span>  
 <span data-ttu-id="86d73-108">线程调用<xref:System.Threading.WaitHandle.WaitOne%2A>请求所有权互斥体的方法。</span><span class="sxs-lookup"><span data-stu-id="86d73-108">A thread calls the <xref:System.Threading.WaitHandle.WaitOne%2A> method of a mutex to request ownership.</span></span> <span data-ttu-id="86d73-109">在 mutex 可用或可选超时间隔结束前，该调用会一直处于阻止状态。</span><span class="sxs-lookup"><span data-stu-id="86d73-109">The call blocks until the mutex is available, or until the optional timeout interval elapses.</span></span> <span data-ttu-id="86d73-110">如果没有任何线程拥有它，则 mutex 将处于已发出信号状态。</span><span class="sxs-lookup"><span data-stu-id="86d73-110">The state of a mutex is signaled if no thread owns it.</span></span>  
  
 <span data-ttu-id="86d73-111">一个线程释放互斥体通过调用其<xref:System.Threading.Mutex.ReleaseMutex%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="86d73-111">A thread releases a mutex by calling its <xref:System.Threading.Mutex.ReleaseMutex%2A> method.</span></span> <span data-ttu-id="86d73-112">Mutex 具有线程关联；即 mutex 只能由拥有它的线程释放。</span><span class="sxs-lookup"><span data-stu-id="86d73-112">Mutexes have thread affinity; that is, the mutex can be released only by the thread that owns it.</span></span> <span data-ttu-id="86d73-113">如果一个线程释放互斥体不拥有，<xref:System.ApplicationException>线程中引发。</span><span class="sxs-lookup"><span data-stu-id="86d73-113">If a thread releases a mutex it does not own, an <xref:System.ApplicationException> is thrown in the thread.</span></span>  
  
 <span data-ttu-id="86d73-114">因为<xref:System.Threading.Mutex>类派生自<xref:System.Threading.WaitHandle>，你还可以调用静态<xref:System.Threading.WaitHandle.WaitAll%2A>或<xref:System.Threading.WaitHandle.WaitAny%2A>方法<xref:System.Threading.WaitHandle>请求所有权的<xref:System.Threading.Mutex>与其他结合使用等待句柄。</span><span class="sxs-lookup"><span data-stu-id="86d73-114">Because the <xref:System.Threading.Mutex> class derives from <xref:System.Threading.WaitHandle>, you can also call the static <xref:System.Threading.WaitHandle.WaitAll%2A> or <xref:System.Threading.WaitHandle.WaitAny%2A> methods of <xref:System.Threading.WaitHandle> to request ownership of a <xref:System.Threading.Mutex> in combination with other wait handles.</span></span>  
  
 <span data-ttu-id="86d73-115">如果一个线程拥有<xref:System.Threading.Mutex>，线程可以指定相同<xref:System.Threading.Mutex>中重复的等待请求在调用而不会阻止其执行; 但是，它必须释放<xref:System.Threading.Mutex>尽可能多的次数，以释放所有权。</span><span class="sxs-lookup"><span data-stu-id="86d73-115">If a thread owns a <xref:System.Threading.Mutex>, that thread can specify the same <xref:System.Threading.Mutex> in repeated wait-request calls without blocking its execution; however, it must release the <xref:System.Threading.Mutex> as many times to release ownership.</span></span>  
  
## <a name="abandoned-mutexes"></a><span data-ttu-id="86d73-116">放弃的 mutex</span><span class="sxs-lookup"><span data-stu-id="86d73-116">Abandoned Mutexes</span></span>  
 <span data-ttu-id="86d73-117">如果某个线程终止而不释放<xref:System.Threading.Mutex>，则认为该 mutex 来放弃。</span><span class="sxs-lookup"><span data-stu-id="86d73-117">If a thread terminates without releasing a <xref:System.Threading.Mutex>, the mutex is said to be abandoned.</span></span> <span data-ttu-id="86d73-118">这通常指示存在严重的编程错误，因为该 mutex 正在保护的资源可能会处于不一致状态。</span><span class="sxs-lookup"><span data-stu-id="86d73-118">This often indicates a serious programming error because the resource the mutex is protecting might be left in an inconsistent state.</span></span> <span data-ttu-id="86d73-119">在.NET Framework 2.0 版中，<xref:System.Threading.AbandonedMutexException>获取互斥体的下一个线程中引发。</span><span class="sxs-lookup"><span data-stu-id="86d73-119">In the .NET Framework version 2.0, an <xref:System.Threading.AbandonedMutexException> is thrown in the next thread that acquires the mutex.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="86d73-120">在.NET framework 1.0 和 1.1 中，放弃的<xref:System.Threading.Mutex>正在设置为终止的状态和下一个等待线程获取所有权。</span><span class="sxs-lookup"><span data-stu-id="86d73-120">In the .NET Framework versions 1.0 and 1.1, an abandoned <xref:System.Threading.Mutex> is set to the signaled state and the next waiting thread gets ownership.</span></span> <span data-ttu-id="86d73-121">如果任何线程在不等待，<xref:System.Threading.Mutex>仍保留在发送信号状态。</span><span class="sxs-lookup"><span data-stu-id="86d73-121">If no thread is waiting, the <xref:System.Threading.Mutex> remains in a signaled state.</span></span> <span data-ttu-id="86d73-122">不引发异常。</span><span class="sxs-lookup"><span data-stu-id="86d73-122">No exception is thrown.</span></span>  
  
 <span data-ttu-id="86d73-123">对于系统范围的 mutex，放弃的 mutex 可能指示应用程序已突然终止（例如，通过使用 Windows 任务管理器终止）。</span><span class="sxs-lookup"><span data-stu-id="86d73-123">In the case of a system-wide mutex, an abandoned mutex might indicate that an application has been terminated abruptly (for example, by using Windows Task Manager).</span></span>  
  
## <a name="local-and-system-mutexes"></a><span data-ttu-id="86d73-124">本地 mutex 和系统 mutex</span><span class="sxs-lookup"><span data-stu-id="86d73-124">Local and System Mutexes</span></span>  
 <span data-ttu-id="86d73-125">Mutex 有两种类型：本地 mutex 和命名系统 mutex。</span><span class="sxs-lookup"><span data-stu-id="86d73-125">Mutexes are of two types: local mutexes and named system mutexes.</span></span> <span data-ttu-id="86d73-126">如果你创建<xref:System.Threading.Mutex>对象使用构造函数接受一个名称，它是与该名称的操作系统对象相关联。</span><span class="sxs-lookup"><span data-stu-id="86d73-126">If you create a <xref:System.Threading.Mutex> object using a constructor that accepts a name, it is associated with an operating-system object of that name.</span></span> <span data-ttu-id="86d73-127">命名系统 mutex 在整个操作系统中都可见，并且可用于同步进程活动。</span><span class="sxs-lookup"><span data-stu-id="86d73-127">Named system mutexes are visible throughout the operating system and can be used to synchronize the activities of processes.</span></span> <span data-ttu-id="86d73-128">你可以创建多个<xref:System.Threading.Mutex>对象来表示同一个已命名系统互斥体，并且你可以使用<xref:System.Threading.Mutex.OpenExisting%2A>方法以打开一个现有的已命名系统互斥体。</span><span class="sxs-lookup"><span data-stu-id="86d73-128">You can create multiple <xref:System.Threading.Mutex> objects that represent the same named system mutex, and you can use the <xref:System.Threading.Mutex.OpenExisting%2A> method to open an existing named system mutex.</span></span>  
  
 <span data-ttu-id="86d73-129">本地 mutex 仅存在于进程中。</span><span class="sxs-lookup"><span data-stu-id="86d73-129">A local mutex exists only within your process.</span></span> <span data-ttu-id="86d73-130">它可供你具有到本地的引用的过程中的任何线程<xref:System.Threading.Mutex>对象。</span><span class="sxs-lookup"><span data-stu-id="86d73-130">It can be used by any thread in your process that has a reference to the local <xref:System.Threading.Mutex> object.</span></span> <span data-ttu-id="86d73-131">每个<xref:System.Threading.Mutex>对象是单独的局部互斥体。</span><span class="sxs-lookup"><span data-stu-id="86d73-131">Each <xref:System.Threading.Mutex> object is a separate local mutex.</span></span>  
  
### <a name="access-control-security-for-system-mutexes"></a><span data-ttu-id="86d73-132">系统 mutex 的访问控制安全性</span><span class="sxs-lookup"><span data-stu-id="86d73-132">Access Control Security for System Mutexes</span></span>  
 <span data-ttu-id="86d73-133">.NET Framework 2.0 版提供查询和设置命名系统对象的 Windows 访问控制安全性的能力。</span><span class="sxs-lookup"><span data-stu-id="86d73-133">The .NET Framework version 2.0 provides the ability to query and set Windows access control security for named system objects.</span></span> <span data-ttu-id="86d73-134">建议从创建起立刻开始保护系统 mutex，因为系统对象是全局对象，因此可能被不是你自己的代码锁定。</span><span class="sxs-lookup"><span data-stu-id="86d73-134">Protecting system mutexes from the moment of creation is recommended because system objects are global and therefore can be locked by code other than your own.</span></span>  
  
 <span data-ttu-id="86d73-135">互斥体的访问控制安全性的信息，请参阅<xref:System.Security.AccessControl.MutexSecurity>和<xref:System.Security.AccessControl.MutexAccessRule>类，<xref:System.Security.AccessControl.MutexRights>枚举， <xref:System.Threading.Mutex.GetAccessControl%2A>， <xref:System.Threading.Mutex.SetAccessControl%2A>，和<xref:System.Threading.Mutex.OpenExisting%2A>方法<xref:System.Threading.Mutex>类，并且<xref:System.Threading.Mutex.%23ctor%28System.Boolean%2CSystem.String%2CSystem.Boolean%40%2CSystem.Security.AccessControl.MutexSecurity%29>构造函数。</span><span class="sxs-lookup"><span data-stu-id="86d73-135">For information on access control security for mutexes, see the <xref:System.Security.AccessControl.MutexSecurity> and <xref:System.Security.AccessControl.MutexAccessRule> classes, the <xref:System.Security.AccessControl.MutexRights> enumeration, the <xref:System.Threading.Mutex.GetAccessControl%2A>, <xref:System.Threading.Mutex.SetAccessControl%2A>, and <xref:System.Threading.Mutex.OpenExisting%2A> methods of the <xref:System.Threading.Mutex> class, and the <xref:System.Threading.Mutex.%23ctor%28System.Boolean%2CSystem.String%2CSystem.Boolean%40%2CSystem.Security.AccessControl.MutexSecurity%29> constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86d73-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86d73-136">See Also</span></span>  
 <xref:System.Threading.Mutex>  
 <xref:System.Threading.Mutex.%23ctor%2A>  
 <xref:System.Security.AccessControl.MutexSecurity>  
 <xref:System.Security.AccessControl.MutexAccessRule>  
 [<span data-ttu-id="86d73-137">线程处理</span><span class="sxs-lookup"><span data-stu-id="86d73-137">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="86d73-138">线程处理对象和功能</span><span class="sxs-lookup"><span data-stu-id="86d73-138">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 [<span data-ttu-id="86d73-139">监视器</span><span class="sxs-lookup"><span data-stu-id="86d73-139">Monitors</span></span>](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)  
 [<span data-ttu-id="86d73-140">线程与线程处理</span><span class="sxs-lookup"><span data-stu-id="86d73-140">Threads and Threading</span></span>](../../../docs/standard/threading/threads-and-threading.md)
