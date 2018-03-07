---
title: "如何：取消 Parallel.For 或 ForEach Loop"
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
- parallel foreach loop, how to cancel
- parallel for loops, how to cancel
ms.assetid: 9d19b591-ea95-4418-8ea7-b6266af9905b
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e3d2ba6776a46573599e581cbfdeb62d181b81e0
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-cancel-a-parallelfor-or-foreach-loop"></a>如何：取消 Parallel.For 或 ForEach Loop
<xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> 和 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> 方法支持通过使用取消令牌进行取消。 若要详细了解取消的大致信息，请参阅[取消](../../../docs/standard/threading/cancellation-in-managed-threads.md)。 在并行循环中，将 <xref:System.Threading.CancellationToken> 提供给 <xref:System.Threading.Tasks.ParallelOptions> 参数中的方法，再将并行调用封闭到 try-catch 块中。  
  
## <a name="example"></a>示例  
 下面的示例展示了如何取消调用 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>。 可以采用相同的方法来取消调用 <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>。  
  
 [!code-csharp[TPL_Parallel#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_cancel.cs#29)]
 [!code-vb[TPL_Parallel#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/cancelloop.vb#29)]  
  
 如果发送取消信号的令牌与<xref:System.Threading.Tasks.ParallelOptions> 实例中指定的令牌相同，并行循环会在取消时抛出一个 <xref:System.OperationCanceledException>。 如果导致取消发生的是其他一些令牌，循环会抛出带 <xref:System.OperationCanceledException> 的 <xref:System.AggregateException> 作为 InnerException。  
  
## <a name="see-also"></a>请参阅  
 [数据并行](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [PLINQ 和 TPL 中的 Lambda 表达式](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
