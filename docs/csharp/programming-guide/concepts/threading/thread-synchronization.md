---
title: 线程同步 (C#)
ms.date: 07/20/2015
ms.assetid: e42b1be6-c93c-479f-a148-be0759f1a4e1
ms.openlocfilehash: 6f0fe42c06b27369612cf586c7a93ce098822162
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509381"
---
# <a name="thread-synchronization-c"></a><span data-ttu-id="1cbd8-102">线程同步 (C#)</span><span class="sxs-lookup"><span data-stu-id="1cbd8-102">Thread Synchronization (C#)</span></span>
<span data-ttu-id="1cbd8-103">以下各节中描述的功能和类可用于同步访问多线程应用程序中的资源。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-103">The following sections describe features and classes that can be used to synchronize access to resources in multithreaded applications.</span></span>  
  
 <span data-ttu-id="1cbd8-104">在应用程序中使用多线程的好处之一是每个线程都可以异步方式执行。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-104">One of the benefits of using multiple threads in an application is that each thread executes asynchronously.</span></span> <span data-ttu-id="1cbd8-105">对于 Windows 应用程序，这允许在后台执行耗时的任务，同时应用程序窗口和控件保持响应状态。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-105">For Windows applications, this allows time-consuming tasks to be performed in the background while the application window and controls remain responsive.</span></span> <span data-ttu-id="1cbd8-106">对于服务器应用程序，多线程处理提供了用不同线程处理每个传入请求的能力。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-106">For server applications, multithreading provides the ability to handle each incoming request with a different thread.</span></span> <span data-ttu-id="1cbd8-107">否则，在满足上一个请求之前，将无法处理任何新请求。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-107">Otherwise, each new request would not get serviced until the previous request had been fully satisfied.</span></span>  
  
 <span data-ttu-id="1cbd8-108">然而，线程的异步性质意味着必须协调对文件句柄、网络连接和内存等资源的访问。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-108">However, the asynchronous nature of threads means that access to resources such as file handles, network connections, and memory must be coordinated.</span></span> <span data-ttu-id="1cbd8-109">否则，两个或多个线程可能在同一时间访问同一资源，且不能感知对方的操作。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-109">Otherwise, two or more threads could access the same resource at the same time, each unaware of the other's actions.</span></span> <span data-ttu-id="1cbd8-110">结果是不可预知的数据损坏。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-110">The result is unpredictable data corruption.</span></span>  
  
 <span data-ttu-id="1cbd8-111">对于针对整数数据类型的简单操作，可以通过 <xref:System.Threading.Interlocked> 类的成员完成同步处理线程。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-111">For simple operations on integral numeric data types, synchronizing threads can be accomplished with members of the <xref:System.Threading.Interlocked> class.</span></span> <span data-ttu-id="1cbd8-112">对于其他所有数据类型和非线程安全资源，只有使用本主题中的构造才能安全地执行多线程处理。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-112">For all other data types and non thread-safe resources, multithreading can only be safely performed using the constructs in this topic.</span></span>  
  
 <span data-ttu-id="1cbd8-113">有关多线程编程中的背景信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="1cbd8-113">For background information on multithreaded programming, see:</span></span>  
  
-   [<span data-ttu-id="1cbd8-114">托管线程处理基本知识</span><span class="sxs-lookup"><span data-stu-id="1cbd8-114">Managed Threading Basics</span></span>](../../../../standard/threading/managed-threading-basics.md)  
  
-   [<span data-ttu-id="1cbd8-115">使用线程和线程处理</span><span class="sxs-lookup"><span data-stu-id="1cbd8-115">Using Threads and Threading</span></span>](../../../../standard/threading/using-threads-and-threading.md)  
  
-   [<span data-ttu-id="1cbd8-116">托管线程处理的最佳做法</span><span class="sxs-lookup"><span data-stu-id="1cbd8-116">Managed Threading Best Practices</span></span>](../../../../standard/threading/managed-threading-best-practices.md)  
  
## <a name="the-lock-keyword"></a><span data-ttu-id="1cbd8-117">lock 关键字</span><span class="sxs-lookup"><span data-stu-id="1cbd8-117">The lock Keyword</span></span>  
 <span data-ttu-id="1cbd8-118">C# `lock` 语句可用于确保代码块运行完成，且不会被其他线程中断。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-118">The C# `lock` statement can be used to ensure that a block of code runs to completion without interruption by other threads.</span></span> <span data-ttu-id="1cbd8-119">这是通过在代码块的持续时间内获得给定对象的互斥锁来实现的。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-119">This is accomplished by obtaining a mutual-exclusion lock for a given object for the duration of the code block.</span></span>  
  
 <span data-ttu-id="1cbd8-120">`lock` 语句被作为参数赋予对象，而且后面跟随的是一次只能由一个线程运行的代码块。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-120">A `lock` statement is given an object as an argument, and is followed by a code block that is to be executed by only one thread at a time.</span></span> <span data-ttu-id="1cbd8-121">例如:</span><span class="sxs-lookup"><span data-stu-id="1cbd8-121">For example:</span></span>  
  
```csharp  
public class TestThreading  
{  
    private System.Object lockThis = new System.Object();  
  
    public void Process()  
    {  
  
        lock (lockThis)  
        {  
            // Access thread-sensitive resources.  
        }  
    }  
  
}  
```  
  
 <span data-ttu-id="1cbd8-122">提供给 `lock` 关键字的参数必须是基于引用类型的对象，并且用于定义锁的范围。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-122">The argument provided to the `lock` keyword must be an object based on a reference type, and is used to define the scope of the lock.</span></span> <span data-ttu-id="1cbd8-123">在上例中，锁定范围仅限于此函数，因为函数外不存在 `lockThis` 对象的任何引用。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-123">In the example above, the lock scope is limited to this function because no references to the object `lockThis` exist outside the function.</span></span> <span data-ttu-id="1cbd8-124">如果存在此类引用，锁定范围将扩展到该对象。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-124">If such a reference did exist, lock scope would extend to that object.</span></span> <span data-ttu-id="1cbd8-125">严格地说，所提供的对象仅用于唯一标识在多个线程之间共享的资源，因此它可以是任意类实例。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-125">Strictly speaking, the object provided is used solely to uniquely identify the resource being shared among multiple threads, so it can be an arbitrary class instance.</span></span> <span data-ttu-id="1cbd8-126">但实际上，该对象通常表示需要线程同步的资源。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-126">In practice, however, this object usually represents the resource for which thread synchronization is necessary.</span></span> <span data-ttu-id="1cbd8-127">例如，如果某个容器对象要被多个线程使用，则可以将该容器传递给锁，而锁后面的同步代码块可访问该容器。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-127">For example, if a container object is to be used by multiple threads, then the container can be passed to lock, and the synchronized code block following the lock would access the container.</span></span> <span data-ttu-id="1cbd8-128">只要其他线程在访问该容器前先锁定该容器，对该对象的访问就是安全同步的。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-128">As long as other threads locks on the same contain before accessing it, then access to the object is safely synchronized.</span></span>  
  
 <span data-ttu-id="1cbd8-129">通常情况下，最好避免锁定 `public` 类型，或者锁定超出应用程序控制的对象实例。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-129">Generally, it is best to avoid locking on a `public` type, or on object instances beyond the control of your application.</span></span> <span data-ttu-id="1cbd8-130">例如，如果可以公开访问实例，则 `lock(this)` 可能会有问题，因为超出控制范围的代码也可能锁定对象。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-130">For example, `lock(this)` can be problematic if the instance can be accessed publicly, because code beyond your control may lock on the object as well.</span></span> <span data-ttu-id="1cbd8-131">这可能会导致死锁情况，即两个或多个线程等待同一对象的释放。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-131">This could create deadlock situations where two or more threads wait for the release of the same object.</span></span> <span data-ttu-id="1cbd8-132">出于相同原因，锁定与对象相对的公共数据类型也可能会导致问题。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-132">Locking on a public data type, as opposed to an object, can cause problems for the same reason.</span></span> <span data-ttu-id="1cbd8-133">锁定文本字符串尤其危险，因为文本字符串被公共语言运行时 (CLR) *暂存*。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-133">Locking on literal strings is especially risky because literal strings are *interned* by the common language runtime (CLR).</span></span> <span data-ttu-id="1cbd8-134">这意味着对于整个程序，任何给定字符串文本都只有一个实例，就是这同一个对象表示了所有运行的应用程序域的所有线程中的该文本。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-134">This means that there is one instance of any given string literal for the entire program, the exact same object represents the literal in all running application domains, on all threads.</span></span> <span data-ttu-id="1cbd8-135">因此，在应用程序进程中任何位置锁定具有相同内容的字符串都会锁定应用程序中该字符串的所有实例。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-135">As a result, a lock placed on a string with the same contents anywhere in the application process locks all instances of that string in the application.</span></span> <span data-ttu-id="1cbd8-136">因此，最好锁定未被暂存的私有或受保护的成员。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-136">As a result, it is best to lock a private or protected member that is not interned.</span></span> <span data-ttu-id="1cbd8-137">某些类提供专用于锁定的成员。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-137">Some classes provide members specifically for locking.</span></span> <span data-ttu-id="1cbd8-138">例如，<xref:System.Array> 类型提供 <xref:System.Array.SyncRoot%2A>。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-138">The <xref:System.Array> type, for example, provides <xref:System.Array.SyncRoot%2A>.</span></span> <span data-ttu-id="1cbd8-139">许多集合类型也提供了 `SyncRoot` 成员。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-139">Many collection types provide a `SyncRoot` member as well.</span></span>  
  
 <span data-ttu-id="1cbd8-140">有关 `lock` 语句的详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="1cbd8-140">For more information about the `lock` statement, see the following topics:</span></span>  
  
-   [<span data-ttu-id="1cbd8-141">lock 语句</span><span class="sxs-lookup"><span data-stu-id="1cbd8-141">lock Statement</span></span>](../../../../csharp/language-reference/keywords/lock-statement.md)  
  
-   <xref:System.Threading.Monitor>  
  
## <a name="monitors"></a><span data-ttu-id="1cbd8-142">监视器</span><span class="sxs-lookup"><span data-stu-id="1cbd8-142">Monitors</span></span>  
 <span data-ttu-id="1cbd8-143">与 `lock` 关键字类似，监视器可防止多个线程同时执行代码块。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-143">Like the `lock` keyword, monitors prevent blocks of code from simultaneous execution by multiple threads.</span></span> <span data-ttu-id="1cbd8-144"><xref:System.Threading.Monitor.Enter%2A> 方法允许有且只有一个线程继续执行下面的语句；执行线程调用 <xref:System.Threading.Monitor.Exit%2A> 之前，将阻止其他所有线程。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-144">The <xref:System.Threading.Monitor.Enter%2A> method allows one and only one thread to proceed into the following statements; all other threads are blocked until the executing thread calls <xref:System.Threading.Monitor.Exit%2A>.</span></span> <span data-ttu-id="1cbd8-145">这与使用 `lock` 关键字类似。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-145">This is just like using the `lock` keyword.</span></span> <span data-ttu-id="1cbd8-146">例如:</span><span class="sxs-lookup"><span data-stu-id="1cbd8-146">For example:</span></span>  
  
```csharp  
lock (x)  
{  
    DoSomething();  
}  
```  
  
 <span data-ttu-id="1cbd8-147">这等效于：</span><span class="sxs-lookup"><span data-stu-id="1cbd8-147">This is equivalent to:</span></span>  
  
```csharp  
System.Object obj = (System.Object)x;  
System.Threading.Monitor.Enter(obj);  
try  
{  
    DoSomething();  
}  
finally  
{  
    System.Threading.Monitor.Exit(obj);  
}  
```  
  
 <span data-ttu-id="1cbd8-148">使用 `lock` 关键字通常优先于直接使用 <xref:System.Threading.Monitor> 类，因为 `lock` 更简洁，而且即使在受保护的代码引发异常时，`lock` 也可确保基础监视器被释放。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-148">Using the `lock` keyword is generally preferred over using the <xref:System.Threading.Monitor> class directly, both because `lock` is more concise, and because `lock` insures that the underlying monitor is released, even if the protected code throws an exception.</span></span> <span data-ttu-id="1cbd8-149">这通过由 `finally` 关键字完成，该关键字执行其关联的代码块，不会受是否引发异常的影响。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-149">This is accomplished with the `finally` keyword, which executes its associated code block regardless of whether an exception is thrown.</span></span>  
  
## <a name="synchronization-events-and-wait-handles"></a><span data-ttu-id="1cbd8-150">同步事件和等待句柄</span><span class="sxs-lookup"><span data-stu-id="1cbd8-150">Synchronization Events and Wait Handles</span></span>  
 <span data-ttu-id="1cbd8-151">使用锁或监视器有助于防止同时执行线程敏感的代码块，但这些构造不允许在线程之间传达事件。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-151">Using a lock or monitor is useful for preventing the simultaneous execution of thread-sensitive blocks of code, but these constructs do not allow one thread to communicate an event to another.</span></span> <span data-ttu-id="1cbd8-152">这就需要“同步事件”，它们是具有两种状态之一（发出信号和未发出信号）的对象，可用于激活和挂起线程。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-152">This requires *synchronization events*, which are objects that have one of two states, signaled and un-signaled, that can be used to activate and suspend threads.</span></span> <span data-ttu-id="1cbd8-153">线程可以通过等待未发出信号的同步事件来挂起，并且可以通过将事件状态改变为发出信号来激活。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-153">Threads can be suspended by being made to wait on a synchronization event that is unsignaled, and can be activated by changing the event state to signaled.</span></span> <span data-ttu-id="1cbd8-154">如果某个线程尝试等待已经发出信号的事件，则该线程将继续执行且无延迟。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-154">If a thread attempts to wait on an event that is already signaled, then the thread continues to execute without delay.</span></span>  
  
 <span data-ttu-id="1cbd8-155">存在两种类型的同步事件：<xref:System.Threading.AutoResetEvent> 和 <xref:System.Threading.ManualResetEvent>。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-155">There are two kinds of synchronization events: <xref:System.Threading.AutoResetEvent>, and <xref:System.Threading.ManualResetEvent>.</span></span> <span data-ttu-id="1cbd8-156">它们唯一的差别在于：<xref:System.Threading.AutoResetEvent> 会在启动线程时自动从发出信号的状态更改为未发出信号的状态。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-156">They differ only in that <xref:System.Threading.AutoResetEvent> changes from signaled to unsignaled automatically any time it activates a thread.</span></span> <span data-ttu-id="1cbd8-157">相反，<xref:System.Threading.ManualResetEvent> 允许其信号状态激活任意数量的线程，且在调用其 <xref:System.Threading.EventWaitHandle.Reset%2A> 方法后，将仅还原到非信号状态。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-157">Conversely, a <xref:System.Threading.ManualResetEvent> allows any number of threads to be activated by its signaled state, and will only revert to an unsignaled state when its <xref:System.Threading.EventWaitHandle.Reset%2A> method is called.</span></span>  
  
 <span data-ttu-id="1cbd8-158">可通过调用某个 wait 方法（例如 <xref:System.Threading.WaitHandle.WaitOne%2A>、<xref:System.Threading.WaitHandle.WaitAny%2A> 或 <xref:System.Threading.WaitHandle.WaitAll%2A>）让线程等待事件。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-158">Threads can be made to wait on events by calling one of the wait methods, such as <xref:System.Threading.WaitHandle.WaitOne%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A>, or <xref:System.Threading.WaitHandle.WaitAll%2A>.</span></span> <span data-ttu-id="1cbd8-159"><xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=nameWithType> 将导致线程等待，直到单个事件进入信号状态，<xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=nameWithType> 将阻止线程，直到一个或多个指示的事件进入信号状态，<xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=nameWithType> 将阻止线程，直到所有指示的事件进入信号状态。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-159"><xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=nameWithType> causes the thread to wait until a single event becomes signaled, <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=nameWithType> blocks a thread until one or more indicated events become signaled, and <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=nameWithType> blocks the thread until all of the indicated events become signaled.</span></span> <span data-ttu-id="1cbd8-160">调用某一事件的 <xref:System.Threading.EventWaitHandle.Set%2A> 方法时，该事件会进入信号状态。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-160">An event becomes signaled when its <xref:System.Threading.EventWaitHandle.Set%2A> method is called.</span></span>  
  
 <span data-ttu-id="1cbd8-161">在下例中，线程由 `Main` 函数创建和启动。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-161">In the following example, a thread is created and started by the `Main` function.</span></span> <span data-ttu-id="1cbd8-162">新线程使用 <xref:System.Threading.WaitHandle.WaitOne%2A> 方法等待事件。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-162">The new thread waits on an event using the <xref:System.Threading.WaitHandle.WaitOne%2A> method.</span></span> <span data-ttu-id="1cbd8-163">该线程将被挂起，直到由执行 `Main` 函数的主线程对事件发出信号。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-163">The thread is suspended until the event becomes signaled by the primary thread that is executing the `Main` function.</span></span> <span data-ttu-id="1cbd8-164">事件发出信号后，辅助线程返回。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-164">Once the event becomes signaled, the auxiliary thread returns.</span></span> <span data-ttu-id="1cbd8-165">在这种情况下，因为该事件仅用于激活一个线程，因此可使用 <xref:System.Threading.AutoResetEvent> 或 <xref:System.Threading.ManualResetEvent> 类。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-165">In this case, because the event is only used for one thread activation, either the <xref:System.Threading.AutoResetEvent> or <xref:System.Threading.ManualResetEvent> classes could be used.</span></span>  
  
```csharp  
using System;  
using System.Threading;  
  
class ThreadingExample  
{  
    static AutoResetEvent autoEvent;  
  
    static void DoWork()  
    {  
        Console.WriteLine("   worker thread started, now waiting on event...");  
        autoEvent.WaitOne();  
        Console.WriteLine("   worker thread reactivated, now exiting...");  
    }  
  
    static void Main()  
    {  
        autoEvent = new AutoResetEvent(false);  
  
        Console.WriteLine("main thread starting worker thread...");  
        Thread t = new Thread(DoWork);  
        t.Start();  
  
        Console.WriteLine("main thread sleeping for 1 second...");  
        Thread.Sleep(1000);  
  
        Console.WriteLine("main thread signaling worker thread...");  
        autoEvent.Set();  
    }  
}  
```  
  
## <a name="mutex-object"></a><span data-ttu-id="1cbd8-166">Mutex 对象</span><span class="sxs-lookup"><span data-stu-id="1cbd8-166">Mutex Object</span></span>  
 <span data-ttu-id="1cbd8-167">*mutex* 与监视器相似；它防止多个线程在某一时间同时执行某个代码块。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-167">A *mutex* is similar to a monitor; it prevents the simultaneous execution of a block of code by more than one thread at a time.</span></span> <span data-ttu-id="1cbd8-168">事实上，名称“mutex”是术语“互相排斥 (mutually exclusive)”的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-168">In fact, the name "mutex" is a shortened form of the term "mutually exclusive."</span></span> <span data-ttu-id="1cbd8-169">但是，与监视器不同，mutex 可用于进程间的同步线程。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-169">Unlike monitors, however, a mutex can be used to synchronize threads across processes.</span></span> <span data-ttu-id="1cbd8-170">mutex 由 <xref:System.Threading.Mutex> 类表示。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-170">A mutex is represented by the <xref:System.Threading.Mutex> class.</span></span>  
  
 <span data-ttu-id="1cbd8-171">当用于进程间同步时，mutex 称为“命名 mutex”，因为它将在另一个应用程序中使用，因此它不能通过全局变量或静态变量共享。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-171">When used for inter-process synchronization, a mutex is called a *named mutex* because it is to be used in another application, and therefore it cannot be shared by means of a global or static variable.</span></span> <span data-ttu-id="1cbd8-172">必须为其提供一个名称，以便两个应用程序能够访问同一个 mutex 对象。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-172">It must be given a name so that both applications can access the same mutex object.</span></span>  
  
 <span data-ttu-id="1cbd8-173">虽然 mutex 可用于进程内线程同步，但通常首选使用 <xref:System.Threading.Monitor>，因为监视器是为 .NET Framework 专门设计的，因此可以更好地利用资源。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-173">Although a mutex can be used for intra-process thread synchronization, using <xref:System.Threading.Monitor> is generally preferred, because monitors were designed specifically for the .NET Framework and therefore make better use of resources.</span></span> <span data-ttu-id="1cbd8-174">与此相反，<xref:System.Threading.Mutex> 类是 Win32 构造的包装器。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-174">In contrast, the <xref:System.Threading.Mutex> class is a wrapper to a Win32 construct.</span></span> <span data-ttu-id="1cbd8-175">虽然它比监视器更强大，但 mutex 需要互操作过渡，其计算成本比 <xref:System.Threading.Monitor> 类所需的成本更多。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-175">While it is more powerful than a monitor, a mutex requires interop transitions that are more computationally expensive than those required by the <xref:System.Threading.Monitor> class.</span></span> <span data-ttu-id="1cbd8-176">有关使用 mutex 的示例，请参阅 [Mutexes](../../../../standard/threading/mutexes.md)。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-176">For an example of using a mutex, see [Mutexes](../../../../standard/threading/mutexes.md).</span></span>  
  
## <a name="interlocked-class"></a><span data-ttu-id="1cbd8-177">Interlocked 类</span><span class="sxs-lookup"><span data-stu-id="1cbd8-177">Interlocked Class</span></span>  
 <span data-ttu-id="1cbd8-178">可以使用 <xref:System.Threading.Interlocked> 类的方法来防止多个线程尝试同时更新或比较相同值时可能发生的问题。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-178">You can use the methods of the <xref:System.Threading.Interlocked> class to prevent problems that can occur when multiple threads attempt to simultaneously update or compare the same value.</span></span> <span data-ttu-id="1cbd8-179">该类的方法可从任何线程安全地递增、递减、交换和比较值。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-179">The methods of this class let you safely increment, decrement, exchange, and compare values from any thread.</span></span>  
  
## <a name="readerwriter-locks"></a><span data-ttu-id="1cbd8-180">ReaderWriter 锁</span><span class="sxs-lookup"><span data-stu-id="1cbd8-180">ReaderWriter Locks</span></span>  
 <span data-ttu-id="1cbd8-181">在某些情况下，建议仅在写入数据时锁定资源，并允许多个客户端在数据未更新时同时读取数据。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-181">In some cases, you may want to lock a resource only when data is being written and permit multiple clients to simultaneously read data when data is not being updated.</span></span> <span data-ttu-id="1cbd8-182">当线程正在修改资源时，<xref:System.Threading.ReaderWriterLock> 类强制执行对资源的独占访问，但在读取资源时允许非独占访问。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-182">The <xref:System.Threading.ReaderWriterLock> class enforces exclusive access to a resource while a thread is modifying the resource, but it allows non-exclusive access when reading the resource.</span></span> <span data-ttu-id="1cbd8-183">ReaderWriter 锁可用于代替排它锁。使用排它锁时，即使其他线程不需要更新数据，也会导致其他线程等待。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-183">ReaderWriter locks are a useful alternative to exclusive locks, which cause other threads to wait, even when those threads do not need to update data.</span></span>  
  
## <a name="deadlocks"></a><span data-ttu-id="1cbd8-184">死锁</span><span class="sxs-lookup"><span data-stu-id="1cbd8-184">Deadlocks</span></span>  
 <span data-ttu-id="1cbd8-185">线程同步在多线程应用程序中非常有用，但是产生 `deadlock` 总是十分危险。一旦产生了死锁，将有多个线程互相等待，从而导致应用程序暂停。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-185">Thread synchronization is invaluable in multithreaded applications, but there is always the danger of creating a `deadlock`, where multiple threads are waiting for each other and the application comes to a halt.</span></span> <span data-ttu-id="1cbd8-186">死锁类似于汽车停在十字路口一样，每个人都在等待别人先出发。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-186">A deadlock is analogous to a situation in which cars are stopped at a four-way stop and each person is waiting for the other to go.</span></span> <span data-ttu-id="1cbd8-187">因此，避免死锁很重要；关键是要仔细规划。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-187">Avoiding deadlocks is important; the key is careful planning.</span></span> <span data-ttu-id="1cbd8-188">开始编码之前，通常可以通过绘制多线程应用程序来预测死锁情况。</span><span class="sxs-lookup"><span data-stu-id="1cbd8-188">You can often predict deadlock situations by diagramming multithreaded applications before you start coding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cbd8-189">请参阅</span><span class="sxs-lookup"><span data-stu-id="1cbd8-189">See Also</span></span>

- <xref:System.Threading.Thread>  
- <xref:System.Threading.WaitHandle.WaitOne%2A>  
- <xref:System.Threading.WaitHandle.WaitAny%2A>  
- <xref:System.Threading.WaitHandle.WaitAll%2A>  
- <xref:System.Threading.Thread.Join%2A>  
- <xref:System.Threading.Thread.Start%2A>  
- <xref:System.Threading.Thread.Sleep%2A>  
- <xref:System.Threading.Monitor>  
- <xref:System.Threading.Mutex>  
- <xref:System.Threading.AutoResetEvent>  
- <xref:System.Threading.ManualResetEvent>  
- <xref:System.Threading.Interlocked>  
- <xref:System.Threading.WaitHandle>  
- <xref:System.Threading.EventWaitHandle>  
- <xref:System.Threading>  
- <xref:System.Threading.EventWaitHandle.Set%2A>  
- <xref:System.Threading.Monitor>  
- [<span data-ttu-id="1cbd8-190">lock 语句</span><span class="sxs-lookup"><span data-stu-id="1cbd8-190">lock Statement</span></span>](../../../../csharp/language-reference/keywords/lock-statement.md)  
- [<span data-ttu-id="1cbd8-191">Mutex</span><span class="sxs-lookup"><span data-stu-id="1cbd8-191">Mutexes</span></span>](../../../../standard/threading/mutexes.md)  
- [<span data-ttu-id="1cbd8-192">互锁操作</span><span class="sxs-lookup"><span data-stu-id="1cbd8-192">Interlocked Operations</span></span>](../../../../standard/threading/interlocked-operations.md)  
- [<span data-ttu-id="1cbd8-193">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="1cbd8-193">AutoResetEvent</span></span>](../../../../standard/threading/autoresetevent.md)  
- [<span data-ttu-id="1cbd8-194">为多线程处理同步数据</span><span class="sxs-lookup"><span data-stu-id="1cbd8-194">Synchronizing Data for Multithreading</span></span>](../../../../standard/threading/synchronizing-data-for-multithreading.md)
