---
title: EventWaitHandle、AutoResetEvent、CountdownEvent、ManualResetEvent
ms.date: 09/14/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- wait handles
- threading [.NET Framework], EventWaitHandle class
- event wait handles [.NET Framework]
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be9c858d7c76fdcc1b3e02485eb0b459f4e7555c
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48583147"
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a>EventWaitHandle、AutoResetEvent、CountdownEvent、ManualResetEvent

事件等待句柄允许线程通过相互发送信号和等待信号来同步活动。 这些同步事件基于操作系统等待句柄，可分为两种类型：收到信号时自动重置的事件和手动重置的事件。  
  
事件等待句柄适用于 <xref:System.Threading.Monitor> 类支持的许多同步方案。 事件等待句柄通常比 <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> 和 <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> 方法更易于使用，可方便用户更好地控制信号。 命名事件等待句柄也可用于跨应用程序域和进程同步活动，而监视器是本地的应用程序域。  
  
## <a name="in-this-section"></a>本节内容

 [EventWaitHandle](eventwaithandle.md)  
 <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> 类可表示自动或手动重置事件，以及本地事件或命名系统事件。  
  
 [AutoResetEvent](autoresetevent.md)  
 <xref:System.Threading.AutoResetEvent?displayProperty=nameWithType> 类派生自 <xref:System.Threading.EventWaitHandle>，表示自动重置的本地事件。  
  
 [ManualResetEvent 和 ManualResetEventSlim](manualresetevent-and-manualreseteventslim.md)  
 <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> 类派生自 <xref:System.Threading.EventWaitHandle>，表示必须手动重置的本地事件。 <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> 类是可用于同一进程内多个事件的轻型快速版本。  
  
 [CountdownEvent](countdownevent.md)  
 <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> 类可以在使用等待句柄的代码中轻松实现分支/联接并行度模式。  

## <a name="see-also"></a>请参阅

- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.Threading.Barrier?displayProperty=nameWithType>
- [线程处理对象和功能](threading-objects-and-features.md)
- [托管线程处理基本知识](managed-threading-basics.md)
