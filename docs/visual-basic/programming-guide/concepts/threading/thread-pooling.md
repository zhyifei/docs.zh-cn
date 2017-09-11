---
title: "线程池 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: 4903fb7a-eaad-435a-9add-1d1b32de3b83
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: eea7c94dffe525bb36c677bf3414f25ed0210074
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="thread-pooling-visual-basic"></a><span data-ttu-id="a76e6-102">线程池 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a76e6-102">Thread Pooling (Visual Basic)</span></span>
<span data-ttu-id="a76e6-103">一个*线程池*是可以用来在后台执行多种任务的线程集合。</span><span class="sxs-lookup"><span data-stu-id="a76e6-103">A *thread pool* is a collection of threads that can be used to perform several tasks in the background.</span></span> <span data-ttu-id="a76e6-104">(请参阅[线程处理 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/threading/index.md)的背景信息。)这将使主线程可以自由以异步方式执行其他任务。</span><span class="sxs-lookup"><span data-stu-id="a76e6-104">(See [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) for background information.) This leaves the primary thread free to perform other tasks asynchronously.</span></span>  
  
 <span data-ttu-id="a76e6-105">线程池通常用于在服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="a76e6-105">Thread pools are often employed in server applications.</span></span> <span data-ttu-id="a76e6-106">每个传入请求被分配给一个线程从线程池，以便可以进行异步处理请求，而无需占用主线程或延迟的后续请求处理。</span><span class="sxs-lookup"><span data-stu-id="a76e6-106">Each incoming request is assigned to a thread from the thread pool, so that the request can be processed asynchronously, without tying up the primary thread or delaying the processing of subsequent requests.</span></span>  
  
 <span data-ttu-id="a76e6-107">后在池中的线程完成其任务，它将返回到等待线程的队列可以重复使用。</span><span class="sxs-lookup"><span data-stu-id="a76e6-107">Once a thread in the pool completes its task, it is returned to a queue of waiting threads, where it can be reused.</span></span> <span data-ttu-id="a76e6-108">这种重用使应用程序可避免创建新的每个任务的线程的开销。</span><span class="sxs-lookup"><span data-stu-id="a76e6-108">This reuse enables applications to avoid the cost of creating a new thread for each task.</span></span>  
  
 <span data-ttu-id="a76e6-109">线程池通常具有最大线程数。</span><span class="sxs-lookup"><span data-stu-id="a76e6-109">Thread pools typically have a maximum number of threads.</span></span> <span data-ttu-id="a76e6-110">如果所有线程都都正忙于，其他任务都被放在队列中，直到它们能够得到处理线程变为可用。</span><span class="sxs-lookup"><span data-stu-id="a76e6-110">If all the threads are busy, additional tasks are put in queue until they can be serviced as threads become available.</span></span>  
  
 <span data-ttu-id="a76e6-111">可以实现您自己的线程池，但很容易地使用线程池提供的.NET Framework<xref:System.Threading.ThreadPool>类。</xref:System.Threading.ThreadPool></span><span class="sxs-lookup"><span data-stu-id="a76e6-111">You can implement your own thread pool, but it is easier to use the thread pool provided by the .NET Framework through the <xref:System.Threading.ThreadPool> class.</span></span>  
  
 <span data-ttu-id="a76e6-112">使用线程池，您调用<xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName>想要运行，有关该过程与委托的方法和 Visual Basic 创建线程，并运行您的过程。</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a76e6-112">With thread pooling, you call the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName> method with a delegate for the procedure you want to run, and Visual Basic creates the thread and runs your procedure.</span></span>  
  
## <a name="thread-pooling-example"></a><span data-ttu-id="a76e6-113">线程池示例</span><span class="sxs-lookup"><span data-stu-id="a76e6-113">Thread Pooling Example</span></span>  
 <span data-ttu-id="a76e6-114">下面的示例演示如何使用线程池来开始几个任务。</span><span class="sxs-lookup"><span data-stu-id="a76e6-114">The following example shows how you can use thread pooling to start several tasks.</span></span>  
  
```vb  
Public Sub DoWork()  
    ' Queue a task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        New System.Threading.WaitCallback(AddressOf SomeLongTask))  
    ' Queue another task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        New System.Threading.WaitCallback(AddressOf AnotherLongTask))  
End Sub  
Private Sub SomeLongTask(ByVal state As Object)  
    ' Insert code to perform a long task.  
End Sub  
Private Sub AnotherLongTask(ByVal state As Object)  
    ' Insert code to perform another long task.  
End Sub  
```  
  
 <span data-ttu-id="a76e6-115">线程池的一个优点是，您可以将参数传递一个状态对象到任务过程。</span><span class="sxs-lookup"><span data-stu-id="a76e6-115">One advantage of thread pooling is that you can pass arguments in a state object to the task procedure.</span></span> <span data-ttu-id="a76e6-116">如果您正在调用的过程需要多个参数，您可以强制转换的结构或到类的实例`Object`数据类型。</span><span class="sxs-lookup"><span data-stu-id="a76e6-116">If the procedure you are calling requires more than one argument, you can cast a structure or an instance of a class into an `Object` data type.</span></span>  
  
