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
# <a name="manualresetevent-and-manualreseteventslim"></a>ManualResetEvent 和 ManualResetEventSlim
<xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>类表示一个本地等待句柄事件，必须手动重置后处于有信号状态。 此类表示其基本类的一种特殊情况<xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>。 有关手动重置的用法和功能，请参阅 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) 概念文档。  
  
 A<xref:System.Threading.ManualResetEvent>对象仍保留终止状态，直到其<xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType>调用方法。 在对象状态为已收到信号时，可以释放任意数量正在等待的线程，或是在收到信号后等待事件的线程。 <xref:System.Threading.ManualResetEvent>对应于 Win32`CreateEvent`调用时，指定`true`为`bManualReset`自变量。  
  
 在[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]，你可以使用<xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>类更好的性能和事件不能跨越进程边界时等待时间预计很短。 <xref:System.Threading.ManualResetEventSlim>使用繁忙旋转很短的时间，等待事件变为终止状态时。 等待时间较短时，旋转的开销相对于使用等待句柄来进行等待的开销会少很多。 但是，如果事件不会变得终止在特定时间段内，<xref:System.Threading.ManualResetEventSlim>转为常规事件句柄等待。  
  
## <a name="see-also"></a>另请参阅  
 [线程处理](../../../docs/standard/threading/index.md)  
 [线程处理对象和功能](../../../docs/standard/threading/threading-objects-and-features.md)  
 [等待句柄](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 [SpinWait](../../../docs/standard/threading/spinwait.md)  
 [Semaphore 和 SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
