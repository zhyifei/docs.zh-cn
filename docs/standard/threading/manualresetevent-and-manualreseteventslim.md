---
title: "ManualResetEvent 和 ManualResetEventSlim"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], ManualResetEvent class
- ManualResetEvent class, about ManualResetEvent class
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f663dd17b063f77e2f9ce6bd4bbd0f8859ba4116
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="manualresetevent-and-manualreseteventslim"></a><span data-ttu-id="b9c13-102">ManualResetEvent 和 ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="b9c13-102">ManualResetEvent and ManualResetEventSlim</span></span>
<span data-ttu-id="b9c13-103"><xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>类表示一个本地等待句柄事件，必须手动重置后处于有信号状态。</span><span class="sxs-lookup"><span data-stu-id="b9c13-103">The <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class represents a local wait handle event that must be reset manually after it is signaled.</span></span> <span data-ttu-id="b9c13-104">此类表示其基本类的一种特殊情况<xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="b9c13-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b9c13-105">有关手动重置的用法和功能，请参阅 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) 概念文档。</span><span class="sxs-lookup"><span data-stu-id="b9c13-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of manual reset events.</span></span>  
  
 <span data-ttu-id="b9c13-106">A<xref:System.Threading.ManualResetEvent>对象仍保留终止状态，直到其<xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType>调用方法。</span><span class="sxs-lookup"><span data-stu-id="b9c13-106">A <xref:System.Threading.ManualResetEvent> object remains signaled until its <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="b9c13-107">在对象状态为已收到信号时，可以释放任意数量正在等待的线程，或是在收到信号后等待事件的线程。</span><span class="sxs-lookup"><span data-stu-id="b9c13-107">Any number of waiting threads, or threads that wait on the event after it has been signaled, can be released while the object's state is signaled.</span></span> <span data-ttu-id="b9c13-108"><xref:System.Threading.ManualResetEvent>对应于 Win32`CreateEvent`调用时，指定`true`为`bManualReset`自变量。</span><span class="sxs-lookup"><span data-stu-id="b9c13-108"><xref:System.Threading.ManualResetEvent> corresponds to a Win32 `CreateEvent` call, specifying `true` for the `bManualReset` argument.</span></span>  
  
 <span data-ttu-id="b9c13-109">在[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]，你可以使用<xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>类更好的性能和事件不能跨越进程边界时等待时间预计很短。</span><span class="sxs-lookup"><span data-stu-id="b9c13-109">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use the <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> class for better performance when wait times are expected to be very short, and when the event does not cross a process boundary.</span></span> <span data-ttu-id="b9c13-110"><xref:System.Threading.ManualResetEventSlim>使用繁忙旋转很短的时间，等待事件变为终止状态时。</span><span class="sxs-lookup"><span data-stu-id="b9c13-110"><xref:System.Threading.ManualResetEventSlim> uses busy spinning for a short time while it waits for the event to become signaled.</span></span> <span data-ttu-id="b9c13-111">等待时间较短时，旋转的开销相对于使用等待句柄来进行等待的开销会少很多。</span><span class="sxs-lookup"><span data-stu-id="b9c13-111">When wait times are short, spinning can be much less expensive than waiting by using wait handles.</span></span> <span data-ttu-id="b9c13-112">但是，如果事件不会变得终止在特定时间段内，<xref:System.Threading.ManualResetEventSlim>转为常规事件句柄等待。</span><span class="sxs-lookup"><span data-stu-id="b9c13-112">However, if the event does not become signaled within a certain period of time, <xref:System.Threading.ManualResetEventSlim> resorts to a regular event handle wait.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9c13-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9c13-113">See Also</span></span>  
 [<span data-ttu-id="b9c13-114">线程处理</span><span class="sxs-lookup"><span data-stu-id="b9c13-114">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="b9c13-115">线程处理对象和功能</span><span class="sxs-lookup"><span data-stu-id="b9c13-115">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 [<span data-ttu-id="b9c13-116">等待句柄</span><span class="sxs-lookup"><span data-stu-id="b9c13-116">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 [<span data-ttu-id="b9c13-117">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="b9c13-117">AutoResetEvent</span></span>](../../../docs/standard/threading/autoresetevent.md)  
 [<span data-ttu-id="b9c13-118">SpinWait</span><span class="sxs-lookup"><span data-stu-id="b9c13-118">SpinWait</span></span>](../../../docs/standard/threading/spinwait.md)  
 [<span data-ttu-id="b9c13-119">Semaphore 和 SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="b9c13-119">Semaphore and SemaphoreSlim</span></span>](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
