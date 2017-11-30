---
title: CountdownEvent
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
helpviewer_keywords: synchronization primitives, CountdownEvent
ms.assetid: eec3812a-e20f-4ecd-bfef-6921d508b708
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9f953f6477abf1f4e0d6aaf79e67005172ff1144
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="countdownevent"></a><span data-ttu-id="4facd-102">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="4facd-102">CountdownEvent</span></span>
<span data-ttu-id="4facd-103"><xref:System.Threading.CountdownEvent?displayProperty=nameWithType>是一个后，将取消其正在等待的线程的同步基元发出信号一定次数。</span><span class="sxs-lookup"><span data-stu-id="4facd-103"><xref:System.Threading.CountdownEvent?displayProperty=nameWithType> is a synchronization primitive that unblocks its waiting threads after it has been signaled a certain number of times.</span></span> <span data-ttu-id="4facd-104"><xref:System.Threading.CountdownEvent>专为在其中你本来要使用的方案<xref:System.Threading.ManualResetEvent>或<xref:System.Threading.ManualResetEventSlim>和手动发出事件信号之前递减的变量。</span><span class="sxs-lookup"><span data-stu-id="4facd-104"><xref:System.Threading.CountdownEvent> is designed for scenarios in which you would otherwise have to use a <xref:System.Threading.ManualResetEvent> or <xref:System.Threading.ManualResetEventSlim> and manually decrement a variable before signaling the event.</span></span> <span data-ttu-id="4facd-105">例如，在分叉/联接方案中，你可以只创建<xref:System.Threading.CountdownEvent>，它具有一个信号计数为 5，且然后开始五个的工作项，而在线程池和具有每个工作项调用<xref:System.Threading.CountdownEvent.Signal%2A>完成时。</span><span class="sxs-lookup"><span data-stu-id="4facd-105">For example, in a fork/join scenario, you can just create a <xref:System.Threading.CountdownEvent> that has a signal count of 5, and then start five work items on the thread pool and have each work item call <xref:System.Threading.CountdownEvent.Signal%2A> when it completes.</span></span> <span data-ttu-id="4facd-106">每次调用<xref:System.Threading.CountdownEvent.Signal%2A>信号计数 1。</span><span class="sxs-lookup"><span data-stu-id="4facd-106">Each call to <xref:System.Threading.CountdownEvent.Signal%2A> decrements the signal count by 1.</span></span> <span data-ttu-id="4facd-107">在主线程调用<xref:System.Threading.CountdownEvent.Wait%2A>将阻止，直到信号计数为零。</span><span class="sxs-lookup"><span data-stu-id="4facd-107">On the main thread, the call to <xref:System.Threading.CountdownEvent.Wait%2A> will block until the signal count is zero.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4facd-108">对于不需要与旧的.NET Framework 同步 Api 结合使用进行交互的代码，请考虑使用<xref:System.Threading.Tasks.Task?displayProperty=nameWithType>对象或<xref:System.Threading.Tasks.Parallel.Invoke%2A>一种更简单的表示分叉联接并行的方法。</span><span class="sxs-lookup"><span data-stu-id="4facd-108">For code that does not have to interact with legacy .NET Framework synchronization APIs, consider using <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or the <xref:System.Threading.Tasks.Parallel.Invoke%2A> method for an even easier approach to expressing fork-join parallelism.</span></span>  
  
 <span data-ttu-id="4facd-109"><xref:System.Threading.CountdownEvent>具有这些附加功能：</span><span class="sxs-lookup"><span data-stu-id="4facd-109"><xref:System.Threading.CountdownEvent> has these additional features:</span></span>  
  
-   <span data-ttu-id="4facd-110">可以通过使用取消标记取消等待操作。</span><span class="sxs-lookup"><span data-stu-id="4facd-110">The wait operation can be canceled by using cancellation tokens.</span></span>  
  
-   <span data-ttu-id="4facd-111">在创建实例之后，可以递增其信号计数。</span><span class="sxs-lookup"><span data-stu-id="4facd-111">Its signal count can be incremented after the instance is created.</span></span>  
  
