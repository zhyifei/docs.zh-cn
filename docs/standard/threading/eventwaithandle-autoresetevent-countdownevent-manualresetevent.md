---
title: "EventWaitHandle、AutoResetEvent、CountdownEvent、ManualResetEvent"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wait handles
- threading [.NET Framework], EventWaitHandle class
- event wait handles [.NET Framework]
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5c0bcb27ed9c8981665a50c129dfbd824c9612f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a><span data-ttu-id="edbc3-102">EventWaitHandle、AutoResetEvent、CountdownEvent、ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="edbc3-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>
<span data-ttu-id="edbc3-103">事件等待句柄允许线程通过相互发送信号和等待信号来同步活动。</span><span class="sxs-lookup"><span data-stu-id="edbc3-103">Event wait handles allow threads to synchronize activities by signaling each other and by waiting on each other's signals.</span></span> <span data-ttu-id="edbc3-104">这些同步事件基于 Win32 等待句柄，可分为两种类型：收到信号时自动重置的事件和手动重置的事件。</span><span class="sxs-lookup"><span data-stu-id="edbc3-104">These synchronization events are based on Win32 wait handles and can be divided into two types: those that reset automatically when signaled and those that are reset manually.</span></span>  
  
 <span data-ttu-id="edbc3-105">事件等待句柄可在很多相同的同步方案作为<xref:System.Threading.Monitor>类。</span><span class="sxs-lookup"><span data-stu-id="edbc3-105">Event wait handles are useful in many of the same synchronization scenarios as the <xref:System.Threading.Monitor> class.</span></span> <span data-ttu-id="edbc3-106">事件等待句柄是通常比使用起来更为简便<xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType>和<xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType>方法，并且它们提供了更好地控制信号。</span><span class="sxs-lookup"><span data-stu-id="edbc3-106">Event wait handles are often easier to use than the <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> and <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> methods, and they offer more control over signaling.</span></span> <span data-ttu-id="edbc3-107">命名事件等待句柄也可用于跨应用程序域和进程同步活动，而监视器是本地的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="edbc3-107">Named event wait handles can also be used to synchronize activities across application domains and processes, whereas monitors are local to an application domain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="edbc3-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="edbc3-108">In This Section</span></span>  
 [<span data-ttu-id="edbc3-109">EventWaitHandle</span><span class="sxs-lookup"><span data-stu-id="edbc3-109">EventWaitHandle</span></span>](../../../docs/standard/threading/eventwaithandle.md)  
 <span data-ttu-id="edbc3-110"><xref:System.Threading.EventWaitHandle>类可以表示自动或手动重置事件以及本地事件，或已命名的系统事件。</span><span class="sxs-lookup"><span data-stu-id="edbc3-110">The <xref:System.Threading.EventWaitHandle> class can represent either automatic or manual reset events and either local events or named system events.</span></span>  
  
 [<span data-ttu-id="edbc3-111">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="edbc3-111">AutoResetEvent</span></span>](../../../docs/standard/threading/autoresetevent.md)  
 <span data-ttu-id="edbc3-112"><xref:System.Threading.AutoResetEvent>类派生自<xref:System.Threading.EventWaitHandle>，表示自动重置的本地事件。</span><span class="sxs-lookup"><span data-stu-id="edbc3-112">The <xref:System.Threading.AutoResetEvent> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that resets automatically.</span></span>  
  
 [<span data-ttu-id="edbc3-113">ManualResetEvent 和 ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="edbc3-113">ManualResetEvent and ManualResetEventSlim</span></span>](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)  
 <span data-ttu-id="edbc3-114"><xref:System.Threading.ManualResetEvent>类派生自<xref:System.Threading.EventWaitHandle>，表示必须手动重置的本地事件。</span><span class="sxs-lookup"><span data-stu-id="edbc3-114">The <xref:System.Threading.ManualResetEvent> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that must be reset manually.</span></span> <span data-ttu-id="edbc3-115"><xref:System.Threading.ManualResetEventSlim>类是可以用于相同的进程内的事件的轻量、 更快版本。</span><span class="sxs-lookup"><span data-stu-id="edbc3-115">The <xref:System.Threading.ManualResetEventSlim> class is a lightweight, faster version that can be used for events within the same process.</span></span>  
  
 [<span data-ttu-id="edbc3-116">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="edbc3-116">CountdownEvent</span></span>](../../../docs/standard/threading/countdownevent.md)  
 <span data-ttu-id="edbc3-117"><xref:System.Threading.CountdownEvent>类提供了一种简化的方法，以在代码中使用等待句柄实现派生/联结并行模式。</span><span class="sxs-lookup"><span data-stu-id="edbc3-117">The <xref:System.Threading.CountdownEvent> class provides a simplified way to implement fork/join parallelism patterns in code that uses wait handles.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="edbc3-118">相关章节</span><span class="sxs-lookup"><span data-stu-id="edbc3-118">Related Sections</span></span>  
 [<span data-ttu-id="edbc3-119">等待句柄</span><span class="sxs-lookup"><span data-stu-id="edbc3-119">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 <span data-ttu-id="edbc3-120"><xref:System.Threading.WaitHandle>类是适用于基<xref:System.Threading.EventWaitHandle>， <xref:System.Threading.Semaphore>，和<xref:System.Threading.Mutex>类。</span><span class="sxs-lookup"><span data-stu-id="edbc3-120">The <xref:System.Threading.WaitHandle> class is the base class for the <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore>, and <xref:System.Threading.Mutex> classes.</span></span> <span data-ttu-id="edbc3-121">它包含静态方法，例如<xref:System.Threading.WaitHandle.SignalAndWait%2A>和<xref:System.Threading.WaitHandle.WaitAll%2A>，当处理所有类型的等待句柄时非常有用。</span><span class="sxs-lookup"><span data-stu-id="edbc3-121">It contains static methods such as <xref:System.Threading.WaitHandle.SignalAndWait%2A> and <xref:System.Threading.WaitHandle.WaitAll%2A> that are useful when working with all types of wait handles.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edbc3-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="edbc3-122">See Also</span></span>  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 [<span data-ttu-id="edbc3-123">线程处理对象和功能</span><span class="sxs-lookup"><span data-stu-id="edbc3-123">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 [<span data-ttu-id="edbc3-124">托管线程处理基本知识</span><span class="sxs-lookup"><span data-stu-id="edbc3-124">Managed Threading Basics</span></span>](../../../docs/standard/threading/managed-threading-basics.md)
