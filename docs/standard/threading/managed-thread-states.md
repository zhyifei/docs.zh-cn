---
title: 托管线程状态
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], states
ms.assetid: 63890d5e-6025-4a7c-aaf0-d8bfd54b455f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a55409cd2c3bed2bc09db10622de1cceab934112
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2018
ms.locfileid: "47235278"
---
# <a name="managed-thread-states"></a>托管线程状态
<xref:System.Threading.Thread.ThreadState%2A?displayProperty=nameWithType> 属性提供了位掩码，以指明线程的当前状态。 一个线程始终处于 <xref:System.Threading.ThreadState> 枚举中的至少一个可能状态，并且可以同时处于多个状态。  
  
> [!IMPORTANT]
>  线程状态仅涉及几个调试方案。 因此，始终不应在代码中使用线程状态来同步线程活动。  
  
 创建托管线程时，该线程处于 <xref:System.Threading.ThreadState.Unstarted> 状态。 线程会一直保持 <xref:System.Threading.ThreadState.Unstarted> 状态，直到操作系统将其转移到已启动状态。 调用 <xref:System.Threading.Thread.Start%2A> 使操作系统知道该线程可启动；它不会更改线程的状态。  
  
 进入托管环境的非托管线程已处于已启动状态。 线程处于已启动状态后，可以执行许多操作来使线程更改状态。 下表列出了使状态发生更改的操作和相应的新状态  
  
|操作|所得到的新状态|  
|------------|-------------------------|  
|调用 <xref:System.Threading.Thread> 类的构造函数。|<xref:System.Threading.ThreadState.Unstarted>|  
|另一个线程调用 <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>。|<xref:System.Threading.ThreadState.Unstarted>|  
|线程响应 <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> 并开始运行。|<xref:System.Threading.ThreadState.Running>|  
|线程调用 <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>。|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|线程对另一个对象调用 <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType>。|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|线程对另一个线程调用 <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>。|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|另一个线程调用 <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>。|<xref:System.Threading.ThreadState.SuspendRequested>|  
|线程响应 <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> 请求。|<xref:System.Threading.ThreadState.Suspended>|  
|另一个线程调用 <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType>。|<xref:System.Threading.ThreadState.Running>|  
|另一个线程调用 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>。|<xref:System.Threading.ThreadState.AbortRequested>|  
|线程响应 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>。|<xref:System.Threading.ThreadState.Aborted>，然后 <xref:System.Threading.ThreadState.Stopped>|  
  
 由于 <xref:System.Threading.ThreadState.Running> 状态具有值 0，因此它不能执行位测试来发现此状态。 相反，可以使用以下测试（以伪代码表示）：  
  
```  
if ((state & (Unstarted | Stopped)) == 0)   // implies Running     
```  
  
 在任何给定时间，线程通常处于多个状态。 例如，如果线程在 <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> 调用中受阻止，并且另一个线程对相同的线程调用 <xref:System.Threading.Thread.Abort%2A>，那么线程就会同时处于 <xref:System.Threading.ThreadState.WaitSleepJoin> 和 <xref:System.Threading.ThreadState.AbortRequested> 状态。 在这种情况下，一旦该线程从对 <xref:System.Threading.Monitor.Wait%2A> 的调用返回或该线程中断，它就会收到 <xref:System.Threading.ThreadAbortException>。  
  
 线程由于调用 <xref:System.Threading.ThreadState.Unstarted> 而离开 <xref:System.Threading.Thread.Start%2A>状态后，它将无法再返回到 <xref:System.Threading.ThreadState.Unstarted> 状态。 同样，线程也永远无法离开 <xref:System.Threading.ThreadState.Stopped> 状态。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Threading.ThreadAbortException>  
- <xref:System.Threading.Thread>  
- <xref:System.Threading.ThreadState>  
- [线程处理](../../../docs/standard/threading/index.md)
