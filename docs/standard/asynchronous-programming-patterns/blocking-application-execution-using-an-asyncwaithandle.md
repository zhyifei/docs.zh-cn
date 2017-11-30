---
title: "使用 AsyncWaitHandle 阻止应用程序的执行"
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
- blocks, asynchronous operations
- ending asynchronous operations
- asynchronous programming, ending operations
- asynchronous programming, blocking applications
- stopping asynchronous operations
- blocking application execution
ms.assetid: 3e32daf2-8161-4e8f-addd-9fd9ff101b03
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2660b3cbf7e8ee43a22edbfb66a4262684983b87
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="blocking-application-execution-using-an-asyncwaithandle"></a>使用 AsyncWaitHandle 阻止应用程序的执行
操作完成之前，必须阻止的应用程序无法继续执行其他工作的同时等待异步操作的结果。 使用以下选项之一来阻止应用程序的主线程在等待异步操作以完成时：  
  
-   使用<xref:System.IAsyncResult.AsyncWaitHandle%2A>属性<xref:System.IAsyncResult>异步操作返回**开始** *OperationName*方法。 本主题中演示了这种方法。  
  
-   调用异步操作的**结束** *OperationName*方法。 有关演示此方法的示例，请参阅[通过结束异步操作来阻止应用程序执行](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md)。  
  
 使用一个或多个应用程序<xref:System.Threading.WaitHandle>对象进行阻止，直到异步操作已完成，通常会调用**开始** *OperationName*方法，执行可以完成任何工作而无需操作，和之前的异步操作的块的结果完成。 应用程序可以通过调用其中一种来阻止一个操作上<xref:System.Threading.WaitHandle.WaitOne%2A>方法使用<xref:System.IAsyncResult.AsyncWaitHandle%2A>。 若要阻止等待异步操作完成的一组时，存储关联<xref:System.IAsyncResult.AsyncWaitHandle%2A>中数组中，然后调用的对象<xref:System.Threading.WaitHandle.WaitAll%2A>方法。 若要阻止等待任一一套异步操作完成时，存储关联<xref:System.IAsyncResult.AsyncWaitHandle%2A>中数组中，然后调用的对象<xref:System.Threading.WaitHandle.WaitAny%2A>方法。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何使用 DNS 类中的异步方法来检索用户指定的计算机的域名系统信息。 示例演示了阻止使用<xref:System.Threading.WaitHandle>与异步操作关联。 请注意， `null` (`Nothing`在 Visual Basic 中) 为传递<xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback`和`stateObject`参数因为使用此方法时，这些并不需要。  
  
 [!code-csharp[AsyncDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlockWait.cs#2)]
 [!code-vb[AsyncDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlockWait.vb#2)]  
  
## <a name="see-also"></a>另请参阅  
 [基于事件的异步模式 (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [基于事件的异步模式概述](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
