---
title: "如何：使用 PLINQ 循环访问文件目录"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: PLINQ queries, how to iterate directories
ms.assetid: 354e8ce3-35c4-431c-99ca-7661d1f3901b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 40fd9f64b5702f5205b7817f3de1e0a8709c5a63
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-iterate-file-directories-with-plinq"></a><span data-ttu-id="0ecbe-102">如何：使用 PLINQ 循环访问文件目录</span><span class="sxs-lookup"><span data-stu-id="0ecbe-102">How to: Iterate File Directories with PLINQ</span></span>
<span data-ttu-id="0ecbe-103">此示例演示两种简单的方法来并行执行对文件目录的操作。</span><span class="sxs-lookup"><span data-stu-id="0ecbe-103">This example shows two simple ways to parallelize operations on file directories.</span></span> <span data-ttu-id="0ecbe-104">第一个查询使用<xref:System.IO.Directory.GetFiles%2A>方法来填充目录及其所有子目录中的文件名称的数组。</span><span class="sxs-lookup"><span data-stu-id="0ecbe-104">The first query uses the <xref:System.IO.Directory.GetFiles%2A> method to populate an array of file names in a directory and all subdirectories.</span></span> <span data-ttu-id="0ecbe-105">此方法不返回直到填充整个数组，并因此它还会带来操作的开始处的延迟。</span><span class="sxs-lookup"><span data-stu-id="0ecbe-105">This method does not return until the entire array is populated, and therefore it can introduce latency at the beginning of the operation.</span></span> <span data-ttu-id="0ecbe-106">但是，填充数组后，PLINQ 在可以处理它并行速度非常快。</span><span class="sxs-lookup"><span data-stu-id="0ecbe-106">However, after the array is populated, PLINQ can process it in parallel very quickly.</span></span>  
  
 <span data-ttu-id="0ecbe-107">第二个查询使用静态<xref:System.IO.Directory.EnumerateDirectories%2A>和<xref:System.IO.DirectoryInfo.EnumerateFiles%2A>立即开始返回结果的方法。</span><span class="sxs-lookup"><span data-stu-id="0ecbe-107">The second query uses the static <xref:System.IO.Directory.EnumerateDirectories%2A> and <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> methods which begin returning results immediately.</span></span> <span data-ttu-id="0ecbe-108">这种方法可以更快时遍历大目录树，但与第一个示例比较的处理时间可以取决于许多因素。</span><span class="sxs-lookup"><span data-stu-id="0ecbe-108">This approach can be faster when you are iterating over large directory trees, although the processing time compared to the first example can depend on many factors.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="0ecbe-109">这些示例旨在演示用法，并且运行速度可能不如等效的顺序 LINQ to Objects 查询。</span><span class="sxs-lookup"><span data-stu-id="0ecbe-109">These examples are intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="0ecbe-110">有关加速的详细信息，请参阅[了解 PLINQ 中的加速](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)。</span><span class="sxs-lookup"><span data-stu-id="0ecbe-110">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ecbe-111">示例</span><span class="sxs-lookup"><span data-stu-id="0ecbe-111">Example</span></span>  
 <span data-ttu-id="0ecbe-112">下面的示例演示如何循环访问文件目录在简单的情况下，当在树中有权访问所有目录、 文件大小不非常大，并且访问时间都不重要。</span><span class="sxs-lookup"><span data-stu-id="0ecbe-112">The following example shows how to iterate over file directories in simple scenarios when you have access to all directories in the tree, the file sizes are not very large, and the access times are not significant.</span></span> <span data-ttu-id="0ecbe-113">正在构造的文件名称的数组时，此方法涉及开头的延迟一段。</span><span class="sxs-lookup"><span data-stu-id="0ecbe-113">This approach involves a period of latency at the beginning while the array of file names is being constructed.</span></span>  
  
 [!code-csharp[PLINQ#33](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#33)]  
  
## <a name="example"></a><span data-ttu-id="0ecbe-114">示例</span><span class="sxs-lookup"><span data-stu-id="0ecbe-114">Example</span></span>  
 <span data-ttu-id="0ecbe-115">下面的示例演示如何循环访问文件目录在简单的情况下，当在树中有权访问所有目录、 文件大小不非常大，并且访问时间都不重要。</span><span class="sxs-lookup"><span data-stu-id="0ecbe-115">The following example shows how to iterate over file directories in simple scenarios when you have access to all directories in the tree, the file sizes are not very large, and the access times are not significant.</span></span> <span data-ttu-id="0ecbe-116">这种方法开始在上一示例的更快地生成的结果。</span><span class="sxs-lookup"><span data-stu-id="0ecbe-116">This approach begins producing results faster than the previous example.</span></span>  
  
 [!code-csharp[PLINQ#34](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#34)]  
  
 <span data-ttu-id="0ecbe-117">使用时<xref:System.IO.Directory.GetFiles%2A>，请确保你具有在树中的所有目录的足够权限。</span><span class="sxs-lookup"><span data-stu-id="0ecbe-117">When using <xref:System.IO.Directory.GetFiles%2A>, be sure that you have sufficient permissions on all directories in the tree.</span></span> <span data-ttu-id="0ecbe-118">否则为将引发异常，将返回任何结果。</span><span class="sxs-lookup"><span data-stu-id="0ecbe-118">Otherwise an exception will be thrown and no results will be returned.</span></span> <span data-ttu-id="0ecbe-119">使用时<xref:System.IO.Directory.EnumerateDirectories%2A>在 PLINQ 查询中，它会产生问题，以使你能够继续循环正常方式处理 I/O 异常。</span><span class="sxs-lookup"><span data-stu-id="0ecbe-119">When using the <xref:System.IO.Directory.EnumerateDirectories%2A> in a PLINQ query, it is problematic to handle I/O exceptions in a graceful way that enables you to continue iterating.</span></span> <span data-ttu-id="0ecbe-120">如果你的代码必须处理 I/O 或未经授权的访问异常，则应考虑中所述的方法[如何： 使用并行类循环访问文件目录](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-the-parallel-class.md)。</span><span class="sxs-lookup"><span data-stu-id="0ecbe-120">If your code must handle I/O or unauthorized access exceptions, then you should consider the approach described in [How to: Iterate File Directories with the Parallel Class](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-the-parallel-class.md).</span></span>  
  
 <span data-ttu-id="0ecbe-121">如果 I/O 延迟的问题，例如使用文件 I/O 通过网络，请考虑使用异步 I/O 方法中所述之一[TPL 和传统.NET Framework 异步编程](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md)和在此[博客文章](http://go.microsoft.com/fwlink/?LinkID=186458).</span><span class="sxs-lookup"><span data-stu-id="0ecbe-121">If I/O latency is an issue, for example with file I/O over a network, consider using one of the asynchronous I/O techniques described in [TPL and Traditional .NET Framework Asynchronous Programming](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md) and in this [blog post](http://go.microsoft.com/fwlink/?LinkID=186458).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ecbe-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ecbe-122">See Also</span></span>  
 [<span data-ttu-id="0ecbe-123">并行 LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="0ecbe-123">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
