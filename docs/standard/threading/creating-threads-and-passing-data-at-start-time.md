---
title: "启动时创建线程并传递数据"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], creating
- threading [.NET Framework], passing data to threads
- threading [.NET Framework], retrieving data from threads
ms.assetid: 52b32222-e185-4f42-91a7-eaca65c0ab6d
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 61808dc804cc627ab368a5250414dfcc5f54c87e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="creating-threads-and-passing-data-at-start-time"></a><span data-ttu-id="c978e-102">启动时创建线程并传递数据</span><span class="sxs-lookup"><span data-stu-id="c978e-102">Creating Threads and Passing Data at Start Time</span></span>
<span data-ttu-id="c978e-103">创建一个操作系统过程时，操作系统将插入一个线程来执行此过程中，包括任何原始的应用程序域中的代码。</span><span class="sxs-lookup"><span data-stu-id="c978e-103">When an operating-system process is created, the operating system injects a thread to execute code in that process, including any original application domain.</span></span> <span data-ttu-id="c978e-104">从那一刻开始，可以创建和销毁，而不一定能创建或销毁任何操作系统线程的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="c978e-104">From that point on, application domains can be created and destroyed without any operating system threads necessarily being created or destroyed.</span></span> <span data-ttu-id="c978e-105">如果所执行的代码托管代码，则<xref:System.Threading.Thread>对象可以通过检索静态获取当前应用程序域中线程执行<xref:System.Threading.Thread.CurrentThread%2A>类型的属性<xref:System.Threading.Thread>。</span><span class="sxs-lookup"><span data-stu-id="c978e-105">If the code being executed is managed code, then a <xref:System.Threading.Thread> object for the thread executing in the current application domain can be obtained by retrieving the static <xref:System.Threading.Thread.CurrentThread%2A> property of type <xref:System.Threading.Thread>.</span></span> <span data-ttu-id="c978e-106">本主题介绍线程创建，并讨论用于将数据传递给了线程过程的替代方法。</span><span class="sxs-lookup"><span data-stu-id="c978e-106">This topic describes thread creation and discusses alternatives for passing data to the thread procedure.</span></span>  
  
