---
title: "多线程应用程序 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: 02b0444b-2e68-4f2c-bc28-28c046004017
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
ms.openlocfilehash: 8b68104fbc5eb0e0eb0f46401f3fcef0d3c4d023
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="multithreaded-applications-visual-basic"></a><span data-ttu-id="78e10-102">多线程应用程序 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78e10-102">Multithreaded Applications (Visual Basic)</span></span>
<span data-ttu-id="78e10-103">使用 Visual Basic 中，您可以编写在同时执行多个任务的应用程序。</span><span class="sxs-lookup"><span data-stu-id="78e10-103">With Visual Basic, you can write applications that perform multiple tasks at the same time.</span></span> <span data-ttu-id="78e10-104">具有潜力支持其他任务的任务可以单独在线程上执行，该过程称为*多线程处理*或*自由线程处理*。</span><span class="sxs-lookup"><span data-stu-id="78e10-104">Tasks with the potential of holding up other tasks can execute on separate threads, a process known as *multithreading* or *free threading*.</span></span>  
  
 <span data-ttu-id="78e10-105">使用多线程处理会更快地响应用户输入因为单独的线程上执行处理器密集型任务用户界面将保持活动状态的应用程序。</span><span class="sxs-lookup"><span data-stu-id="78e10-105">Applications that use multithreading are more responsive to user input because the user interface stays active as processor-intensive tasks execute on separate threads.</span></span> <span data-ttu-id="78e10-106">多线程编程时也很有帮助创建可扩展应用程序，因为您可以随着负载的增加添加线程。</span><span class="sxs-lookup"><span data-stu-id="78e10-106">Multithreading is also useful when you create scalable applications, because you can add threads as the workload increases.</span></span>  
  
## <a name="creating-and-using-threads"></a><span data-ttu-id="78e10-107">创建和使用线程</span><span class="sxs-lookup"><span data-stu-id="78e10-107">Creating and Using Threads</span></span>  
 <span data-ttu-id="78e10-108">如果您需要更好地控制应用程序的线程的行为，您可以自己管理线程。</span><span class="sxs-lookup"><span data-stu-id="78e10-108">If you need more control over the behavior of your application's threads, you can manage the threads yourself.</span></span> <span data-ttu-id="78e10-109">但是，请注意，编写正确的多线程应用程序可能很困难︰ 您的应用程序可能会停止响应或遇到暂时性错误引起的争用条件。</span><span class="sxs-lookup"><span data-stu-id="78e10-109">However, realize that writing correct multithreaded applications can be difficult: Your application may stop responding or experience transient errors caused by race conditions.</span></span> <span data-ttu-id="78e10-110">有关详细信息，请参阅[线程安全组件](http://msdn.microsoft.com/library/4f7c7377-a782-4bd0-aaa3-9db8c12945ee)。</span><span class="sxs-lookup"><span data-stu-id="78e10-110">For more information, see [Thread-Safe Components](http://msdn.microsoft.com/library/4f7c7377-a782-4bd0-aaa3-9db8c12945ee).</span></span>  
  
 <span data-ttu-id="78e10-111">声明类型的变量创建一个新线程<xref:System.Threading.Thread>并调用构造函数中，在提供的过程或你想要在新线程上执行的方法的名称。</xref:System.Threading.Thread></span><span class="sxs-lookup"><span data-stu-id="78e10-111">You create a new thread by declaring a variable of type <xref:System.Threading.Thread> and calling the constructor, providing the name of the procedure or method that you want to execute on the new thread.</span></span> <span data-ttu-id="78e10-112">下面的代码提供了一个示例。</span><span class="sxs-lookup"><span data-stu-id="78e10-112">The following code provides an example.</span></span>  
  
```vb  
Dim newThread As New System.Threading.Thread(AddressOf AMethod)  
```  
  
### <a name="starting-and-stopping-threads"></a><span data-ttu-id="78e10-113">启动和停止的线程</span><span class="sxs-lookup"><span data-stu-id="78e10-113">Starting and Stopping Threads</span></span>  
 <span data-ttu-id="78e10-114">若要启动新线程的执行，使用<xref:System.Threading.Thread.Start%2A>方法，如下面的代码中所示。</xref:System.Threading.Thread.Start%2A></span><span class="sxs-lookup"><span data-stu-id="78e10-114">To start the execution of a new thread, use the <xref:System.Threading.Thread.Start%2A> method, as shown in the following code.</span></span>  
  
```vb  
newThread.Start()  
```  
  
 <span data-ttu-id="78e10-115">若要停止线程的执行，使用<xref:System.Threading.Thread.Abort%2A>方法，如下面的代码中所示。</xref:System.Threading.Thread.Abort%2A></span><span class="sxs-lookup"><span data-stu-id="78e10-115">To stop the execution of a thread, use the <xref:System.Threading.Thread.Abort%2A> method, as shown in the following code.</span></span>  
  
