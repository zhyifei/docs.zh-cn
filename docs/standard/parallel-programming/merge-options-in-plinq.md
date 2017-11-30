---
title: "PLINQ 中的合并选项"
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
helpviewer_keywords: PLINQ queries, merge options
ms.assetid: e8f7be3b-88de-4f33-ab14-dc008e76c1ba
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e9bf586c1805fc5b5f1cc5f96f4e6b08d80c199a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="merge-options-in-plinq"></a><span data-ttu-id="9c1e7-102">PLINQ 中的合并选项</span><span class="sxs-lookup"><span data-stu-id="9c1e7-102">Merge Options in PLINQ</span></span>
<span data-ttu-id="9c1e7-103">当查询正在作为并行，PLINQ 分区的源序列，以便多个线程可以同时处理同一置于不同部分，通常在单独线程上。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-103">When a query is executing as parallel, PLINQ partitions the source sequence so that multiple threads can work on different parts concurrently, typically on separate threads.</span></span> <span data-ttu-id="9c1e7-104">如果结果为将使用上一个线程，例如，在`foreach`(`For Each`中[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) 循环，则来自每个线程的结果必须合并回一个序列。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-104">If the results are to be consumed on one thread, for example, in a `foreach` (`For Each` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) loop, then the results from every thread must be merged back into one sequence.</span></span> <span data-ttu-id="9c1e7-105">PLINQ 执行 merge 的类型取决于查询中存在的运算符。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-105">The kind of merge that PLINQ performs depends on the operators that are present in the query.</span></span> <span data-ttu-id="9c1e7-106">例如，应用于的结果新顺序的运算符必须缓冲的所有线程中的所有元素。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-106">For example, operators that impose a new order on the results must buffer all elements from all threads.</span></span> <span data-ttu-id="9c1e7-107">从使用它的线程 （这也是，应用程序用户） 的角度来看完全缓冲的查询可能会明显期运行之前它将生成其第一个结果的时间。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-107">From the perspective of the consuming thread (which is also that of the application user) a fully buffered query might run for a noticeable period of time before it produces its first result.</span></span> <span data-ttu-id="9c1e7-108">其他运算符，默认情况下，部分缓冲;它们会产生分批其结果。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-108">Other operators, by default, are partially buffered; they yield their results in batches.</span></span> <span data-ttu-id="9c1e7-109">运算符，<xref:System.Linq.ParallelEnumerable.ForAll%2A>默认情况下未缓冲。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-109">One operator, <xref:System.Linq.ParallelEnumerable.ForAll%2A> is not buffered by default.</span></span> <span data-ttu-id="9c1e7-110">它立即从所有线程中生成的所有元素。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-110">It yields all elements from all threads immediately.</span></span>  
  
 <span data-ttu-id="9c1e7-111">通过使用<xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A>方法，如下面的示例中所示你可以提供一个提示 plinq，该值指示要执行的合并类型。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-111">By using the <xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A> method, as shown in the following example, you can provide a hint to PLINQ that indicates what kind of merging to perform.</span></span>  
  
 [!code-csharp[PLINQ#26](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#26)]
 [!code-vb[PLINQ#26](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#26)]  
  
 <span data-ttu-id="9c1e7-112">有关完整示例，请参阅[如何： 在 PLINQ 中指定合并选项](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-112">For the complete example, see [How to: Specify Merge Options in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md).</span></span>  
  
 <span data-ttu-id="9c1e7-113">如果特定的查询不支持请求的选项，则只需忽略选项。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-113">If the particular query cannot support the requested option, then the option will just be ignored.</span></span> <span data-ttu-id="9c1e7-114">在大多数情况下，无需指定 PLINQ 查询的合并选项。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-114">In most cases, you do not have to specify a merge option for a PLINQ query.</span></span> <span data-ttu-id="9c1e7-115">但是，在某些情况下你可能会发现通过测试和查询执行最在非默认模式下的测量。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-115">However, in some cases you may find by testing and measurement that a query executes best in a non-default mode.</span></span> <span data-ttu-id="9c1e7-116">此选项的一个常见用途是强制使用区块合并运算符流式以便提供更快地响应用户界面处理其结果。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-116">A common use of this option is to force a chunk-merging operator to stream its results in order to provide a more responsive user interface.</span></span>  
  
## <a name="parallelmergeoptions"></a><span data-ttu-id="9c1e7-117">ParallelMergeOptions</span><span class="sxs-lookup"><span data-stu-id="9c1e7-117">ParallelMergeOptions</span></span>  
 <span data-ttu-id="9c1e7-118"><xref:System.Linq.ParallelMergeOptions>枚举包含以下选项，指定如何生成查询的最终输出了结果使用在一个线程上时，支持的查询形状：</span><span class="sxs-lookup"><span data-stu-id="9c1e7-118">The <xref:System.Linq.ParallelMergeOptions> enumeration includes the following options that specify, for supported query shapes, how the final output of the query is yielded when the results are consumed on one thread:</span></span>  
  
-   `Not Buffered`  
  
     <span data-ttu-id="9c1e7-119"><xref:System.Linq.ParallelMergeOptions.NotBuffered>选项将导致每个已处理的元素，返回从每个线程，就会立即生成它。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-119">The <xref:System.Linq.ParallelMergeOptions.NotBuffered> option causes each processed element to be returned from each thread as soon as it is produced.</span></span> <span data-ttu-id="9c1e7-120">此行为是类似于"流式处理"输出。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-120">This behavior is analogous to "streaming" the output.</span></span> <span data-ttu-id="9c1e7-121">如果<xref:System.Linq.ParallelEnumerable.AsOrdered%2A>运算符是在查询中，存在`NotBuffered`保留源元素的顺序。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-121">If the <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> operator is present in the query, `NotBuffered` preserves the order of the source elements.</span></span> <span data-ttu-id="9c1e7-122">尽管`NotBuffered`开始就立即可用，就产生结果、 的总时间以生成所有结果可能仍然能长于使用其他合并选项之一。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-122">Although `NotBuffered` starts yielding results as soon as they're available,, the total time to produce all the results might still be longer than using one of the other merge options.</span></span>  
  
-   `Auto Buffered`  
  
     <span data-ttu-id="9c1e7-123">通过 <xref:System.Linq.ParallelMergeOptions.AutoBuffered> 选项，查询将元素收集到缓冲区中，并定期一次性将所有缓冲内容生成到使用线程中。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-123">The <xref:System.Linq.ParallelMergeOptions.AutoBuffered> option causes the query to collect elements into a buffer and then periodically yield the buffer contents all at once to the consuming thread.</span></span> <span data-ttu-id="9c1e7-124">这是类似于生成而不使用的"流式处理"行为"区块"中的源数据`NotBuffered`。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-124">This is analogous to yielding the source data in "chunks" instead of using the "streaming" behavior of `NotBuffered`.</span></span> <span data-ttu-id="9c1e7-125">`AutoBuffered`可能需要超过`NotBuffered`以使第一个元素在使用它的线程上可用。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-125">`AutoBuffered` may take longer than `NotBuffered` to make the first element available on the consuming thread.</span></span> <span data-ttu-id="9c1e7-126">大小以及缓冲区准确的生成行为是不可配置的并可能会有所不同，具体取决于与查询相关的各种因素。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-126">The size of the buffer and the exact yielding behavior are not configurable and may vary, depending on various factors that relate to the query.</span></span>  
  
-   `FullyBuffered`  
  
     <span data-ttu-id="9c1e7-127"><xref:System.Linq.ParallelMergeOptions.FullyBuffered>选项会导致整个查询之前的任何元素都生成缓存的输出。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-127">The <xref:System.Linq.ParallelMergeOptions.FullyBuffered> option causes the output of the whole query to be buffered before any of the elements are yielded.</span></span> <span data-ttu-id="9c1e7-128">当你使用此选项时，则可以较长时间之前的第一个元素上使用它的线程，可用，但可能仍然生成完整的结果比使用其他选项更快。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-128">When you use this option, it can take longer before the first element is available on the consuming thread, but the complete results might still be produced faster than by using the other options.</span></span>  
  
## <a name="query-operators-that-support-merge-options"></a><span data-ttu-id="9c1e7-129">支持合并选项的查询运算符</span><span class="sxs-lookup"><span data-stu-id="9c1e7-129">Query Operators that Support Merge Options</span></span>  
 <span data-ttu-id="9c1e7-130">下表列出了支持所有的合并选项模式，根据指定的限制的运算符。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-130">The following table lists the operators that support all merge option modes, subject to the specified restrictions.</span></span>  
  
|<span data-ttu-id="9c1e7-131">运算符</span><span class="sxs-lookup"><span data-stu-id="9c1e7-131">Operator</span></span>|<span data-ttu-id="9c1e7-132">限制</span><span class="sxs-lookup"><span data-stu-id="9c1e7-132">Restrictions</span></span>|  
|--------------|------------------|  
|<xref:System.Linq.ParallelEnumerable.AsEnumerable%2A>|<span data-ttu-id="9c1e7-133">无</span><span class="sxs-lookup"><span data-stu-id="9c1e7-133">None</span></span>|  
|<xref:System.Linq.ParallelEnumerable.Cast%2A>|<span data-ttu-id="9c1e7-134">无</span><span class="sxs-lookup"><span data-stu-id="9c1e7-134">None</span></span>|  
|<xref:System.Linq.ParallelEnumerable.Concat%2A>|<span data-ttu-id="9c1e7-135">有一个数组或列表源仅的非排序的查询。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-135">Non-ordered queries that have an Array or List source only.</span></span>|  
|<xref:System.Linq.ParallelEnumerable.DefaultIfEmpty%2A>|<span data-ttu-id="9c1e7-136">无</span><span class="sxs-lookup"><span data-stu-id="9c1e7-136">None</span></span>|  
|<xref:System.Linq.ParallelEnumerable.OfType%2A>|<span data-ttu-id="9c1e7-137">无</span><span class="sxs-lookup"><span data-stu-id="9c1e7-137">None</span></span>|  
|<xref:System.Linq.ParallelEnumerable.Reverse%2A>|<span data-ttu-id="9c1e7-138">有一个数组或列表源仅的非排序的查询。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-138">Non-ordered queries that have an Array or List source only.</span></span>|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>|<span data-ttu-id="9c1e7-139">无</span><span class="sxs-lookup"><span data-stu-id="9c1e7-139">None</span></span>|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>|<span data-ttu-id="9c1e7-140">无</span><span class="sxs-lookup"><span data-stu-id="9c1e7-140">None</span></span>|  
|<xref:System.Linq.ParallelEnumerable.Skip%2A>|<span data-ttu-id="9c1e7-141">无</span><span class="sxs-lookup"><span data-stu-id="9c1e7-141">None</span></span>|  
|<xref:System.Linq.ParallelEnumerable.Take%2A>|<span data-ttu-id="9c1e7-142">无</span><span class="sxs-lookup"><span data-stu-id="9c1e7-142">None</span></span>|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>|<span data-ttu-id="9c1e7-143">无</span><span class="sxs-lookup"><span data-stu-id="9c1e7-143">None</span></span>|  
  
 <span data-ttu-id="9c1e7-144">所有其他 PLINQ 查询运算符可能会忽略用户提供的合并选项。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-144">All other PLINQ query operators might ignore user-provided merge options.</span></span> <span data-ttu-id="9c1e7-145">某些查询运算符，例如，<xref:System.Linq.ParallelEnumerable.Reverse%2A>和<xref:System.Linq.ParallelEnumerable.OrderBy%2A>，无法生成任何元素，直到所有已生成并重新排序。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-145">Some query operators, for example, <xref:System.Linq.ParallelEnumerable.Reverse%2A> and <xref:System.Linq.ParallelEnumerable.OrderBy%2A>, cannot yield any elements until all have been produced and reordered.</span></span> <span data-ttu-id="9c1e7-146">因此，当<xref:System.Linq.ParallelMergeOptions>还包含操作员例如查询中使用<xref:System.Linq.ParallelEnumerable.Reverse%2A>，合并行为后该运算符生成其结果不会在查询中，直到应用。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-146">Therefore, when <xref:System.Linq.ParallelMergeOptions> is used in a query that also contains an operator such as <xref:System.Linq.ParallelEnumerable.Reverse%2A>, the merge behavior will not be applied in the query until after that operator has produced its results.</span></span>  
  
 <span data-ttu-id="9c1e7-147">有些运算符能够处理合并选项取决于源序列中的类型和是否<xref:System.Linq.ParallelEnumerable.AsOrdered%2A>运算符使用前面的查询。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-147">The ability of some operators to handle merge options depends on the type of the source sequence, and whether the <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> operator was used earlier in the query.</span></span> <span data-ttu-id="9c1e7-148"><xref:System.Linq.ParallelEnumerable.ForAll%2A>始终<xref:System.Linq.ParallelMergeOptions.NotBuffered>; 它将立即生成它的元素。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-148"><xref:System.Linq.ParallelEnumerable.ForAll%2A> is always <xref:System.Linq.ParallelMergeOptions.NotBuffered> ; it yields its elements immediately.</span></span> <span data-ttu-id="9c1e7-149"><xref:System.Linq.ParallelEnumerable.OrderBy%2A>始终<xref:System.Linq.ParallelMergeOptions.FullyBuffered>; 它之前它将产生必须对整个列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="9c1e7-149"><xref:System.Linq.ParallelEnumerable.OrderBy%2A> is always <xref:System.Linq.ParallelMergeOptions.FullyBuffered>; it must sort the whole list before it yields.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c1e7-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c1e7-150">See Also</span></span>  
 [<span data-ttu-id="9c1e7-151">并行 LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="9c1e7-151">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [<span data-ttu-id="9c1e7-152">如何：在 PLINQ 中指定合并选项</span><span class="sxs-lookup"><span data-stu-id="9c1e7-152">How to: Specify Merge Options in PLINQ</span></span>](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)
