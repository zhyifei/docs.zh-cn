---
title: 如何：在 PLINQ 中指定执行模式
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to use execution mode
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
ms.openlocfilehash: f035dbcd5091d81a3cce3b9e9e683d836fe84bb7
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635814"
---
# <a name="how-to-specify-the-execution-mode-in-plinq"></a><span data-ttu-id="b3f2c-102">如何：在 PLINQ 中指定执行模式</span><span class="sxs-lookup"><span data-stu-id="b3f2c-102">How to: Specify the Execution Mode in PLINQ</span></span>

<span data-ttu-id="b3f2c-103">此示例展示了如何强制 PLINQ 规避默认启发，同时并行执行查询，无论查询的形状如何。</span><span class="sxs-lookup"><span data-stu-id="b3f2c-103">This example shows how to force PLINQ to bypass its default heuristics and parallelize a query regardless of the query's shape.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b3f2c-104">本示例旨在演示用法，运行速度可能不如等效的顺序 LINQ to Objects 查询快。</span><span class="sxs-lookup"><span data-stu-id="b3f2c-104">This example is intended to demonstrate usage and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="b3f2c-105">若要详细了解加速，请参阅[了解 PLINQ 中的加速](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)。</span><span class="sxs-lookup"><span data-stu-id="b3f2c-105">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3f2c-106">示例</span><span class="sxs-lookup"><span data-stu-id="b3f2c-106">Example</span></span>  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 <span data-ttu-id="b3f2c-107">PLINQ 旨在利用机会并行执行查询。</span><span class="sxs-lookup"><span data-stu-id="b3f2c-107">PLINQ is designed to exploit opportunities for parallelization.</span></span> <span data-ttu-id="b3f2c-108">不过，并非所有查询都受益于并行执行。</span><span class="sxs-lookup"><span data-stu-id="b3f2c-108">However, not all queries benefit from parallel execution.</span></span> <span data-ttu-id="b3f2c-109">例如，如果查询包含一个工作量较小的用户委托，顺序运行查询的速度通常更快。</span><span class="sxs-lookup"><span data-stu-id="b3f2c-109">For example, when a query contains a single user delegate that does little work, the query will usually run faster sequentially.</span></span> <span data-ttu-id="b3f2c-110">顺序执行速度更快是因为相较所实现的加速，启用并行执行所涉及的开销更加昂贵。</span><span class="sxs-lookup"><span data-stu-id="b3f2c-110">Sequential execution is faster because the overhead involved in enabling parallelizing execution is more expensive than the speedup that's obtained.</span></span> <span data-ttu-id="b3f2c-111">因此，PLINQ 并不自动并行执行每个查询。</span><span class="sxs-lookup"><span data-stu-id="b3f2c-111">Therefore, PLINQ does not automatically parallelize every query.</span></span> <span data-ttu-id="b3f2c-112">它先检查查询的形状和所包含的各种运算符。</span><span class="sxs-lookup"><span data-stu-id="b3f2c-112">It first examines the shape of the query and the various operators that comprise it.</span></span> <span data-ttu-id="b3f2c-113">根据此分析，默认执行模式下的 PLINQ 可能会决定顺序执行部分或全部查询。</span><span class="sxs-lookup"><span data-stu-id="b3f2c-113">Based on this analysis, PLINQ in the default execution mode may decide to execute some or all of the query sequentially.</span></span> <span data-ttu-id="b3f2c-114">不过，在某些情况下，你对查询更加了解，所做决定可能优于 PLINQ 根据分析所做的决定。</span><span class="sxs-lookup"><span data-stu-id="b3f2c-114">However, in some cases you may know more about your query than PLINQ is able to determine from its analysis.</span></span> <span data-ttu-id="b3f2c-115">例如，你可能知道委托比较昂贵，且查询一定会受益于并行执行。</span><span class="sxs-lookup"><span data-stu-id="b3f2c-115">For example, you may know that a delegate is expensive and that the query will definitely benefit from parallelization.</span></span> <span data-ttu-id="b3f2c-116">在这种情况下，可以使用 <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> 方法并指定 <xref:System.Linq.ParallelExecutionMode.ForceParallelism> 值，以指示 PLINQ 始终并行运行查询。</span><span class="sxs-lookup"><span data-stu-id="b3f2c-116">In such cases, you can use the <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> method and specify the <xref:System.Linq.ParallelExecutionMode.ForceParallelism> value to instruct PLINQ to always run the query as parallel.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b3f2c-117">编译代码</span><span class="sxs-lookup"><span data-stu-id="b3f2c-117">Compiling the Code</span></span>  
 <span data-ttu-id="b3f2c-118">将此代码剪切并粘贴到 [PLINQ 数据样本](../../../docs/standard/parallel-programming/plinq-data-sample.md)中，并通过 `Main` 调用方法。</span><span class="sxs-lookup"><span data-stu-id="b3f2c-118">Cut and paste this code into the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) and call the method from `Main`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3f2c-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="b3f2c-119">See also</span></span>

- <xref:System.Linq.ParallelEnumerable.AsSequential%2A>
- [<span data-ttu-id="b3f2c-120">并行 LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="b3f2c-120">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
