---
title: "如何：在 PLINQ 中指定执行模式"
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
helpviewer_keywords: PLINQ queries, how to use execution mode
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 745ceae9832582c7b66a56075d128f9cf1c8ff69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-execution-mode-in-plinq"></a><span data-ttu-id="16a73-102">如何：在 PLINQ 中指定执行模式</span><span class="sxs-lookup"><span data-stu-id="16a73-102">How to: Specify the Execution Mode in PLINQ</span></span>
<span data-ttu-id="16a73-103">此示例演示如何强制 PLINQ 跳过其默认试探法并并行执行的查询而不考虑查询的形状。</span><span class="sxs-lookup"><span data-stu-id="16a73-103">This example shows how to force PLINQ to bypass its default heuristics and parallelize a query regardless of the query's shape.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="16a73-104">本示例旨在演示用法，运行速度可能不如等效的顺序 LINQ to Objects 查询快。</span><span class="sxs-lookup"><span data-stu-id="16a73-104">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="16a73-105">有关加速的详细信息，请参阅[了解 PLINQ 中的加速](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)。</span><span class="sxs-lookup"><span data-stu-id="16a73-105">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="16a73-106">示例</span><span class="sxs-lookup"><span data-stu-id="16a73-106">Example</span></span>  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 <span data-ttu-id="16a73-107">PLINQ 旨在利用并行化的机会。</span><span class="sxs-lookup"><span data-stu-id="16a73-107">PLINQ is designed to exploit opportunities for parallelization.</span></span> <span data-ttu-id="16a73-108">但是，并非所有查询都受益于并行执行。</span><span class="sxs-lookup"><span data-stu-id="16a73-108">However, not all queries benefit from parallel execution.</span></span> <span data-ttu-id="16a73-109">例如，当查询包含很少执行工作的单个用户委托，该查询通常将更快地按顺序运行。</span><span class="sxs-lookup"><span data-stu-id="16a73-109">For example, when a query contains a single user delegate that does very little work, the query will usually run faster sequentially.</span></span> <span data-ttu-id="16a73-110">这是因为启用并行化执行所涉及的开销是比速度提高获取开销更大。</span><span class="sxs-lookup"><span data-stu-id="16a73-110">This is because the overhead involved in enabling parallelizing execution is more expensive than the speedup that is obtained.</span></span> <span data-ttu-id="16a73-111">因此，PLINQ 不自动并行化的每个查询。</span><span class="sxs-lookup"><span data-stu-id="16a73-111">Therefore, PLINQ does not automatically parallelize every query.</span></span> <span data-ttu-id="16a73-112">它首先检查查询和包含它的各种运算符的形状。</span><span class="sxs-lookup"><span data-stu-id="16a73-112">It first examines the shape of the query and the various operators that comprise it.</span></span> <span data-ttu-id="16a73-113">基于此分析，PLINQ 中的默认执行模式可能决定按顺序执行部分或所有查询。</span><span class="sxs-lookup"><span data-stu-id="16a73-113">Based on this analysis, PLINQ in the default execution mode may decide to execute some or all of the query sequentially.</span></span> <span data-ttu-id="16a73-114">但是，在某些情况下你可能知道更多有关您的查询比 PLINQ 能够从其分析确定。</span><span class="sxs-lookup"><span data-stu-id="16a73-114">However, in some cases you may know more about your query than PLINQ is able to determine from its analysis.</span></span> <span data-ttu-id="16a73-115">例如，你可能知道委托是代价很高，并查询将一定受益于并行化。</span><span class="sxs-lookup"><span data-stu-id="16a73-115">For example, you may know that a delegate is very expensive, and that the query will definitely benefit from parallelization.</span></span> <span data-ttu-id="16a73-116">在这种情况下，你可以使用<xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A>方法并指定<xref:System.Linq.ParallelExecutionMode.ForceParallelism>值，以指示 PLINQ 为始终以并行运行查询。</span><span class="sxs-lookup"><span data-stu-id="16a73-116">In such cases, you can use the <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> method and specify the <xref:System.Linq.ParallelExecutionMode.ForceParallelism> value to instruct PLINQ to always run the query as parallel.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="16a73-117">编译代码</span><span class="sxs-lookup"><span data-stu-id="16a73-117">Compiling the Code</span></span>  
 <span data-ttu-id="16a73-118">到此代码剪切并粘贴[PLINQ 数据示例](../../../docs/standard/parallel-programming/plinq-data-sample.md)调用该方法从`Main`。</span><span class="sxs-lookup"><span data-stu-id="16a73-118">Cut and paste this code into the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) and call the method from `Main`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16a73-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16a73-119">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable.AsSequential%2A>  
 [<span data-ttu-id="16a73-120">并行 LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="16a73-120">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
