---
title: "线程池 (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 98ae68c1-ace8-44b9-9317-8920ac9ef2b6
caps.latest.revision: "5"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 09dd597e8ac7a6b336f71891ccc89984ea659614
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="thread-pooling-c"></a><span data-ttu-id="56d67-102">线程池 (C#)</span><span class="sxs-lookup"><span data-stu-id="56d67-102">Thread Pooling (C#)</span></span>
<span data-ttu-id="56d67-103">线程池是可用于在后台执行多种任务的线程集合。</span><span class="sxs-lookup"><span data-stu-id="56d67-103">A *thread pool* is a collection of threads that can be used to perform several tasks in the background.</span></span> <span data-ttu-id="56d67-104">（有关背景信息，请参阅[线程处理 (C#)](../../../../csharp/programming-guide/concepts/threading/index.md)。）这使主线程可以自由地异步执行其他任务。</span><span class="sxs-lookup"><span data-stu-id="56d67-104">(See [Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md) for background information.) This leaves the primary thread free to perform other tasks asynchronously.</span></span>  
  
 <span data-ttu-id="56d67-105">线程池通常用于服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="56d67-105">Thread pools are often employed in server applications.</span></span> <span data-ttu-id="56d67-106">每个传入请求都将分配给线程池中的一个线程，因此可以异步处理请求，而不会占用主线程，也不会延迟后续请求的处理。</span><span class="sxs-lookup"><span data-stu-id="56d67-106">Each incoming request is assigned to a thread from the thread pool, so that the request can be processed asynchronously, without tying up the primary thread or delaying the processing of subsequent requests.</span></span>  
  
 <span data-ttu-id="56d67-107">一旦池中的线程完成任务，它将返回到等待线程队列中，等待被重复使用。</span><span class="sxs-lookup"><span data-stu-id="56d67-107">Once a thread in the pool completes its task, it is returned to a queue of waiting threads, where it can be reused.</span></span> <span data-ttu-id="56d67-108">通过这种重复使用，应用程序可以避免产生为每个任务创建新线程的开销。</span><span class="sxs-lookup"><span data-stu-id="56d67-108">This reuse enables applications to avoid the cost of creating a new thread for each task.</span></span>  
  
 <span data-ttu-id="56d67-109">线程池通常具有最大线程数限制。</span><span class="sxs-lookup"><span data-stu-id="56d67-109">Thread pools typically have a maximum number of threads.</span></span> <span data-ttu-id="56d67-110">如果所有线程处于忙碌状态，则额外的任务将放入队列中，直到有线程可用时才能够得到处理。</span><span class="sxs-lookup"><span data-stu-id="56d67-110">If all the threads are busy, additional tasks are put in queue until they can be serviced as threads become available.</span></span>  
  
 <span data-ttu-id="56d67-111">你可以实现自己的线程池，但是通过 <xref:System.Threading.ThreadPool> 类使用 .NET Framework 提供的线程池更容易。</span><span class="sxs-lookup"><span data-stu-id="56d67-111">You can implement your own thread pool, but it is easier to use the thread pool provided by the .NET Framework through the <xref:System.Threading.ThreadPool> class.</span></span>  
  
 <span data-ttu-id="56d67-112">通过使用线程池，可针对想运行的过程调用具有一个委托的 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> 方法，然后 C# 将创建线程并运行此过程。</span><span class="sxs-lookup"><span data-stu-id="56d67-112">With thread pooling, you call the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> method with a delegate for the procedure you want to run, and C# creates the thread and runs your procedure.</span></span>  
  
## <a name="thread-pooling-example"></a><span data-ttu-id="56d67-113">线程池示例</span><span class="sxs-lookup"><span data-stu-id="56d67-113">Thread Pooling Example</span></span>  
 <span data-ttu-id="56d67-114">下面的示例演示如何使用线程池来启动若干任务。</span><span class="sxs-lookup"><span data-stu-id="56d67-114">The following example shows how you can use thread pooling to start several tasks.</span></span>  
  
```csharp  
public void DoWork()  
{  
    // Queue a task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        new System.Threading.WaitCallback(SomeLongTask));  
    // Queue another task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        new System.Threading.WaitCallback(AnotherLongTask));  
}  
  
private void SomeLongTask(Object state)  
{  
    // Insert code to perform a long task.  
}  
  
private void AnotherLongTask(Object state)  
{  
    // Insert code to perform a long task.  
}  
```  
  
 <span data-ttu-id="56d67-115">线程池的一个优点是可以将状态对象中的自变量传递到任务过程。</span><span class="sxs-lookup"><span data-stu-id="56d67-115">One advantage of thread pooling is that you can pass arguments in a state object to the task procedure.</span></span> <span data-ttu-id="56d67-116">如果要调用的过程需要多个自变量，可将结构或类的实例强制转换为 `Object` 数据类型。</span><span class="sxs-lookup"><span data-stu-id="56d67-116">If the procedure you are calling requires more than one argument, you can cast a structure or an instance of a class into an `Object` data type.</span></span>  
  
## <a name="thread-pool-parameters-and-return-values"></a><span data-ttu-id="56d67-117">线程池参数和返回值</span><span class="sxs-lookup"><span data-stu-id="56d67-117">Thread Pool Parameters and Return Values</span></span>  
 <span data-ttu-id="56d67-118">不能直接从线程池线程返回值。</span><span class="sxs-lookup"><span data-stu-id="56d67-118">Returning values from a thread-pool thread is not straightforward.</span></span> <span data-ttu-id="56d67-119">不允许使用通过函数调用来返回值的标准方法，因为 `Sub` 过程是唯一一种可以排队到线程池的过程。</span><span class="sxs-lookup"><span data-stu-id="56d67-119">The standard way of returning values from a function call is not allowed because `Sub` procedures are the only type of procedure that can be queued to a thread pool.</span></span> <span data-ttu-id="56d67-120">一种提供参数和返回值的方法是将参数、返回值和方法包装在一个包装类中，如[多线程过程的参数和返回值 (C#)](../../../../csharp/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md) 中所述。</span><span class="sxs-lookup"><span data-stu-id="56d67-120">One way you can provide parameters and return values is by wrapping the parameters, return values, and methods in a wrapper class as described in [Parameters and Return Values for Multithreaded Procedures (C#)](../../../../csharp/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).</span></span>  
  
 <span data-ttu-id="56d67-121">一种提供参数和返回值的更简单方法是使用 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> 方法的可选 `ByVal` 状态对象变量。</span><span class="sxs-lookup"><span data-stu-id="56d67-121">An easer way to provide parameters and return values is by using the optional `ByVal` state object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="56d67-122">如果使用此变量来传递对类实例的引用，则该实例的成员可以由线程池线程修改，并用作返回值。</span><span class="sxs-lookup"><span data-stu-id="56d67-122">If you use this variable to pass a reference to an instance of a class, the members of the instance can be modified by the thread-pool thread and used as return values.</span></span>  
  
 <span data-ttu-id="56d67-123">最初，可以修改由值传递的变量所引用的对象可能并不明显。</span><span class="sxs-lookup"><span data-stu-id="56d67-123">At first it may not be obvious that you can modify an object referred to by a variable that is passed by value.</span></span> <span data-ttu-id="56d67-124">由于只有对象引用由值传递，因此可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="56d67-124">You can do this because only the object reference is passed by value.</span></span> <span data-ttu-id="56d67-125">当对由对象引用所引用的对象的成员进行更改时，这些更改将应用于实际的类实例。</span><span class="sxs-lookup"><span data-stu-id="56d67-125">When you make changes to members of the object referred to by the object reference, the changes apply to the actual class instance.</span></span>  
  
 <span data-ttu-id="56d67-126">不能使用结构在状态对象内部返回值。</span><span class="sxs-lookup"><span data-stu-id="56d67-126">Structures cannot be used to return values inside state objects.</span></span> <span data-ttu-id="56d67-127">由于结构属于值类型，异步进程所做的更改不会更改原始结构的成员。</span><span class="sxs-lookup"><span data-stu-id="56d67-127">Because structures are value types, changes that the asynchronous process makes do not change the members of the original structure.</span></span> <span data-ttu-id="56d67-128">如果不需要返回值，可以使用结构来提供参数。</span><span class="sxs-lookup"><span data-stu-id="56d67-128">Use structures to provide parameters when return values are not needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56d67-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56d67-129">See Also</span></span>  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="56d67-130">如何：使用线程池 (C#)</span><span class="sxs-lookup"><span data-stu-id="56d67-130">How to: Use a Thread Pool (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)  
 <span data-ttu-id="56d67-131">[线程处理 [C#]](../../../../csharp/programming-guide/concepts/threading/index.md)</span><span class="sxs-lookup"><span data-stu-id="56d67-131">[Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md)</span></span>  
 [<span data-ttu-id="56d67-132">多线程应用程序 (C#)</span><span class="sxs-lookup"><span data-stu-id="56d67-132">Multithreaded Applications (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)  
 [<span data-ttu-id="56d67-133">线程同步 (C#)</span><span class="sxs-lookup"><span data-stu-id="56d67-133">Thread Synchronization (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)
