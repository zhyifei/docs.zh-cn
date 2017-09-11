---
title: "线程同步 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 04f485d1-8333-4510-9e72-c334e7427e7e
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 240937905254120f777ce140049084279c35005c
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="thread-synchronization-visual-basic"></a><span data-ttu-id="4106d-102">线程同步 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4106d-102">Thread Synchronization (Visual Basic)</span></span>
<span data-ttu-id="4106d-103">以下各节描述了功能和可用于同步对多线程应用程序中的资源的访问的类。</span><span class="sxs-lookup"><span data-stu-id="4106d-103">The following sections describe features and classes that can be used to synchronize access to resources in multithreaded applications.</span></span>  
  
 <span data-ttu-id="4106d-104">在应用程序中使用多个线程的优势之一在于每个线程以异步方式执行。</span><span class="sxs-lookup"><span data-stu-id="4106d-104">One of the benefits of using multiple threads in an application is that each thread executes asynchronously.</span></span> <span data-ttu-id="4106d-105">对于 Windows 应用程序，这允许耗时的任务可以在应用程序窗口时后台执行，并且控件保持响应状态。</span><span class="sxs-lookup"><span data-stu-id="4106d-105">For Windows applications, this allows time-consuming tasks to be performed in the background while the application window and controls remain responsive.</span></span> <span data-ttu-id="4106d-106">为服务器应用程序，多线程处理提供的功能来处理不同的线程与每个传入请求。</span><span class="sxs-lookup"><span data-stu-id="4106d-106">For server applications, multithreading provides the ability to handle each incoming request with a different thread.</span></span> <span data-ttu-id="4106d-107">否则，直到上一个请求在完全满足将无法处理每个新请求。</span><span class="sxs-lookup"><span data-stu-id="4106d-107">Otherwise, each new request would not get serviced until the previous request had been fully satisfied.</span></span>  
  
 <span data-ttu-id="4106d-108">但是，如文件句柄、 网络连接和内存资源的访问权限的线程表示的异步特性必须协调。</span><span class="sxs-lookup"><span data-stu-id="4106d-108">However, the asynchronous nature of threads means that access to resources such as file handles, network connections, and memory must be coordinated.</span></span> <span data-ttu-id="4106d-109">否则，两个或多个线程可能在同一时间，每个不知道对方的操作访问同一资源。</span><span class="sxs-lookup"><span data-stu-id="4106d-109">Otherwise, two or more threads could access the same resource at the same time, each unaware of the other's actions.</span></span> <span data-ttu-id="4106d-110">结果是不可预知的数据损坏。</span><span class="sxs-lookup"><span data-stu-id="4106d-110">The result is unpredictable data corruption.</span></span>  
  
 <span data-ttu-id="4106d-111">对于整数数据类型的简单操作，同步线程可以通过实现<xref:System.Threading.Interlocked>类</xref:System.Threading.Interlocked>的成员</span><span class="sxs-lookup"><span data-stu-id="4106d-111">For simple operations on integral numeric data types, synchronizing threads can be accomplished with members of the <xref:System.Threading.Interlocked> class.</span></span> <span data-ttu-id="4106d-112">对于其他所有数据类型和非线程安全资源，多线程处理只能安全地执行本主题中使用的结构。</span><span class="sxs-lookup"><span data-stu-id="4106d-112">For all other data types and non thread-safe resources, multithreading can only be safely performed using the constructs in this topic.</span></span>  
  
 <span data-ttu-id="4106d-113">有关多线程编程的背景信息，请参阅︰</span><span class="sxs-lookup"><span data-stu-id="4106d-113">For background information on multithreaded programming, see:</span></span>  
  
