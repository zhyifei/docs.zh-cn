---
title: "如何：解除嵌套任务的包装"
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
helpviewer_keywords: tasks, how to unwrap nested tasks
ms.assetid: a0769dd2-0f6d-48ca-8418-a9d39de7f450
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2da3de912abb693c4342e1ede02f273348e4b571
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-unwrap-a-nested-task"></a><span data-ttu-id="3899d-102">如何：解除嵌套任务的包装</span><span class="sxs-lookup"><span data-stu-id="3899d-102">How to: Unwrap a Nested Task</span></span>
<span data-ttu-id="3899d-103">你可以返回的任务从方法返回，然后等待或继续从该任务，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="3899d-103">You can return a task from a method, and then wait on or continue from that task, as shown in the following example:</span></span>  
  
 [!code-csharp[TPL_Unwrap#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#01)]
 [!code-vb[TPL_Unwrap#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#01)]  
  
 <span data-ttu-id="3899d-104">在前面的示例中，<xref:System.Threading.Tasks.Task%601.Result%2A>属性属于类型`string`(`String`在 Visual Basic 中)。</span><span class="sxs-lookup"><span data-stu-id="3899d-104">In the previous example, the <xref:System.Threading.Tasks.Task%601.Result%2A> property is of type `string` (`String` in Visual Basic).</span></span>  
  
 <span data-ttu-id="3899d-105">但是，在某些情况下，你可能想要创建另一个任务中的任务，然后返回嵌套的任务。</span><span class="sxs-lookup"><span data-stu-id="3899d-105">However, in some scenarios, you might want to create a task within another task, and then return the nested task.</span></span> <span data-ttu-id="3899d-106">在这种情况下，`TResult`的封闭任务本身就是一项任务。</span><span class="sxs-lookup"><span data-stu-id="3899d-106">In this case, the `TResult` of the enclosing task is itself a task.</span></span> <span data-ttu-id="3899d-107">在以下示例中，结果属性是`Task<Task<string>>`在 C# 或`Task(Of Task(Of String))`在 Visual Basic 中。</span><span class="sxs-lookup"><span data-stu-id="3899d-107">In the following example, the Result property is a `Task<Task<string>>` in C# or `Task(Of Task(Of String))` in Visual Basic.</span></span>  
  
 [!code-csharp[TPL_Unwrap#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#02)]
 [!code-vb[TPL_Unwrap#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#02)]  
  
 <span data-ttu-id="3899d-108">但也可以编写代码来解除外部的任务的包装和检索原始任务并将其<xref:System.Threading.Tasks.Task%601.Result%2A>属性，此类代码是不容易编写，因为您必须处理的异常以及取消请求。</span><span class="sxs-lookup"><span data-stu-id="3899d-108">Although it is possible to write code to unwrap the outer task and retrieve the original task and its <xref:System.Threading.Tasks.Task%601.Result%2A> property, such code is not easy to write because you must handle exceptions and also cancellation requests.</span></span> <span data-ttu-id="3899d-109">在此情况下，我们建议你使用之一<xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>扩展方法，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="3899d-109">In this situation, we recommend that you use one of the <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> extension methods, as shown in the following example.</span></span>  
  
 [!code-csharp[TPL_UnWrap#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#03)]
 [!code-vb[TPL_UnWrap#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#03)]  
  
 <span data-ttu-id="3899d-110"><xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>方法可以用于转换任何`Task<Task>`或`Task<Task<TResult>>`(`Task(Of Task)`或`Task(Of Task(Of TResult))`在 Visual Basic 中) 到`Task`或`Task<TResult>`(`Task(Of TResult)`在 Visual Basic 中)。</span><span class="sxs-lookup"><span data-stu-id="3899d-110">The <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> methods can be used to transform any `Task<Task>` or `Task<Task<TResult>>` (`Task(Of Task)` or `Task(Of Task(Of TResult))` in Visual Basic) to a `Task` or `Task<TResult>` (`Task(Of TResult)` in Visual Basic).</span></span> <span data-ttu-id="3899d-111">新任务完全表示内部的嵌套的任务，并包括取消状态，以及所有异常。</span><span class="sxs-lookup"><span data-stu-id="3899d-111">The new task fully represents the inner nested task, and includes cancellation state and all exceptions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3899d-112">示例</span><span class="sxs-lookup"><span data-stu-id="3899d-112">Example</span></span>  
 <span data-ttu-id="3899d-113">下面的示例演示如何使用<xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>扩展方法。</span><span class="sxs-lookup"><span data-stu-id="3899d-113">The following example demonstrates how to use the <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> extension methods.</span></span>  
  
 [!code-csharp[TPL_UnWrap#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#04)]
 [!code-vb[TPL_UnWrap#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippet04.vb#04)]  
  
## <a name="see-also"></a><span data-ttu-id="3899d-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3899d-114">See Also</span></span>  
 <xref:System.Threading.Tasks.TaskExtensions?displayProperty=nameWithType>  
 [<span data-ttu-id="3899d-115">基于任务的异步编程</span><span class="sxs-lookup"><span data-stu-id="3899d-115">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