## <a name="thread-pool-parameters-and-return-values"></a><span data-ttu-id="a76e6-117">线程池参数和返回值</span><span class="sxs-lookup"><span data-stu-id="a76e6-117">Thread Pool Parameters and Return Values</span></span>  
 <span data-ttu-id="a76e6-118">从一个线程池线程返回值并不简单。</span><span class="sxs-lookup"><span data-stu-id="a76e6-118">Returning values from a thread-pool thread is not straightforward.</span></span> <span data-ttu-id="a76e6-119">不能使用函数调用返回值的标准方法，因为`Sub`过程是唯一的一种可排入线程池的过程。</span><span class="sxs-lookup"><span data-stu-id="a76e6-119">The standard way of returning values from a function call is not allowed because `Sub` procedures are the only type of procedure that can be queued to a thread pool.</span></span> <span data-ttu-id="a76e6-120">一种方法可以提供参数，并返回值是通过包装这些参数，返回值和方法在包装器类，如中所述[参数和多线程过程 (Visual Basic 中) 的返回值](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="a76e6-120">One way you can provide parameters and return values is by wrapping the parameters, return values, and methods in a wrapper class as described in [Parameters and Return Values for Multithreaded Procedures (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).</span></span>  
  
 <span data-ttu-id="a76e6-121">提供的参数和返回值的数据更容易方法是通过使用可选`ByVal`状态对象变量<xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>方法。</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></span><span class="sxs-lookup"><span data-stu-id="a76e6-121">An easer way to provide parameters and return values is by using the optional `ByVal` state object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="a76e6-122">如果使用此变量来传递到类的实例的引用，则可以修改由线程池线程的实例的成员，并将其用作返回值。</span><span class="sxs-lookup"><span data-stu-id="a76e6-122">If you use this variable to pass a reference to an instance of a class, the members of the instance can be modified by the thread-pool thread and used as return values.</span></span>  
  
 <span data-ttu-id="a76e6-123">开始时它可能不明显，可以修改通过值传递的变量引用的对象。</span><span class="sxs-lookup"><span data-stu-id="a76e6-123">At first it may not be obvious that you can modify an object referred to by a variable that is passed by value.</span></span> <span data-ttu-id="a76e6-124">您可以这样做，因为仅将对象引用通过值传递。</span><span class="sxs-lookup"><span data-stu-id="a76e6-124">You can do this because only the object reference is passed by value.</span></span> <span data-ttu-id="a76e6-125">如果对引用的对象引用的对象的成员进行更改，所做的更改适用于实际的类实例。</span><span class="sxs-lookup"><span data-stu-id="a76e6-125">When you make changes to members of the object referred to by the object reference, the changes apply to the actual class instance.</span></span>  
  
 <span data-ttu-id="a76e6-126">结构不能用于返回状态对象内的值。</span><span class="sxs-lookup"><span data-stu-id="a76e6-126">Structures cannot be used to return values inside state objects.</span></span> <span data-ttu-id="a76e6-127">结构是值类型，因为异步进程所做的更改不会更改原始结构的成员。</span><span class="sxs-lookup"><span data-stu-id="a76e6-127">Because structures are value types, changes that the asynchronous process makes do not change the members of the original structure.</span></span> <span data-ttu-id="a76e6-128">使用结构时返回值，则不需要提供参数。</span><span class="sxs-lookup"><span data-stu-id="a76e6-128">Use structures to provide parameters when return values are not needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a76e6-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a76e6-129">See Also</span></span>  
 <span data-ttu-id="a76e6-130"><xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></span><span class="sxs-lookup"><span data-stu-id="a76e6-130"><xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></span></span>   
 <span data-ttu-id="a76e6-131"><xref:System.Threading></xref:System.Threading></span><span class="sxs-lookup"><span data-stu-id="a76e6-131"><xref:System.Threading></span></span>   
 <span data-ttu-id="a76e6-132"><xref:System.Threading.ThreadPool></xref:System.Threading.ThreadPool></span><span class="sxs-lookup"><span data-stu-id="a76e6-132"><xref:System.Threading.ThreadPool></span></span>   
<span data-ttu-id="a76e6-133"> [如何︰ 使用线程池 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md) </span><span class="sxs-lookup"><span data-stu-id="a76e6-133"> [How to: Use a Thread Pool (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md) </span></span>  
<span data-ttu-id="a76e6-134"> [线程处理 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) </span><span class="sxs-lookup"><span data-stu-id="a76e6-134"> [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) </span></span>  
<span data-ttu-id="a76e6-135"> [多线程应用程序 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md) </span><span class="sxs-lookup"><span data-stu-id="a76e6-135"> [Multithreaded Applications (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md) </span></span>  
<span data-ttu-id="a76e6-136"> [线程同步 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="a76e6-136"> [Thread Synchronization (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)</span></span>
