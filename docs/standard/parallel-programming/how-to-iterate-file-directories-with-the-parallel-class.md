---
title: "如何：使用并行类循环访问文件目录"
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
helpviewer_keywords: parallel loops, how to iterate directories
ms.assetid: 555e9f48-f53d-4774-9bcf-3e965c732ec5
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c21aadf70eaccafc8c8ec9c4efefff1c66abc6b5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-iterate-file-directories-with-the-parallel-class"></a><span data-ttu-id="e1d12-102">如何：使用并行类循环访问文件目录</span><span class="sxs-lookup"><span data-stu-id="e1d12-102">How to: Iterate File Directories with the Parallel Class</span></span>
<span data-ttu-id="e1d12-103">在许多情况下，文件迭代是可以轻松地并行化操作。</span><span class="sxs-lookup"><span data-stu-id="e1d12-103">In many cases, file iteration is an operation that can be easily parallelized.</span></span> <span data-ttu-id="e1d12-104">主题[如何： 使用 PLINQ 循环文件目录](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-plinq.md)演示很多情况下执行此任务的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="e1d12-104">The topic [How to: Iterate File Directories with PLINQ](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-plinq.md) shows the easiest way to perform this task for many scenarios.</span></span> <span data-ttu-id="e1d12-105">但是，当你的代码具有许多类型的访问的文件系统时可能会出现的异常处理，则可能会出现复杂性。</span><span class="sxs-lookup"><span data-stu-id="e1d12-105">However, complications can arise when your code has to deal with the many types of exceptions that can arise when accessing the file system.</span></span> <span data-ttu-id="e1d12-106">下面的示例演示问题的一种方法。</span><span class="sxs-lookup"><span data-stu-id="e1d12-106">The following example shows one approach to the problem.</span></span> <span data-ttu-id="e1d12-107">它使用基于堆栈的迭代来遍历所有文件和文件夹下指定的目录，使你的代码以捕获和处理各种异常。</span><span class="sxs-lookup"><span data-stu-id="e1d12-107">It uses a stack-based iteration to traverse all files and folders under a specified directory, and it enables your code to catch and handle various exceptions.</span></span> <span data-ttu-id="e1d12-108">当然，处理异常的方法是由您决定。</span><span class="sxs-lookup"><span data-stu-id="e1d12-108">Of course, the way that you handle the exceptions is up to you.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1d12-109">示例</span><span class="sxs-lookup"><span data-stu-id="e1d12-109">Example</span></span>  
 <span data-ttu-id="e1d12-110">下面的示例按顺序循环访问目录，但会并行处理文件。</span><span class="sxs-lookup"><span data-stu-id="e1d12-110">The following example iterates the directories sequentially, but processes the files in parallel.</span></span> <span data-ttu-id="e1d12-111">当你具有大型文件目录比率时，这可能是最好的方法。</span><span class="sxs-lookup"><span data-stu-id="e1d12-111">This is probably the best approach when you have a large file-to-directory ratio.</span></span> <span data-ttu-id="e1d12-112">还有可能并行化目录迭代中，并按顺序访问每个文件。</span><span class="sxs-lookup"><span data-stu-id="e1d12-112">It is also possible to parallelize the directory iteration, and access each file sequentially.</span></span> <span data-ttu-id="e1d12-113">它可能不是高效以并行化这两个循环，除非特别面向具有大量的处理器的计算机。</span><span class="sxs-lookup"><span data-stu-id="e1d12-113">It is probably not efficient to parallelize both loops unless you are specifically targeting a machine with a large number of processors.</span></span> <span data-ttu-id="e1d12-114">但是，如下所示所有情况下，你应测试你的应用程序进行全面以确定最佳的方法。</span><span class="sxs-lookup"><span data-stu-id="e1d12-114">However, as in all cases, you should test your application thoroughly to determine the best approach.</span></span>  
  
 [!code-csharp[TPL_Parallel#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_file.cs#08)]
 [!code-vb[TPL_Parallel#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/fileiteration08.vb#08)]  
  
 <span data-ttu-id="e1d12-115">在此示例中，以同步方式执行文件 I/O。</span><span class="sxs-lookup"><span data-stu-id="e1d12-115">In this example, the file I/O is performed synchronously.</span></span> <span data-ttu-id="e1d12-116">在处理大型文件或慢速网络连接，它可能更可取的方法以异步方式访问的文件。</span><span class="sxs-lookup"><span data-stu-id="e1d12-116">When dealing with large files or slow network connections, it might be preferable to access the files asynchronously.</span></span> <span data-ttu-id="e1d12-117">你可以使用并行迭代组合异步 I/O 技术。</span><span class="sxs-lookup"><span data-stu-id="e1d12-117">You can combine asynchronous I/O techniques with parallel iteration.</span></span> <span data-ttu-id="e1d12-118">有关详细信息，请参阅 [TPL 和传统 .NET Framework 异步编程](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md)。</span><span class="sxs-lookup"><span data-stu-id="e1d12-118">For more information, see [TPL and Traditional .NET Framework Asynchronous Programming](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md).</span></span>  
  
 <span data-ttu-id="e1d12-119">此示例使用局部 `fileCount` 变量维护已处理的总文件数的计数。</span><span class="sxs-lookup"><span data-stu-id="e1d12-119">The example uses the local `fileCount` variable to maintain a count of the total number of files processed.</span></span> <span data-ttu-id="e1d12-120">由于多个任务可能并发访问此变量，可以调用 <xref:System.Threading.Interlocked.Add%2A?displayProperty=nameWithType> 方法来同步对它的访问。</span><span class="sxs-lookup"><span data-stu-id="e1d12-120">Because the variable might be accessed concurrently by multiple tasks, access to it is synchronized by calling the <xref:System.Threading.Interlocked.Add%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="e1d12-121">请注意，如果主引发异常的线程，通过启动的线程<xref:System.Threading.Tasks.Parallel.ForEach%2A>方法可能会继续运行。</span><span class="sxs-lookup"><span data-stu-id="e1d12-121">Note that if an exception is thrown on the main thread, the threads that are started by the <xref:System.Threading.Tasks.Parallel.ForEach%2A> method might continue to run.</span></span> <span data-ttu-id="e1d12-122">若要停止这些线程，你可以在异常处理程序，设置布尔变量，并检查它并行循环的每个迭代上的值。</span><span class="sxs-lookup"><span data-stu-id="e1d12-122">To stop these threads, you can set a Boolean variable in your exception handlers, and check its value on each iteration of the parallel loop.</span></span> <span data-ttu-id="e1d12-123">如果值指示已引发异常，则使用<xref:System.Threading.Tasks.ParallelLoopState>变量以停止或中断循环。</span><span class="sxs-lookup"><span data-stu-id="e1d12-123">If the value indicates that an exception has been thrown, use the <xref:System.Threading.Tasks.ParallelLoopState> variable to stop or break from the loop.</span></span> <span data-ttu-id="e1d12-124">有关详细信息，请参阅[如何： 停止或中断 Parallel.For 循环](http://msdn.microsoft.com/en-us/de52e4f1-9346-4ad5-b582-1a4d54dc7f7e)。</span><span class="sxs-lookup"><span data-stu-id="e1d12-124">For more information, see [How to: Stop or Break from a Parallel.For Loop](http://msdn.microsoft.com/en-us/de52e4f1-9346-4ad5-b582-1a4d54dc7f7e).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1d12-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1d12-125">See Also</span></span>  
 [<span data-ttu-id="e1d12-126">数据并行</span><span class="sxs-lookup"><span data-stu-id="e1d12-126">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
