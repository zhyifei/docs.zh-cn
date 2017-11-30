---
title: AutoResetEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], AutoResetEvent class
- AutoResetEvent class
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 69d16e8c6491b4c66ab5a5452762e73172ebbb77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="autoresetevent"></a>AutoResetEvent
<xref:System.Threading.AutoResetEvent>类表示在终止后释放单个正在等待的线程时自动重置本地等待句柄事件。 此类表示其基本类的一种特殊情况<xref:System.Threading.EventWaitHandle>。 有关自动重置事件的用法和功能，请参阅 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) 概念文档。  
  
 <xref:System.Threading.AutoResetEvent>对象被自动重置为非终止系统在发布单个正在等待的线程之后。 如果没有线程在等待，则事件对象的状态将保持已发信号状态。 <xref:System.Threading.AutoResetEvent>对应于 Win32`CreateEvent`调用时，指定`false`为`bManualReset`自变量。  
  
 有关示例，使用<xref:System.Threading.AutoResetEvent>，请参阅[监视器](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [EventWaitHandle、AutoResetEvent、CountdownEvent、ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 [线程处理](../../../docs/standard/threading/index.md)  
 [线程处理对象和功能](../../../docs/standard/threading/threading-objects-and-features.md)  
 [等待句柄](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)
