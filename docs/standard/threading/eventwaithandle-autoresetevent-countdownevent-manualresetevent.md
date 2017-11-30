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
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a>EventWaitHandle、AutoResetEvent、CountdownEvent、ManualResetEvent
事件等待句柄允许线程通过相互发送信号和等待信号来同步活动。 这些同步事件基于 Win32 等待句柄，可分为两种类型：收到信号时自动重置的事件和手动重置的事件。  
  
 事件等待句柄可在很多相同的同步方案作为<xref:System.Threading.Monitor>类。 事件等待句柄是通常比使用起来更为简便<xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType>和<xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType>方法，并且它们提供了更好地控制信号。 命名事件等待句柄也可用于跨应用程序域和进程同步活动，而监视器是本地的应用程序域。  
  
## <a name="in-this-section"></a>本节内容  
 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md)  
 <xref:System.Threading.EventWaitHandle>类可以表示自动或手动重置事件以及本地事件，或已命名的系统事件。  
  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 <xref:System.Threading.AutoResetEvent>类派生自<xref:System.Threading.EventWaitHandle>，表示自动重置的本地事件。  
  
 [ManualResetEvent 和 ManualResetEventSlim](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)  
 <xref:System.Threading.ManualResetEvent>类派生自<xref:System.Threading.EventWaitHandle>，表示必须手动重置的本地事件。 <xref:System.Threading.ManualResetEventSlim>类是可以用于相同的进程内的事件的轻量、 更快版本。  
  
 [CountdownEvent](../../../docs/standard/threading/countdownevent.md)  
 <xref:System.Threading.CountdownEvent>类提供了一种简化的方法，以在代码中使用等待句柄实现派生/联结并行模式。  
  
## <a name="related-sections"></a>相关章节  
 [等待句柄](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 <xref:System.Threading.WaitHandle>类是适用于基<xref:System.Threading.EventWaitHandle>， <xref:System.Threading.Semaphore>，和<xref:System.Threading.Mutex>类。 它包含静态方法，例如<xref:System.Threading.WaitHandle.SignalAndWait%2A>和<xref:System.Threading.WaitHandle.WaitAll%2A>，当处理所有类型的等待句柄时非常有用。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 [线程处理对象和功能](../../../docs/standard/threading/threading-objects-and-features.md)  
 [托管线程处理基本知识](../../../docs/standard/threading/managed-threading-basics.md)
