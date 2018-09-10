---
title: 如何：衡量 PLINQ 查询性能
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to measure performance
ms.assetid: 491ba43b-2c10-473d-9aab-e2cb96446711
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd9e3a0ead62450e87225212f4fc6ecec6ec9489
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44211627"
---
# <a name="how-to-measure-plinq-query-performance"></a><span data-ttu-id="eb942-102">如何：衡量 PLINQ 查询性能</span><span class="sxs-lookup"><span data-stu-id="eb942-102">How to: Measure PLINQ Query Performance</span></span>
<span data-ttu-id="eb942-103">此示例展示了如何使用 <xref:System.Diagnostics.Stopwatch> 类度量 PLINQ 查询的执行时间。</span><span class="sxs-lookup"><span data-stu-id="eb942-103">This example shows how use the <xref:System.Diagnostics.Stopwatch> class to measure the time it takes for a PLINQ query to execute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb942-104">示例</span><span class="sxs-lookup"><span data-stu-id="eb942-104">Example</span></span>  
 <span data-ttu-id="eb942-105">此示例使用空 `foreach` 循环（Visual Basic 中为 `For Each`）来衡量查询执行所用的时间。</span><span class="sxs-lookup"><span data-stu-id="eb942-105">This example uses an empty `foreach` loop (`For Each` in Visual Basic) to measure the time it takes for the query to execute.</span></span> <span data-ttu-id="eb942-106">在实际代码中，循环通常会包含其他处理步骤，这会增加查询总执行时间。</span><span class="sxs-lookup"><span data-stu-id="eb942-106">In real-world code, the loop typically contains additional processing steps that add to the total query execution time.</span></span> <span data-ttu-id="eb942-107">请注意，秒表会恰好在循环开始之前启动，因为此时查询开始执行。</span><span class="sxs-lookup"><span data-stu-id="eb942-107">Notice that the stopwatch is not started until just before the loop, because that is when the query execution begins.</span></span> <span data-ttu-id="eb942-108">如果需要更精细的度量，可以使用 `ElapsedTicks` 属性，而不是 `ElapsedMilliseconds`。</span><span class="sxs-lookup"><span data-stu-id="eb942-108">If you require more fine-grained measurement, you can use the `ElapsedTicks` property instead of `ElapsedMilliseconds`.</span></span>  
  
 [!code-csharp[PLINQ#19](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/measure2.cs#19)]
 [!code-vb[PLINQ#19](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/measure2.vb#19)]  
  
 <span data-ttu-id="eb942-109">试验查询实现时，总执行时间是有用的指标，但它并不总是能说明一切。</span><span class="sxs-lookup"><span data-stu-id="eb942-109">The total execution time is a useful metric when you are experimenting with query implementations, but it does not always tell the whole story.</span></span> <span data-ttu-id="eb942-110">为了更深入全面地了解查询线程相互之间以及查询线程和其他运行进程之前的交互，请使用并发可视化工具。</span><span class="sxs-lookup"><span data-stu-id="eb942-110">To get a deeper and richer view of the interaction of the query threads with one another and with other running processes, use the Concurrency Visualizer.</span></span> <span data-ttu-id="eb942-111">有关详细信息，请参阅[并发可视化工具](/visualstudio/profiling/concurrency-visualizer)。</span><span class="sxs-lookup"><span data-stu-id="eb942-111">For more information, see [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb942-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="eb942-112">See also</span></span>

- [<span data-ttu-id="eb942-113">并行 LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="eb942-113">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
