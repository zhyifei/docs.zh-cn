---
title: "通过结束异步操作来阻止应用程序执行"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- blocks, asynchronous operations
- AsyncWaitHandle property
- asynchronous programming, blocking applications
- blocking application execution
ms.assetid: cc5e2834-a65b-4df8-b750-7bdb79997fee
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
dev_langs:
- csharp
- vb
ms.openlocfilehash: ccca6e1e4f6b5cdf098018b59426fb2262e2b346
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="blocking-application-execution-by-ending-an-async-operation"></a>通过结束异步操作来阻止应用程序执行
操作完成之前，必须阻止的应用程序无法继续执行其他工作的同时等待异步操作的结果。 使用以下选项之一来阻止应用程序的主线程在等待异步操作以完成时：  
  
-   调用异步操作**结束** *OperationName*方法。 本主题中演示了这种方法。  
  
-   使用<xref:System.IAsyncResult.AsyncWaitHandle%2A>属性<xref:System.IAsyncResult>异步操作返回**开始** *OperationName*方法。 有关演示此方法的示例，请参阅[使用 AsyncWaitHandle 阻止应用程序执行](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md)。  
  
 应用程序使用**结束** *OperationName*方法进行阻止，直到异步操作已完成，通常会调用**开始** *OperationName*方法，执行任何工作，也能在不操作的结果，然后调用**结束** *OperationName*。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何使用中的异步方法<xref:System.Net.Dns>类检索指定用户的计算机的域名系统信息。 请注意， `null` (`Nothing`在 Visual Basic 中) 为传递<xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback`和`stateObject`参数因为这些自变量并不需要使用此方法时。  
  
 [!code-csharp[AsyncDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlock.cs#1)]
 [!code-vb[AsyncDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlock.vb#1)]  
  
## <a name="see-also"></a>另请参阅  
 [基于事件的异步模式 (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [基于事件的异步模式概述](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
