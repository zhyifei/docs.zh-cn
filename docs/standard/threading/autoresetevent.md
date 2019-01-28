---
title: AutoResetEvent
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], AutoResetEvent class
- AutoResetEvent class
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 70af739bdb90a70a1319354b4964c261e432912b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54729952"
---
# <a name="autoresetevent"></a>AutoResetEvent
<xref:System.Threading.AutoResetEvent> 类表示本地等待句柄事件，此事件在一个等待线程释放后收到信号时自动重置。 此类表示其基类 <xref:System.Threading.EventWaitHandle> 的特例。 有关自动重置事件的用法和功能，请参阅 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) 概念文档。  
  
 在一个等待线程已释放后，系统会自动将 <xref:System.Threading.AutoResetEvent> 对象重置为处于未收到信号状态。 如果没有线程在等待，则事件对象的状态将保持已发信号状态。
  
 有关使用 <xref:System.Threading.AutoResetEvent> 的示例，请参阅 <xref:System.Threading.Monitor>。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>
- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- [EventWaitHandle、AutoResetEvent、CountdownEvent、ManualResetEvent](eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)
- [线程处理对象和功能](threading-objects-and-features.md)
- [线程处理](index.md)