```vb  
newThread.Abort()  
```  
  
 <span data-ttu-id="78e10-116">除了启动和终止线程，您也可以暂停线程通过调用<xref:System.Threading.Thread.Sleep%2A>或<xref:System.Threading.Thread.Suspend%2A>方法中，使用恢复挂起的线程<xref:System.Threading.Thread.Resume%2A>方法，并销毁线程时使用的<xref:System.Threading.Thread.Abort%2A>方法</xref:System.Threading.Thread.Abort%2A></xref:System.Threading.Thread.Resume%2A></xref:System.Threading.Thread.Suspend%2A></xref:System.Threading.Thread.Sleep%2A></span><span class="sxs-lookup"><span data-stu-id="78e10-116">Besides starting and stopping threads, you can also pause threads by calling the <xref:System.Threading.Thread.Sleep%2A> or <xref:System.Threading.Thread.Suspend%2A> method, resume a suspended thread by using the <xref:System.Threading.Thread.Resume%2A> method, and destroy a thread by using the <xref:System.Threading.Thread.Abort%2A> method</span></span>  
  
### <a name="thread-methods"></a><span data-ttu-id="78e10-117">线程方法</span><span class="sxs-lookup"><span data-stu-id="78e10-117">Thread Methods</span></span>  
 <span data-ttu-id="78e10-118">下表显示了一些可用于控制各个线程的方法。</span><span class="sxs-lookup"><span data-stu-id="78e10-118">The following table shows some of the methods that you can use to control individual threads.</span></span>  
  
|<span data-ttu-id="78e10-119">方法</span><span class="sxs-lookup"><span data-stu-id="78e10-119">Method</span></span>|<span data-ttu-id="78e10-120">操作</span><span class="sxs-lookup"><span data-stu-id="78e10-120">Action</span></span>|  
|------------|------------|  
|<span data-ttu-id="78e10-121"><xref:System.Threading.Thread.Start%2A></xref:System.Threading.Thread.Start%2A></span><span class="sxs-lookup"><span data-stu-id="78e10-121"><xref:System.Threading.Thread.Start%2A></span></span>|<span data-ttu-id="78e10-122">使线程开始运行。</span><span class="sxs-lookup"><span data-stu-id="78e10-122">Causes a thread to start to run.</span></span>|  
|<span data-ttu-id="78e10-123"><xref:System.Threading.Thread.Sleep%2A></xref:System.Threading.Thread.Sleep%2A></span><span class="sxs-lookup"><span data-stu-id="78e10-123"><xref:System.Threading.Thread.Sleep%2A></span></span>|<span data-ttu-id="78e10-124">使线程暂停一段指定时间。</span><span class="sxs-lookup"><span data-stu-id="78e10-124">Pauses a thread for a specified time.</span></span>|  
|<span data-ttu-id="78e10-125"><xref:System.Threading.Thread.Suspend%2A></xref:System.Threading.Thread.Suspend%2A></span><span class="sxs-lookup"><span data-stu-id="78e10-125"><xref:System.Threading.Thread.Suspend%2A></span></span>|<span data-ttu-id="78e10-126">在到达某一安全点时，线程暂停。</span><span class="sxs-lookup"><span data-stu-id="78e10-126">Pauses a thread when it reaches a safe point.</span></span>|  
|<span data-ttu-id="78e10-127"><xref:System.Threading.Thread.Abort%2A></xref:System.Threading.Thread.Abort%2A></span><span class="sxs-lookup"><span data-stu-id="78e10-127"><xref:System.Threading.Thread.Abort%2A></span></span>|<span data-ttu-id="78e10-128">在到达某一安全点时停止某个线程。</span><span class="sxs-lookup"><span data-stu-id="78e10-128">Stops a thread when it reaches a safe point.</span></span>|  
|<span data-ttu-id="78e10-129"><xref:System.Threading.Thread.Resume%2A></xref:System.Threading.Thread.Resume%2A></span><span class="sxs-lookup"><span data-stu-id="78e10-129"><xref:System.Threading.Thread.Resume%2A></span></span>|<span data-ttu-id="78e10-130">重新启动挂起的线程</span><span class="sxs-lookup"><span data-stu-id="78e10-130">Restarts a suspended thread</span></span>|  
|<span data-ttu-id="78e10-131"><xref:System.Threading.Thread.Join%2A></xref:System.Threading.Thread.Join%2A></span><span class="sxs-lookup"><span data-stu-id="78e10-131"><xref:System.Threading.Thread.Join%2A></span></span>|<span data-ttu-id="78e10-132">导致当前线程等待另一个线程来完成。</span><span class="sxs-lookup"><span data-stu-id="78e10-132">Causes the current thread to wait for another thread to finish.</span></span> <span data-ttu-id="78e10-133">如果使用的超时值，此方法返回`True`如果线程在分配的时间内完成。</span><span class="sxs-lookup"><span data-stu-id="78e10-133">If used with a time-out value, this method returns `True` if the thread finishes in the allocated time.</span></span>|  
  
