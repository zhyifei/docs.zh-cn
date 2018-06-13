---
title: EventWaitHandle、AutoResetEvent、CountdownEvent、ManualResetEvent
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- wait handles
- threading [.NET Framework], EventWaitHandle class
- event wait handles [.NET Framework]
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 543853f581436a5fb7e5c897012b99bef20dc289
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33582924"
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a><span data-ttu-id="c63dd-102">EventWaitHandle、AutoResetEvent、CountdownEvent、ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="c63dd-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>
<span data-ttu-id="c63dd-103">事件等待句柄允许线程通过相互发送信号和等待信号来同步活动。</span><span class="sxs-lookup"><span data-stu-id="c63dd-103">Event wait handles allow threads to synchronize activities by signaling each other and by waiting on each other's signals.</span></span> <span data-ttu-id="c63dd-104">这些同步事件基于 Win32 等待句柄，可分为两种类型：收到信号时自动重置的事件和手动重置的事件。</span><span class="sxs-lookup"><span data-stu-id="c63dd-104">These synchronization events are based on Win32 wait handles and can be divided into two types: those that reset automatically when signaled and those that are reset manually.</span></span>  
  
 <span data-ttu-id="c63dd-105">事件等待句柄适用于 <xref:System.Threading.Monitor> 类支持的许多同步方案。</span><span class="sxs-lookup"><span data-stu-id="c63dd-105">Event wait handles are useful in many of the same synchronization scenarios as the <xref:System.Threading.Monitor> class.</span></span> <span data-ttu-id="c63dd-106">事件等待句柄通常比 <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> 和 <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> 方法更易于使用，可方便用户更好地控制信号。</span><span class="sxs-lookup"><span data-stu-id="c63dd-106">Event wait handles are often easier to use than the <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> and <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> methods, and they offer more control over signaling.</span></span> <span data-ttu-id="c63dd-107">命名事件等待句柄也可用于跨应用程序域和进程同步活动，而监视器是本地的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="c63dd-107">Named event wait handles can also be used to synchronize activities across application domains and processes, whereas monitors are local to an application domain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c63dd-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="c63dd-108">In This Section</span></span>  
 [<span data-ttu-id="c63dd-109">EventWaitHandle</span><span class="sxs-lookup"><span data-stu-id="c63dd-109">EventWaitHandle</span></span>](../../../docs/standard/threading/eventwaithandle.md)  
 <span data-ttu-id="c63dd-110"><xref:System.Threading.EventWaitHandle> 类可表示自动或手动重置事件，以及本地事件或命名系统事件。</span><span class="sxs-lookup"><span data-stu-id="c63dd-110">The <xref:System.Threading.EventWaitHandle> class can represent either automatic or manual reset events and either local events or named system events.</span></span>  
  
 [<span data-ttu-id="c63dd-111">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="c63dd-111">AutoResetEvent</span></span>](../../../docs/standard/threading/autoresetevent.md)  
 <span data-ttu-id="c63dd-112"><xref:System.Threading.AutoResetEvent> 类派生自 <xref:System.Threading.EventWaitHandle>，表示自动重置的本地事件。</span><span class="sxs-lookup"><span data-stu-id="c63dd-112">The <xref:System.Threading.AutoResetEvent> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that resets automatically.</span></span>  
  
 [<span data-ttu-id="c63dd-113">ManualResetEvent 和 ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="c63dd-113">ManualResetEvent and ManualResetEventSlim</span></span>](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)  
 <span data-ttu-id="c63dd-114"><xref:System.Threading.ManualResetEvent> 类派生自 <xref:System.Threading.EventWaitHandle>，表示必须手动重置的本地事件。</span><span class="sxs-lookup"><span data-stu-id="c63dd-114">The <xref:System.Threading.ManualResetEvent> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that must be reset manually.</span></span> <span data-ttu-id="c63dd-115"><xref:System.Threading.ManualResetEventSlim> 类是可用于同一进程内多个事件的轻型快速版本。</span><span class="sxs-lookup"><span data-stu-id="c63dd-115">The <xref:System.Threading.ManualResetEventSlim> class is a lightweight, faster version that can be used for events within the same process.</span></span>  
  
 [<span data-ttu-id="c63dd-116">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="c63dd-116">CountdownEvent</span></span>](../../../docs/standard/threading/countdownevent.md)  
 <span data-ttu-id="c63dd-117"><xref:System.Threading.CountdownEvent> 类可以在使用等待句柄的代码中轻松实现分支/联接并行度模式。</span><span class="sxs-lookup"><span data-stu-id="c63dd-117">The <xref:System.Threading.CountdownEvent> class provides a simplified way to implement fork/join parallelism patterns in code that uses wait handles.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c63dd-118">相关章节</span><span class="sxs-lookup"><span data-stu-id="c63dd-118">Related Sections</span></span>  
 [<span data-ttu-id="c63dd-119">等待句柄</span><span class="sxs-lookup"><span data-stu-id="c63dd-119">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 <span data-ttu-id="c63dd-120"><xref:System.Threading.WaitHandle> 类是 <xref:System.Threading.EventWaitHandle>、<xref:System.Threading.Semaphore> 和 <xref:System.Threading.Mutex> 类的基类。</span><span class="sxs-lookup"><span data-stu-id="c63dd-120">The <xref:System.Threading.WaitHandle> class is the base class for the <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore>, and <xref:System.Threading.Mutex> classes.</span></span> <span data-ttu-id="c63dd-121">它包含静态方法（如 <xref:System.Threading.WaitHandle.SignalAndWait%2A> 和 <xref:System.Threading.WaitHandle.WaitAll%2A>），这些方法在处理所有类型的等待句柄时非常有用。</span><span class="sxs-lookup"><span data-stu-id="c63dd-121">It contains static methods such as <xref:System.Threading.WaitHandle.SignalAndWait%2A> and <xref:System.Threading.WaitHandle.WaitAll%2A> that are useful when working with all types of wait handles.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c63dd-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="c63dd-122">See Also</span></span>  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 [<span data-ttu-id="c63dd-123">线程处理对象和功能</span><span class="sxs-lookup"><span data-stu-id="c63dd-123">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 [<span data-ttu-id="c63dd-124">托管线程处理基本知识</span><span class="sxs-lookup"><span data-stu-id="c63dd-124">Managed Threading Basics</span></span>](../../../docs/standard/threading/managed-threading-basics.md)
