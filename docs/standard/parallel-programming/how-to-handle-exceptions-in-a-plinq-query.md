---
title: "如何：处理 PLINQ 查询中的异常"
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
helpviewer_keywords: PLINQ queries, how to handle exceptions
ms.assetid: 8d56ff9b-a571-4d31-b41f-80c0b51b70a5
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 209e0c1bf89f231d03647ae4351279bfdb172e68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-handle-exceptions-in-a-plinq-query"></a><span data-ttu-id="eceb8-102">如何：处理 PLINQ 查询中的异常</span><span class="sxs-lookup"><span data-stu-id="eceb8-102">How to: Handle Exceptions in a PLINQ Query</span></span>
<span data-ttu-id="eceb8-103">本主题中的第一个示例演示如何处理<xref:System.AggregateException?displayProperty=nameWithType>，可能引发从 PLINQ 查询执行时。</span><span class="sxs-lookup"><span data-stu-id="eceb8-103">The first example in this topic shows how to handle the <xref:System.AggregateException?displayProperty=nameWithType> that can be thrown from a PLINQ query when it executes.</span></span> <span data-ttu-id="eceb8-104">第二个示例显示如何将 try-catch 块中的代理，而到会引发该异常尽可能地接近。</span><span class="sxs-lookup"><span data-stu-id="eceb8-104">The second example shows how to put try-catch blocks within delegates, as close as possible to where the exception will be thrown.</span></span> <span data-ttu-id="eceb8-105">在这种方式，你可以捕获它们就会立即发生，并且可能继续执行查询。</span><span class="sxs-lookup"><span data-stu-id="eceb8-105">In this way, you can catch them as soon as they occur and possibly continue query execution.</span></span> <span data-ttu-id="eceb8-106">如果允许异常向上冒泡回到联接线程，则查询也许可以在引发异常后继续处理一些项。</span><span class="sxs-lookup"><span data-stu-id="eceb8-106">When exceptions are allowed to bubble up back to the joining thread, then it is possible that a query may continue to process some items after the exception is raised.</span></span>  
  
 <span data-ttu-id="eceb8-107">在某些情况下 PLINQ 回退到顺序执行，并发生异常时，异常可能比较传播直接，因此不包装在<xref:System.AggregateException>。</span><span class="sxs-lookup"><span data-stu-id="eceb8-107">In some cases when PLINQ falls back to sequential execution, and an exception occurs, the exception may be propagated directly, and not wrapped in an <xref:System.AggregateException>.</span></span> <span data-ttu-id="eceb8-108">此外， <xref:System.Threading.ThreadAbortException>s 会始终直接传播。</span><span class="sxs-lookup"><span data-stu-id="eceb8-108">Also, <xref:System.Threading.ThreadAbortException>s are always propagated directly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eceb8-109">Visual Studio 启用"仅我的代码"后，将引发异常的行中断并显示一条显示"未处理异常由用户代码。"的错误消息</span><span class="sxs-lookup"><span data-stu-id="eceb8-109">When "Just My Code" is enabled, Visual Studio will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="eceb8-110">此错误是良性的。</span><span class="sxs-lookup"><span data-stu-id="eceb8-110">This error is benign.</span></span> <span data-ttu-id="eceb8-111">可以按 F5 继续运行，并请参阅下面示例中所示的异常处理行为。</span><span class="sxs-lookup"><span data-stu-id="eceb8-111">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="eceb8-112">若要阻止 Visual Studio 的第一个错误时中断，只需取消选中下的"仅我的代码"复选框**工具、 选项、 调试、 常规**。</span><span class="sxs-lookup"><span data-stu-id="eceb8-112">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
>   
>  <span data-ttu-id="eceb8-113">本示例旨在演示用法，运行速度可能不如等效的顺序 LINQ to Objects 查询快。</span><span class="sxs-lookup"><span data-stu-id="eceb8-113">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="eceb8-114">有关加速的详细信息，请参阅[了解 PLINQ 中的加速](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)。</span><span class="sxs-lookup"><span data-stu-id="eceb8-114">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eceb8-115">示例</span><span class="sxs-lookup"><span data-stu-id="eceb8-115">Example</span></span>  
 <span data-ttu-id="eceb8-116">此示例演示如何将在执行查询以捕获所有的代码周围 try catch 块<xref:System.AggregateException?displayProperty=nameWithType>引发的 s。</span><span class="sxs-lookup"><span data-stu-id="eceb8-116">This example shows how to put the try-catch blocks around the code that executes the query to catch any <xref:System.AggregateException?displayProperty=nameWithType>s that are thrown.</span></span>  
  
 [!code-csharp[PLINQ#41](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#41)]
 [!code-vb[PLINQ#41](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#41)]  
  
 <span data-ttu-id="eceb8-117">在此示例中，查询无法继续后，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="eceb8-117">In this example, the query cannot continue after the exception is thrown.</span></span> <span data-ttu-id="eceb8-118">应用程序代码捕获异常时，PLINQ 已查询已停止所有线程上。</span><span class="sxs-lookup"><span data-stu-id="eceb8-118">By the time your application code catches the exception, PLINQ has already stopped the query on all threads.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eceb8-119">示例</span><span class="sxs-lookup"><span data-stu-id="eceb8-119">Example</span></span>  
 <span data-ttu-id="eceb8-120">下面的示例演示如何将 try catch 块放在一个委托，以使其可以捕获异常并继续执行查询。</span><span class="sxs-lookup"><span data-stu-id="eceb8-120">The following example shows how to put a try-catch block in a delegate to make it possible to catch an exception and continue with the query execution.</span></span>  
  
 [!code-csharp[PLINQ#42](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#42)]
 [!code-vb[PLINQ#42](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#42)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="eceb8-121">编译代码</span><span class="sxs-lookup"><span data-stu-id="eceb8-121">Compiling the Code</span></span>  
  
-   <span data-ttu-id="eceb8-122">若要编译并运行这些示例，将它们复制到的 PLINQ 数据示例示例中，并从 Main 调用方法。</span><span class="sxs-lookup"><span data-stu-id="eceb8-122">To compile and run these examples, copy them into the PLINQ Data Sample example and call the method from Main.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="eceb8-123">可靠编程</span><span class="sxs-lookup"><span data-stu-id="eceb8-123">Robust Programming</span></span>  
 <span data-ttu-id="eceb8-124">除非你知道如何处理它，以便不会损坏你的程序的状态，则不要捕捉异常。</span><span class="sxs-lookup"><span data-stu-id="eceb8-124">Do not catch an exception unless you know how to handle it so that you do not corrupt the state of your program.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eceb8-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eceb8-125">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="eceb8-126">并行 LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="eceb8-126">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