### <a name="safe-points"></a><span data-ttu-id="78e10-134">安全点</span><span class="sxs-lookup"><span data-stu-id="78e10-134">Safe Points</span></span>  
 <span data-ttu-id="78e10-135">这些方法中的大多数都一目了然，但这一概念*安全点*可能还不熟悉给您。</span><span class="sxs-lookup"><span data-stu-id="78e10-135">Most of these methods are self-explanatory, but the concept of *safe points* may be new to you.</span></span> <span data-ttu-id="78e10-136">安全点是在代码中的位置位置是安全的公共语言运行时来执行自动*垃圾回收*，释放未使用的变量并回收内存的过程。</span><span class="sxs-lookup"><span data-stu-id="78e10-136">Safe points are locations in code where it is safe for the common language runtime to perform automatic *garbage collection*, the process of releasing unused variables and reclaiming memory.</span></span> <span data-ttu-id="78e10-137">当您调用<xref:System.Threading.Thread.Abort%2A>或<xref:System.Threading.Thread.Suspend%2A>方法的线程，公共语言运行时分析的代码，并确定要停止正在运行的线程的合适位置的位置。</xref:System.Threading.Thread.Suspend%2A> </xref:System.Threading.Thread.Abort%2A></span><span class="sxs-lookup"><span data-stu-id="78e10-137">When you call the <xref:System.Threading.Thread.Abort%2A> or <xref:System.Threading.Thread.Suspend%2A> method of a thread, the common language runtime analyzes the code and determines the location of an appropriate location for the thread to stop running.</span></span>  
  
### <a name="thread-properties"></a><span data-ttu-id="78e10-138">线程属性</span><span class="sxs-lookup"><span data-stu-id="78e10-138">Thread Properties</span></span>  
 <span data-ttu-id="78e10-139">线程也包含几个有用的属性，如下面的表中所示︰</span><span class="sxs-lookup"><span data-stu-id="78e10-139">Threads also contain several useful properties, as shown in the following table:</span></span>  
  
|<span data-ttu-id="78e10-140">属性</span><span class="sxs-lookup"><span data-stu-id="78e10-140">Property</span></span>|<span data-ttu-id="78e10-141">值</span><span class="sxs-lookup"><span data-stu-id="78e10-141">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="78e10-142"><xref:System.Threading.Thread.IsAlive%2A></xref:System.Threading.Thread.IsAlive%2A></span><span class="sxs-lookup"><span data-stu-id="78e10-142"><xref:System.Threading.Thread.IsAlive%2A></span></span>|<span data-ttu-id="78e10-143">包含值`True`如果某个线程处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="78e10-143">Contains the value `True` if a thread is active.</span></span>|  
|<span data-ttu-id="78e10-144"><xref:System.Threading.Thread.IsBackground%2A></xref:System.Threading.Thread.IsBackground%2A></span><span class="sxs-lookup"><span data-stu-id="78e10-144"><xref:System.Threading.Thread.IsBackground%2A></span></span>|<span data-ttu-id="78e10-145">获取或设置一个布尔值，该值指示是否一个线程为或应该是后台线程。</span><span class="sxs-lookup"><span data-stu-id="78e10-145">Gets or sets a Boolean that indicates if a thread is or should be a background thread.</span></span> <span data-ttu-id="78e10-146">后台线程与前台线程类似但后台线程不会阻止从停止的进程。</span><span class="sxs-lookup"><span data-stu-id="78e10-146">Background threads are like foreground threads, but a background thread does not prevent a process from stopping.</span></span> <span data-ttu-id="78e10-147">一旦某个进程的所有前台线程已都停止，公共语言运行时就会结束该进程通过调用<xref:System.Threading.Thread.Abort%2A>仍处于活动状态的后台线程上的方法。</xref:System.Threading.Thread.Abort%2A></span><span class="sxs-lookup"><span data-stu-id="78e10-147">Once all foreground threads that belong to a process have stopped, the common language runtime ends the process by calling the <xref:System.Threading.Thread.Abort%2A> method on background threads that are still alive.</span></span>|  
|<span data-ttu-id="78e10-148"><xref:System.Threading.Thread.Name%2A></xref:System.Threading.Thread.Name%2A></span><span class="sxs-lookup"><span data-stu-id="78e10-148"><xref:System.Threading.Thread.Name%2A></span></span>|<span data-ttu-id="78e10-149">获取或设置线程的名称。</span><span class="sxs-lookup"><span data-stu-id="78e10-149">Gets or sets the name of a thread.</span></span> <span data-ttu-id="78e10-150">最常用于在调试时查找各个线程。</span><span class="sxs-lookup"><span data-stu-id="78e10-150">Most frequently used to discover individual threads when you debug.</span></span>|  
|<span data-ttu-id="78e10-151"><xref:System.Threading.Thread.Priority%2A></xref:System.Threading.Thread.Priority%2A></span><span class="sxs-lookup"><span data-stu-id="78e10-151"><xref:System.Threading.Thread.Priority%2A></span></span>|<span data-ttu-id="78e10-152">获取或设置一个值，由操作系统来确定线程调度优先顺序。</span><span class="sxs-lookup"><span data-stu-id="78e10-152">Gets or sets a value that is used by the operating system to prioritize thread scheduling.</span></span>|  
|<span data-ttu-id="78e10-153"><xref:System.Threading.Thread.ThreadState%2A></xref:System.Threading.Thread.ThreadState%2A></span><span class="sxs-lookup"><span data-stu-id="78e10-153"><xref:System.Threading.Thread.ThreadState%2A></span></span>|<span data-ttu-id="78e10-154">包含描述线程的状态或状态的值。</span><span class="sxs-lookup"><span data-stu-id="78e10-154">Contains a value that describes a thread's state or states.</span></span>|  
  
