---
title: AutoResetEvent
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], AutoResetEvent class
- AutoResetEvent class
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1785ce223f0dcd4da7ea6ef9fa3a3e897a39dca
ms.sourcegitcommit: dc02d7d95f1e3efcc7166eaf431b0ec0dc9d8dca
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37143508"
---
# <a name="autoresetevent"></a><span data-ttu-id="8e664-102">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="8e664-102">AutoResetEvent</span></span>
<span data-ttu-id="8e664-103"><xref:System.Threading.AutoResetEvent> 类表示本地等待句柄事件，此事件在一个等待线程释放后收到信号时自动重置。</span><span class="sxs-lookup"><span data-stu-id="8e664-103">The <xref:System.Threading.AutoResetEvent> class represents a local wait handle event that resets automatically when signaled, after releasing a single waiting thread.</span></span> <span data-ttu-id="8e664-104">此类表示其基类 <xref:System.Threading.EventWaitHandle> 的特例。</span><span class="sxs-lookup"><span data-stu-id="8e664-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle>.</span></span> <span data-ttu-id="8e664-105">有关自动重置事件的用法和功能，请参阅 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) 概念文档。</span><span class="sxs-lookup"><span data-stu-id="8e664-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of automatic reset events.</span></span>  
  
 <span data-ttu-id="8e664-106">在一个等待线程已释放后，系统会自动将 <xref:System.Threading.AutoResetEvent> 对象重置为处于未收到信号状态。</span><span class="sxs-lookup"><span data-stu-id="8e664-106">An <xref:System.Threading.AutoResetEvent> object is automatically reset to non-signaled by the system after a single waiting thread has been released.</span></span> <span data-ttu-id="8e664-107">如果没有线程在等待，则事件对象的状态将保持已发信号状态。</span><span class="sxs-lookup"><span data-stu-id="8e664-107">If no threads are waiting, the event object's state remains signaled.</span></span> <span data-ttu-id="8e664-108"><xref:System.Threading.AutoResetEvent> 对应于 Win32 `CreateEvent` 调用，同时为 `bManualReset` 参数指定 `false`。</span><span class="sxs-lookup"><span data-stu-id="8e664-108"><xref:System.Threading.AutoResetEvent> corresponds to a Win32 `CreateEvent` call, specifying `false` for the `bManualReset` argument.</span></span>  
  
 <span data-ttu-id="8e664-109">有关使用 <xref:System.Threading.AutoResetEvent> 的示例，请参阅 <xref:System.Threading.Monitor>。</span><span class="sxs-lookup"><span data-stu-id="8e664-109">For an example that uses <xref:System.Threading.AutoResetEvent>, see <xref:System.Threading.Monitor>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e664-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e664-110">See Also</span></span>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="8e664-111">EventWaitHandle、AutoResetEvent、CountdownEvent、ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="8e664-111">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 [<span data-ttu-id="8e664-112">线程处理</span><span class="sxs-lookup"><span data-stu-id="8e664-112">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="8e664-113">线程处理对象和功能</span><span class="sxs-lookup"><span data-stu-id="8e664-113">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 [<span data-ttu-id="8e664-114">等待句柄</span><span class="sxs-lookup"><span data-stu-id="8e664-114">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)
