---
title: ManualResetEvent 和 ManualResetEventSlim
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], ManualResetEvent class
- ManualResetEvent class, about ManualResetEvent class
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4949540b9f61e71301647a83a1c05d8b4c941412
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2018
ms.locfileid: "46581267"
---
# <a name="manualresetevent-and-manualreseteventslim"></a><span data-ttu-id="634f6-102">ManualResetEvent 和 ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="634f6-102">ManualResetEvent and ManualResetEventSlim</span></span>
<span data-ttu-id="634f6-103"><xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> 类表示必须在收到信号后手动重置的本地等待句柄事件。</span><span class="sxs-lookup"><span data-stu-id="634f6-103">The <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class represents a local wait handle event that must be reset manually after it is signaled.</span></span> <span data-ttu-id="634f6-104">此类表示其基类 <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> 的特例。</span><span class="sxs-lookup"><span data-stu-id="634f6-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>.</span></span> <span data-ttu-id="634f6-105">有关手动重置的用法和功能，请参阅 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) 概念文档。</span><span class="sxs-lookup"><span data-stu-id="634f6-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of manual reset events.</span></span>  
  
 <span data-ttu-id="634f6-106">在 <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> 方法获得调用前，<xref:System.Threading.ManualResetEvent> 对象会一直收到信号。</span><span class="sxs-lookup"><span data-stu-id="634f6-106">A <xref:System.Threading.ManualResetEvent> object remains signaled until its <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="634f6-107">在对象状态为已收到信号时，可以释放任意数量正在等待的线程，或是在收到信号后等待事件的线程。</span><span class="sxs-lookup"><span data-stu-id="634f6-107">Any number of waiting threads, or threads that wait on the event after it has been signaled, can be released while the object's state is signaled.</span></span>
  
 <span data-ttu-id="634f6-108">在 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 中，如果应缩短等待时间，且事件不会跨越进程边界，可以使用 <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> 类，以提升性能。</span><span class="sxs-lookup"><span data-stu-id="634f6-108">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use the <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> class for better performance when wait times are expected to be very short, and when the event does not cross a process boundary.</span></span> <span data-ttu-id="634f6-109">等待事件收到信号期间，<xref:System.Threading.ManualResetEventSlim> 会短暂使用忙碌旋转。</span><span class="sxs-lookup"><span data-stu-id="634f6-109"><xref:System.Threading.ManualResetEventSlim> uses busy spinning for a short time while it waits for the event to become signaled.</span></span> <span data-ttu-id="634f6-110">等待时间较短时，旋转的开销相对于使用等待句柄来进行等待的开销会少很多。</span><span class="sxs-lookup"><span data-stu-id="634f6-110">When wait times are short, spinning can be much less expensive than waiting by using wait handles.</span></span> <span data-ttu-id="634f6-111">不过，如果在特定时间段内事件没有收到信号，<xref:System.Threading.ManualResetEventSlim> 会求助于常规的事件句柄等待。</span><span class="sxs-lookup"><span data-stu-id="634f6-111">However, if the event does not become signaled within a certain period of time, <xref:System.Threading.ManualResetEventSlim> resorts to a regular event handle wait.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="634f6-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="634f6-112">See also</span></span>

- [<span data-ttu-id="634f6-113">线程处理</span><span class="sxs-lookup"><span data-stu-id="634f6-113">Threading</span></span>](../../../docs/standard/threading/index.md)  
- [<span data-ttu-id="634f6-114">线程处理对象和功能</span><span class="sxs-lookup"><span data-stu-id="634f6-114">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
- [<span data-ttu-id="634f6-115">等待句柄</span><span class="sxs-lookup"><span data-stu-id="634f6-115">Wait Handles</span></span>](https://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
- [<span data-ttu-id="634f6-116">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="634f6-116">AutoResetEvent</span></span>](../../../docs/standard/threading/autoresetevent.md)  
- [<span data-ttu-id="634f6-117">SpinWait</span><span class="sxs-lookup"><span data-stu-id="634f6-117">SpinWait</span></span>](../../../docs/standard/threading/spinwait.md)  
- [<span data-ttu-id="634f6-118">Semaphore 和 SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="634f6-118">Semaphore and SemaphoreSlim</span></span>](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
