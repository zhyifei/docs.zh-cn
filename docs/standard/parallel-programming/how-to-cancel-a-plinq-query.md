---
title: "如何：取消 PLINQ 查询"
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
- PLINQ queries, how to cancel
- cancellation, PLINQ
ms.assetid: 80b14640-edfa-4153-be1b-3e003d3e9c1a
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d8031758462df45c030b8b75a3507f1bfb44bfd0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-cancel-a-plinq-query"></a><span data-ttu-id="609df-102">如何：取消 PLINQ 查询</span><span class="sxs-lookup"><span data-stu-id="609df-102">How to: Cancel a PLINQ Query</span></span>
<span data-ttu-id="609df-103">下面的示例演示两种方法取消 PLINQ 查询。</span><span class="sxs-lookup"><span data-stu-id="609df-103">The following examples show two ways to cancel a PLINQ query.</span></span> <span data-ttu-id="609df-104">第一个示例演示如何取消查询主要组成数据遍历。</span><span class="sxs-lookup"><span data-stu-id="609df-104">The first example shows how to cancel a query that consists mostly of data traversal.</span></span> <span data-ttu-id="609df-105">第二个示例演示如何取消查询包含一个用户函数，则计算开销很大。</span><span class="sxs-lookup"><span data-stu-id="609df-105">The second example shows how to cancel a query that contains a user function that is computationally expensive.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="609df-106">Visual Studio 启用"仅我的代码"后，将引发异常的行中断并显示一条显示"未处理异常由用户代码。"的错误消息</span><span class="sxs-lookup"><span data-stu-id="609df-106">When "Just My Code" is enabled, Visual Studio will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="609df-107">此错误是良性的。</span><span class="sxs-lookup"><span data-stu-id="609df-107">This error is benign.</span></span> <span data-ttu-id="609df-108">可以按 F5 继续运行，并请参阅下面示例中所示的异常处理行为。</span><span class="sxs-lookup"><span data-stu-id="609df-108">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="609df-109">若要阻止 Visual Studio 的第一个错误时中断，只需取消选中下的"仅我的代码"复选框**工具、 选项、 调试、 常规**。</span><span class="sxs-lookup"><span data-stu-id="609df-109">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
>   
>  <span data-ttu-id="609df-110">本示例旨在演示用法，运行速度可能不如等效的顺序 LINQ to Objects 查询快。</span><span class="sxs-lookup"><span data-stu-id="609df-110">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="609df-111">有关加速的详细信息，请参阅[了解 PLINQ 中的加速](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)。</span><span class="sxs-lookup"><span data-stu-id="609df-111">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="609df-112">示例</span><span class="sxs-lookup"><span data-stu-id="609df-112">Example</span></span>  
 [!code-csharp[PLINQ#16](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#16)]
 [!code-vb[PLINQ#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#16)]  
  
 <span data-ttu-id="609df-113">PLINQ framework 不会回滚单个<xref:System.OperationCanceledException>到<xref:System.AggregateException?displayProperty=nameWithType>;<xref:System.OperationCanceledException>必须在单独的 catch 块中处理。</span><span class="sxs-lookup"><span data-stu-id="609df-113">The PLINQ framework does not roll a single <xref:System.OperationCanceledException> into an <xref:System.AggregateException?displayProperty=nameWithType>; the <xref:System.OperationCanceledException> must be handled in a separate catch block.</span></span> <span data-ttu-id="609df-114">如果一个或多个用户委托引发 OperationCanceledException(externalCT) (通过使用外部<xref:System.Threading.CancellationToken?displayProperty=nameWithType>) 但没有其他异常，并且查询被定义为`AsParallel().WithCancellation(externalCT)`，然后 PLINQ 将发出单个<xref:System.OperationCanceledException>(externalCT) 而非<xref:System.AggregateException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="609df-114">If one or more user delegates throws an OperationCanceledException(externalCT) (by using an external <xref:System.Threading.CancellationToken?displayProperty=nameWithType>) but no other exception, and the query was defined as `AsParallel().WithCancellation(externalCT)`, then PLINQ will issue a single <xref:System.OperationCanceledException> (externalCT) rather than an <xref:System.AggregateException?displayProperty=nameWithType>.</span></span> <span data-ttu-id="609df-115">但是，如果一个用户委托引发<xref:System.OperationCanceledException>，并且另一个委托引发其他异常类型，则这两种异常的事务将回滚到<xref:System.AggregateException>。</span><span class="sxs-lookup"><span data-stu-id="609df-115">However, if one user delegate throws an <xref:System.OperationCanceledException>, and another delegate throws another exception type, then both exceptions will be rolled into an <xref:System.AggregateException>.</span></span>  
  
 <span data-ttu-id="609df-116">有关取消的一般性指导原则是，如下所示：</span><span class="sxs-lookup"><span data-stu-id="609df-116">The general guidance on cancellation is as follows:</span></span>  
  
1.  <span data-ttu-id="609df-117">如果你执行用户委托取消您应通知外部 PLINQ<xref:System.Threading.CancellationToken>并引发<xref:System.OperationCanceledException>(externalCT)。</span><span class="sxs-lookup"><span data-stu-id="609df-117">If you perform user-delegate cancellation you should inform PLINQ about the external <xref:System.Threading.CancellationToken> and throw an <xref:System.OperationCanceledException>(externalCT).</span></span>  
  
2.  <span data-ttu-id="609df-118">如果取消，并且没有其他引发异常，则您应处理<xref:System.OperationCanceledException>而非<xref:System.AggregateException>。</span><span class="sxs-lookup"><span data-stu-id="609df-118">If cancellation occurs and no other exceptions are thrown, then you should handle an <xref:System.OperationCanceledException> rather than an <xref:System.AggregateException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="609df-119">示例</span><span class="sxs-lookup"><span data-stu-id="609df-119">Example</span></span>  
 <span data-ttu-id="609df-120">下面的示例演示如何处理取消时在用户代码中有计算开销很大的函数。</span><span class="sxs-lookup"><span data-stu-id="609df-120">The following example shows how to handle cancellation when you have a computationally expensive function in user code.</span></span>  
  
 [!code-csharp[PLINQ#17](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#17)]
 [!code-vb[PLINQ#17](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#17)]  
  
 <span data-ttu-id="609df-121">在处理用户代码中的取消操作时，则不需要使用<xref:System.Linq.ParallelEnumerable.WithCancellation%2A>查询定义中。</span><span class="sxs-lookup"><span data-stu-id="609df-121">When you handle the cancellation in user code, you do not have to use <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> in the query definition.</span></span> <span data-ttu-id="609df-122">但是，我们建议你这样做，因为<xref:System.Linq.ParallelEnumerable.WithCancellation%2A>有对查询性能影响，并且它使由查询运算符和你的用户代码处理取消操作。</span><span class="sxs-lookup"><span data-stu-id="609df-122">However, we recommended that you do this because <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> has no effect on query performance and it enables the cancellation to be handled by query operators and your user code.</span></span>  
  
 <span data-ttu-id="609df-123">为了确保系统的响应能力，我们建议你检查解决每毫秒; 一次取消但是，最多 10 毫秒任意一段被视为可接受。</span><span class="sxs-lookup"><span data-stu-id="609df-123">In order to ensure system responsiveness, we recommend that you check for cancellation around once per millisecond; however, any period up to 10 milliseconds is considered acceptable.</span></span> <span data-ttu-id="609df-124">此频率不应在代码的性能产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="609df-124">This frequency should not have a negative impact on your code's performance.</span></span>  
  
 <span data-ttu-id="609df-125">当释放枚举器时，例如代码中断的 （对于 Visual Basic 中的每个） 的 foreach 循环中循环访问查询结果外，则查询被取消时，但不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="609df-125">When an enumerator is disposed, for example when code breaks out of a foreach (For Each in Visual Basic) loop that is iterating over query results, then the query is cancelled, but no exception is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="609df-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="609df-126">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="609df-127">并行 LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="609df-127">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [<span data-ttu-id="609df-128">托管线程中的取消</span><span class="sxs-lookup"><span data-stu-id="609df-128">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
