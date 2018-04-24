---
title: 并行 LINQ (PLINQ)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PLINQ, overview
ms.assetid: 3d4d0cd3-bde4-490b-99e7-f4e41be96455
caps.latest.revision: 17
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5c24f51401b1e493864409ddafe580cea7ac435e
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="parallel-linq-plinq"></a><span data-ttu-id="cfff8-102">并行 LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="cfff8-102">Parallel LINQ (PLINQ)</span></span>
<span data-ttu-id="cfff8-103">并行 LINQ (PLINQ) 是 LINQ to Objects 的并行实现。</span><span class="sxs-lookup"><span data-stu-id="cfff8-103">Parallel LINQ (PLINQ) is a parallel implementation of LINQ to Objects.</span></span> <span data-ttu-id="cfff8-104">PLINQ 将整套 LINQ 标准查询运算符实现为 <xref:System.Linq> 命名空间的扩展方法，并提供适用于并行操作的其他运算符。</span><span class="sxs-lookup"><span data-stu-id="cfff8-104">PLINQ implements the full set of LINQ standard query operators as extension methods for the <xref:System.Linq> namespace and has additional operators for parallel operations.</span></span> <span data-ttu-id="cfff8-105">PLINQ 将 LINQ 语法的简洁和可靠性与并行编程的强大功能结合在一起。</span><span class="sxs-lookup"><span data-stu-id="cfff8-105">PLINQ combines the simplicity and readability of LINQ syntax with the power of parallel programming.</span></span> <span data-ttu-id="cfff8-106">就像面向任务并行库的代码一样，PLINQ 查询会根据主计算机的能力按比例调整并发程度。</span><span class="sxs-lookup"><span data-stu-id="cfff8-106">Just like code that targets the Task Parallel Library, PLINQ queries scale in the degree of concurrency based on the capabilities of the host computer.</span></span>  
  
 <span data-ttu-id="cfff8-107">在许多情况下，PLINQ 可通过更有效地使用主计算机上的所有可用内核来显著提高 LINQ to Objects 查询的速度。</span><span class="sxs-lookup"><span data-stu-id="cfff8-107">In many scenarios, PLINQ can significantly increase the speed of LINQ to Objects queries by using all available cores on the host computer more efficiently.</span></span> <span data-ttu-id="cfff8-108">这一性能提升使桌面具备高性能计算能力。</span><span class="sxs-lookup"><span data-stu-id="cfff8-108">This increased performance brings high performance computing power onto the desktop.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cfff8-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="cfff8-109">In This Section</span></span>  
 [<span data-ttu-id="cfff8-110">PLINQ 介绍</span><span class="sxs-lookup"><span data-stu-id="cfff8-110">Introduction to PLINQ</span></span>](../../../docs/standard/parallel-programming/introduction-to-plinq.md)  
  
 [<span data-ttu-id="cfff8-111">了解 PLINQ 中的加速</span><span class="sxs-lookup"><span data-stu-id="cfff8-111">Understanding Speedup in PLINQ</span></span>](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)  
  
 [<span data-ttu-id="cfff8-112">PLINQ 中的顺序保留</span><span class="sxs-lookup"><span data-stu-id="cfff8-112">Order Preservation in PLINQ</span></span>](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md)  
  
 [<span data-ttu-id="cfff8-113">PLINQ 中的合并选项</span><span class="sxs-lookup"><span data-stu-id="cfff8-113">Merge Options in PLINQ</span></span>](../../../docs/standard/parallel-programming/merge-options-in-plinq.md)  
  
 [<span data-ttu-id="cfff8-114">如何：创建并执行简单的 PLINQ 查询</span><span class="sxs-lookup"><span data-stu-id="cfff8-114">How to: Create and Execute a Simple PLINQ Query</span></span>](../../../docs/standard/parallel-programming/how-to-create-and-execute-a-simple-plinq-query.md)  
  
 [<span data-ttu-id="cfff8-115">如何：在 PLINQ 查询中控制排序</span><span class="sxs-lookup"><span data-stu-id="cfff8-115">How to: Control Ordering in a PLINQ Query</span></span>](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md)  
  
 [<span data-ttu-id="cfff8-116">如何：合并并行和顺序 LINQ 查询</span><span class="sxs-lookup"><span data-stu-id="cfff8-116">How to: Combine Parallel and Sequential LINQ Queries</span></span>](../../../docs/standard/parallel-programming/how-to-combine-parallel-and-sequential-linq-queries.md)  
  
 [<span data-ttu-id="cfff8-117">如何：处理 PLINQ 查询中的异常</span><span class="sxs-lookup"><span data-stu-id="cfff8-117">How to: Handle Exceptions in a PLINQ Query</span></span>](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md)  
  
 [<span data-ttu-id="cfff8-118">如何：取消 PLINQ 查询</span><span class="sxs-lookup"><span data-stu-id="cfff8-118">How to: Cancel a PLINQ Query</span></span>](../../../docs/standard/parallel-programming/how-to-cancel-a-plinq-query.md)  
  
 [<span data-ttu-id="cfff8-119">如何：编写自定义 PLINQ 聚合函数</span><span class="sxs-lookup"><span data-stu-id="cfff8-119">How to: Write a Custom PLINQ Aggregate Function</span></span>](../../../docs/standard/parallel-programming/how-to-write-a-custom-plinq-aggregate-function.md)  
  
 [<span data-ttu-id="cfff8-120">如何：在 PLINQ 中指定执行模式</span><span class="sxs-lookup"><span data-stu-id="cfff8-120">How to: Specify the Execution Mode in PLINQ</span></span>](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md)  
  
 [<span data-ttu-id="cfff8-121">如何：在 PLINQ 中指定合并选项</span><span class="sxs-lookup"><span data-stu-id="cfff8-121">How to: Specify Merge Options in PLINQ</span></span>](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)  
  
 [<span data-ttu-id="cfff8-122">如何：使用 PLINQ 循环访问文件目录</span><span class="sxs-lookup"><span data-stu-id="cfff8-122">How to: Iterate File Directories with PLINQ</span></span>](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-plinq.md)  
  
 [<span data-ttu-id="cfff8-123">如何：衡量 PLINQ 查询性能</span><span class="sxs-lookup"><span data-stu-id="cfff8-123">How to: Measure PLINQ Query Performance</span></span>](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md)  
  
 [<span data-ttu-id="cfff8-124">PLINQ 数据示例</span><span class="sxs-lookup"><span data-stu-id="cfff8-124">PLINQ Data Sample</span></span>](../../../docs/standard/parallel-programming/plinq-data-sample.md)  
  
## <a name="see-also"></a><span data-ttu-id="cfff8-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="cfff8-125">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="cfff8-126">并行编程</span><span class="sxs-lookup"><span data-stu-id="cfff8-126">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 [<span data-ttu-id="cfff8-127">LINQ（语言集成查询）</span><span class="sxs-lookup"><span data-stu-id="cfff8-127">LINQ (Language-Integrated Query)</span></span>](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)
