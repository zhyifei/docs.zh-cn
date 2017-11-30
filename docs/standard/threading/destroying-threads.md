---
title: "销毁线程"
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
- destroying threads
- threading [.NET Framework], destroying threads
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4a41dce5db707d0be49c283256de665d316e1a1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="destroying-threads"></a>销毁线程
<xref:System.Threading.Thread.Abort%2A>方法用于永久停止托管的线程。 当调用<xref:System.Threading.Thread.Abort%2A>，公共语言运行时会引发<xref:System.Threading.ThreadAbortException>目标线程，可以捕获此目标线程中。 有关详细信息，请参阅<xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>。  
  
> [!NOTE]
>  如果线程执行非托管代码时其<xref:System.Threading.Thread.Abort%2A>方法被调用时，运行时将其标记<xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>。 当线程返回给托管代码引发异常。  
  
 一旦线程被中止，它不能重新启动。  
  
 <xref:System.Threading.Thread.Abort%2A>方法不会导致立即中止的线程因为目标线程可以捕获<xref:System.Threading.ThreadAbortException>和执行任意数量的代码中`finally`块。 你可以调用<xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>如果你需要等待，直到线程已结束。 <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>是一个线程确实已停止执行后才返回值的阻塞调用或可选的超时间隔已过去。 中止的线程可以调用<xref:System.Threading.Thread.ResetAbort%2A>方法或执行中的不受限制的处理`finally`块中，因此如果不指定超时，则不保证在等待结束。  
  
 在调用等待的线程<xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>方法可以由其他线程调用中断<xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>。  
  
## <a name="handling-threadabortexception"></a>处理 ThreadAbortException  
 如果希望你的线程将中止，调用的结果作为<xref:System.Threading.Thread.Abort%2A>从你自己的代码或由于而卸载线程正在运行的应用程序域 (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType>使用<xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>终止线程)，你的线程必须处理<xref:System.Threading.ThreadAbortException>并执行中的任何最终处理`finally`子句，如下面的代码中所示。  
  
```vb  
Try  
    ' Code that is executing when the thread is aborted.  
Catch ex As ThreadAbortException  
    ' Clean-up code can go here.  
    ' If there is no Finally clause, ThreadAbortException is  
    ' re-thrown by the system at the end of the Catch clause.   
Finally  
    ' Clean-up code can go here.  
End Try  
' Do not put clean-up code here, because the exception   
' is rethrown at the end of the Finally clause.  
```  
  
```csharp  
try   
{  
    // Code that is executing when the thread is aborted.  
}   
catch (ThreadAbortException ex)   
{  
    // Clean-up code can go here.  
    // If there is no Finally clause, ThreadAbortException is  
    // re-thrown by the system at the end of the Catch clause.   
}  
// Do not put clean-up code here, because the exception   
// is rethrown at the end of the Finally clause.  
```  
  
 清理代码必须在`catch`子句或`finally`子句，因为<xref:System.Threading.ThreadAbortException>末尾的系统将被重新引发`finally`子句，或末尾`catch`子句如果没有任何`finally`子句。  
  
 你可以通过调用重新引发的异常阻止系统<xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType>方法。 但是，应执行你自己的代码导致此才<xref:System.Threading.ThreadAbortException>。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Threading.ThreadAbortException>  
 <xref:System.Threading.Thread>  
 [使用线程和线程处理](../../../docs/standard/threading/using-threads-and-threading.md)
