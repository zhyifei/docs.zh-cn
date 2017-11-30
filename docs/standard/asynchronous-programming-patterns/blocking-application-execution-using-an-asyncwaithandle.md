---
title: "使用 AsyncWaitHandle 阻止应用程序的执行"
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
helpviewer_keywords:
- blocks, asynchronous operations
- ending asynchronous operations
- asynchronous programming, ending operations
- asynchronous programming, blocking applications
- stopping asynchronous operations
- blocking application execution
ms.assetid: 3e32daf2-8161-4e8f-addd-9fd9ff101b03
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2660b3cbf7e8ee43a22edbfb66a4262684983b87
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="blocking-application-execution-using-an-asyncwaithandle"></a><span data-ttu-id="df603-102">使用 AsyncWaitHandle 阻止应用程序的执行</span><span class="sxs-lookup"><span data-stu-id="df603-102">Blocking Application Execution Using an AsyncWaitHandle</span></span>
<span data-ttu-id="df603-103">操作完成之前，必须阻止的应用程序无法继续执行其他工作的同时等待异步操作的结果。</span><span class="sxs-lookup"><span data-stu-id="df603-103">Applications that cannot continue to do other work while waiting for the results of an asynchronous operation must block until the operation completes.</span></span> <span data-ttu-id="df603-104">使用以下选项之一来阻止应用程序的主线程在等待异步操作以完成时：</span><span class="sxs-lookup"><span data-stu-id="df603-104">Use one of the following options to block your application's main thread while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="df603-105">使用<xref:System.IAsyncResult.AsyncWaitHandle%2A>属性<xref:System.IAsyncResult>异步操作返回**开始** *OperationName*方法。</span><span class="sxs-lookup"><span data-stu-id="df603-105">Use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin** *OperationName* method.</span></span> <span data-ttu-id="df603-106">本主题中演示了这种方法。</span><span class="sxs-lookup"><span data-stu-id="df603-106">This approach is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="df603-107">调用异步操作的**结束** *OperationName*方法。</span><span class="sxs-lookup"><span data-stu-id="df603-107">Call the asynchronous operation's **End** *OperationName* method.</span></span> <span data-ttu-id="df603-108">有关演示此方法的示例，请参阅[通过结束异步操作来阻止应用程序执行](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md)。</span><span class="sxs-lookup"><span data-stu-id="df603-108">For an example that demonstrates this approach, see [Blocking Application Execution by Ending an Async Operation](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).</span></span>  
  
 <span data-ttu-id="df603-109">使用一个或多个应用程序<xref:System.Threading.WaitHandle>对象进行阻止，直到异步操作已完成，通常会调用**开始** *OperationName*方法，执行可以完成任何工作而无需操作，和之前的异步操作的块的结果完成。</span><span class="sxs-lookup"><span data-stu-id="df603-109">Applications that use one or more <xref:System.Threading.WaitHandle> objects to block until an asynchronous operation is complete will typically call the **Begin** *OperationName* method, perform any work that can be done without the results of the operation, and then block until the asynchronous operation(s) completes.</span></span> <span data-ttu-id="df603-110">应用程序可以通过调用其中一种来阻止一个操作上<xref:System.Threading.WaitHandle.WaitOne%2A>方法使用<xref:System.IAsyncResult.AsyncWaitHandle%2A>。</span><span class="sxs-lookup"><span data-stu-id="df603-110">An application can block on a single operation by calling one of the <xref:System.Threading.WaitHandle.WaitOne%2A> methods using the <xref:System.IAsyncResult.AsyncWaitHandle%2A>.</span></span> <span data-ttu-id="df603-111">若要阻止等待异步操作完成的一组时，存储关联<xref:System.IAsyncResult.AsyncWaitHandle%2A>中数组中，然后调用的对象<xref:System.Threading.WaitHandle.WaitAll%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="df603-111">To block while waiting for a set of asynchronous operations to complete, store the associated <xref:System.IAsyncResult.AsyncWaitHandle%2A> objects in an array and call one of the <xref:System.Threading.WaitHandle.WaitAll%2A> methods.</span></span> <span data-ttu-id="df603-112">若要阻止等待任一一套异步操作完成时，存储关联<xref:System.IAsyncResult.AsyncWaitHandle%2A>中数组中，然后调用的对象<xref:System.Threading.WaitHandle.WaitAny%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="df603-112">To block while waiting for any one of a set of asynchronous operations to complete, store the associated <xref:System.IAsyncResult.AsyncWaitHandle%2A> objects in an array and call one of the <xref:System.Threading.WaitHandle.WaitAny%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df603-113">示例</span><span class="sxs-lookup"><span data-stu-id="df603-113">Example</span></span>  
 <span data-ttu-id="df603-114">下面的代码示例演示如何使用 DNS 类中的异步方法来检索用户指定的计算机的域名系统信息。</span><span class="sxs-lookup"><span data-stu-id="df603-114">The following code example demonstrates using asynchronous methods in the DNS class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="df603-115">示例演示了阻止使用<xref:System.Threading.WaitHandle>与异步操作关联。</span><span class="sxs-lookup"><span data-stu-id="df603-115">The example demonstrates blocking using the <xref:System.Threading.WaitHandle> associated with the asynchronous operation.</span></span> <span data-ttu-id="df603-116">请注意， `null` (`Nothing`在 Visual Basic 中) 为传递<xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback`和`stateObject`参数因为使用此方法时，这些并不需要。</span><span class="sxs-lookup"><span data-stu-id="df603-116">Note that `null` (`Nothing` in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` and `stateObject` parameters because these are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlockWait.cs#2)]
 [!code-vb[AsyncDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlockWait.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="df603-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df603-117">See Also</span></span>  
 [<span data-ttu-id="df603-118">基于事件的异步模式 (EAP)</span><span class="sxs-lookup"><span data-stu-id="df603-118">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="df603-119">基于事件的异步模式概述</span><span class="sxs-lookup"><span data-stu-id="df603-119">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
