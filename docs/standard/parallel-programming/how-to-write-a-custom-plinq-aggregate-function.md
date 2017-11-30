---
title: "如何：编写自定义 PLINQ 聚合函数"
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
helpviewer_keywords: PLINQ queries, how to create aggregate function
ms.assetid: 5a70dd49-ab2a-4798-b551-196ee7042b1a
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8b098f21e29d0d59cd99ddbb64af6246d9953a3a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-a-custom-plinq-aggregate-function"></a><span data-ttu-id="4e094-102">如何：编写自定义 PLINQ 聚合函数</span><span class="sxs-lookup"><span data-stu-id="4e094-102">How to: Write a Custom PLINQ Aggregate Function</span></span>
<span data-ttu-id="4e094-103">此示例演示如何使用<xref:System.Linq.ParallelEnumerable.Aggregate%2A>方法将自定义聚合函数应用于源序列。</span><span class="sxs-lookup"><span data-stu-id="4e094-103">This example shows how to use the <xref:System.Linq.ParallelEnumerable.Aggregate%2A> method to apply a custom aggregation function to a source sequence.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="4e094-104">本示例旨在演示用法，运行速度可能不如等效的顺序 LINQ to Objects 查询快。</span><span class="sxs-lookup"><span data-stu-id="4e094-104">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="4e094-105">有关加速的详细信息，请参阅[了解 PLINQ 中的加速](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)。</span><span class="sxs-lookup"><span data-stu-id="4e094-105">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e094-106">示例</span><span class="sxs-lookup"><span data-stu-id="4e094-106">Example</span></span>  
 <span data-ttu-id="4e094-107">下面的示例计算整数的序列的标准偏差。</span><span class="sxs-lookup"><span data-stu-id="4e094-107">The following example calculates the standard deviation of a sequence of integers.</span></span>  
  
 [!code-csharp[PLINQ#31](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#31)]
 [!code-vb[PLINQ#31](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#31)]  
  
 <span data-ttu-id="4e094-108">此示例使用是唯一的 PLINQ 聚合的标准查询运算符的重载。</span><span class="sxs-lookup"><span data-stu-id="4e094-108">This example uses an overload of the Aggregate standard query operator that is unique to PLINQ.</span></span> <span data-ttu-id="4e094-109">此重载采用额外<xref:System.Func%603?displayProperty=nameWithType>作为第三个输入参数。</span><span class="sxs-lookup"><span data-stu-id="4e094-109">This overload takes an extra <xref:System.Func%603?displayProperty=nameWithType> as the third input parameter.</span></span> <span data-ttu-id="4e094-110">执行最终计算聚合结果之前，此委托将合并所有线程的结果。</span><span class="sxs-lookup"><span data-stu-id="4e094-110">This delegate combines the results from all threads before it performs the final calculation on the aggregated results.</span></span> <span data-ttu-id="4e094-111">在此示例中我们将添加在一起总和所有线程。</span><span class="sxs-lookup"><span data-stu-id="4e094-111">In this example we add together the sums from all the threads.</span></span>  
  
 <span data-ttu-id="4e094-112">请注意，当 lambda 表达式主体包含单个表达式，返回值的<xref:System.Func%602?displayProperty=nameWithType>委托是表达式的值。</span><span class="sxs-lookup"><span data-stu-id="4e094-112">Note that when a lambda expression body consists of a single expression, the return value of the <xref:System.Func%602?displayProperty=nameWithType> delegate is the value of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e094-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4e094-113">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="4e094-114">并行 LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="4e094-114">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
