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
# <a name="how-to-cancel-a-parallelfor-or-foreach-loop"></a><span data-ttu-id="be55d-102">如何：取消 Parallel.For 或 ForEach Loop</span><span class="sxs-lookup"><span data-stu-id="be55d-102">How to: Cancel a Parallel.For or ForEach Loop</span></span>
<span data-ttu-id="be55d-103"><xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> 和 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> 方法支持通过使用取消令牌进行取消。</span><span class="sxs-lookup"><span data-stu-id="be55d-103">The <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> methods support cancellation through the use of cancellation tokens.</span></span> <span data-ttu-id="be55d-104">若要详细了解取消的大致信息，请参阅[取消](../../../docs/standard/threading/cancellation-in-managed-threads.md)。</span><span class="sxs-lookup"><span data-stu-id="be55d-104">For more information about cancellation in general, see [Cancellation](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span></span> <span data-ttu-id="be55d-105">在并行循环中，将 <xref:System.Threading.CancellationToken> 提供给 <xref:System.Threading.Tasks.ParallelOptions> 参数中的方法，再将并行调用封闭到 try-catch 块中。</span><span class="sxs-lookup"><span data-stu-id="be55d-105">In a parallel loop, you supply the <xref:System.Threading.CancellationToken> to the method in the <xref:System.Threading.Tasks.ParallelOptions> parameter and then enclose the parallel call in a try-catch block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be55d-106">示例</span><span class="sxs-lookup"><span data-stu-id="be55d-106">Example</span></span>  
 <span data-ttu-id="be55d-107">下面的示例展示了如何取消调用 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="be55d-107">The following example shows how to cancel a call to <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="be55d-108">可以采用相同的方法来取消调用 <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="be55d-108">You can apply the same approach to a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> call.</span></span>  
  
 [!code-csharp[TPL_Parallel#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_cancel.cs#29)]
 [!code-vb[TPL_Parallel#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/cancelloop.vb#29)]  
  
 <span data-ttu-id="be55d-109">如果发送取消信号的令牌与<xref:System.Threading.Tasks.ParallelOptions> 实例中指定的令牌相同，并行循环会在取消时抛出一个 <xref:System.OperationCanceledException>。</span><span class="sxs-lookup"><span data-stu-id="be55d-109">If the token that signals the cancellation is the same token that is specified in the <xref:System.Threading.Tasks.ParallelOptions> instance, then the parallel loop will throw a single <xref:System.OperationCanceledException> on cancellation.</span></span> <span data-ttu-id="be55d-110">如果导致取消发生的是其他一些令牌，循环会抛出带 <xref:System.OperationCanceledException> 的 <xref:System.AggregateException> 作为 InnerException。</span><span class="sxs-lookup"><span data-stu-id="be55d-110">If some other token causes cancellation, the loop will throw an <xref:System.AggregateException> with an <xref:System.OperationCanceledException> as an InnerException.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be55d-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="be55d-111">See Also</span></span>  
 [<span data-ttu-id="be55d-112">数据并行</span><span class="sxs-lookup"><span data-stu-id="be55d-112">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [<span data-ttu-id="be55d-113">PLINQ 和 TPL 中的 Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="be55d-113">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
