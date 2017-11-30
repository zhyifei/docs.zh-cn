---
title: "如何：合并并行和顺序 LINQ 查询"
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
helpviewer_keywords: parallel queries, combine parallel and sequential
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4da91ff535059b181baa637164a854cd75d06334
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a><span data-ttu-id="2b001-102">如何：合并并行和顺序 LINQ 查询</span><span class="sxs-lookup"><span data-stu-id="2b001-102">How to: Combine Parallel and Sequential LINQ Queries</span></span>
<span data-ttu-id="2b001-103">此示例演示如何使用<xref:System.Linq.ParallelEnumerable.AsSequential%2A>方法来指示 PLINQ 查询中的所有后续运算符按顺序处理。</span><span class="sxs-lookup"><span data-stu-id="2b001-103">This example shows how to use the <xref:System.Linq.ParallelEnumerable.AsSequential%2A> method to instruct PLINQ to process all subsequent operators in the query sequentially.</span></span> <span data-ttu-id="2b001-104">尽管顺序处理是通常比并行速度慢，但有时很必要生成正确的结果。</span><span class="sxs-lookup"><span data-stu-id="2b001-104">Although sequential processing is generally slower than parallel, sometimes it is necessary to produce correct results.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="2b001-105">本示例旨在演示用法，运行速度可能不如等效的顺序 LINQ to Objects 查询快。</span><span class="sxs-lookup"><span data-stu-id="2b001-105">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="2b001-106">有关加速的详细信息，请参阅[了解 PLINQ 中的加速](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)。</span><span class="sxs-lookup"><span data-stu-id="2b001-106">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b001-107">示例</span><span class="sxs-lookup"><span data-stu-id="2b001-107">Example</span></span>  
 <span data-ttu-id="2b001-108">下面的示例演示一种情况，在其中<xref:System.Linq.ParallelEnumerable.AsSequential%2A>是必需的即到保留在查询的前一个子句中已建立的排序。</span><span class="sxs-lookup"><span data-stu-id="2b001-108">The following example shows one scenario in which <xref:System.Linq.ParallelEnumerable.AsSequential%2A> is required, namely to preserve the ordering that was established in a previous clause of the query.</span></span>  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2b001-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="2b001-109">Compiling the Code</span></span>  
 <span data-ttu-id="2b001-110">若要编译并运行此代码，将其粘贴到[PLINQ 数据示例](../../../docs/standard/parallel-programming/plinq-data-sample.md)项目中，添加行，以调用方法中的，从`Main`，并按 F5。</span><span class="sxs-lookup"><span data-stu-id="2b001-110">To compile and run this code, paste it into the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project, add a line to call the method from `Main`, and press F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b001-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b001-111">See Also</span></span>  
 [<span data-ttu-id="2b001-112">并行 LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="2b001-112">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
