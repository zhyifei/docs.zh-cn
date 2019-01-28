---
title: 销毁线程
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- destroying threads
- threading [.NET Framework], destroying threads
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93832a296f9b80a5374bc729c04e19d1f178e99f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54502541"
---
# <a name="destroying-threads"></a><span data-ttu-id="59adc-102">销毁线程</span><span class="sxs-lookup"><span data-stu-id="59adc-102">Destroying threads</span></span>
<span data-ttu-id="59adc-103"><xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> 方法用于永久停止托管线程。</span><span class="sxs-lookup"><span data-stu-id="59adc-103">The <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> method is used to stop a managed thread permanently.</span></span> <span data-ttu-id="59adc-104">调用 <xref:System.Threading.Thread.Abort%2A> 时，公共语言运行时在目标线程中抛出目标线程可以捕获的 <xref:System.Threading.ThreadAbortException>。</span><span class="sxs-lookup"><span data-stu-id="59adc-104">When you call <xref:System.Threading.Thread.Abort%2A>, the common language runtime throws a <xref:System.Threading.ThreadAbortException> in the target thread, which the target thread can catch.</span></span> <span data-ttu-id="59adc-105">有关更多信息，请参见<xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="59adc-105">For more information, see <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59adc-106">如果线程在调用 <xref:System.Threading.Thread.Abort%2A> 方法时执行的是非托管代码，运行时将它标记为 <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="59adc-106">If a thread is executing unmanaged code when its <xref:System.Threading.Thread.Abort%2A> method is called, the runtime marks it <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>.</span></span> <span data-ttu-id="59adc-107">当线程返回到托管代码时，异常就会抛出。</span><span class="sxs-lookup"><span data-stu-id="59adc-107">The exception is thrown when the thread returns to managed code.</span></span>  
  
 <span data-ttu-id="59adc-108">一旦线程中止，就无法再重启。</span><span class="sxs-lookup"><span data-stu-id="59adc-108">Once a thread is aborted, it cannot be restarted.</span></span>  
  
 <span data-ttu-id="59adc-109"><xref:System.Threading.Thread.Abort%2A> 方法不会导致线程立即中止，因为目标线程可以捕获 <xref:System.Threading.ThreadAbortException>，并在 `finally` 块中执行任意数量的代码。</span><span class="sxs-lookup"><span data-stu-id="59adc-109">The <xref:System.Threading.Thread.Abort%2A> method does not cause the thread to abort immediately, because the target thread can catch the <xref:System.Threading.ThreadAbortException> and execute arbitrary amounts of code in a `finally` block.</span></span> <span data-ttu-id="59adc-110">如果需要等到线程结束，可以调用 <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="59adc-110">You can call <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> if you need to wait until the thread has ended.</span></span> <span data-ttu-id="59adc-111"><xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> 是阻止调用，除非线程实际已停止执行或可选超时间隔已结束，否则不会返回结果。</span><span class="sxs-lookup"><span data-stu-id="59adc-111"><xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> is a blocking call that does not return until the thread has actually stopped executing or an optional timeout interval has elapsed.</span></span> <span data-ttu-id="59adc-112">由于中止的线程可以调用 <xref:System.Threading.Thread.ResetAbort%2A> 方法或在 `finally` 块中执行无限处理，因此如果不指定超时，就无法保证等到线程结束。</span><span class="sxs-lookup"><span data-stu-id="59adc-112">The aborted thread could call the <xref:System.Threading.Thread.ResetAbort%2A> method or perform unbounded processing in a `finally` block, so if you do not specify a timeout, the wait is not guaranteed to end.</span></span>  
  
 <span data-ttu-id="59adc-113">正在等待调用 <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> 方法的线程可能会被调用 <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> 的其他线程中断。</span><span class="sxs-lookup"><span data-stu-id="59adc-113">Threads that are waiting on a call to the <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> method can be interrupted by other threads that call <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="handling-threadabortexception"></a><span data-ttu-id="59adc-114">处理 ThreadAbortException</span><span class="sxs-lookup"><span data-stu-id="59adc-114">Handling ThreadAbortException</span></span>  
 <span data-ttu-id="59adc-115">如果应中止线程，无论是由于在自己的代码中调用 <xref:System.Threading.Thread.Abort%2A> 所致，还是由于卸载正在运行线程的应用域（<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> 使用 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> 终止线程）所致，线程都必须处理 <xref:System.Threading.ThreadAbortException>，并在 `finally` 子句中执行任何最终处理，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="59adc-115">If you expect your thread to be aborted, either as a result of calling <xref:System.Threading.Thread.Abort%2A> from your own code or as a result of unloading an application domain in which the thread is running (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> uses <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> to terminate threads), your thread must handle the <xref:System.Threading.ThreadAbortException> and perform any final processing in a `finally` clause, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="59adc-116">清理代码必须位于 `catch` 子句或 `finally` 子句中，因为系统会在 `finally` 子句末尾或 `catch` 子句（如果没有 `finally` 子句的话）末尾重新抛出 <xref:System.Threading.ThreadAbortException>。</span><span class="sxs-lookup"><span data-stu-id="59adc-116">Your clean-up code must be in the `catch` clause or the `finally` clause, because a <xref:System.Threading.ThreadAbortException> is rethrown by the system at the end of the `finally` clause, or at the end of the `catch` clause if there is no `finally` clause.</span></span>  
  
 <span data-ttu-id="59adc-117">可以调用 <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> 方法，以防系统重新抛出异常。</span><span class="sxs-lookup"><span data-stu-id="59adc-117">You can prevent the system from rethrowing the exception by calling the <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="59adc-118">不过，只有在自己的代码导致 <xref:System.Threading.ThreadAbortException> 抛出时，才应这样做。</span><span class="sxs-lookup"><span data-stu-id="59adc-118">However, you should do this only if your own code caused the <xref:System.Threading.ThreadAbortException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59adc-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="59adc-119">See also</span></span>

- <xref:System.Threading.ThreadAbortException>
- <xref:System.Threading.Thread>
- [<span data-ttu-id="59adc-120">使用线程和线程处理</span><span class="sxs-lookup"><span data-stu-id="59adc-120">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
