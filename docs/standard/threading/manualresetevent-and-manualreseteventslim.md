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
# <a name="manualresetevent-and-manualreseteventslim"></a>ManualResetEvent 和 ManualResetEventSlim
<xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> 类表示必须在收到信号后手动重置的本地等待句柄事件。 此类表示其基类 <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> 的特例。 有关手动重置的用法和功能，请参阅 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) 概念文档。  
  
 在 <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> 方法获得调用前，<xref:System.Threading.ManualResetEvent> 对象会一直收到信号。 在对象状态为已收到信号时，可以释放任意数量正在等待的线程，或是在收到信号后等待事件的线程。
  
 在 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 中，如果应缩短等待时间，且事件不会跨越进程边界，可以使用 <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> 类，以提升性能。 等待事件收到信号期间，<xref:System.Threading.ManualResetEventSlim> 会短暂使用忙碌旋转。 等待时间较短时，旋转的开销相对于使用等待句柄来进行等待的开销会少很多。 不过，如果在特定时间段内事件没有收到信号，<xref:System.Threading.ManualResetEventSlim> 会求助于常规的事件句柄等待。  
  
## <a name="see-also"></a>请参阅

- [线程处理](../../../docs/standard/threading/index.md)  
- [线程处理对象和功能](../../../docs/standard/threading/threading-objects-and-features.md)  
- [等待句柄](https://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
- [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
- [SpinWait](../../../docs/standard/threading/spinwait.md)  
- [Semaphore 和 SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
