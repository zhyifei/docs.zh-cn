---
title: CountdownEvent
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
helpviewer_keywords: synchronization primitives, CountdownEvent
ms.assetid: eec3812a-e20f-4ecd-bfef-6921d508b708
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9f953f6477abf1f4e0d6aaf79e67005172ff1144
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="countdownevent"></a>CountdownEvent
<xref:System.Threading.CountdownEvent?displayProperty=nameWithType>是一个后，将取消其正在等待的线程的同步基元发出信号一定次数。 <xref:System.Threading.CountdownEvent>专为在其中你本来要使用的方案<xref:System.Threading.ManualResetEvent>或<xref:System.Threading.ManualResetEventSlim>和手动发出事件信号之前递减的变量。 例如，在分叉/联接方案中，你可以只创建<xref:System.Threading.CountdownEvent>，它具有一个信号计数为 5，且然后开始五个的工作项，而在线程池和具有每个工作项调用<xref:System.Threading.CountdownEvent.Signal%2A>完成时。 每次调用<xref:System.Threading.CountdownEvent.Signal%2A>信号计数 1。 在主线程调用<xref:System.Threading.CountdownEvent.Wait%2A>将阻止，直到信号计数为零。  
  
> [!NOTE]
>  对于不需要与旧的.NET Framework 同步 Api 结合使用进行交互的代码，请考虑使用<xref:System.Threading.Tasks.Task?displayProperty=nameWithType>对象或<xref:System.Threading.Tasks.Parallel.Invoke%2A>一种更简单的表示分叉联接并行的方法。  
  
 <xref:System.Threading.CountdownEvent>具有这些附加功能：  
  
-   可以通过使用取消标记取消等待操作。  
  
-   在创建实例之后，可以递增其信号计数。  
  
-   实例可以重用后<xref:System.Threading.CountdownEvent.Wait%2A>已返回通过调用<xref:System.Threading.CountdownEvent.Reset%2A>方法。  
  
-   实例公开<xref:System.Threading.WaitHandle>与其他.NET Framework 同步 Api 结合使用的集成如<xref:System.Threading.WaitHandle.WaitAll%2A>。  
  
## <a name="basic-usage"></a>基本用法  
 下面的示例演示如何使用<xref:System.Threading.CountdownEvent>与<xref:System.Threading.ThreadPool>工作项。  
  
 [!code-csharp[CDS_CountdownEvent#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#01)]
 [!code-vb[CDS_CountdownEvent#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/module1.vb#01)]  
  
## <a name="countdownevent-with-cancellation"></a>CountdownEvent 的取消  
 下面的示例演示如何在取消的等待操作<xref:System.Threading.CountdownEvent>使用取消标记。 基本模式遵循统一取消情况，在中引入模型[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]。 有关详细信息，请参阅[托管线程中的取消](../../../docs/standard/threading/cancellation-in-managed-threads.md)。  
  
 [!code-csharp[CDS_CountdownEvent#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#02)]
 [!code-vb[CDS_CountdownEvent#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/canceleventwait.vb#02)]  
  
 请注意，等待操作不会取消向其发出信号的线程。 通常情况下，取消应用于逻辑运算，且其中可以包括有关事件，以及所有工作项同步等待的等待。 在此示例中，每个工作项传递的相同的取消标记的副本，以便它可以响应取消请求。  
  
## <a name="see-also"></a>另请参阅  
 [EventWaitHandle、AutoResetEvent、CountdownEvent、ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)
