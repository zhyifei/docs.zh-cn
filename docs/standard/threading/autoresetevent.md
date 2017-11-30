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
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 69d16e8c6491b4c66ab5a5452762e73172ebbb77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="autoresetevent"></a><span data-ttu-id="753d7-102">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="753d7-102">AutoResetEvent</span></span>
<span data-ttu-id="753d7-103"><xref:System.Threading.AutoResetEvent>类表示在终止后释放单个正在等待的线程时自动重置本地等待句柄事件。</span><span class="sxs-lookup"><span data-stu-id="753d7-103">The <xref:System.Threading.AutoResetEvent> class represents a local wait handle event that resets automatically when signaled, after releasing a single waiting thread.</span></span> <span data-ttu-id="753d7-104">此类表示其基本类的一种特殊情况<xref:System.Threading.EventWaitHandle>。</span><span class="sxs-lookup"><span data-stu-id="753d7-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle>.</span></span> <span data-ttu-id="753d7-105">有关自动重置事件的用法和功能，请参阅 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) 概念文档。</span><span class="sxs-lookup"><span data-stu-id="753d7-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of automatic reset events.</span></span>  
  
 <span data-ttu-id="753d7-106"><xref:System.Threading.AutoResetEvent>对象被自动重置为非终止系统在发布单个正在等待的线程之后。</span><span class="sxs-lookup"><span data-stu-id="753d7-106">An <xref:System.Threading.AutoResetEvent> object is automatically reset to non-signaled by the system after a single waiting thread has been released.</span></span> <span data-ttu-id="753d7-107">如果没有线程在等待，则事件对象的状态将保持已发信号状态。</span><span class="sxs-lookup"><span data-stu-id="753d7-107">If no threads are waiting, the event object's state remains signaled.</span></span> <span data-ttu-id="753d7-108"><xref:System.Threading.AutoResetEvent>对应于 Win32`CreateEvent`调用时，指定`false`为`bManualReset`自变量。</span><span class="sxs-lookup"><span data-stu-id="753d7-108"><xref:System.Threading.AutoResetEvent> corresponds to a Win32 `CreateEvent` call, specifying `false` for the `bManualReset` argument.</span></span>  
  
 <span data-ttu-id="753d7-109">有关示例，使用<xref:System.Threading.AutoResetEvent>，请参阅[监视器](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)。</span><span class="sxs-lookup"><span data-stu-id="753d7-109">For an example that uses <xref:System.Threading.AutoResetEvent>, see [Monitor](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="753d7-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="753d7-110">See Also</span></span>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="753d7-111">EventWaitHandle、AutoResetEvent、CountdownEvent、ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="753d7-111">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 [<span data-ttu-id="753d7-112">线程处理</span><span class="sxs-lookup"><span data-stu-id="753d7-112">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="753d7-113">线程处理对象和功能</span><span class="sxs-lookup"><span data-stu-id="753d7-113">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 [<span data-ttu-id="753d7-114">等待句柄</span><span class="sxs-lookup"><span data-stu-id="753d7-114">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)
