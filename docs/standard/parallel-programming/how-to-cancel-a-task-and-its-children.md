---
title: "如何：取消任务及其子级"
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
helpviewer_keywords: tasks, how to cancel
ms.assetid: 08574301-8331-4719-ad50-9cf7f6ff3048
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 374068694a3aa9724905964717dc5e77c09fc0ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-cancel-a-task-and-its-children"></a><span data-ttu-id="ac464-102">如何：取消任务及其子级</span><span class="sxs-lookup"><span data-stu-id="ac464-102">How to: Cancel a Task and Its Children</span></span>
<span data-ttu-id="ac464-103">这些示例演示如何执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="ac464-103">These examples show how to perform the following tasks:</span></span>  
  
1.  <span data-ttu-id="ac464-104">创建并启动可取消任务。</span><span class="sxs-lookup"><span data-stu-id="ac464-104">Create and start a cancelable task.</span></span>  
  
2.  <span data-ttu-id="ac464-105">（可选） 你的用户委托和任务实例，请传递一个取消标记。</span><span class="sxs-lookup"><span data-stu-id="ac464-105">Pass a cancellation token to your user delegate and optionally to the task instance.</span></span>  
  
3.  <span data-ttu-id="ac464-106">请注意并响应用户委托中的取消请求。</span><span class="sxs-lookup"><span data-stu-id="ac464-106">Notice and respond to the cancellation request in your user delegate.</span></span>  
  
4.  <span data-ttu-id="ac464-107">（可选） 请注意，在调用线程的任务已取消。</span><span class="sxs-lookup"><span data-stu-id="ac464-107">Optionally notice on the calling thread that the task was canceled.</span></span>  
  
 <span data-ttu-id="ac464-108">调用线程不会强制结束任务;它仅发出信号已请求取消操作。</span><span class="sxs-lookup"><span data-stu-id="ac464-108">The calling thread does not forcibly end the task; it only signals that cancellation is requested.</span></span> <span data-ttu-id="ac464-109">如果任务已在运行，负责注意请求并做出相应响应的用户委托。</span><span class="sxs-lookup"><span data-stu-id="ac464-109">If the task is already running, it is up to the user delegate to notice the request and respond appropriately.</span></span> <span data-ttu-id="ac464-110">如果在任务运行前请求取消，然后永远不会执行的用户委托和任务对象转换为 Canceled 状态。</span><span class="sxs-lookup"><span data-stu-id="ac464-110">If cancellation is requested before the task runs, then the user delegate is never executed and the task object transitions into the Canceled state.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac464-111">示例</span><span class="sxs-lookup"><span data-stu-id="ac464-111">Example</span></span>  
 <span data-ttu-id="ac464-112">此示例演示如何终止<xref:System.Threading.Tasks.Task>及其子级以响应取消请求。</span><span class="sxs-lookup"><span data-stu-id="ac464-112">This example shows how to terminate a <xref:System.Threading.Tasks.Task> and its children in response to a cancellation request.</span></span> <span data-ttu-id="ac464-113">还会演示，当用户委托通过引发 <xref:System.Threading.Tasks.TaskCanceledException> 终止时，调用线程可以选择使用 <xref:System.Threading.Tasks.Task.Wait%2A> 方法或 <xref:System.Threading.Tasks.Task.WaitAll%2A> 方法来等待任务完成。</span><span class="sxs-lookup"><span data-stu-id="ac464-113">It also shows that when a user delegate terminates by throwing a <xref:System.Threading.Tasks.TaskCanceledException>, the calling thread can optionally use the <xref:System.Threading.Tasks.Task.Wait%2A> method or <xref:System.Threading.Tasks.Task.WaitAll%2A> method to wait for the tasks to finish.</span></span> <span data-ttu-id="ac464-114">在这种情况下，必须使用 `try/catch` 块来处理调用线程上的异常。</span><span class="sxs-lookup"><span data-stu-id="ac464-114">In this case, you must use a `try/catch` block to handle the exceptions on the calling thread.</span></span>  
  
 [!code-csharp[TPL_Cancellation#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/cancel1.cs#04)]
 [!code-vb[TPL_Cancellation#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/cancel1.vb#04)]  
  
 <span data-ttu-id="ac464-115"><xref:System.Threading.Tasks.Task?displayProperty=nameWithType>与基于取消模型完全集成类<xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType>和<xref:System.Threading.CancellationToken?displayProperty=nameWithType>类型。</span><span class="sxs-lookup"><span data-stu-id="ac464-115">The <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> class is fully integrated with the cancellation model that is based on the <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> and <xref:System.Threading.CancellationToken?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="ac464-116">有关详细信息，请参阅[托管线程中的取消](../../../docs/standard/threading/cancellation-in-managed-threads.md)和[任务取消](../../../docs/standard/parallel-programming/task-cancellation.md)。</span><span class="sxs-lookup"><span data-stu-id="ac464-116">For more information, see [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md) and [Task Cancellation](../../../docs/standard/parallel-programming/task-cancellation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac464-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac464-117">See Also</span></span>  
 <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType>  
 <xref:System.Threading.CancellationToken?displayProperty=nameWithType>  
 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>  
 <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>  
 [<span data-ttu-id="ac464-118">基于任务的异步编程</span><span class="sxs-lookup"><span data-stu-id="ac464-118">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)  
 [<span data-ttu-id="ac464-119">附加和分离的子任务</span><span class="sxs-lookup"><span data-stu-id="ac464-119">Attached and Detached Child Tasks</span></span>](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md)  
 [<span data-ttu-id="ac464-120">PLINQ 和 TPL 中的 Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="ac464-120">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
