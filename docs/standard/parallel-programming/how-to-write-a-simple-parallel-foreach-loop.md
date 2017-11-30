---
title: "如何：编写简单的 Parallel.ForEach 循环"
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
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 16d8cd3c3c01c2f9d83786e78f0eb1c45a38a49b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a><span data-ttu-id="57653-102">如何：编写简单的 Parallel.ForEach 循环</span><span class="sxs-lookup"><span data-stu-id="57653-102">How to: Write a Simple Parallel.ForEach Loop</span></span>
<span data-ttu-id="57653-103">此示例演示如何使用<xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>循环，以启用对任何数据并行<xref:System.Collections.IEnumerable?displayProperty=nameWithType>或<xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>数据源。</span><span class="sxs-lookup"><span data-stu-id="57653-103">This example shows how to use a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> loop to enable data parallelism over any <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> data source.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57653-104">本文档使用 lambda 表达式在 PLINQ 中定义委托。</span><span class="sxs-lookup"><span data-stu-id="57653-104">This documentation uses lambda expressions to define delegates in PLINQ.</span></span> <span data-ttu-id="57653-105">如果不熟悉 C# 或 Visual Basic 中的 lambda 表达式，请参阅 [PLINQ 和 TPL 中的 Lambda 表达式](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)。</span><span class="sxs-lookup"><span data-stu-id="57653-105">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="57653-106">示例</span><span class="sxs-lookup"><span data-stu-id="57653-106">Example</span></span>  
 [!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
 [!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]  
  
 <span data-ttu-id="57653-107">A<xref:System.Threading.Tasks.Parallel.ForEach%2A>循环的工作原理类似<xref:System.Threading.Tasks.Parallel.For%2A>循环。</span><span class="sxs-lookup"><span data-stu-id="57653-107">A <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop works like a <xref:System.Threading.Tasks.Parallel.For%2A> loop.</span></span> <span data-ttu-id="57653-108">对源集合进行分区，并基于系统环境的多个线程上计划工作。</span><span class="sxs-lookup"><span data-stu-id="57653-108">The source collection is partitioned and the work is scheduled on multiple threads based on the system environment.</span></span> <span data-ttu-id="57653-109">在系统上的处理器越多，越快，并行方法运行。</span><span class="sxs-lookup"><span data-stu-id="57653-109">The more processors on the system, the faster the parallel method runs.</span></span> <span data-ttu-id="57653-110">对于某些源集合，一个顺序循环可能更快，具体取决于源和正在执行的工作类型的大小。</span><span class="sxs-lookup"><span data-stu-id="57653-110">For some source collections, a sequential loop may be faster, depending on the size of the source, and the kind of work being performed.</span></span> <span data-ttu-id="57653-111">有关性能的详细信息，请参阅[数据并行和任务并行中的潜在缺陷](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)</span><span class="sxs-lookup"><span data-stu-id="57653-111">For more information about performance, see [Potential Pitfalls in Data and Task Parallelism](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)</span></span>  
  
 <span data-ttu-id="57653-112">有关并行循环的详细信息，请参阅[如何： 编写简单的 Parallel.For 循环](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md)。</span><span class="sxs-lookup"><span data-stu-id="57653-112">For more information about parallel loops, see [How to: Write a Simple Parallel.For Loop](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).</span></span>  
  
 <span data-ttu-id="57653-113">若要使用<xref:System.Threading.Tasks.Parallel.ForEach%2A>对于非泛型集合，你可以使用<xref:System.Linq.Enumerable.Cast%2A>扩展方法将集合转换为泛型集合，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="57653-113">To use <xref:System.Threading.Tasks.Parallel.ForEach%2A> with a non-generic collection, you can use the <xref:System.Linq.Enumerable.Cast%2A> extension method to convert the collection to a generic collection, as shown in the following example:</span></span>  
  
 [!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
 [!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]  
  
 <span data-ttu-id="57653-114">此外可以使用并行 LINQ (PLINQ) 来并行执行的处理<xref:System.Collections.Generic.IEnumerable%601>数据源。</span><span class="sxs-lookup"><span data-stu-id="57653-114">You can also use Parallel LINQ (PLINQ) to parallelize processing of <xref:System.Collections.Generic.IEnumerable%601> data sources.</span></span> <span data-ttu-id="57653-115">PLINQ，可使用声明性查询语法表示的循环行为。</span><span class="sxs-lookup"><span data-stu-id="57653-115">PLINQ enables you to use declarative query syntax to express the loop behavior.</span></span> <span data-ttu-id="57653-116">有关详细信息，请参阅[并行 LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)。</span><span class="sxs-lookup"><span data-stu-id="57653-116">For more information, see [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="57653-117">编译代码</span><span class="sxs-lookup"><span data-stu-id="57653-117">Compiling the Code</span></span>  
  
-   <span data-ttu-id="57653-118">复制并粘贴到此代码[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]2010年控制台应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="57653-118">Copy and paste this code into a [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 2010 Console Application project.</span></span>  
  
-   <span data-ttu-id="57653-119">添加对 System.Drawing.dll 的引用</span><span class="sxs-lookup"><span data-stu-id="57653-119">Add a reference to System.Drawing.dll</span></span>  
  
-   <span data-ttu-id="57653-120">按 F5</span><span class="sxs-lookup"><span data-stu-id="57653-120">Press F5</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57653-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57653-121">See Also</span></span>  
 [<span data-ttu-id="57653-122">数据并行</span><span class="sxs-lookup"><span data-stu-id="57653-122">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [<span data-ttu-id="57653-123">并行编程</span><span class="sxs-lookup"><span data-stu-id="57653-123">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 [<span data-ttu-id="57653-124">并行 LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="57653-124">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
