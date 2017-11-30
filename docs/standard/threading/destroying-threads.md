---
title: "销毁线程"
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
- destroying threads
- threading [.NET Framework], destroying threads
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4a41dce5db707d0be49c283256de665d316e1a1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="destroying-threads"></a><span data-ttu-id="e51b4-102">销毁线程</span><span class="sxs-lookup"><span data-stu-id="e51b4-102">Destroying Threads</span></span>
<span data-ttu-id="e51b4-103"><xref:System.Threading.Thread.Abort%2A>方法用于永久停止托管的线程。</span><span class="sxs-lookup"><span data-stu-id="e51b4-103">The <xref:System.Threading.Thread.Abort%2A> method is used to stop a managed thread permanently.</span></span> <span data-ttu-id="e51b4-104">当调用<xref:System.Threading.Thread.Abort%2A>，公共语言运行时会引发<xref:System.Threading.ThreadAbortException>目标线程，可以捕获此目标线程中。</span><span class="sxs-lookup"><span data-stu-id="e51b4-104">When you call <xref:System.Threading.Thread.Abort%2A>, the common language runtime throws a <xref:System.Threading.ThreadAbortException> in the target thread, which the target thread can catch.</span></span> <span data-ttu-id="e51b4-105">有关详细信息，请参阅<xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="e51b4-105">For more information, see <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e51b4-106">如果线程执行非托管代码时其<xref:System.Threading.Thread.Abort%2A>方法被调用时，运行时将其标记<xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="e51b4-106">If a thread is executing unmanaged code when its <xref:System.Threading.Thread.Abort%2A> method is called, the runtime marks it <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e51b4-107">当线程返回给托管代码引发异常。</span><span class="sxs-lookup"><span data-stu-id="e51b4-107">The exception is thrown when the thread returns to managed code.</span></span>  
  
 <span data-ttu-id="e51b4-108">一旦线程被中止，它不能重新启动。</span><span class="sxs-lookup"><span data-stu-id="e51b4-108">Once a thread is aborted, it cannot be restarted.</span></span>  
  
 <span data-ttu-id="e51b4-109"><xref:System.Threading.Thread.Abort%2A>方法不会导致立即中止的线程因为目标线程可以捕获<xref:System.Threading.ThreadAbortException>和执行任意数量的代码中`finally`块。</span><span class="sxs-lookup"><span data-stu-id="e51b4-109">The <xref:System.Threading.Thread.Abort%2A> method does not cause the thread to abort immediately, because the target thread can catch the <xref:System.Threading.ThreadAbortException> and execute arbitrary amounts of code in a `finally` block.</span></span> <span data-ttu-id="e51b4-110">你可以调用<xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>如果你需要等待，直到线程已结束。</span><span class="sxs-lookup"><span data-stu-id="e51b4-110">You can call <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> if you need to wait until the thread has ended.</span></span> <span data-ttu-id="e51b4-111"><xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>是一个线程确实已停止执行后才返回值的阻塞调用或可选的超时间隔已过去。</span><span class="sxs-lookup"><span data-stu-id="e51b4-111"><xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> is a blocking call that does not return until the thread has actually stopped executing or an optional timeout interval has elapsed.</span></span> <span data-ttu-id="e51b4-112">中止的线程可以调用<xref:System.Threading.Thread.ResetAbort%2A>方法或执行中的不受限制的处理`finally`块中，因此如果不指定超时，则不保证在等待结束。</span><span class="sxs-lookup"><span data-stu-id="e51b4-112">The aborted thread could call the <xref:System.Threading.Thread.ResetAbort%2A> method or perform unbounded processing in a `finally` block, so if you do not specify a timeout, the wait is not guaranteed to end.</span></span>  
  
 <span data-ttu-id="e51b4-113">在调用等待的线程<xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>方法可以由其他线程调用中断<xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="e51b4-113">Threads that are waiting on a call to the <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> method can be interrupted by other threads that call <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="handling-threadabortexception"></a><span data-ttu-id="e51b4-114">处理 ThreadAbortException</span><span class="sxs-lookup"><span data-stu-id="e51b4-114">Handling ThreadAbortException</span></span>  
 <span data-ttu-id="e51b4-115">如果希望你的线程将中止，调用的结果作为<xref:System.Threading.Thread.Abort%2A>从你自己的代码或由于而卸载线程正在运行的应用程序域 (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType>使用<xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>终止线程)，你的线程必须处理<xref:System.Threading.ThreadAbortException>并执行中的任何最终处理`finally`子句，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="e51b4-115">If you expect your thread to be aborted, either as a result of calling <xref:System.Threading.Thread.Abort%2A> from your own code or as a result of unloading an application domain in which the thread is running (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> uses <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> to terminate threads), your thread must handle the <xref:System.Threading.ThreadAbortException> and perform any final processing in a `finally` clause, as shown in the following code.</span></span>  
  
```vb  
Try  
    ' Code that is executing when the thread is aborted.  
Catch ex As ThreadAbortException  
    ' Clean-up code can go here.  
    ' If there is no Finally clause, ThreadAbortException is  
    ' re-thrown by the system at the end of the Catch clause.   
Finally  
    ' Clean-up code can go here.  
End Try  
' Do not put clean-up code here, because the exception   
' is rethrown at the end of the Finally clause.  
```  
  
```csharp  
try   
{  
    // Code that is executing when the thread is aborted.  
}   
catch (ThreadAbortException ex)   
{  
    // Clean-up code can go here.  
    // If there is no Finally clause, ThreadAbortException is  
    // re-thrown by the system at the end of the Catch clause.   
}  
// Do not put clean-up code here, because the exception   
// is rethrown at the end of the Finally clause.  
```  
  
 <span data-ttu-id="e51b4-116">清理代码必须在`catch`子句或`finally`子句，因为<xref:System.Threading.ThreadAbortException>末尾的系统将被重新引发`finally`子句，或末尾`catch`子句如果没有任何`finally`子句。</span><span class="sxs-lookup"><span data-stu-id="e51b4-116">Your clean-up code must be in the `catch` clause or the `finally` clause, because a <xref:System.Threading.ThreadAbortException> is rethrown by the system at the end of the `finally` clause, or at the end of the `catch` clause if there is no `finally` clause.</span></span>  
  
 <span data-ttu-id="e51b4-117">你可以通过调用重新引发的异常阻止系统<xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="e51b4-117">You can prevent the system from rethrowing the exception by calling the <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="e51b4-118">但是，应执行你自己的代码导致此才<xref:System.Threading.ThreadAbortException>。</span><span class="sxs-lookup"><span data-stu-id="e51b4-118">However, you should do this only if your own code caused the <xref:System.Threading.ThreadAbortException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e51b4-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e51b4-119">See Also</span></span>  
 <xref:System.Threading.ThreadAbortException>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="e51b4-120">使用线程和线程处理</span><span class="sxs-lookup"><span data-stu-id="e51b4-120">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
