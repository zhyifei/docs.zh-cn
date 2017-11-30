---
title: "使用 AsyncCallback 委托结束异步操作"
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
- ending asynchronous operations
- asynchronous programming, ending operations
- AsyncCallback delegate
- stopping asynchronous operations
ms.assetid: 9d97206c-8917-406c-8961-7d0909d84eeb
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bbe170588776daa97fec4c736d4b1bdd871de518
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="using-an-asynccallback-delegate-to-end-an-asynchronous-operation"></a>使用 AsyncCallback 委托结束异步操作
应用程序可以完成其他工作的同时等待异步操作的结果不应阻止等待操作完成。 使用以下选项之一可继续在等待异步操作以完成时执行的说明：  
  
-   使用<xref:System.AsyncCallback>委托的一个单独的线程中的异步操作对结果进行处理。 本主题中演示了这种方法。  
  
-   使用<xref:System.IAsyncResult.IsCompleted%2A>属性<xref:System.IAsyncResult>异步操作返回**开始** *OperationName*方法来确定是否已完成该操作。 有关演示此方法的示例，请参阅[轮询异步操作的状态](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md)。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何使用中的异步方法<xref:System.Net.Dns>类检索指定用户的计算机的域名系统 (DNS) 信息。 此示例将创建<xref:System.AsyncCallback>委托，它引用`ProcessDnsInformation`方法。 为每个异步请求的 DNS 信息一次调用此方法。  
  
 请注意，用户指定主机传递给<xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.Object>参数。 有关演示如何定义和使用更复杂的状态对象的示例，请参阅[使用 AsyncCallback 委托和状态对象](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)。  
  
 [!code-csharp[AsyncDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateNoStateObject.cs#4)]
 [!code-vb[AsyncDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateNoState.vb#4)]  
  
## <a name="see-also"></a>另请参阅  
 [基于事件的异步模式 (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [基于事件的异步模式概述](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [使用 IAsyncResult 调用异步方法](../../../docs/standard/asynchronous-programming-patterns/calling-asynchronous-methods-using-iasyncresult.md)  
 [使用 AsyncCallback 委托和状态对象](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)
