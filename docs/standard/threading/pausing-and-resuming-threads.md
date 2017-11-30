---
title: "暂停和继续线程"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resuming threads
- threading [.NET Framework], pausing
- pausing threads
ms.assetid: 9fce4859-a19d-4506-b082-7dd0792688ca
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b146987d2491f044e1f5794eba17d02d8f5e478c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="pausing-and-resuming-threads"></a>暂停和继续线程
同步线程活动最常见的方法是阻止和释放线程，或者锁定对象或代码区域。 有关这些锁定和阻止机制的详细信息，请参阅[同步基元概述](../../../docs/standard/threading/overview-of-synchronization-primitives.md)。  
  
 也可使线程将自身置于睡眠状态。 当线程被阻止或处于休眠状态时，可以使用 <xref:System.Threading.ThreadInterruptedException> 使它们脱离等待状态。  
  
## <a name="the-threadsleep-method"></a>Thread.Sleep 方法  
 调用<xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>方法将使当前线程立即被阻塞的毫秒数或将传递给该方法的时间间隔数，并生成另一个线程到其时间片的剩余部分。 受阻时间过后，休眠线程继续执行。  
  
 一个线程不能调用另一线程上的 <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>。  <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>是始终将使当前线程进入睡眠状态的静态方法。  
  
 调用<xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>值为<xref:System.Threading.Timeout.Infinite?displayProperty=nameWithType>使线程进入睡眠状态之前调用的另一个线程将其中断<xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>方法上的休眠的线程，或通过调用终止之前其<xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>方法。  下面的示例阐释了这两种中断休眠线程的方法。  
  
 [!code-csharp[Conceptual.Threading.Resuming#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Threading.Resuming/cs/Sleep1.cs#1)]
 [!code-vb[Conceptual.Threading.Resuming#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Threading.Resuming/vb/Sleep1.vb#1)]  
  
## <a name="interrupting-threads"></a>中断线程  
 你可以通过调用中断正在等待的线程<xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>方法被阻塞的线程引发<xref:System.Threading.ThreadInterruptedException>，这将中断的阻止调用线程。 线程应该捕获 <xref:System.Threading.ThreadInterruptedException> 并执行任何适于继续工作的操作。 如果线程忽略该异常，则运行时捕获异常，并停止该线程。  
  
> [!NOTE]
>  如果在调用 <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> 时，未阻止目标线程，则线程在被阻止前将不会中断。 如果线程永远不被阻止，则它可在不被中断的情况下完成。  
  
 如果等待是托管的等待，则 <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> 和 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> 都会立即唤醒线程。 如果等待是非托管的等待 (例如，平台调用调用 Win32 [WaitForSingleObject](https://msdn.microsoft.com/library/windows/desktop/ms687032\(v=vs.85\).aspx)函数)，既不<xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>也不<xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>可能需要控制线程，直到它返回到或调入托管代码。 在托管代码中，该行为如下：  
  
-   <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> 将线程从其可能处于的任何等待中唤醒，并导致在目标线程中引发 <xref:System.Threading.ThreadInterruptedException>。  
  
-   <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>线程从它可能在中，并会导致任何等待中唤醒<xref:System.Threading.ThreadAbortException>线程上引发。 有关详细信息，请参阅[销毁线程](../../../docs/standard/threading/destroying-threads.md)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadInterruptedException>  
 <xref:System.Threading.ThreadAbortException>  
 [线程处理](../../../docs/standard/threading/index.md)  
 [使用线程和线程处理](../../../docs/standard/threading/using-threads-and-threading.md)  
 [同步基元概述](../../../docs/standard/threading/overview-of-synchronization-primitives.md)
