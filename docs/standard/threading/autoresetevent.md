---
title: AutoResetEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], AutoResetEvent class
- AutoResetEvent class
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 71933d0be804fdf68b0dc602902343f2d88b8c82
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="autoresetevent"></a><span data-ttu-id="c1dbf-102">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="c1dbf-102">AutoResetEvent</span></span>
<span data-ttu-id="c1dbf-103"><xref:System.Threading.AutoResetEvent> 类表示本地等待句柄事件，此事件在一个等待线程释放后收到信号时自动重置。</span><span class="sxs-lookup"><span data-stu-id="c1dbf-103">The <xref:System.Threading.AutoResetEvent> class represents a local wait handle event that resets automatically when signaled, after releasing a single waiting thread.</span></span> <span data-ttu-id="c1dbf-104">此类表示其基类 <xref:System.Threading.EventWaitHandle> 的特例。</span><span class="sxs-lookup"><span data-stu-id="c1dbf-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle>.</span></span> <span data-ttu-id="c1dbf-105">有关自动重置事件的用法和功能，请参阅 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) 概念文档。</span><span class="sxs-lookup"><span data-stu-id="c1dbf-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of automatic reset events.</span></span>  
  
 <span data-ttu-id="c1dbf-106">在一个等待线程已释放后，系统会自动将 <xref:System.Threading.AutoResetEvent> 对象重置为处于未收到信号状态。</span><span class="sxs-lookup"><span data-stu-id="c1dbf-106">An <xref:System.Threading.AutoResetEvent> object is automatically reset to non-signaled by the system after a single waiting thread has been released.</span></span> <span data-ttu-id="c1dbf-107">如果没有线程在等待，则事件对象的状态将保持已发信号状态。</span><span class="sxs-lookup"><span data-stu-id="c1dbf-107">If no threads are waiting, the event object's state remains signaled.</span></span> <span data-ttu-id="c1dbf-108"><xref:System.Threading.AutoResetEvent> 对应于 Win32 `CreateEvent` 调用，同时为 `bManualReset` 参数指定 `false`。</span><span class="sxs-lookup"><span data-stu-id="c1dbf-108"><xref:System.Threading.AutoResetEvent> corresponds to a Win32 `CreateEvent` call, specifying `false` for the `bManualReset` argument.</span></span>  
  
 <span data-ttu-id="c1dbf-109">有关使用 <xref:System.Threading.AutoResetEvent> 的示例，请参阅[监视器](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)。</span><span class="sxs-lookup"><span data-stu-id="c1dbf-109">For an example that uses <xref:System.Threading.AutoResetEvent>, see [Monitor](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1dbf-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1dbf-110">See Also</span></span>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="c1dbf-111">EventWaitHandle、AutoResetEvent、CountdownEvent、ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="c1dbf-111">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 [<span data-ttu-id="c1dbf-112">线程处理</span><span class="sxs-lookup"><span data-stu-id="c1dbf-112">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="c1dbf-113">线程处理对象和功能</span><span class="sxs-lookup"><span data-stu-id="c1dbf-113">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 [<span data-ttu-id="c1dbf-114">等待句柄</span><span class="sxs-lookup"><span data-stu-id="c1dbf-114">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)