-   [<span data-ttu-id="4106d-114">托管线程处理基本知识</span><span class="sxs-lookup"><span data-stu-id="4106d-114">Managed Threading Basics</span></span>](http://msdn.microsoft.com/library/b2944911-0e8f-427d-a8bb-077550618935)  
  
-   [<span data-ttu-id="4106d-115">使用线程和线程处理</span><span class="sxs-lookup"><span data-stu-id="4106d-115">Using Threads and Threading</span></span>](http://msdn.microsoft.com/library/9b5ec2cd-121b-4d49-b075-222cf26f2344)  
  
-   [<span data-ttu-id="4106d-116">托管线程处理最佳做法</span><span class="sxs-lookup"><span data-stu-id="4106d-116">Managed Threading Best Practices</span></span>](http://msdn.microsoft.com/library/e51988e7-7f4b-4646-a06d-1416cee8d557)  
  
## <a name="the-lock-and-synclock-keywords"></a><span data-ttu-id="4106d-117">Lock 和 SyncLock 关键字</span><span class="sxs-lookup"><span data-stu-id="4106d-117">The lock and SyncLock Keywords</span></span>  
 <span data-ttu-id="4106d-118">Visual Basic`SyncLock`语句可用来确保代码块运行完成，无需中断由其他线程。</span><span class="sxs-lookup"><span data-stu-id="4106d-118">The Visual Basic `SyncLock` statement can be used to ensure that a block of code runs to completion without interruption by other threads.</span></span> <span data-ttu-id="4106d-119">通过获取给定对象的互斥锁的代码块的持续时间内完成此操作。</span><span class="sxs-lookup"><span data-stu-id="4106d-119">This is accomplished by obtaining a mutual-exclusion lock for a given object for the duration of the code block.</span></span>  
  
 <span data-ttu-id="4106d-120">一个`SyncLock`语句给定对象作为参数，并且后面跟着一次只能由一个线程要执行的代码块。</span><span class="sxs-lookup"><span data-stu-id="4106d-120">A `SyncLock` statement is given an object as an argument, and is followed by a code block that is to be executed by only one thread at a time.</span></span> <span data-ttu-id="4106d-121">例如: </span><span class="sxs-lookup"><span data-stu-id="4106d-121">For example:</span></span>  
  
```vb  
Public Class TestThreading  
    Dim lockThis As New Object  
  
    Public Sub Process()  
        SyncLock lockThis  
            ' Access thread-sensitive resources.  
        End SyncLock  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="4106d-122">参数提供给`SyncLock`关键字必须是基于引用类型的对象，用于定义锁定的范围。</span><span class="sxs-lookup"><span data-stu-id="4106d-122">The argument provided to the `SyncLock` keyword must be an object based on a reference type, and is used to define the scope of the lock.</span></span> <span data-ttu-id="4106d-123">在上面的示例中，锁的范围被限制为此函数因为没有对该对象引用`lockThis`函数外不存在。</span><span class="sxs-lookup"><span data-stu-id="4106d-123">In the example above, the lock scope is limited to this function because no references to the object `lockThis` exist outside the function.</span></span> <span data-ttu-id="4106d-124">如果存在这样的引用一样，锁的范围会扩展到该对象。</span><span class="sxs-lookup"><span data-stu-id="4106d-124">If such a reference did exist, lock scope would extend to that object.</span></span> <span data-ttu-id="4106d-125">严格地说，提供的对象是仅用于唯一标识要在多个线程之间共享，因此它可以是任意类实例的资源。</span><span class="sxs-lookup"><span data-stu-id="4106d-125">Strictly speaking, the object provided is used solely to uniquely identify the resource being shared among multiple threads, so it can be an arbitrary class instance.</span></span> <span data-ttu-id="4106d-126">在实践中，但是，此对象通常表示为哪个线程同步是必不可少的资源。</span><span class="sxs-lookup"><span data-stu-id="4106d-126">In practice, however, this object usually represents the resource for which thread synchronization is necessary.</span></span> <span data-ttu-id="4106d-127">例如，如果容器对象是由多个线程使用，然后传递容器要锁定，而后面锁的同步的代码块将访问该容器。</span><span class="sxs-lookup"><span data-stu-id="4106d-127">For example, if a container object is to be used by multiple threads, then the container can be passed to lock, and the synchronized code block following the lock would access the container.</span></span> <span data-ttu-id="4106d-128">只要其他线程锁定在同一个包含然后才能访问它，然后对该对象的访问安全地同步。</span><span class="sxs-lookup"><span data-stu-id="4106d-128">As long as other threads locks on the same contain before accessing it, then access to the object is safely synchronized.</span></span>  
  
 <span data-ttu-id="4106d-129">通常情况下，最好避免锁定`public`类型，或在您的应用程序的控制之外的对象实例。</span><span class="sxs-lookup"><span data-stu-id="4106d-129">Generally, it is best to avoid locking on a `public` type, or on object instances beyond the control of your application.</span></span> <span data-ttu-id="4106d-130">例如，`lockThis`由于受控制的代码可能会锁定对象也可能存在问题，如果该实例可以公开访问。</span><span class="sxs-lookup"><span data-stu-id="4106d-130">For example, `lockThis` can be problematic if the instance can be accessed publicly, because code beyond your control may lock on the object as well.</span></span> <span data-ttu-id="4106d-131">这可能导致死锁，其中两个或多个线程等待的同一个对象的版本。</span><span class="sxs-lookup"><span data-stu-id="4106d-131">This could create deadlock situations where two or more threads wait for the release of the same object.</span></span> <span data-ttu-id="4106d-132">出于同一原因，锁定对公共数据类型，而不是一个对象，可能导致问题。</span><span class="sxs-lookup"><span data-stu-id="4106d-132">Locking on a public data type, as opposed to an object, can cause problems for the same reason.</span></span> <span data-ttu-id="4106d-133">锁定字符串是尤其危险，因为字符串被*暂留*由公共语言运行时 (CLR)。</span><span class="sxs-lookup"><span data-stu-id="4106d-133">Locking on literal strings is especially risky because literal strings are *interned* by the common language runtime (CLR).</span></span> <span data-ttu-id="4106d-134">这意味着没有文字整个程序的任何给定的字符串的一个实例，即完全相同的对象表示在所有文字在所有线程上运行应用程序域。</span><span class="sxs-lookup"><span data-stu-id="4106d-134">This means that there is one instance of any given string literal for the entire program, the exact same object represents the literal in all running application domains, on all threads.</span></span> <span data-ttu-id="4106d-135">结果是，锁放置在具有相同的内容的字符串任意位置在应用程序进程锁定应用程序中该字符串的所有实例。</span><span class="sxs-lookup"><span data-stu-id="4106d-135">As a result, a lock placed on a string with the same contents anywhere in the application process locks all instances of that string in the application.</span></span> <span data-ttu-id="4106d-136">因此，最好锁定不暂留的私有或受保护成员。</span><span class="sxs-lookup"><span data-stu-id="4106d-136">As a result, it is best to lock a private or protected member that is not interned.</span></span> <span data-ttu-id="4106d-137">某些类提供专门用于锁定的成员。</span><span class="sxs-lookup"><span data-stu-id="4106d-137">Some classes provide members specifically for locking.</span></span> <span data-ttu-id="4106d-138">的<xref:System.Array>类型，例如，提供了<xref:System.Array.SyncRoot%2A>。</xref:System.Array.SyncRoot%2A> </xref:System.Array></span><span class="sxs-lookup"><span data-stu-id="4106d-138">The <xref:System.Array> type, for example, provides <xref:System.Array.SyncRoot%2A>.</span></span> <span data-ttu-id="4106d-139">提供了许多集合类型`SyncRoot`以及成员。</span><span class="sxs-lookup"><span data-stu-id="4106d-139">Many collection types provide a `SyncRoot` member as well.</span></span>  
  
 <span data-ttu-id="4106d-140">有关详细信息`SyncLock`语句中，请参阅下列主题︰</span><span class="sxs-lookup"><span data-stu-id="4106d-140">For more information about the `SyncLock` statement, see the following topics:</span></span>  
  
-   [<span data-ttu-id="4106d-141">SyncLock 语句</span><span class="sxs-lookup"><span data-stu-id="4106d-141">SyncLock Statement</span></span>](../../../../visual-basic/language-reference/statements/synclock-statement.md)  
  
-   @System.Threading.Monitor  
  
## <a name="monitors"></a><span data-ttu-id="4106d-142">监视器</span><span class="sxs-lookup"><span data-stu-id="4106d-142">Monitors</span></span>  
 <span data-ttu-id="4106d-143">如`SyncLock`关键字，监视器防止多个线程同时执行代码块。</span><span class="sxs-lookup"><span data-stu-id="4106d-143">Like the `SyncLock` keyword, monitors prevent blocks of code from simultaneous execution by multiple threads.</span></span> <span data-ttu-id="4106d-144"><xref:System.Threading.Monitor.Enter%2A>方法允许一个且只有一个线程继续执行下面的语句; 所有其他线程被阻塞，直到执行的线程调用<xref:System.Threading.Monitor.Exit%2A>。</xref:System.Threading.Monitor.Exit%2A> </xref:System.Threading.Monitor.Enter%2A></span><span class="sxs-lookup"><span data-stu-id="4106d-144">The <xref:System.Threading.Monitor.Enter%2A> method allows one and only one thread to proceed into the following statements; all other threads are blocked until the executing thread calls <xref:System.Threading.Monitor.Exit%2A>.</span></span> <span data-ttu-id="4106d-145">这就类似于使用`SyncLock`关键字。</span><span class="sxs-lookup"><span data-stu-id="4106d-145">This is just like using the `SyncLock` keyword.</span></span> <span data-ttu-id="4106d-146">例如：</span><span class="sxs-lookup"><span data-stu-id="4106d-146">For example:</span></span>  
  
```vb  
SyncLock x  
    DoSomething()  
End SyncLock  
```  
  
 <span data-ttu-id="4106d-147">这等效于︰</span><span class="sxs-lookup"><span data-stu-id="4106d-147">This is equivalent to:</span></span>  
  
```vb  
Dim obj As Object = CType(x, Object)  
System.Threading.Monitor.Enter(obj)  
Try  
    DoSomething()  
Finally  
    System.Threading.Monitor.Exit(obj)  
End Try  
```  
  
 <span data-ttu-id="4106d-148">使用`SyncLock`关键字优于通常使用<xref:System.Threading.Monitor>类直接，同时由于`SyncLock`更为简洁，而且因为`SyncLock`可确保发布后的基础的监视器，即使受保护的代码将引发异常。</xref:System.Threading.Monitor></span><span class="sxs-lookup"><span data-stu-id="4106d-148">Using the `SyncLock` keyword is generally preferred over using the <xref:System.Threading.Monitor> class directly, both because `SyncLock` is more concise, and because `SyncLock` insures that the underlying monitor is released, even if the protected code throws an exception.</span></span> <span data-ttu-id="4106d-149">完成此操作`Finally`关键字，它都执行关联的代码块而不考虑是否会引发异常。</span><span class="sxs-lookup"><span data-stu-id="4106d-149">This is accomplished with the `Finally` keyword, which executes its associated code block regardless of whether an exception is thrown.</span></span>  
  
## <a name="synchronization-events-and-wait-handles"></a><span data-ttu-id="4106d-150">同步事件和等待句柄</span><span class="sxs-lookup"><span data-stu-id="4106d-150">Synchronization Events and Wait Handles</span></span>  
 <span data-ttu-id="4106d-151">使用锁或监视器可用于预防同时执行的线程敏感代码块，但这些构造不允许一个线程通信到另一个事件。</span><span class="sxs-lookup"><span data-stu-id="4106d-151">Using a lock or monitor is useful for preventing the simultaneous execution of thread-sensitive blocks of code, but these constructs do not allow one thread to communicate an event to another.</span></span> <span data-ttu-id="4106d-152">这要求*同步事件*，哪些是具有两种状态之一的对象终止和非终止，可用来激活和挂起的线程。</span><span class="sxs-lookup"><span data-stu-id="4106d-152">This requires *synchronization events*, which are objects that have one of two states, signaled and un-signaled, that can be used to activate and suspend threads.</span></span> <span data-ttu-id="4106d-153">线程可以通过所进行的同步事件为非终止状态，等待挂起，并且可以通过将事件状态为终止状态更改激活。</span><span class="sxs-lookup"><span data-stu-id="4106d-153">Threads can be suspended by being made to wait on a synchronization event that is unsignaled, and can be activated by changing the event state to signaled.</span></span> <span data-ttu-id="4106d-154">如果线程尝试等待已终止的事件，该线程将继续执行而不会延迟。</span><span class="sxs-lookup"><span data-stu-id="4106d-154">If a thread attempts to wait on an event that is already signaled, then the thread continues to execute without delay.</span></span>  
  
 <span data-ttu-id="4106d-155">有两种类型的同步事件︰ <xref:System.Threading.AutoResetEvent>，和<xref:System.Threading.ManualResetEvent>。</xref:System.Threading.ManualResetEvent> </xref:System.Threading.AutoResetEvent></span><span class="sxs-lookup"><span data-stu-id="4106d-155">There are two kinds of synchronization events: <xref:System.Threading.AutoResetEvent>, and <xref:System.Threading.ManualResetEvent>.</span></span> <span data-ttu-id="4106d-156">它们的差异仅在于<xref:System.Threading.AutoResetEvent>从终止变为非终止自动无论何时激活线程。</xref:System.Threading.AutoResetEvent></span><span class="sxs-lookup"><span data-stu-id="4106d-156">They differ only in that <xref:System.Threading.AutoResetEvent> changes from signaled to unsignaled automatically any time it activates a thread.</span></span> <span data-ttu-id="4106d-157">相反，<xref:System.Threading.ManualResetEvent>允许任意数量的线程将激活其终止状态的并且将仅恢复到非终止时，状态其<xref:System.Threading.EventWaitHandle.Reset%2A>调用方法。</xref:System.Threading.EventWaitHandle.Reset%2A> </xref:System.Threading.ManualResetEvent></span><span class="sxs-lookup"><span data-stu-id="4106d-157">Conversely, a <xref:System.Threading.ManualResetEvent> allows any number of threads to be activated by its signaled state, and will only revert to an unsignaled state when its <xref:System.Threading.EventWaitHandle.Reset%2A> method is called.</span></span>  
  
 <span data-ttu-id="4106d-158">线程会等待事件通过调用等待方法之一来如<xref:System.Threading.WaitHandle.WaitOne%2A>， <xref:System.Threading.WaitHandle.WaitAny%2A>，或<xref:System.Threading.WaitHandle.WaitAll%2A>.</xref:System.Threading.WaitHandle.WaitAll%2A> </xref:System.Threading.WaitHandle.WaitAny%2A> </xref:System.Threading.WaitHandle.WaitOne%2A></span><span class="sxs-lookup"><span data-stu-id="4106d-158">Threads can be made to wait on events by calling one of the wait methods, such as <xref:System.Threading.WaitHandle.WaitOne%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A>, or <xref:System.Threading.WaitHandle.WaitAll%2A>.</span></span> <span data-ttu-id="4106d-159"><xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=fullName>导致线程等待，直到一个事件将被发送信号，<xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=fullName>阻止线程，直到一个或多个指示的事件发送信号，和<xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=fullName>阻止线程，直到所有指示的事件发送信号。</xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=fullName> </xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=fullName></xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4106d-159"><xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=fullName> causes the thread to wait until a single event becomes signaled, <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=fullName> blocks a thread until one or more indicated events become signaled, and <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=fullName> blocks the thread until all of the indicated events become signaled.</span></span> <span data-ttu-id="4106d-160">事件将被发送信号时其<xref:System.Threading.EventWaitHandle.Set%2A>调用方法。</xref:System.Threading.EventWaitHandle.Set%2A></span><span class="sxs-lookup"><span data-stu-id="4106d-160">An event becomes signaled when its <xref:System.Threading.EventWaitHandle.Set%2A> method is called.</span></span>  
  
 <span data-ttu-id="4106d-161">在下面的示例中，创建和启动线程`Main`函数。</span><span class="sxs-lookup"><span data-stu-id="4106d-161">In the following example, a thread is created and started by the `Main` function.</span></span> <span data-ttu-id="4106d-162">新线程等待事件使用<xref:System.Threading.WaitHandle.WaitOne%2A>方法。</xref:System.Threading.WaitHandle.WaitOne%2A></span><span class="sxs-lookup"><span data-stu-id="4106d-162">The new thread waits on an event using the <xref:System.Threading.WaitHandle.WaitOne%2A> method.</span></span> <span data-ttu-id="4106d-163">挂起线程，直到该事件终止正在执行的主线程`Main`函数。</span><span class="sxs-lookup"><span data-stu-id="4106d-163">The thread is suspended until the event becomes signaled by the primary thread that is executing the `Main` function.</span></span> <span data-ttu-id="4106d-164">一旦该事件将被发送信号，辅助线程将返回。</span><span class="sxs-lookup"><span data-stu-id="4106d-164">Once the event becomes signaled, the auxiliary thread returns.</span></span> <span data-ttu-id="4106d-165">在这种情况下，因为该事件仅用于实现一个线程的激活，或者<xref:System.Threading.AutoResetEvent>或<xref:System.Threading.ManualResetEvent>无法使用类。</xref:System.Threading.ManualResetEvent> </xref:System.Threading.AutoResetEvent></span><span class="sxs-lookup"><span data-stu-id="4106d-165">In this case, because the event is only used for one thread activation, either the <xref:System.Threading.AutoResetEvent> or <xref:System.Threading.ManualResetEvent> classes could be used.</span></span>  
  
```vb  
Imports System.Threading  
  
Module Module1  
    Dim autoEvent As AutoResetEvent  
  
    Sub DoWork()  
        Console.WriteLine("   worker thread started, now waiting on event...")  
        autoEvent.WaitOne()  
        Console.WriteLine("   worker thread reactivated, now exiting...")  
    End Sub  
  
    Sub Main()  
        autoEvent = New AutoResetEvent(False)  
  
        Console.WriteLine("main thread starting worker thread...")  
        Dim t As New Thread(AddressOf DoWork)  
        t.Start()  
  
        Console.WriteLine("main thread sleeping for 1 second...")  
        Thread.Sleep(1000)  
  
        Console.WriteLine("main thread signaling worker thread...")  
        autoEvent.Set()  
    End Sub  
End Module  
```  
  
## <a name="mutex-object"></a><span data-ttu-id="4106d-166">Mutex 对象</span><span class="sxs-lookup"><span data-stu-id="4106d-166">Mutex Object</span></span>  
 <span data-ttu-id="4106d-167">一个*互斥体*类似于监视器; 它会阻止的代码块的同时执行多个线程一次。</span><span class="sxs-lookup"><span data-stu-id="4106d-167">A *mutex* is similar to a monitor; it prevents the simultaneous execution of a block of code by more than one thread at a time.</span></span> <span data-ttu-id="4106d-168">事实上，名称"互斥体"是"互相排斥。"一词的缩写形式</span><span class="sxs-lookup"><span data-stu-id="4106d-168">In fact, the name "mutex" is a shortened form of the term "mutually exclusive."</span></span> <span data-ttu-id="4106d-169">与不同的监视器，但是，互斥锁可在进程间同步线程。</span><span class="sxs-lookup"><span data-stu-id="4106d-169">Unlike monitors, however, a mutex can be used to synchronize threads across processes.</span></span> <span data-ttu-id="4106d-170">由<xref:System.Threading.Mutex>类</xref:System.Threading.Mutex>表示一个 mutex</span><span class="sxs-lookup"><span data-stu-id="4106d-170">A mutex is represented by the <xref:System.Threading.Mutex> class.</span></span>  
  
 <span data-ttu-id="4106d-171">当用于进程间同步，mutex 称为*已命名互斥体*因为它是在另一个应用程序中使用，因此它不能通过全局或静态变量共享。</span><span class="sxs-lookup"><span data-stu-id="4106d-171">When used for inter-process synchronization, a mutex is called a *named mutex* because it is to be used in another application, and therefore it cannot be shared by means of a global or static variable.</span></span> <span data-ttu-id="4106d-172">必须为其提供一个名称，以便两个应用程序能够访问同一个 mutex 对象。</span><span class="sxs-lookup"><span data-stu-id="4106d-172">It must be given a name so that both applications can access the same mutex object.</span></span>  
  
 <span data-ttu-id="4106d-173">虽然互斥体可用于进程内的线程同步，但是使用<xref:System.Threading.Monitor>是通常首选，因为监视器专门为.NET Framework 设计，因此作出更好地利用资源。</xref:System.Threading.Monitor></span><span class="sxs-lookup"><span data-stu-id="4106d-173">Although a mutex can be used for intra-process thread synchronization, using <xref:System.Threading.Monitor> is generally preferred, because monitors were designed specifically for the .NET Framework and therefore make better use of resources.</span></span> <span data-ttu-id="4106d-174">与此相反，<xref:System.Threading.Mutex>类是 Win32 构造的包装。</xref:System.Threading.Mutex></span><span class="sxs-lookup"><span data-stu-id="4106d-174">In contrast, the <xref:System.Threading.Mutex> class is a wrapper to a Win32 construct.</span></span> <span data-ttu-id="4106d-175">尽管它是一个监视器，它比功能更强大，互斥体，就需要更占用计算资源比所需的<xref:System.Threading.Monitor>类</xref:System.Threading.Monitor>的互操作转换</span><span class="sxs-lookup"><span data-stu-id="4106d-175">While it is more powerful than a monitor, a mutex requires interop transitions that are more computationally expensive than those required by the <xref:System.Threading.Monitor> class.</span></span> <span data-ttu-id="4106d-176">有关使用互斥体的示例，请参阅[互斥锁](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2)。</span><span class="sxs-lookup"><span data-stu-id="4106d-176">For an example of using a mutex, see [Mutexes](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2).</span></span>  
  
## <a name="interlocked-class"></a><span data-ttu-id="4106d-177">Interlocked 的类</span><span class="sxs-lookup"><span data-stu-id="4106d-177">Interlocked Class</span></span>  
 <span data-ttu-id="4106d-178">您可以使用的方法<xref:System.Threading.Interlocked>类来避免在多个线程尝试同时更新或相同的值进行比较时可能发生的问题。</xref:System.Threading.Interlocked></span><span class="sxs-lookup"><span data-stu-id="4106d-178">You can use the methods of the <xref:System.Threading.Interlocked> class to prevent problems that can occur when multiple threads attempt to simultaneously update or compare the same value.</span></span> <span data-ttu-id="4106d-179">此类方法可以安全地递增、 递减、 交换，并比较值从任意线程。</span><span class="sxs-lookup"><span data-stu-id="4106d-179">The methods of this class let you safely increment, decrement, exchange, and compare values from any thread.</span></span>  
  
## <a name="readerwriter-locks"></a><span data-ttu-id="4106d-180">ReaderWriter 锁</span><span class="sxs-lookup"><span data-stu-id="4106d-180">ReaderWriter Locks</span></span>  
 <span data-ttu-id="4106d-181">在某些情况下，您可能希望仅在写入数据时锁定资源，并允许多个客户端同时读取数据时不更新数据。</span><span class="sxs-lookup"><span data-stu-id="4106d-181">In some cases, you may want to lock a resource only when data is being written and permit multiple clients to simultaneously read data when data is not being updated.</span></span> <span data-ttu-id="4106d-182"><xref:System.Threading.ReaderWriterLock>类强制执行对资源的独占访问，而在线程修改该资源，但在读取资源时，它允许非独占访问。</xref:System.Threading.ReaderWriterLock></span><span class="sxs-lookup"><span data-stu-id="4106d-182">The <xref:System.Threading.ReaderWriterLock> class enforces exclusive access to a resource while a thread is modifying the resource, but it allows non-exclusive access when reading the resource.</span></span> <span data-ttu-id="4106d-183">ReaderWriter 锁是排他锁，这会使其他线程等待，即使当这些线程不需要更新数据的有用替代方法。</span><span class="sxs-lookup"><span data-stu-id="4106d-183">ReaderWriter locks are a useful alternative to exclusive locks, which cause other threads to wait, even when those threads do not need to update data.</span></span>  
  
## <a name="deadlocks"></a><span data-ttu-id="4106d-184">死锁</span><span class="sxs-lookup"><span data-stu-id="4106d-184">Deadlocks</span></span>  
 <span data-ttu-id="4106d-185">线程同步是在多线程应用程序中非常有用，但始终是创建的危险`deadlock`，其中多个线程正在等待对方，而该应用程序就会停顿。</span><span class="sxs-lookup"><span data-stu-id="4106d-185">Thread synchronization is invaluable in multithreaded applications, but there is always the danger of creating a `deadlock`, where multiple threads are waiting for each other and the application comes to a halt.</span></span> <span data-ttu-id="4106d-186">死锁的情况，汽车停止在四路停止，而每个用户正在等待另一个以转到相当。</span><span class="sxs-lookup"><span data-stu-id="4106d-186">A deadlock is analogous to a situation in which cars are stopped at a four-way stop and each person is waiting for the other to go.</span></span> <span data-ttu-id="4106d-187">避免死锁很重要;关键是仔细规划。</span><span class="sxs-lookup"><span data-stu-id="4106d-187">Avoiding deadlocks is important; the key is careful planning.</span></span> <span data-ttu-id="4106d-188">图表多线程应用程序，在开始编码之前，通常可以预测死锁情况。</span><span class="sxs-lookup"><span data-stu-id="4106d-188">You can often predict deadlock situations by diagramming multithreaded applications before you start coding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4106d-189">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4106d-189">See Also</span></span>  
 <span data-ttu-id="4106d-190"><xref:System.Threading.Thread></xref:System.Threading.Thread></span><span class="sxs-lookup"><span data-stu-id="4106d-190"><xref:System.Threading.Thread></span></span>   
 <span data-ttu-id="4106d-191"><xref:System.Threading.WaitHandle.WaitOne%2A></xref:System.Threading.WaitHandle.WaitOne%2A></span><span class="sxs-lookup"><span data-stu-id="4106d-191"><xref:System.Threading.WaitHandle.WaitOne%2A></span></span>   
 <span data-ttu-id="4106d-192"><xref:System.Threading.WaitHandle.WaitAny%2A></xref:System.Threading.WaitHandle.WaitAny%2A></span><span class="sxs-lookup"><span data-stu-id="4106d-192"><xref:System.Threading.WaitHandle.WaitAny%2A></span></span>   
 <span data-ttu-id="4106d-193"><xref:System.Threading.WaitHandle.WaitAll%2A></xref:System.Threading.WaitHandle.WaitAll%2A></span><span class="sxs-lookup"><span data-stu-id="4106d-193"><xref:System.Threading.WaitHandle.WaitAll%2A></span></span>   
 <span data-ttu-id="4106d-194"><xref:System.Threading.Thread.Join%2A></xref:System.Threading.Thread.Join%2A></span><span class="sxs-lookup"><span data-stu-id="4106d-194"><xref:System.Threading.Thread.Join%2A></span></span>   
 <span data-ttu-id="4106d-195"><xref:System.Threading.Thread.Start%2A></xref:System.Threading.Thread.Start%2A></span><span class="sxs-lookup"><span data-stu-id="4106d-195"><xref:System.Threading.Thread.Start%2A></span></span>   
 <span data-ttu-id="4106d-196"><xref:System.Threading.Thread.Sleep%2A></xref:System.Threading.Thread.Sleep%2A></span><span class="sxs-lookup"><span data-stu-id="4106d-196"><xref:System.Threading.Thread.Sleep%2A></span></span>   
 <span data-ttu-id="4106d-197"><xref:System.Threading.Monitor></xref:System.Threading.Monitor></span><span class="sxs-lookup"><span data-stu-id="4106d-197"><xref:System.Threading.Monitor></span></span>   
 <span data-ttu-id="4106d-198"><xref:System.Threading.Mutex></xref:System.Threading.Mutex></span><span class="sxs-lookup"><span data-stu-id="4106d-198"><xref:System.Threading.Mutex></span></span>   
 <span data-ttu-id="4106d-199"><xref:System.Threading.AutoResetEvent></xref:System.Threading.AutoResetEvent></span><span class="sxs-lookup"><span data-stu-id="4106d-199"><xref:System.Threading.AutoResetEvent></span></span>   
 <span data-ttu-id="4106d-200"><xref:System.Threading.ManualResetEvent></xref:System.Threading.ManualResetEvent></span><span class="sxs-lookup"><span data-stu-id="4106d-200"><xref:System.Threading.ManualResetEvent></span></span>   
 <span data-ttu-id="4106d-201"><xref:System.Threading.Interlocked></xref:System.Threading.Interlocked></span><span class="sxs-lookup"><span data-stu-id="4106d-201"><xref:System.Threading.Interlocked></span></span>   
 <span data-ttu-id="4106d-202"><xref:System.Threading.WaitHandle></xref:System.Threading.WaitHandle></span><span class="sxs-lookup"><span data-stu-id="4106d-202"><xref:System.Threading.WaitHandle></span></span>   
 <span data-ttu-id="4106d-203"><xref:System.Threading.EventWaitHandle></xref:System.Threading.EventWaitHandle></span><span class="sxs-lookup"><span data-stu-id="4106d-203"><xref:System.Threading.EventWaitHandle></span></span>   
 <span data-ttu-id="4106d-204"><xref:System.Threading></xref:System.Threading></span><span class="sxs-lookup"><span data-stu-id="4106d-204"><xref:System.Threading></span></span>   
 <span data-ttu-id="4106d-205"><xref:System.Threading.EventWaitHandle.Set%2A></xref:System.Threading.EventWaitHandle.Set%2A></span><span class="sxs-lookup"><span data-stu-id="4106d-205"><xref:System.Threading.EventWaitHandle.Set%2A></span></span>   
<span data-ttu-id="4106d-206"> [多线程应用程序 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md) </span><span class="sxs-lookup"><span data-stu-id="4106d-206"> [Multithreaded Applications (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md) </span></span>  
<span data-ttu-id="4106d-207"> [SyncLock 语句](../../../../visual-basic/language-reference/statements/synclock-statement.md) </span><span class="sxs-lookup"><span data-stu-id="4106d-207"> [SyncLock Statement](../../../../visual-basic/language-reference/statements/synclock-statement.md) </span></span>  
<span data-ttu-id="4106d-208"> [互斥锁](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2) </span><span class="sxs-lookup"><span data-stu-id="4106d-208"> [Mutexes](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2) </span></span>  
 @System.Threading.Monitor   
<span data-ttu-id="4106d-209"> [互锁的操作](http://msdn.microsoft.com/library/cbda7114-c752-4f3e-ada1-b1e8dd262f2b) </span><span class="sxs-lookup"><span data-stu-id="4106d-209"> [Interlocked Operations](http://msdn.microsoft.com/library/cbda7114-c752-4f3e-ada1-b1e8dd262f2b) </span></span>  
<span data-ttu-id="4106d-210"> [AutoResetEvent](http://msdn.microsoft.com/library/6d39c48d-6b37-4a9b-8631-f2924cfd9c18) </span><span class="sxs-lookup"><span data-stu-id="4106d-210"> [AutoResetEvent](http://msdn.microsoft.com/library/6d39c48d-6b37-4a9b-8631-f2924cfd9c18) </span></span>  
<span data-ttu-id="4106d-211"> [同步数据的多线程处理](http://msdn.microsoft.com/library/b980eb4c-71d5-4860-864a-6dfe3692430a)</span><span class="sxs-lookup"><span data-stu-id="4106d-211"> [Synchronizing Data for Multithreading](http://msdn.microsoft.com/library/b980eb4c-71d5-4860-864a-6dfe3692430a)</span></span>