-   <span data-ttu-id="4facd-112">实例可以重用后<xref:System.Threading.CountdownEvent.Wait%2A>已返回通过调用<xref:System.Threading.CountdownEvent.Reset%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="4facd-112">Instances can be reused after <xref:System.Threading.CountdownEvent.Wait%2A> has returned by calling the <xref:System.Threading.CountdownEvent.Reset%2A> method.</span></span>  
  
-   <span data-ttu-id="4facd-113">实例公开<xref:System.Threading.WaitHandle>与其他.NET Framework 同步 Api 结合使用的集成如<xref:System.Threading.WaitHandle.WaitAll%2A>。</span><span class="sxs-lookup"><span data-stu-id="4facd-113">Instances expose a <xref:System.Threading.WaitHandle> for integration with other .NET Framework synchronization APIs such as <xref:System.Threading.WaitHandle.WaitAll%2A>.</span></span>  
  
## <a name="basic-usage"></a><span data-ttu-id="4facd-114">基本用法</span><span class="sxs-lookup"><span data-stu-id="4facd-114">Basic Usage</span></span>  
 <span data-ttu-id="4facd-115">下面的示例演示如何使用<xref:System.Threading.CountdownEvent>与<xref:System.Threading.ThreadPool>工作项。</span><span class="sxs-lookup"><span data-stu-id="4facd-115">The following example demonstrates how to use a <xref:System.Threading.CountdownEvent> with <xref:System.Threading.ThreadPool> work items.</span></span>  
  
 [!code-csharp[CDS_CountdownEvent#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#01)]
 [!code-vb[CDS_CountdownEvent#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/module1.vb#01)]  
  
## <a name="countdownevent-with-cancellation"></a><span data-ttu-id="4facd-116">CountdownEvent 的取消</span><span class="sxs-lookup"><span data-stu-id="4facd-116">CountdownEvent With Cancellation</span></span>  
 <span data-ttu-id="4facd-117">下面的示例演示如何在取消的等待操作<xref:System.Threading.CountdownEvent>使用取消标记。</span><span class="sxs-lookup"><span data-stu-id="4facd-117">The following example shows how to cancel the wait operation on <xref:System.Threading.CountdownEvent> by using a cancellation token.</span></span> <span data-ttu-id="4facd-118">基本模式遵循统一取消情况，在中引入模型[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4facd-118">The basic pattern follows the model for unified cancellation, which is introduced in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="4facd-119">有关详细信息，请参阅[托管线程中的取消](../../../docs/standard/threading/cancellation-in-managed-threads.md)。</span><span class="sxs-lookup"><span data-stu-id="4facd-119">For more information, see [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span></span>  
  
 [!code-csharp[CDS_CountdownEvent#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#02)]
 [!code-vb[CDS_CountdownEvent#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/canceleventwait.vb#02)]  
  
 <span data-ttu-id="4facd-120">请注意，等待操作不会取消向其发出信号的线程。</span><span class="sxs-lookup"><span data-stu-id="4facd-120">Note that the wait operation does not cancel the threads that are signaling it.</span></span> <span data-ttu-id="4facd-121">通常情况下，取消应用于逻辑运算，且其中可以包括有关事件，以及所有工作项同步等待的等待。</span><span class="sxs-lookup"><span data-stu-id="4facd-121">Typically, cancellation is applied to a logical operation, and that can include waiting on the event as well as all the work items that the wait is synchronizing.</span></span> <span data-ttu-id="4facd-122">在此示例中，每个工作项传递的相同的取消标记的副本，以便它可以响应取消请求。</span><span class="sxs-lookup"><span data-stu-id="4facd-122">In this example, each work item is passed a copy of the same cancellation token so that it can respond to the cancellation request.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4facd-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4facd-123">See Also</span></span>  
 [<span data-ttu-id="4facd-124">EventWaitHandle、AutoResetEvent、CountdownEvent、ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="4facd-124">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)
