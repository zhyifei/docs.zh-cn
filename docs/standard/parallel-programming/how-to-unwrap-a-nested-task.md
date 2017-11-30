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
# <a name="how-to-unwrap-a-nested-task"></a>如何：解除嵌套任务的包装
你可以返回的任务从方法返回，然后等待或继续从该任务，如下面的示例中所示：  
  
 [!code-csharp[TPL_Unwrap#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#01)]
 [!code-vb[TPL_Unwrap#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#01)]  
  
 在前面的示例中，<xref:System.Threading.Tasks.Task%601.Result%2A>属性属于类型`string`(`String`在 Visual Basic 中)。  
  
 但是，在某些情况下，你可能想要创建另一个任务中的任务，然后返回嵌套的任务。 在这种情况下，`TResult`的封闭任务本身就是一项任务。 在以下示例中，结果属性是`Task<Task<string>>`在 C# 或`Task(Of Task(Of String))`在 Visual Basic 中。  
  
 [!code-csharp[TPL_Unwrap#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#02)]
 [!code-vb[TPL_Unwrap#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#02)]  
  
 但也可以编写代码来解除外部的任务的包装和检索原始任务并将其<xref:System.Threading.Tasks.Task%601.Result%2A>属性，此类代码是不容易编写，因为您必须处理的异常以及取消请求。 在此情况下，我们建议你使用之一<xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>扩展方法，如下面的示例中所示。  
  
 [!code-csharp[TPL_UnWrap#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#03)]
 [!code-vb[TPL_UnWrap#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#03)]  
  
 <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>方法可以用于转换任何`Task<Task>`或`Task<Task<TResult>>`(`Task(Of Task)`或`Task(Of Task(Of TResult))`在 Visual Basic 中) 到`Task`或`Task<TResult>`(`Task(Of TResult)`在 Visual Basic 中)。 新任务完全表示内部的嵌套的任务，并包括取消状态，以及所有异常。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用<xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>扩展方法。  
  
 [!code-csharp[TPL_UnWrap#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#04)]
 [!code-vb[TPL_UnWrap#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippet04.vb#04)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Threading.Tasks.TaskExtensions?displayProperty=nameWithType>  
 [基于任务的异步编程](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
