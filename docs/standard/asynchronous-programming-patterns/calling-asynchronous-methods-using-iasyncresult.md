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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f943633f554433d30598f11e8611d3e837d94280
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64628833"
---
# <a name="calling-asynchronous-methods-using-iasyncresult"></a><span data-ttu-id="eee42-102">使用 IAsyncResult 调用异步方法</span><span class="sxs-lookup"><span data-stu-id="eee42-102">Calling Asynchronous Methods Using IAsyncResult</span></span>
<span data-ttu-id="eee42-103">.NET Framework 和第三方类库中的类型可以提供方法，以便应用能够继续执行，同时在除主应用线程外的线程中执行异步操作。</span><span class="sxs-lookup"><span data-stu-id="eee42-103">Types in the .NET Framework and third-party class libraries can provide methods that allow an application to continue executing while performing asynchronous operations in threads other than the main application thread.</span></span> <span data-ttu-id="eee42-104">下面各部分介绍并提供了代码示例，展示了可以调用使用 <xref:System.IAsyncResult> 设计模式的异步方法的不同方式。</span><span class="sxs-lookup"><span data-stu-id="eee42-104">The following sections describe and provide code examples that demonstrate the different ways you can call asynchronous methods that use the <xref:System.IAsyncResult> design pattern.</span></span>  
  
- <span data-ttu-id="eee42-105">[通过结束异步操作阻止应用执行](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md)。</span><span class="sxs-lookup"><span data-stu-id="eee42-105">[Blocking Application Execution by Ending an Async Operation](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).</span></span>  
  
- <span data-ttu-id="eee42-106">[使用 AsyncWaitHandle 阻止应用执行](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md)。</span><span class="sxs-lookup"><span data-stu-id="eee42-106">[Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span></span>  
  
- <span data-ttu-id="eee42-107">[轮询异步操作状态](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md)。</span><span class="sxs-lookup"><span data-stu-id="eee42-107">[Polling for the Status of an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).</span></span>  
  
- <span data-ttu-id="eee42-108">[使用 AsyncCallback 委托结束异步操作](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)。</span><span class="sxs-lookup"><span data-stu-id="eee42-108">[Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eee42-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="eee42-109">See also</span></span>

- [<span data-ttu-id="eee42-110">基于事件的异步模式 (EAP)</span><span class="sxs-lookup"><span data-stu-id="eee42-110">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- [<span data-ttu-id="eee42-111">基于事件的异步模式概述</span><span class="sxs-lookup"><span data-stu-id="eee42-111">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
