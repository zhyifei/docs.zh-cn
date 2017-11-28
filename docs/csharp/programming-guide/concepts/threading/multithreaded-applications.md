---
title: "多线程应用程序 (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: b7015cfb-d506-4eac-b2f8-b2caaa9cc977
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 48b056172e3260952155eb40a1a393d86da78344
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="multithreaded-applications-c"></a><span data-ttu-id="55959-102">多线程应用程序 (C#)</span><span class="sxs-lookup"><span data-stu-id="55959-102">Multithreaded Applications (C#)</span></span>
<span data-ttu-id="55959-103">借助 C#，可以编写同时执行多个任务的应用程序。</span><span class="sxs-lookup"><span data-stu-id="55959-103">With C#, you can write applications that perform multiple tasks at the same time.</span></span> <span data-ttu-id="55959-104">可在单独的线程上执行可能妨碍其他任务的任务，这些线程是称为多线程处理或自由线程处理的进程。</span><span class="sxs-lookup"><span data-stu-id="55959-104">Tasks with the potential of holding up other tasks can execute on separate threads, a process known as *multithreading* or *free threading*.</span></span>  
  
 <span data-ttu-id="55959-105">使用多线程处理的应用程序可以更快地响应用户输入，因为在单独的线程上执行处理器密集型任务时，用户界面将保持活动状态。</span><span class="sxs-lookup"><span data-stu-id="55959-105">Applications that use multithreading are more responsive to user input because the user interface stays active as processor-intensive tasks execute on separate threads.</span></span> <span data-ttu-id="55959-106">创建可扩展的应用程序时，多线程编程也很有用，因为可以随着负载的增加添加线程。</span><span class="sxs-lookup"><span data-stu-id="55959-106">Multithreading is also useful when you create scalable applications, because you can add threads as the workload increases.</span></span>  
  
## <a name="creating-and-using-threads"></a><span data-ttu-id="55959-107">创建和使用线程</span><span class="sxs-lookup"><span data-stu-id="55959-107">Creating and Using Threads</span></span>  
 <span data-ttu-id="55959-108">如果需要更强地控制应用程序线程的行为，可以自己管理线程。</span><span class="sxs-lookup"><span data-stu-id="55959-108">If you need more control over the behavior of your application's threads, you can manage the threads yourself.</span></span> <span data-ttu-id="55959-109">但是，请注意，编写正确的多线程应用程序可能很困难：应用程序可能会停止响应或遇到争用条件引起的暂时性错误。</span><span class="sxs-lookup"><span data-stu-id="55959-109">However, realize that writing correct multithreaded applications can be difficult: Your application may stop responding or experience transient errors caused by race conditions.</span></span> <span data-ttu-id="55959-110">有关详细信息，请参阅[线程安全组件](http://msdn.microsoft.com/library/4f7c7377-a782-4bd0-aaa3-9db8c12945ee)。</span><span class="sxs-lookup"><span data-stu-id="55959-110">For more information, see [Thread-Safe Components](http://msdn.microsoft.com/library/4f7c7377-a782-4bd0-aaa3-9db8c12945ee).</span></span>  
  
 <span data-ttu-id="55959-111">通过声明类型 <xref:System.Threading.Thread> 的变量和调用构造函数，然后提供要在新线程上执行的过程或方法的名称来新建线程。</span><span class="sxs-lookup"><span data-stu-id="55959-111">You create a new thread by declaring a variable of type <xref:System.Threading.Thread> and calling the constructor, providing the name of the procedure or method that you want to execute on the new thread.</span></span> <span data-ttu-id="55959-112">下面的代码提供了一个示例。</span><span class="sxs-lookup"><span data-stu-id="55959-112">The following code provides an example.</span></span>  
  
```csharp  
System.Threading.Thread newThread =  
    new System.Threading.Thread(AMethod);  
```  
  
### <a name="starting-and-stopping-threads"></a><span data-ttu-id="55959-113">启动和停止线程</span><span class="sxs-lookup"><span data-stu-id="55959-113">Starting and Stopping Threads</span></span>  
 <span data-ttu-id="55959-114">要开始执行新线程，请使用 <xref:System.Threading.Thread.Start%2A> 方法，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="55959-114">To start the execution of a new thread, use the <xref:System.Threading.Thread.Start%2A> method, as shown in the following code.</span></span>  
  
```csharp  
newThread.Start();  
```  
  
 <span data-ttu-id="55959-115">要停止执行线程，请使用 <xref:System.Threading.Thread.Abort%2A> 方法，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="55959-115">To stop the execution of a thread, use the <xref:System.Threading.Thread.Abort%2A> method, as shown in the following code.</span></span>  
  
```csharp  
newThread.Abort();  
```  
  
 <span data-ttu-id="55959-116">除了启动和停止线程，还可以通过调用 <xref:System.Threading.Thread.Sleep%2A> 或 <xref:System.Threading.Thread.Suspend%2A> 方法暂停线程；通过使用 <xref:System.Threading.Thread.Resume%2A> 方法恢复挂起的线程，以及通过使用 <xref:System.Threading.Thread.Abort%2A> 方法销毁线程</span><span class="sxs-lookup"><span data-stu-id="55959-116">Besides starting and stopping threads, you can also pause threads by calling the <xref:System.Threading.Thread.Sleep%2A> or <xref:System.Threading.Thread.Suspend%2A> method, resume a suspended thread by using the <xref:System.Threading.Thread.Resume%2A> method, and destroy a thread by using the <xref:System.Threading.Thread.Abort%2A> method</span></span>  
  
### <a name="thread-methods"></a><span data-ttu-id="55959-117">线程方法</span><span class="sxs-lookup"><span data-stu-id="55959-117">Thread Methods</span></span>  
 <span data-ttu-id="55959-118">下表显示了一些可用于控制各个线程的方法。</span><span class="sxs-lookup"><span data-stu-id="55959-118">The following table shows some of the methods that you can use to control individual threads.</span></span>  
  
|<span data-ttu-id="55959-119">方法</span><span class="sxs-lookup"><span data-stu-id="55959-119">Method</span></span>|<span data-ttu-id="55959-120">操作</span><span class="sxs-lookup"><span data-stu-id="55959-120">Action</span></span>|  
|------------|------------|  
|<xref:System.Threading.Thread.Start%2A>|<span data-ttu-id="55959-121">使线程开始运行。</span><span class="sxs-lookup"><span data-stu-id="55959-121">Causes a thread to start to run.</span></span>|  
|<xref:System.Threading.Thread.Sleep%2A>|<span data-ttu-id="55959-122">使线程暂停指定的一段时间。</span><span class="sxs-lookup"><span data-stu-id="55959-122">Pauses a thread for a specified time.</span></span>|  
|<xref:System.Threading.Thread.Suspend%2A>|<span data-ttu-id="55959-123">线程到达某一安全点时暂停。</span><span class="sxs-lookup"><span data-stu-id="55959-123">Pauses a thread when it reaches a safe point.</span></span>|  
|<xref:System.Threading.Thread.Abort%2A>|<span data-ttu-id="55959-124">线程到达某一安全点时停止。</span><span class="sxs-lookup"><span data-stu-id="55959-124">Stops a thread when it reaches a safe point.</span></span>|  
|<xref:System.Threading.Thread.Resume%2A>|<span data-ttu-id="55959-125">重新启动挂起的线程</span><span class="sxs-lookup"><span data-stu-id="55959-125">Restarts a suspended thread</span></span>|  
|<xref:System.Threading.Thread.Join%2A>|<span data-ttu-id="55959-126">使当前线程等待其他线程完成。</span><span class="sxs-lookup"><span data-stu-id="55959-126">Causes the current thread to wait for another thread to finish.</span></span> <span data-ttu-id="55959-127">如果与超时值配合使用，当线程在分配的时间内完成时，此方法会返回 `True`。</span><span class="sxs-lookup"><span data-stu-id="55959-127">If used with a time-out value, this method returns `True` if the thread finishes in the allocated time.</span></span>|  
  
### <a name="safe-points"></a><span data-ttu-id="55959-128">安全点</span><span class="sxs-lookup"><span data-stu-id="55959-128">Safe Points</span></span>  
 <span data-ttu-id="55959-129">这些方法中的大多数都明白易晓，但可能对安全点这一概念会比较陌生。</span><span class="sxs-lookup"><span data-stu-id="55959-129">Most of these methods are self-explanatory, but the concept of *safe points* may be new to you.</span></span> <span data-ttu-id="55959-130">安全点是代码中的位置，公共语言运行时可在其中安全执行自动垃圾回收（释放未使用的变量并回收内存的过程）。</span><span class="sxs-lookup"><span data-stu-id="55959-130">Safe points are locations in code where it is safe for the common language runtime to perform automatic *garbage collection*, the process of releasing unused variables and reclaiming memory.</span></span> <span data-ttu-id="55959-131">调用线程的 <xref:System.Threading.Thread.Abort%2A> 或 <xref:System.Threading.Thread.Suspend%2A> 方法时，公共语言运行时将分析代码并确定线程停止运行的合适位置。</span><span class="sxs-lookup"><span data-stu-id="55959-131">When you call the <xref:System.Threading.Thread.Abort%2A> or <xref:System.Threading.Thread.Suspend%2A> method of a thread, the common language runtime analyzes the code and determines the location of an appropriate location for the thread to stop running.</span></span>  
  
### <a name="thread-properties"></a><span data-ttu-id="55959-132">线程属性</span><span class="sxs-lookup"><span data-stu-id="55959-132">Thread Properties</span></span>  
 <span data-ttu-id="55959-133">线程还包含多个有用的属性，如下表中所示：</span><span class="sxs-lookup"><span data-stu-id="55959-133">Threads also contain several useful properties, as shown in the following table:</span></span>  
  
|<span data-ttu-id="55959-134">属性</span><span class="sxs-lookup"><span data-stu-id="55959-134">Property</span></span>|<span data-ttu-id="55959-135">值</span><span class="sxs-lookup"><span data-stu-id="55959-135">Value</span></span>|  
|--------------|-----------|  
|<xref:System.Threading.Thread.IsAlive%2A>|<span data-ttu-id="55959-136">如果线程处于活动状态，将包含值 `True`。</span><span class="sxs-lookup"><span data-stu-id="55959-136">Contains the value `True` if a thread is active.</span></span>|  
|<xref:System.Threading.Thread.IsBackground%2A>|<span data-ttu-id="55959-137">获取或设置布尔值，该值指示线程是否为或应为后台线程。</span><span class="sxs-lookup"><span data-stu-id="55959-137">Gets or sets a Boolean that indicates if a thread is or should be a background thread.</span></span> <span data-ttu-id="55959-138">后台线程类似前台线程，但后台线程不会阻止进程停止。</span><span class="sxs-lookup"><span data-stu-id="55959-138">Background threads are like foreground threads, but a background thread does not prevent a process from stopping.</span></span> <span data-ttu-id="55959-139">属于某个进程的所有前台线程均停止后，公共语言运行时通过对仍处于活动状态的后台进程调用 <xref:System.Threading.Thread.Abort%2A> 方法来结束进程。</span><span class="sxs-lookup"><span data-stu-id="55959-139">Once all foreground threads that belong to a process have stopped, the common language runtime ends the process by calling the <xref:System.Threading.Thread.Abort%2A> method on background threads that are still alive.</span></span>|  
|<xref:System.Threading.Thread.Name%2A>|<span data-ttu-id="55959-140">获取或设置线程的名称。</span><span class="sxs-lookup"><span data-stu-id="55959-140">Gets or sets the name of a thread.</span></span> <span data-ttu-id="55959-141">最常用于在调试时查找各个线程。</span><span class="sxs-lookup"><span data-stu-id="55959-141">Most frequently used to discover individual threads when you debug.</span></span>|  
|<xref:System.Threading.Thread.Priority%2A>|<span data-ttu-id="55959-142">获取或设置由操作系统用来确定线程计划优先顺序的值。</span><span class="sxs-lookup"><span data-stu-id="55959-142">Gets or sets a value that is used by the operating system to prioritize thread scheduling.</span></span>|  
|<xref:System.Threading.Thread.ThreadState%2A>|<span data-ttu-id="55959-143">包含描述线程状态的值。</span><span class="sxs-lookup"><span data-stu-id="55959-143">Contains a value that describes a thread's state or states.</span></span>|  
  
## <a name="thread-priorities"></a><span data-ttu-id="55959-144">线程优先级</span><span class="sxs-lookup"><span data-stu-id="55959-144">Thread Priorities</span></span>  
 <span data-ttu-id="55959-145">每个线程都具有优先级属性，用来确定线程必须执行的一段处理器时间的大小。</span><span class="sxs-lookup"><span data-stu-id="55959-145">Every thread has a priority property that determines how big or small a slice of processor time it has to execute.</span></span> <span data-ttu-id="55959-146">操作系统向高优先级线程分配较长时间段。而向低优先级线程分配较短时间段。</span><span class="sxs-lookup"><span data-stu-id="55959-146">The operating system allocates longer time slices to high-priority threads and shorter time slices to low-priority threads.</span></span> <span data-ttu-id="55959-147">新线程是使用 `Normal` 的值创建的，但可将 <xref:System.Threading.Thread.Priority%2A> 属性更改为 <xref:System.Threading.ThreadPriority> 枚举中的任何值。</span><span class="sxs-lookup"><span data-stu-id="55959-147">New threads are created with the value of `Normal`, but you can change the <xref:System.Threading.Thread.Priority%2A> property to any value in the <xref:System.Threading.ThreadPriority> enumeration.</span></span>  
  
 <span data-ttu-id="55959-148">有关各个线程优先级的详细说明，请参阅 <xref:System.Threading.ThreadPriority>。</span><span class="sxs-lookup"><span data-stu-id="55959-148">See <xref:System.Threading.ThreadPriority> for a detailed description of the various thread priorities.</span></span>  
  
## <a name="foreground-and-background-threads"></a><span data-ttu-id="55959-149">前台和后台线程</span><span class="sxs-lookup"><span data-stu-id="55959-149">Foreground and Background Threads</span></span>  
 <span data-ttu-id="55959-150">前台线程可无限制地运行，而后台线程将在最后一个前台线程停止后立即停止。</span><span class="sxs-lookup"><span data-stu-id="55959-150">A *foreground thread* runs indefinitely, whereas a *background thread* stops as soon as the last foreground thread has stopped.</span></span> <span data-ttu-id="55959-151">可以使用 <xref:System.Threading.Thread.IsBackground%2A> 属性来确定或更改线程的后台状态。</span><span class="sxs-lookup"><span data-stu-id="55959-151">You can use the <xref:System.Threading.Thread.IsBackground%2A> property to determine or change the background status of a thread.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55959-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55959-152">See Also</span></span>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="55959-153">线程同步 (C#)</span><span class="sxs-lookup"><span data-stu-id="55959-153">Thread Synchronization (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)  
 [<span data-ttu-id="55959-154">多线程过程的参数和返回值 (C#)</span><span class="sxs-lookup"><span data-stu-id="55959-154">Parameters and Return Values for Multithreaded Procedures (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)  
 <span data-ttu-id="55959-155">[线程处理 [C#]](../../../../csharp/programming-guide/concepts/threading/index.md)</span><span class="sxs-lookup"><span data-stu-id="55959-155">[Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md)</span></span>
