---
title: 通过结束异步操作来阻止应用程序执行
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- blocks, asynchronous operations
- AsyncWaitHandle property
- asynchronous programming, blocking applications
- blocking application execution
ms.assetid: cc5e2834-a65b-4df8-b750-7bdb79997fee
dev_langs:
- csharp
- vb
ms.openlocfilehash: aed3b18c154d4b7a4390b28fb1f14536690f6b3a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "73121332"
---
# <a name="blocking-application-execution-by-ending-an-async-operation"></a><span data-ttu-id="37b70-102">通过结束异步操作来阻止应用程序执行</span><span class="sxs-lookup"><span data-stu-id="37b70-102">Blocking Application Execution by Ending an Async Operation</span></span>
<span data-ttu-id="37b70-103">如果应用无法在等待异步操作结果期间继续执行其他工作，必须阻止应用一直到操作完成。</span><span class="sxs-lookup"><span data-stu-id="37b70-103">Applications that cannot continue to do other work while waiting for the results of an asynchronous operation must block until the operation completes.</span></span> <span data-ttu-id="37b70-104">请使用下列方法之一，在应用等待异步操作完成期间阻止应用的主线程：</span><span class="sxs-lookup"><span data-stu-id="37b70-104">Use one of the following options to block your application's main thread while waiting for an asynchronous operation to complete:</span></span>  
  
- <span data-ttu-id="37b70-105">调用异步操作的 EndOperationName 方法   。</span><span class="sxs-lookup"><span data-stu-id="37b70-105">Call the asynchronous operations **End**_OperationName_ method.</span></span> <span data-ttu-id="37b70-106">本主题介绍的就是这种方法。</span><span class="sxs-lookup"><span data-stu-id="37b70-106">This approach is demonstrated in this topic.</span></span>  
  
- <span data-ttu-id="37b70-107">使用异步操作的 BeginOperationName<xref:System.IAsyncResult.AsyncWaitHandle%2A><xref:System.IAsyncResult>  方法返回的 _的_ 属性。</span><span class="sxs-lookup"><span data-stu-id="37b70-107">Use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin**_OperationName_ method.</span></span> <span data-ttu-id="37b70-108">有关展示这种方法的示例，请参阅[使用 AsyncWaitHandle 阻止应用执行](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md)。</span><span class="sxs-lookup"><span data-stu-id="37b70-108">For an example that demonstrates this approach, see [Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span></span>  
  
 <span data-ttu-id="37b70-109">在异步操作完成前使用 End**OperationName 方法阻止的应用程序，通常会调用 Begin**OperationName 方法，执行任何不需要等待操作结果也可以执行的工作，然后调用 End_OperationName_     。</span><span class="sxs-lookup"><span data-stu-id="37b70-109">Applications that use the **End**_OperationName_ method to block until an asynchronous operation is complete will typically call the **Begin**_OperationName_ method, perform any work that can be done without the results of the operation, and then call **End**_OperationName_.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37b70-110">示例</span><span class="sxs-lookup"><span data-stu-id="37b70-110">Example</span></span>  
 <span data-ttu-id="37b70-111">下面的代码示例展示了如何使用 <xref:System.Net.Dns> 类中的异步方法，检索用户指定计算机的域名系统信息。</span><span class="sxs-lookup"><span data-stu-id="37b70-111">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="37b70-112">请注意，对 `null``Nothing` 和 <xref:System.Net.Dns.BeginGetHostByName%2A> 参数传递的是 `requestCallback`（Visual Basic 中的 `stateObject`），因为使用这种方法时这些是可选参数。</span><span class="sxs-lookup"><span data-stu-id="37b70-112">Note that `null` (`Nothing` in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` and `stateObject` parameters because these arguments are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlock.cs#1)]
 [!code-vb[AsyncDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlock.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="37b70-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37b70-113">See also</span></span>

- [<span data-ttu-id="37b70-114">基于事件的异步模式 (EAP)</span><span class="sxs-lookup"><span data-stu-id="37b70-114">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- [<span data-ttu-id="37b70-115">基于事件的异步模式概述</span><span class="sxs-lookup"><span data-stu-id="37b70-115">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
