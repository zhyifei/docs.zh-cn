---
title: "如何：从任务中返回值"
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
- tasks, how to return a value
ms.assetid: c4bc0f44-eba2-4e96-9e03-1cc787461e61
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 4497f7f9c6802a9b3d4edca66ceb4a894a59646a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-return-a-value-from-a-task"></a><span data-ttu-id="e2f92-102">如何：从任务中返回值</span><span class="sxs-lookup"><span data-stu-id="e2f92-102">How to: Return a Value from a Task</span></span>
<span data-ttu-id="e2f92-103">此示例演示如何使用 <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> 类型，以返回 <xref:System.Threading.Tasks.Task%601.Result%2A> 属性的值。</span><span class="sxs-lookup"><span data-stu-id="e2f92-103">This example shows how to use the <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> type to return a value from the <xref:System.Threading.Tasks.Task%601.Result%2A> property.</span></span> <span data-ttu-id="e2f92-104">它要求 C:\Users\Public\Pictures\Sample Pictures\ 目录存在，并且该目录包含文件。</span><span class="sxs-lookup"><span data-stu-id="e2f92-104">It requires that the C:\Users\Public\Pictures\Sample Pictures\ directory exists, and that it contains files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2f92-105">示例</span><span class="sxs-lookup"><span data-stu-id="e2f92-105">Example</span></span>  
 [!code-csharp[TPL#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/returnavalue10.cs#10)]
 [!code-vb[TPL#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/10_returnavalue.vb#10)]  
  
 <span data-ttu-id="e2f92-106"><xref:System.Threading.Tasks.Task%601.Result%2A> 属性将阻止调用线程，直到任务完成。</span><span class="sxs-lookup"><span data-stu-id="e2f92-106">The <xref:System.Threading.Tasks.Task%601.Result%2A> property blocks the calling thread until the task finishes.</span></span>  
  
 <span data-ttu-id="e2f92-107">若要了解如何将一个 <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> 的结果传递到延续任务，请参阅[使用延续任务链接任务](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md)。</span><span class="sxs-lookup"><span data-stu-id="e2f92-107">To see how to pass the result of one <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> to a continuation task, see [Chaining Tasks by Using Continuation Tasks](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2f92-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2f92-108">See Also</span></span>  
 [<span data-ttu-id="e2f92-109">基于任务的异步编程</span><span class="sxs-lookup"><span data-stu-id="e2f92-109">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)  
 [<span data-ttu-id="e2f92-110">PLINQ 和 TPL 中的 Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="e2f92-110">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