## <a name="thread-priorities"></a><span data-ttu-id="78e10-155">线程优先级</span><span class="sxs-lookup"><span data-stu-id="78e10-155">Thread Priorities</span></span>  
 <span data-ttu-id="78e10-156">每个线程都具有用于确定需要执行进程 \ 处理器时间的方式大或小切片的优先级属性。</span><span class="sxs-lookup"><span data-stu-id="78e10-156">Every thread has a priority property that determines how big or small a slice of processor time it has to execute.</span></span> <span data-ttu-id="78e10-157">操作系统分配到高优先级的线程的较长的时间段和为低优先级的线程的较短的时间段。</span><span class="sxs-lookup"><span data-stu-id="78e10-157">The operating system allocates longer time slices to high-priority threads and shorter time slices to low-priority threads.</span></span> <span data-ttu-id="78e10-158">值创建新线程`Normal`，但您可以更改<xref:System.Threading.Thread.Priority%2A>属性中的任何值<xref:System.Threading.ThreadPriority>枚举。</xref:System.Threading.ThreadPriority> </xref:System.Threading.Thread.Priority%2A></span><span class="sxs-lookup"><span data-stu-id="78e10-158">New threads are created with the value of `Normal`, but you can change the <xref:System.Threading.Thread.Priority%2A> property to any value in the <xref:System.Threading.ThreadPriority> enumeration.</span></span>  
  
 <span data-ttu-id="78e10-159">请参阅<xref:System.Threading.ThreadPriority>有关各种线程优先级的详细说明。</xref:System.Threading.ThreadPriority></span><span class="sxs-lookup"><span data-stu-id="78e10-159">See <xref:System.Threading.ThreadPriority> for a detailed description of the various thread priorities.</span></span>  
  
## <a name="foreground-and-background-threads"></a><span data-ttu-id="78e10-160">前台和后台线程</span><span class="sxs-lookup"><span data-stu-id="78e10-160">Foreground and Background Threads</span></span>  
 <span data-ttu-id="78e10-161">一个*前台线程*无限制地运行而*后台线程*停止时的最后一个前台线程已停止。</span><span class="sxs-lookup"><span data-stu-id="78e10-161">A *foreground thread* runs indefinitely, whereas a *background thread* stops as soon as the last foreground thread has stopped.</span></span> <span data-ttu-id="78e10-162">您可以使用<xref:System.Threading.Thread.IsBackground%2A>属性来确定或更改后台线程的状态。</xref:System.Threading.Thread.IsBackground%2A></span><span class="sxs-lookup"><span data-stu-id="78e10-162">You can use the <xref:System.Threading.Thread.IsBackground%2A> property to determine or change the background status of a thread.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78e10-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78e10-163">See Also</span></span>  
 <span data-ttu-id="78e10-164"><xref:System.Threading.Thread></xref:System.Threading.Thread></span><span class="sxs-lookup"><span data-stu-id="78e10-164"><xref:System.Threading.Thread></span></span>   
<span data-ttu-id="78e10-165"> [线程同步 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md) </span><span class="sxs-lookup"><span data-stu-id="78e10-165"> [Thread Synchronization (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md) </span></span>  
<span data-ttu-id="78e10-166"> [参数和多线程过程 (Visual Basic 中) 的返回值](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="78e10-166"> [Parameters and Return Values for Multithreaded Procedures (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md) </span></span>  
<span data-ttu-id="78e10-167"> [线程处理 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)</span><span class="sxs-lookup"><span data-stu-id="78e10-167"> [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)</span></span>
