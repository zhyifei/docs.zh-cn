---
title: "轮询异步操作的状态"
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
- asynchronous programming, status polling
- polling asynchronous operation status
- status information [.NET Framework], asynchronous operations
ms.assetid: b541af31-dacb-4e20-8847-1b1ff7c35363
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1f7f74a8b38c06f6a042d55c0def76ddfc5da77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="polling-for-the-status-of-an-asynchronous-operation"></a>轮询异步操作的状态
应用程序可以完成其他工作的同时等待异步操作的结果不应阻止等待操作完成。 使用以下选项之一可继续在等待异步操作以完成时执行的说明：  
  
-   使用<xref:System.IAsyncResult.IsCompleted%2A>属性<xref:System.IAsyncResult>异步操作返回**开始** *OperationName*方法来确定是否已完成该操作。 此方法被称为轮询，并在本主题中所示。  
  
-   使用<xref:System.AsyncCallback>委托的一个单独的线程中的异步操作对结果进行处理。 有关演示此方法的示例，请参阅[使用 AsyncCallback 委托结束异步操作](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何使用中的异步方法<xref:System.Net.Dns>类检索指定用户的计算机的域名系统信息。 此示例将启动异步操作，然后输出句点 ("。") 在控制台完成该操作之前。 请注意， **null** (**执行任何操作**在 Visual Basic 中) 为传递<xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.AsyncCallback>和<xref:System.Object>参数因为这些自变量并不需要使用此方法时。  
  
 [!code-csharp[AsyncDesignPattern#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_Poll.cs#3)]
 [!code-vb[AsyncDesignPattern#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_Poll.vb#3)]  
  
## <a name="see-also"></a>另请参阅  
 [基于事件的异步模式 (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [基于事件的异步模式概述](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
