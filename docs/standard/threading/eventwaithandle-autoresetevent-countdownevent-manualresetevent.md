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
ms.openlocfilehash: f818ecf52ae1179d6d32d0b76cea3cc2a8f36ea8
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43416407"
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a>EventWaitHandle、AutoResetEvent、CountdownEvent、ManualResetEvent
事件等待句柄允许线程通过相互发送信号和等待信号来同步活动。 这些同步事件基于 Win32 等待句柄，可分为两种类型：收到信号时自动重置的事件和手动重置的事件。  
  
 事件等待句柄适用于 <xref:System.Threading.Monitor> 类支持的许多同步方案。 事件等待句柄通常比 <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> 和 <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> 方法更易于使用，可方便用户更好地控制信号。 命名事件等待句柄也可用于跨应用程序域和进程同步活动，而监视器是本地的应用程序域。  
  
## <a name="in-this-section"></a>本节内容  
 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md)  
 <xref:System.Threading.EventWaitHandle> 类可表示自动或手动重置事件，以及本地事件或命名系统事件。  
  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 <xref:System.Threading.AutoResetEvent> 类派生自 <xref:System.Threading.EventWaitHandle>，表示自动重置的本地事件。  
  
 [ManualResetEvent 和 ManualResetEventSlim](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)  
 <xref:System.Threading.ManualResetEvent> 类派生自 <xref:System.Threading.EventWaitHandle>，表示必须手动重置的本地事件。 <xref:System.Threading.ManualResetEventSlim> 类是可用于同一进程内多个事件的轻型快速版本。  
  
 [CountdownEvent](../../../docs/standard/threading/countdownevent.md)  
 <xref:System.Threading.CountdownEvent> 类可以在使用等待句柄的代码中轻松实现分支/联接并行度模式。  
  
## <a name="related-sections"></a>相关章节  
 [等待句柄](https://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 <xref:System.Threading.WaitHandle> 类是 <xref:System.Threading.EventWaitHandle>、<xref:System.Threading.Semaphore> 和 <xref:System.Threading.Mutex> 类的基类。 它包含静态方法（如 <xref:System.Threading.WaitHandle.SignalAndWait%2A> 和 <xref:System.Threading.WaitHandle.WaitAll%2A>），这些方法在处理所有类型的等待句柄时非常有用。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 [线程处理对象和功能](../../../docs/standard/threading/threading-objects-and-features.md)  
 [托管线程处理基本知识](../../../docs/standard/threading/managed-threading-basics.md)
