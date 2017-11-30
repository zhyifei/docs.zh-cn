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
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3f82c5758e02b4beebf035fe8f43f856447855a3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-cancel-a-parallelfor-or-foreach-loop"></a><span data-ttu-id="9861a-102">如何：取消 Parallel.For 或 ForEach Loop</span><span class="sxs-lookup"><span data-stu-id="9861a-102">How to: Cancel a Parallel.For or ForEach Loop</span></span>
<span data-ttu-id="9861a-103"><xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>和<xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>方法支持通过使用取消标记取消。</span><span class="sxs-lookup"><span data-stu-id="9861a-103">The <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> methods support cancellation through the use of cancellation tokens.</span></span> <span data-ttu-id="9861a-104">有关取消一般情况下，请参阅[取消](../../../docs/standard/threading/cancellation-in-managed-threads.md)。</span><span class="sxs-lookup"><span data-stu-id="9861a-104">For more information about cancellation in general, see [Cancellation](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span></span> <span data-ttu-id="9861a-105">在并行循环中，你提供<xref:System.Threading.CancellationToken>到中的方法<xref:System.Threading.Tasks.ParallelOptions>参数并在 try catch 块中加入然后并行调用。</span><span class="sxs-lookup"><span data-stu-id="9861a-105">In a parallel loop, you supply the <xref:System.Threading.CancellationToken> to the method in the <xref:System.Threading.Tasks.ParallelOptions> parameter and then enclose the parallel call in a try-catch block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9861a-106">示例</span><span class="sxs-lookup"><span data-stu-id="9861a-106">Example</span></span>  
 <span data-ttu-id="9861a-107">下面的示例演示如何取消调用<xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="9861a-107">The following example shows how to cancel a call to <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9861a-108">你可以将应用到相同的方法<xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>调用。</span><span class="sxs-lookup"><span data-stu-id="9861a-108">You can apply the same approach to a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> call.</span></span>  
  
 [!code-csharp[TPL_Parallel#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_cancel.cs#29)]
 [!code-vb[TPL_Parallel#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/cancelloop.vb#29)]  
  
 <span data-ttu-id="9861a-109">如果令牌发出取消信号的相同令牌中指定<xref:System.Threading.Tasks.ParallelOptions>实例，则并行循环将引发一个<xref:System.OperationCanceledException>上取消。</span><span class="sxs-lookup"><span data-stu-id="9861a-109">If the token that signals the cancellation is the same token that is specified in the <xref:System.Threading.Tasks.ParallelOptions> instance, then the parallel loop will throw a single <xref:System.OperationCanceledException> on cancellation.</span></span> <span data-ttu-id="9861a-110">如果某些其他令牌可导致取消，将引发循环<xref:System.AggregateException>与<xref:System.OperationCanceledException>作为内部异常。</span><span class="sxs-lookup"><span data-stu-id="9861a-110">If some other token causes cancellation, the loop will throw an <xref:System.AggregateException> with an <xref:System.OperationCanceledException> as an InnerException.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9861a-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9861a-111">See Also</span></span>  
 [<span data-ttu-id="9861a-112">数据并行</span><span class="sxs-lookup"><span data-stu-id="9861a-112">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [<span data-ttu-id="9861a-113">PLINQ 和 TPL 中的 Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="9861a-113">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
