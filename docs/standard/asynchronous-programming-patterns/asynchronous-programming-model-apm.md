---
title: "异步编程模型 (APM)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ending asynchronous operations
- starting asynchronous operations
- beginning asynchronous operations
- asynchronous programming, ending operations
- asynchronous programming
- stopping asynchronous operations
- asynchronous programming, beginning operations
ms.assetid: c9b3501e-6bc6-40f9-8efd-4b6d9e39ccf0
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 66553d18d46d94fb0febfff8460ac7764e9b62bb
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="asynchronous-programming-model-apm"></a>异步编程模型 (APM)
使用 <xref:System.IAsyncResult> 设计模式的异步操作实现为 BeginOperationName 和 EndOperationName 这两个方法，它们分别用于开始和结束异步操作 OperationName。 例如， <xref:System.IO.FileStream> 类提供 <xref:System.IO.FileStream.BeginRead%2A> 和 <xref:System.IO.FileStream.EndRead%2A> 方法来从文件异步读取字节。 这两个方法实现了 <xref:System.IO.FileStream.Read%2A> 方法的异步版本。  
  
> [!NOTE]
>  从 .NET Framework 4 开始，任务并行库为异步和并行编程提供了一种新模型。 有关详细信息，请参阅 [Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md) 和 [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)。  
  
 调用 BeginOperationName 后，应用可以继续对调用线程执行指令，同时异步操作在另一个线程上运行。 每次调用 BeginOperationName 时，应用还应调用 EndOperationName，以获取操作结果。  
  
## <a name="beginning-an-asynchronous-operation"></a>开始异步操作  
 BeginOperationName 方法开始异步操作 OperationName，并返回实现 <xref:System.IAsyncResult> 接口的对象。 <xref:System.IAsyncResult> 对象存储有关异步操作的信息。 下表显示有关异步操作的信息。  
  
|成员|描述|  
|------------|-----------------|  
|<xref:System.IAsyncResult.AsyncState%2A>|一个特定于应用程序的可选对象，其中包含有关异步操作的信息。|  
|<xref:System.IAsyncResult.AsyncWaitHandle%2A>|一个 <xref:System.Threading.WaitHandle> ，可用来在异步操作完成之前阻止应用程序执行。|  
|<xref:System.IAsyncResult.CompletedSynchronously%2A>|指示异步操作是否是在用于调用 BeginOperationName 的线程上完成，而不是在单独的 <xref:System.Threading.ThreadPool> 线程上完成的值。|  
|<xref:System.IAsyncResult.IsCompleted%2A>|一个值，指示异步操作是否已完成。|  
  
 BeginOperationName 方法需要使用方法同步版本签名中声明的所有参数（按值或按引用传递）。 BeginOperationName 方法签名中不包含任何输出参数。 另外，BeginOperationName 方法签名还包含其他两个参数。 第一个参数定义一个 <xref:System.AsyncCallback> 委托，此委托引用在异步操作完成时调用的方法。 如果调用方不希望在操作完成后调用方法，它可以指定 `null` （在 Visual Basic 中为`Nothing` ）。 第二个参数是一个用户定义的对象。 此对象可用来向异步操作完成时调用的方法传递应用程序特定的状态信息。 如果 BeginOperationName 方法需要使用其他操作专用参数（如用于存储从文件读取的字节的字节数组），<xref:System.AsyncCallback> 和应用状态对象是 BeginOperationName 方法签名中的最后两个参数。  
  
 BeginOperationName 立即返回对调用线程的控制。 如果 BeginOperationName 方法抛出异常，那么异常在异步操作开始前抛出。 如果 BeginOperationName 方法抛出异常，表明没有调用回调方法。  
  
## <a name="ending-an-asynchronous-operation"></a>结束异步操作  
 EndOperationName 方法用于结束异步操作 OperationName。 EndOperationName 方法与对应方法同步版本的返回值的类型相同，前者的返回值是异步操作专用。 例如， <xref:System.IO.FileStream.EndRead%2A> 方法返回从 <xref:System.IO.FileStream> 读取的字节数， <xref:System.Net.Dns.EndGetHostByName%2A> 方法返回包含有关主机的信息的 <xref:System.Net.IPHostEntry> 对象。 EndOperationName 方法需要使用方法同步版本签名中声明的所有输出参数或引用参数。 除了同步方法中的参数外，EndOperationName 方法还包括 <xref:System.IAsyncResult> 参数。 调用方必须传递对应 BeginOperationName 调用返回的实例。  
  
 如果调用 EndOperationName 时 <xref:System.IAsyncResult> 对象表示的异步操作尚未完成，EndOperationName 将调用线程一直阻止到异步操作完成。 异步操作抛出的异常是通过 EndOperationName 方法抛出。 多次使用同一 <xref:System.IAsyncResult> 调用 EndOperationName 方法造成的效应未经定义。 同样，使用相关 Begin 方法未返回的 <xref:System.IAsyncResult> 调用 EndOperationName 方法造成的效应也未经定义。  
  
> [!NOTE]
>  对于这两种未定义的情况，实施者应考虑引发 <xref:System.InvalidOperationException>。  
  
> [!NOTE]
>  此设计模式的实施者应通知调用方异步操作已通过以下步骤完成：将 <xref:System.IAsyncResult.IsCompleted%2A> 设置为 true，调用异步回调方法（如果已指定一个回调方法），然后发送 <xref:System.IAsyncResult.AsyncWaitHandle%2A>信号。  
  
 对于访问异步操作的结果，应用程序开发人员有若干种设计选择。 正确的选择取决于应用程序是否有可以在操作完成时执行的指令。 如果应用程序在接收到异步操作结果之前不能进行任何其他工作，则必须在获得这些结果之前先阻止该应用程序进行其他工作。 若要在异步操作完成之前阻止应用程序，可以使用下列方法之一：  
  
-   通过应用的主线程调用 EndOperationName，将应用执行一直阻止到操作完成。 有关展示了此方法的示例，请参阅[通过结束异步操作阻止应用执行](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md)。  
  
-   使用 <xref:System.IAsyncResult.AsyncWaitHandle%2A> 来阻止应用程序执行，直到一个或多个操作完成。 有关演示此方法的示例，请参阅 [Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md)。  
  
 在异步操作完成时不需要阻止的应用程序可使用下列方法之一：  
  
-   轮询操作完成状态，具体操作是定期检查 <xref:System.IAsyncResult.IsCompleted%2A> 属性，并在操作完成时调用 EndOperationName。 有关演示此方法的示例，请参阅 [Polling for the Status of an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md)。  
  
-   使用 <xref:System.AsyncCallback> 委托来指定要在操作完成时调用的方法。 有关演示此方法的示例，请参阅 [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)。  
  
## <a name="see-also"></a>请参阅  
 [基于事件的异步模式 (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [使用异步方式调用同步方法](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 [使用 AsyncCallback 委托和状态对象](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)
