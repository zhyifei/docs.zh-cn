---
title: "使用 AsyncCallback 委托和状态对象"
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
- asynchronous programming, delegates
- AsyncCallback delegate, samples
- asynchronous programming, state objects
- IAsyncResult interface, samples
ms.assetid: e3e5475d-c5e9-43f0-928e-d18df8ca1f1d
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e8793a78289e9b58407038f41cc9d403ff9f9940
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="using-an-asynccallback-delegate-and-state-object"></a>使用 AsyncCallback 委托和状态对象
当你使用<xref:System.AsyncCallback>委托的一个单独的线程中的异步操作对结果进行处理，则可以使用的状态对象，两个回调之间传递信息以及如何检索最终结果。 本主题通过扩展中的示例演示这种做法[使用 AsyncCallback 委托结束异步操作](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何使用中的异步方法<xref:System.Net.Dns>类检索指定用户的计算机的域名系统 (DNS) 信息。 此示例定义并使用`HostRequest`类来存储状态信息。 A`HostRequest`获取用户输入的每个计算机名创建对象。 此对象传递给<xref:System.Net.Dns.BeginGetHostByName%2A>方法。 `ProcessDnsInformation`每次请求完成后调用方法。 `HostRequest`对象使用检索<xref:System.IAsyncResult.AsyncState%2A>属性。 `ProcessDnsInformation`方法使用`HostRequest`要存储对象<xref:System.Net.IPHostEntry>该请求返回的或<xref:System.Net.Sockets.SocketException>引发的请求。 应用程序完成后的所有请求，循环访问`HostRequest`对象，并显示的 DNS 信息或<xref:System.Net.Sockets.SocketException>错误消息。  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## <a name="see-also"></a>另请参阅  
 [基于事件的异步模式 (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [基于事件的异步模式概述](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [使用 AsyncCallback 委托停止异步操作](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)