## <a name="creating-a-thread"></a><span data-ttu-id="c978e-107">创建线程</span><span class="sxs-lookup"><span data-stu-id="c978e-107">Creating a Thread</span></span>  
 <span data-ttu-id="c978e-108">创建一个新<xref:System.Threading.Thread>对象创建一个新的托管的线程。</span><span class="sxs-lookup"><span data-stu-id="c978e-108">Creating a new <xref:System.Threading.Thread> object creates a new managed thread.</span></span> <span data-ttu-id="c978e-109"><xref:System.Threading.Thread>类具有构造函数采用<xref:System.Threading.ThreadStart>委托或<xref:System.Threading.ParameterizedThreadStart>委托; 委托包装在调用时，新的线程调用的方法的<xref:System.Threading.Thread.Start%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="c978e-109">The <xref:System.Threading.Thread> class has constructors that take a <xref:System.Threading.ThreadStart> delegate or a <xref:System.Threading.ParameterizedThreadStart> delegate; the delegate wraps the method that is invoked by the new thread when you call the <xref:System.Threading.Thread.Start%2A> method.</span></span> <span data-ttu-id="c978e-110">调用<xref:System.Threading.Thread.Start%2A>不止一次导致<xref:System.Threading.ThreadStateException>引发。</span><span class="sxs-lookup"><span data-stu-id="c978e-110">Calling <xref:System.Threading.Thread.Start%2A> more than once causes a <xref:System.Threading.ThreadStateException> to be thrown.</span></span>  
  
 <span data-ttu-id="c978e-111"><xref:System.Threading.Thread.Start%2A>方法返回立即，通常之前已实际启动新线程。</span><span class="sxs-lookup"><span data-stu-id="c978e-111">The <xref:System.Threading.Thread.Start%2A> method returns immediately, often before the new thread has actually started.</span></span> <span data-ttu-id="c978e-112">你可以使用<xref:System.Threading.Thread.ThreadState%2A>和<xref:System.Threading.Thread.IsAlive%2A>属性来确定在任何一个的时刻，线程的状态，但这些属性应永远不会用于同步线程活动。</span><span class="sxs-lookup"><span data-stu-id="c978e-112">You can use the <xref:System.Threading.Thread.ThreadState%2A> and <xref:System.Threading.Thread.IsAlive%2A> properties to determine the state of the thread at any one moment, but these properties should never be used for synchronizing the activities of threads.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c978e-113">线程启动后，不需要保留对引用<xref:System.Threading.Thread>对象。</span><span class="sxs-lookup"><span data-stu-id="c978e-113">Once a thread is started, it is not necessary to retain a reference to the <xref:System.Threading.Thread> object.</span></span> <span data-ttu-id="c978e-114">线程将继续执行，直到线程过程结束。</span><span class="sxs-lookup"><span data-stu-id="c978e-114">The thread continues to execute until the thread procedure ends.</span></span>  
  
 <span data-ttu-id="c978e-115">下面的代码示例创建两个新线程在另一个对象上调用实例和静态方法。</span><span class="sxs-lookup"><span data-stu-id="c978e-115">The following code example creates two new threads to call instance and static methods on another object.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.ThreadStart2#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source2.cs#2)]
 [!code-vb[System.Threading.ThreadStart2#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source2.vb#2)]  
  
## <a name="passing-data-to-threads-and-retrieving-data-from-threads"></a><span data-ttu-id="c978e-116">将数据传递给线程和线程从检索数据</span><span class="sxs-lookup"><span data-stu-id="c978e-116">Passing Data to Threads and Retrieving Data from Threads</span></span>  
 <span data-ttu-id="c978e-117">在.NET Framework 2.0 版中，<xref:System.Threading.ParameterizedThreadStart>委托可以轻松地将对象包含为某个线程的数据，在调用时传递<xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>方法重载。</span><span class="sxs-lookup"><span data-stu-id="c978e-117">In the .NET Framework version 2.0, the <xref:System.Threading.ParameterizedThreadStart> delegate provides an easy way to pass an object containing data to a thread when you call the <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> method overload.</span></span> <span data-ttu-id="c978e-118">有关代码示例，请参阅 <xref:System.Threading.ParameterizedThreadStart>。</span><span class="sxs-lookup"><span data-stu-id="c978e-118">See <xref:System.Threading.ParameterizedThreadStart> for a code example.</span></span>  
  
 <span data-ttu-id="c978e-119">使用<xref:System.Threading.ParameterizedThreadStart>委托不是以类型安全的方式传递数据，因为<xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>方法重载接受任何对象。</span><span class="sxs-lookup"><span data-stu-id="c978e-119">Using the <xref:System.Threading.ParameterizedThreadStart> delegate is not a type-safe way to pass data, because the <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> method overload accepts any object.</span></span> <span data-ttu-id="c978e-120">替代方法是封装了线程过程和帮助器类中的数据，并使用<xref:System.Threading.ThreadStart>委托执行了线程过程。</span><span class="sxs-lookup"><span data-stu-id="c978e-120">An alternative is to encapsulate the thread procedure and the data in a helper class and use the <xref:System.Threading.ThreadStart> delegate to execute the thread procedure.</span></span> <span data-ttu-id="c978e-121">下面的两个代码示例演示了此技术。</span><span class="sxs-lookup"><span data-stu-id="c978e-121">This technique is shown in the two code examples that follow.</span></span>  
  
 <span data-ttu-id="c978e-122">两种情况均委托具有返回值，因为不是在将数据返回的异步调用从任何位置。</span><span class="sxs-lookup"><span data-stu-id="c978e-122">Neither of these delegates has a return value, because there is no place to return the data from an asynchronous call.</span></span> <span data-ttu-id="c978e-123">若要检索线程方法的结果，可以使用回调方法，如第二个代码示例中所示。</span><span class="sxs-lookup"><span data-stu-id="c978e-123">To retrieve the results of a thread method, you can use a callback method, as demonstrated in the second code example.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source3.cpp#3)]
 [!code-csharp[System.Threading.ThreadStart2#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source3.cs#3)]
 [!code-vb[System.Threading.ThreadStart2#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source3.vb#3)]  
  
### <a name="retrieving-data-with-callback-methods"></a><span data-ttu-id="c978e-124">使用回调方法中检索数据</span><span class="sxs-lookup"><span data-stu-id="c978e-124">Retrieving Data with Callback Methods</span></span>  
 <span data-ttu-id="c978e-125">下面的示例演示如何从一个线程中检索数据的回调方法。</span><span class="sxs-lookup"><span data-stu-id="c978e-125">The following example demonstrates a callback method that retrieves data from a thread.</span></span> <span data-ttu-id="c978e-126">包含的数据和线程方法的类的构造函数还接受委托表示的回调方法;线程方法结束之前，它调用的回调委托。</span><span class="sxs-lookup"><span data-stu-id="c978e-126">The constructor for the class that contains the data and the thread method also accepts a delegate representing the callback method; before the thread method ends, it invokes the callback delegate.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#4](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source4.cpp#4)]
 [!code-csharp[System.Threading.ThreadStart2#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source4.cs#4)]
 [!code-vb[System.Threading.ThreadStart2#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source4.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="c978e-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c978e-127">See Also</span></span>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadStart>  
 <xref:System.Threading.ParameterizedThreadStart>  
 <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="c978e-128">线程处理</span><span class="sxs-lookup"><span data-stu-id="c978e-128">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="c978e-129">使用线程和线程处理</span><span class="sxs-lookup"><span data-stu-id="c978e-129">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
