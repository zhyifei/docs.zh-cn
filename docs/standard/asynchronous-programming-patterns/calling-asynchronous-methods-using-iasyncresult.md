---
title: 使用 IAsyncResult 调用异步方法
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- ending asynchronous operations
- waiting for asynchronous operations
- asynchronous method calling
- calling asynchronous methods
- asynchronous programming, calling asynchronous methods
- IAsyncResult interface, calling asynchronous methods
- stopping asynchronous operations
ms.assetid: 07fba116-045b-473c-a0b7-acdbeb49861f
ms.openlocfilehash: 2a9ce8bc2d2edd09ef79c060b9bb173d4d054d02
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121315"
---
# <a name="calling-asynchronous-methods-using-iasyncresult"></a>使用 IAsyncResult 调用异步方法
.NET Framework 和第三方类库中的类型可以提供方法，以便应用能够继续执行，同时在除主应用线程外的线程中执行异步操作。 下面各部分介绍并提供了代码示例，展示了可以调用使用 <xref:System.IAsyncResult> 设计模式的异步方法的不同方式。  
  
- [通过结束异步操作阻止应用执行](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md)。  
  
- [使用 AsyncWaitHandle 阻止应用执行](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md)。  
  
- [轮询异步操作状态](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md)。  
  
- [使用 AsyncCallback 委托结束异步操作](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)。  
  
## <a name="see-also"></a>请参阅

- [基于事件的异步模式 (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- [基于事件的异步模式概述](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
