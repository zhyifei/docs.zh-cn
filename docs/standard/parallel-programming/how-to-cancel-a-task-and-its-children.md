---
title: "如何：取消任务及其子级"
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
helpviewer_keywords: tasks, how to cancel
ms.assetid: 08574301-8331-4719-ad50-9cf7f6ff3048
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 374068694a3aa9724905964717dc5e77c09fc0ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-cancel-a-task-and-its-children"></a>如何：取消任务及其子级
这些示例演示如何执行以下任务：  
  
1.  创建并启动可取消任务。  
  
2.  （可选） 你的用户委托和任务实例，请传递一个取消标记。  
  
3.  请注意并响应用户委托中的取消请求。  
  
4.  （可选） 请注意，在调用线程的任务已取消。  
  
 调用线程不会强制结束任务;它仅发出信号已请求取消操作。 如果任务已在运行，负责注意请求并做出相应响应的用户委托。 如果在任务运行前请求取消，然后永远不会执行的用户委托和任务对象转换为 Canceled 状态。  
  
## <a name="example"></a>示例  
 此示例演示如何终止<xref:System.Threading.Tasks.Task>及其子级以响应取消请求。 还会演示，当用户委托通过引发 <xref:System.Threading.Tasks.TaskCanceledException> 终止时，调用线程可以选择使用 <xref:System.Threading.Tasks.Task.Wait%2A> 方法或 <xref:System.Threading.Tasks.Task.WaitAll%2A> 方法来等待任务完成。 在这种情况下，必须使用 `try/catch` 块来处理调用线程上的异常。  
  
 [!code-csharp[TPL_Cancellation#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/cancel1.cs#04)]
 [!code-vb[TPL_Cancellation#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/cancel1.vb#04)]  
  
 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>与基于取消模型完全集成类<xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType>和<xref:System.Threading.CancellationToken?displayProperty=nameWithType>类型。 有关详细信息，请参阅[托管线程中的取消](../../../docs/standard/threading/cancellation-in-managed-threads.md)和[任务取消](../../../docs/standard/parallel-programming/task-cancellation.md)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType>  
 <xref:System.Threading.CancellationToken?displayProperty=nameWithType>  
 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>  
 <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>  
 [基于任务的异步编程](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)  
 [附加和分离的子任务](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md)  
 [PLINQ 和 TPL 中的 Lambda 表达式](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
