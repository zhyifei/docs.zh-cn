---
title: "如何：使用 Parallel.Invoke 来执行并行操作"
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
- task parallelism in .NET
- parallel programming, task parallelism
ms.assetid: 6b3ecd79-dec9-4ce1-abf4-62e5392a59c6
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 942ba120fa5273f84ac3d0a51e276223de5f5484
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a><span data-ttu-id="21b5a-102">如何：使用 Parallel.Invoke 来执行并行操作</span><span class="sxs-lookup"><span data-stu-id="21b5a-102">How to: Use Parallel.Invoke to Execute Parallel Operations</span></span>
<span data-ttu-id="21b5a-103">此示例演示如何通过使用任务并行库中的 <xref:System.Threading.Tasks.Parallel.Invoke%2A> 并行操作。</span><span class="sxs-lookup"><span data-stu-id="21b5a-103">This example shows how to parallelize operations by using <xref:System.Threading.Tasks.Parallel.Invoke%2A> in the Task Parallel Library.</span></span> <span data-ttu-id="21b5a-104">共享的数据源上执行三个操作。</span><span class="sxs-lookup"><span data-stu-id="21b5a-104">Three operations are performed on a shared data source.</span></span> <span data-ttu-id="21b5a-105">因为操作均不修改源，所以可以直接的方式并行执行。</span><span class="sxs-lookup"><span data-stu-id="21b5a-105">Because none of the operations modifies the source, they can be executed in parallel in a straightforward manner.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="21b5a-106">本文档使用 lambda 表达式在 TPL 中定义委托。</span><span class="sxs-lookup"><span data-stu-id="21b5a-106">This documentation uses lambda expressions to define delegates in TPL.</span></span> <span data-ttu-id="21b5a-107">如果不熟悉 C# 或 Visual Basic 中的 lambda 表达式，请参阅 [PLINQ 和 TPL 中的 Lambda 表达式](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)。</span><span class="sxs-lookup"><span data-stu-id="21b5a-107">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="21b5a-108">示例</span><span class="sxs-lookup"><span data-stu-id="21b5a-108">Example</span></span>  
 [!code-csharp[TPL_Parallel#06](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallelinvoke.cs#06)]
 [!code-vb[TPL_Parallel#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/parallelinvoke.vb#06)]  
  
 <span data-ttu-id="21b5a-109">请注意，借助 <xref:System.Threading.Tasks.Parallel.Invoke%2A>，你只需表达想同时运行的操作，运行时会处理所有线程计划详细信息（包括自动缩放至主计算机上的内核数）。</span><span class="sxs-lookup"><span data-stu-id="21b5a-109">Note that with <xref:System.Threading.Tasks.Parallel.Invoke%2A>, you simply express which actions you want to run concurrently, and the runtime handles all thread scheduling details, including scaling automatically to the number of cores on the host computer.</span></span>  
  
 <span data-ttu-id="21b5a-110">此示例并行操作，而非数据。</span><span class="sxs-lookup"><span data-stu-id="21b5a-110">This example parallelizes the operations, not the data.</span></span> <span data-ttu-id="21b5a-111">此外，可使用 PLINQ 并行 LINQ 查询，并按顺序运行查询。</span><span class="sxs-lookup"><span data-stu-id="21b5a-111">As an alternate approach, you can parallelize the LINQ queries by using PLINQ and run the queries sequentially.</span></span> <span data-ttu-id="21b5a-112">或者，可使用 PLINQ 并行数据。</span><span class="sxs-lookup"><span data-stu-id="21b5a-112">Alternatively, you could parallelize the data by using PLINQ.</span></span> <span data-ttu-id="21b5a-113">另一个选项是并行查询和任务。</span><span class="sxs-lookup"><span data-stu-id="21b5a-113">Another option is to parallelize both the queries and the tasks.</span></span> <span data-ttu-id="21b5a-114">尽管生成的开销在处理器相对较少的主机计算机上可能会降低性能，但在处理器较多的计算机上可进行更好的缩放。</span><span class="sxs-lookup"><span data-stu-id="21b5a-114">Although the resulting overhead might degrade performance on host computers with relatively few processors, it would scale much better on computers with many processors.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="21b5a-115">编译代码</span><span class="sxs-lookup"><span data-stu-id="21b5a-115">Compiling the Code</span></span>  
  
-   <span data-ttu-id="21b5a-116">将完整示例复制和粘贴到 Microsoft Visual Studio 2010 项目，并按 F5 键。</span><span class="sxs-lookup"><span data-stu-id="21b5a-116">Copy and paste the entire example into a Microsoft Visual Studio 2010 project and press F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21b5a-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="21b5a-117">See Also</span></span>  
 [<span data-ttu-id="21b5a-118">并行编程</span><span class="sxs-lookup"><span data-stu-id="21b5a-118">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 [<span data-ttu-id="21b5a-119">如何：取消任务及其子级</span><span class="sxs-lookup"><span data-stu-id="21b5a-119">How to: Cancel a Task and Its Children</span></span>](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md)  
 [<span data-ttu-id="21b5a-120">并行 LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="21b5a-120">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
