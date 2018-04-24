---
title: 如何：加快小型循环体的速度
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to speed up
ms.assetid: c7a66677-cb59-4cbf-969a-d2e8fc61a6ce
caps.latest.revision: 18
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 856c2a60150cb7a376afb291e6806d7fc91f3d2b
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-speed-up-small-loop-bodies"></a><span data-ttu-id="f6649-102">如何：加快小型循环体的速度</span><span class="sxs-lookup"><span data-stu-id="f6649-102">How to: Speed Up Small Loop Bodies</span></span>
<span data-ttu-id="f6649-103">如果 <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> 循环的主体很小，它的执行速度可能慢于相当的顺序循环，如 C# 中的 [for](~/docs/csharp/language-reference/keywords/for.md) 循环和 Visual Basic 中的 [For](http://msdn.microsoft.com/library/c470a263-9b49-4308-8fd6-8592b84a7980) 循环。</span><span class="sxs-lookup"><span data-stu-id="f6649-103">When a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> loop has a small body, it might perform more slowly than the equivalent sequential loop, such as the [for](~/docs/csharp/language-reference/keywords/for.md) loop in C# and the [For](http://msdn.microsoft.com/library/c470a263-9b49-4308-8fd6-8592b84a7980) loop in Visual Basic.</span></span> <span data-ttu-id="f6649-104">性能下降是由数据分区中的开销和在每个循环迭代上调用委托的成本所引起的。</span><span class="sxs-lookup"><span data-stu-id="f6649-104">Slower performance is caused by the overhead involved in partitioning the data and the cost of invoking a delegate on each loop iteration.</span></span> <span data-ttu-id="f6649-105">若要解决这种情况下，<xref:System.Collections.Concurrent.Partitioner> 类提供了 <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> 方法，使你能够为委托主体提供一个顺序循环，以便每个分区仅调用一次委托，而不是每个迭代调用一次委托。</span><span class="sxs-lookup"><span data-stu-id="f6649-105">To address such scenarios, the <xref:System.Collections.Concurrent.Partitioner> class provides the <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> method, which enables you to provide a sequential loop for the delegate body, so that the delegate is invoked only once per partition, instead of once per iteration.</span></span> <span data-ttu-id="f6649-106">有关详细信息，请参阅 [PLINQ 和 TPL 的自定义分区程序](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)。</span><span class="sxs-lookup"><span data-stu-id="f6649-106">For more information, see [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6649-107">示例</span><span class="sxs-lookup"><span data-stu-id="f6649-107">Example</span></span>  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 <span data-ttu-id="f6649-108">在循环执行最少量的工作时，此示例中演示的方法很有用。</span><span class="sxs-lookup"><span data-stu-id="f6649-108">The approach demonstrated in this example is useful when the loop performs a minimal amount of work.</span></span> <span data-ttu-id="f6649-109">随着工作变得更占用计算资源，通过默认分区程序，使用 <xref:System.Threading.Tasks.Parallel.For%2A> 或 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 循环，很有可能会获得相同或更好的性能。</span><span class="sxs-lookup"><span data-stu-id="f6649-109">As the work becomes more computationally expensive, you will probably get the same or better performance by using a <xref:System.Threading.Tasks.Parallel.For%2A> or <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop with the default partitioner.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6649-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6649-110">See Also</span></span>  
 [<span data-ttu-id="f6649-111">数据并行</span><span class="sxs-lookup"><span data-stu-id="f6649-111">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [<span data-ttu-id="f6649-112">PLINQ 和 TPL 的自定义分区程序</span><span class="sxs-lookup"><span data-stu-id="f6649-112">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)  
 [<span data-ttu-id="f6649-113">迭代器</span><span class="sxs-lookup"><span data-stu-id="f6649-113">Iterators</span></span>](https://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)  
 [<span data-ttu-id="f6649-114">PLINQ 和 TPL 中的 Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="f6649-114">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
