---
title: Windows 系统上的大型对象堆
ms.date: 05/02/2018
helpviewer_keywords:
- large object heap (LOH)"
- LOH
- garbage collection, large object heap
- GC [.NET ], large object heap
author: rpetrusha
ms.author: ronpet
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 852efc14af02eec4608e133e4c75507cd881b80e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43513599"
---
# <a name="the-large-object-heap-on-windows-systems"></a><span data-ttu-id="868bf-102">Windows 系统上的大型对象堆</span><span class="sxs-lookup"><span data-stu-id="868bf-102">The large object heap on Windows systems</span></span>

<span data-ttu-id="868bf-103">.NET 垃圾回收器 (GC) 将对象分为小型和大型对象。</span><span class="sxs-lookup"><span data-stu-id="868bf-103">The .NET Garbage Collector (GC) divides objects up into small and large objects.</span></span> <span data-ttu-id="868bf-104">如果是大型对象，它的某些特性将比对象较小时显得更为重要。</span><span class="sxs-lookup"><span data-stu-id="868bf-104">When an object is large, some of its attributes become more significant than if the object is small.</span></span> <span data-ttu-id="868bf-105">例如，压缩大型对象（也就是在内存中将其复制到堆上的其他地方）的费用相当高。</span><span class="sxs-lookup"><span data-stu-id="868bf-105">For instance, compacting it -- that is, copying it in memory elsewhere on the heap -- can be expensive.</span></span> <span data-ttu-id="868bf-106">因此，.NET 垃圾回收器将大型对象放置在大型对象堆 (LOH) 上。</span><span class="sxs-lookup"><span data-stu-id="868bf-106">Because of this, the .NET Garbage Collector places large objects on the large object heap (LOH).</span></span> <span data-ttu-id="868bf-107">在本主题中，我们将深度探讨大型对象堆。</span><span class="sxs-lookup"><span data-stu-id="868bf-107">In this topic, we'll look at the large object heap in depth.</span></span> <span data-ttu-id="868bf-108">我们将讨论符合什么条件的对象才能称之为大型对象，如何回收这些大型对象，以及大型对象具备哪些性能意义。</span><span class="sxs-lookup"><span data-stu-id="868bf-108">We'll discuss what qualifies an object as a large object, how these large objects are collected, and what kind of performance implications large objects impose.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="868bf-109">本主题仅讨论 .NET Framework 中的大型对象堆和 Windows 系统上运行的 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="868bf-109">This topic discusses the large object heap in the .NET Framework and .NET Core running on Windows systems only.</span></span> <span data-ttu-id="868bf-110">不包括在其他平台上的 .NET 实现上运行的 LOH。</span><span class="sxs-lookup"><span data-stu-id="868bf-110">It does not cover the LOH running on .NET implementations on other platforms.</span></span>

## <a name="how-an-object-ends-up-on-the-large-object-heap-and-how-gc-handles-them"></a><span data-ttu-id="868bf-111">对象如何在大型对象堆上结束以及 GC 如何处理它们</span><span class="sxs-lookup"><span data-stu-id="868bf-111">How an object ends up on the large object heap and how GC handles them</span></span>

<span data-ttu-id="868bf-112">如果对象大于或等于 85,000 字节，将被视为大型对象。</span><span class="sxs-lookup"><span data-stu-id="868bf-112">If an object is greater than or equal to 85,000 bytes, it’s considered a large object.</span></span> <span data-ttu-id="868bf-113">此数字根据性能优化确定。</span><span class="sxs-lookup"><span data-stu-id="868bf-113">This number was determined by performance tuning.</span></span> <span data-ttu-id="868bf-114">对象分配请求为 85,000 字节或更大时，运行时会将其分配到大型对象堆。</span><span class="sxs-lookup"><span data-stu-id="868bf-114">When an object allocation request is for 85,000 or more bytes, the runtime allocates it on the large object heap.</span></span>

<span data-ttu-id="868bf-115">若要了解其意义，可查看 .NET GC 的部分相关基础知识。</span><span class="sxs-lookup"><span data-stu-id="868bf-115">To understand what this means, it's useful to examine some fundamentals about the .NET GC.</span></span>

<span data-ttu-id="868bf-116">.NET 垃圾回收器是分代回收器。</span><span class="sxs-lookup"><span data-stu-id="868bf-116">The .NET Garbage Collector is a generational collector.</span></span> <span data-ttu-id="868bf-117">它包含三代：第 0 代、第 1 代和第 2 代。</span><span class="sxs-lookup"><span data-stu-id="868bf-117">It has three generations: generation 0, generation 1, and generation 2.</span></span> <span data-ttu-id="868bf-118">包含 3 代的原因是，在优化良好的应用中，大部分对象都在第 0 代就清除了。</span><span class="sxs-lookup"><span data-stu-id="868bf-118">The reason for having 3 generations is that, in a well-tuned app, most objects die in gen0.</span></span> <span data-ttu-id="868bf-119">例如，在服务器应用中，与每个请求相关的分配应在请求完成后清除。</span><span class="sxs-lookup"><span data-stu-id="868bf-119">For example, in a server app, the allocations associated with each request should die after the request is finished.</span></span> <span data-ttu-id="868bf-120">仍存在的分配请求将转到第 1 代，并在那里进行清除。</span><span class="sxs-lookup"><span data-stu-id="868bf-120">The in-flight allocation requests will make it into gen1 and die there.</span></span> <span data-ttu-id="868bf-121">从本质上讲，第 1 代是新对象区域与生存期较长的对象区域之间的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="868bf-121">Essentially, gen1 acts as a buffer between young object areas and long-lived object areas.</span></span>

<span data-ttu-id="868bf-122">小型对象始终在第 0 代中进行分配，或者根据它们的生存期，可能会提升为第 1 代或第 2 代。</span><span class="sxs-lookup"><span data-stu-id="868bf-122">Small objects are always allocated in generation 0 and, depending on their lifetime, may be promoted to generation 1 or generation2.</span></span> <span data-ttu-id="868bf-123">大型对象始终在第 2 代中进行分配。</span><span class="sxs-lookup"><span data-stu-id="868bf-123">Large objects are always allocated in generation 2.</span></span>

<span data-ttu-id="868bf-124">大型对象属于第 2 代，因为只有在第 2 代回收期间才能回收它们。</span><span class="sxs-lookup"><span data-stu-id="868bf-124">Large objects belong to generation 2 because they are collected only during a generation 2 collection.</span></span> <span data-ttu-id="868bf-125">回收一代时，同时也会回收它前面的所有代。</span><span class="sxs-lookup"><span data-stu-id="868bf-125">When a generation is collected, all its younger generation(s) are also collected.</span></span> <span data-ttu-id="868bf-126">例如，执行第 1 代 GC 时，将同时回收第 1 代和第 0 代。</span><span class="sxs-lookup"><span data-stu-id="868bf-126">For example, when a generation 1 GC happens, both generation 1 and 0 are collected.</span></span> <span data-ttu-id="868bf-127">执行第 2 代 GC 时，将回收整个堆。</span><span class="sxs-lookup"><span data-stu-id="868bf-127">And when a generation 2 GC happens, the whole heap is collected.</span></span> <span data-ttu-id="868bf-128">因此，第 2 代 GC 还可称为“完整 GC”。</span><span class="sxs-lookup"><span data-stu-id="868bf-128">For this reason, a generation 2 GC is also called a *full GC*.</span></span> <span data-ttu-id="868bf-129">本文引用第 2 代 GC 而不是完整 GC，但这两个术语是可以互换的。</span><span class="sxs-lookup"><span data-stu-id="868bf-129">This article refers to generation 2 GC instead of full GC, but the terms are interchangeable.</span></span>

<span data-ttu-id="868bf-130">代可提供 GC 堆的逻辑视图。</span><span class="sxs-lookup"><span data-stu-id="868bf-130">Generations provide a logical view of the GC heap.</span></span> <span data-ttu-id="868bf-131">实际上，对象存在于托管堆段中。</span><span class="sxs-lookup"><span data-stu-id="868bf-131">Physically, objects live in managed heap segments.</span></span> <span data-ttu-id="868bf-132">托管堆段是 GC 通过调用 [VirtualAlloc 功能](https://msdn.microsoft.com/library/windows/desktop/aa366887(v=vs.85).aspx)代表托管代码在操作系统上保留的内存块。</span><span class="sxs-lookup"><span data-stu-id="868bf-132">A *managed heap segment* is a chunk of memory that the GC reserves from the OS by calling the [VirtualAlloc function](https://msdn.microsoft.com/library/windows/desktop/aa366887(v=vs.85).aspx) on behalf of managed code.</span></span> <span data-ttu-id="868bf-133">加载 CLR 时，GC 分配两个初始堆段：一个用于小型对象（小型对象堆或 SOH），一个用于大型对象（大型对象堆）。</span><span class="sxs-lookup"><span data-stu-id="868bf-133">When the CLR is loaded, the GC allocates two initial heap segments: one for small objects (the Small Object Heap, or SOH), and one for large objects (the Large Object Heap).</span></span>

<span data-ttu-id="868bf-134">然后，通过将托管对象置于这些托管堆段上来满足分配请求。</span><span class="sxs-lookup"><span data-stu-id="868bf-134">The allocation requests are then satisfied by putting managed objects on these managed heap segments.</span></span> <span data-ttu-id="868bf-135">如果该对象小于 85,000 字节，则将它置于 SOH 的段上，否则，将它置于 LOH 段。</span><span class="sxs-lookup"><span data-stu-id="868bf-135">If the object is less than 85,000 bytes, it is put on the segment for the SOH; otherwise, it is put on an LOH segment.</span></span> <span data-ttu-id="868bf-136">随着分配到各段上的对象越来越多，会以较小块的形式提交这些段。</span><span class="sxs-lookup"><span data-stu-id="868bf-136">Segments are committed (in smaller chunks) as more and more objects are allocated onto them.</span></span>
<span data-ttu-id="868bf-137">对于 SOH，GC 未处理的对象将提升为下一代。</span><span class="sxs-lookup"><span data-stu-id="868bf-137">For the SOH, objects that survive a GC are promoted to the next generation.</span></span> <span data-ttu-id="868bf-138">第 0 代回收未处理的对象现在视为第 1 代对象，以此类推。</span><span class="sxs-lookup"><span data-stu-id="868bf-138">Objects that survive a generation 0 collection are now considered generation 1 objects, and so on.</span></span> <span data-ttu-id="868bf-139">但是，最后一代回收未处理的对象仍会被视为最后一代中的对象。</span><span class="sxs-lookup"><span data-stu-id="868bf-139">However, objects that survive the oldest generation are still considered to be in the oldest generation.</span></span> <span data-ttu-id="868bf-140">也就是说，第 2 代垃圾回收未处理的对象仍是第 2 代对象；LOH 未处理的对象仍是 LOH 对象（由第 2 代回收）。</span><span class="sxs-lookup"><span data-stu-id="868bf-140">In other words, survivors from generation 2 are generation 2 objects; and survivors from the LOH are LOH objects (which are collected with gen2).</span></span>

<span data-ttu-id="868bf-141">用户代码只能在第 0 代（小型对象）或 LOH（大型对象）中分配。</span><span class="sxs-lookup"><span data-stu-id="868bf-141">User code can only allocate in generation 0 (small objects) or the LOH (large objects).</span></span> <span data-ttu-id="868bf-142">只有 GC 可以在第 1 代（通过提升第 0 代回收未处理的对象）和第 2 代（通过提升第 1 代和第 2 代回收未处理的对象）中“分配”对象。</span><span class="sxs-lookup"><span data-stu-id="868bf-142">Only the GC can “allocate” objects in generation 1 (by promoting survivors from generation 0) and generation 2 (by promoting survivors from generations 1 and 2).</span></span>

<span data-ttu-id="868bf-143">触发垃圾回收后，GC 将寻找存在的对象并将它们压缩。</span><span class="sxs-lookup"><span data-stu-id="868bf-143">When a garbage collection is triggered, the GC traces through the live objects and compacts them.</span></span> <span data-ttu-id="868bf-144">但是由于压缩费用很高，GC 会扫过 LOH，列出没有被清除的对象列表以供以后重新使用，从而满足大型对象的分配请求。</span><span class="sxs-lookup"><span data-stu-id="868bf-144">But because compaction is expensive, the GC *sweeps* the LOH; it makes a free list out of dead objects that can be reused later to satisfy large object allocation requests.</span></span> <span data-ttu-id="868bf-145">相邻的被清除对象将组成一个自由对象。</span><span class="sxs-lookup"><span data-stu-id="868bf-145">Adjacent dead objects are made into one free object.</span></span>

<span data-ttu-id="868bf-146">.NET Core 和 .NET Framework（从 .NET Framework 4.5.1 开始）包括 <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode?displayProperty=nameWithType> 属性，该属性可让用户指定在下一完整阻止 GC 期间压缩 LOH。</span><span class="sxs-lookup"><span data-stu-id="868bf-146">.NET Core and .NET Framework (starting with .NET Framework 4.5.1) include the <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode?displayProperty=nameWithType> property that allows users to specify that the LOH should be compacted during the next full blocking GC.</span></span> <span data-ttu-id="868bf-147">并且在以后，.NET 可能会自动决定压缩 LOH。</span><span class="sxs-lookup"><span data-stu-id="868bf-147">And in the future, .NET may decide to compact the LOH automatically.</span></span> <span data-ttu-id="868bf-148">这就意味着，如果分配了大型对象并希望确保它们不被移动，则应将其固定起来。</span><span class="sxs-lookup"><span data-stu-id="868bf-148">This means that, if you allocate large objects and want to make sure that they don’t move, you should still pin them.</span></span>

<span data-ttu-id="868bf-149">图 1 说明了一种情况，在第一次第 0 代 GC 后 GC 形成了第 1 代，其中 `Obj1` 和 `Obj3` 被清除；在第一次第 1 代 GC 后形成了第 2 代，其中 `Obj2` 和 `Obj5` 被清除。</span><span class="sxs-lookup"><span data-stu-id="868bf-149">Figure 1 illustrates a scenario where the GC forms generation 1 after the first generation 0 GC where `Obj1` and `Obj3` are dead, and it forms generation 2 after the first generation 1 GC where `Obj2` and `Obj5` are dead.</span></span> <span data-ttu-id="868bf-150">请注意此图和下图仅用于说明，它们只包含能更好展示堆上的情况的极少几个对象。</span><span class="sxs-lookup"><span data-stu-id="868bf-150">Note that this and the following figures are only for illustration purposes; they contain very few objects to better show what happens on the heap.</span></span> <span data-ttu-id="868bf-151">实际上，GC 中通常包含更多的对象。</span><span class="sxs-lookup"><span data-stu-id="868bf-151">In reality, many more objects are typically involved in a GC.</span></span>

![图 1：第 0 代 GC 和第 1 代 GC](media/loh/loh-figure-1.jpg)  
<span data-ttu-id="868bf-153">图 1：第 0 代和第 1 代 GC。</span><span class="sxs-lookup"><span data-stu-id="868bf-153">Figure 1: A generation 0 and a generation 1 GC.</span></span>

<span data-ttu-id="868bf-154">图 2 显示了第 2 代 GC 发现 `Obj1` 和 `Obj2` 被清除后，GC 在内存中形成了相邻的可用空间，由 `Obj1` 和 `Obj2` 占用，然后用于满足 `Obj4` 的分配要求。</span><span class="sxs-lookup"><span data-stu-id="868bf-154">Figure 2 shows that after a generation 2 GC which saw that `Obj1` and `Obj2` are dead, the GC forms contiguous free space out of memory that used to be occupied by `Obj1` and `Obj2`, which then was used to satisfy an allocation request for `Obj4`.</span></span> <span data-ttu-id="868bf-155">从最后一个对象 `Obj3` 到此段末尾的空间仍可用于满足分配请求。</span><span class="sxs-lookup"><span data-stu-id="868bf-155">The space after the last object, `Obj3`, to end of the segment can also be used to satisfy allocation requests.</span></span>

![图 2：第 2 代 GC 之后](media/loh/loh-figure-2.jpg)  
<span data-ttu-id="868bf-157">图 2：第 2 代 GC 之后</span><span class="sxs-lookup"><span data-stu-id="868bf-157">Figure 2: After a generation 2 GC</span></span>

<span data-ttu-id="868bf-158">如果没有足够的可用空间来容纳大型对象分配请求，GC 首先尝试从操作系统获取更多段。</span><span class="sxs-lookup"><span data-stu-id="868bf-158">If there isn't enough free space to accommodate the large object allocation requests, the GC first attempts to acquire more segments from the OS.</span></span> <span data-ttu-id="868bf-159">如果失败了，它将触发第 2 代 GC，试图释放部分空间。</span><span class="sxs-lookup"><span data-stu-id="868bf-159">If that fails, it triggers a generation 2 GC in the hope of freeing up some space.</span></span>

<span data-ttu-id="868bf-160">在第 1 代或第 2 代 GC 期间，垃圾回收器会通过调用 [VirtualFree 功能](https://msdn.microsoft.com/library/windows/desktop/aa366892(v=vs.85).aspx)将不包含活动对象的段释放回操作系统。</span><span class="sxs-lookup"><span data-stu-id="868bf-160">During a generation 1 or generation 2 GC, the garbage collector releases segments that have no live objects on them back to the OS by calling the [VirtualFree function](https://msdn.microsoft.com/library/windows/desktop/aa366892(v=vs.85).aspx).</span></span> <span data-ttu-id="868bf-161">将退回最后一个活动对象到段末尾的空间（第 0 代/第 1 代存在的短暂段上的空间除外，垃圾回收器会在该段上会保存部分提交内容，因为应用程序将在其中立即分配）。</span><span class="sxs-lookup"><span data-stu-id="868bf-161">Space after the last live object to the end of the segment is decommitted (except on the ephemeral segment where gen0/gen1 live, where the garbage collector does keep some committed because your application will be allocating in it right away).</span></span> <span data-ttu-id="868bf-162">而且，尽管已重置可用空间，但仍会提交它们，这意味着操作系统无需将其中的数据重新写入磁盘。</span><span class="sxs-lookup"><span data-stu-id="868bf-162">And the free spaces remain committed though they are reset, meaning that the OS doesn’t need to write data in them back to disk.</span></span>

<span data-ttu-id="868bf-163">由于 LOH 仅在第 2 代 GC 期间进行回收，所以 LOH 段仅在此类 GC 期间可用。</span><span class="sxs-lookup"><span data-stu-id="868bf-163">Since the LOH is only collected during generation 2 GCs, the LOH segment can only be freed during such a GC.</span></span> <span data-ttu-id="868bf-164">图 3 说明了一种情况，在此情况下，垃圾回收器将某段（段 2）释放回操作系统并且退回剩余段上更多的空间。</span><span class="sxs-lookup"><span data-stu-id="868bf-164">Figure 3 illustrates a scenario where the garbage collector releases one segment (segment 2) back to the OS and decommits more space on the remaining segments.</span></span> <span data-ttu-id="868bf-165">如果需要使用该段末尾的已退回空间来满足大型对象分配请求，它会再次提交该内存。</span><span class="sxs-lookup"><span data-stu-id="868bf-165">If it needs to use the decommitted space at the end of the segment to satisfy large object allocation requests, it commits the memory again.</span></span> <span data-ttu-id="868bf-166">（有关提交/退回的解释说明，请参阅 [VirtualAlloc](https://msdn.microsoft.com/library/windows/desktop/aa366887(v=vs.85).aspx) 的文档）。</span><span class="sxs-lookup"><span data-stu-id="868bf-166">(For an explanation of commit/decommit, see the documentation for [VirtualAlloc](https://msdn.microsoft.com/library/windows/desktop/aa366887(v=vs.85).aspx).</span></span>

![图 3：第 2 代 GC 后的 LOH](media/loh/loh-figure-3.jpg)  
<span data-ttu-id="868bf-168">图 3：第 2 代 GC 后的 LOH</span><span class="sxs-lookup"><span data-stu-id="868bf-168">Figure 3: The LOH after a generation 2 GC</span></span>

## <a name="when-is-a-large-object-collected"></a><span data-ttu-id="868bf-169">何时收集大型对象？</span><span class="sxs-lookup"><span data-stu-id="868bf-169">When is a large object collected?</span></span>

<span data-ttu-id="868bf-170">通常情况下，出现以下三种情形中的任一情况，都会执行 GC：</span><span class="sxs-lookup"><span data-stu-id="868bf-170">In general, a GC occurs when one of the following following 3 conditions happens:</span></span>

- <span data-ttu-id="868bf-171">分配超出第 0 代或大型对象阈值。</span><span class="sxs-lookup"><span data-stu-id="868bf-171">Allocation exceeds the generation 0 or large object threshold.</span></span>

  <span data-ttu-id="868bf-172">阈值是某代的属性。</span><span class="sxs-lookup"><span data-stu-id="868bf-172">The threshold is a property of a generation.</span></span> <span data-ttu-id="868bf-173">垃圾回收器在其中分配对象时，会为代设置阈值。</span><span class="sxs-lookup"><span data-stu-id="868bf-173">A threshold for a generation is set when the garbage collector allocates objects into it.</span></span> <span data-ttu-id="868bf-174">超出阈值后，会在该代上触发 GC。</span><span class="sxs-lookup"><span data-stu-id="868bf-174">When the threshold is exceeded, a GC is triggered on that generation.</span></span> <span data-ttu-id="868bf-175">因此，分配小型或大型对象时，需要分别使用第 0 代和 LOH 的阈值。</span><span class="sxs-lookup"><span data-stu-id="868bf-175">When you allocate small or large objects, you consume generation 0 and the LOH’s thresholds, respectively.</span></span> <span data-ttu-id="868bf-176">当垃圾回收器分配到第 1 代和第 2 代中时，将使用它们的阈值。</span><span class="sxs-lookup"><span data-stu-id="868bf-176">When the garbage collector allocates into generation 1 and 2, it consumes their thresholds.</span></span> <span data-ttu-id="868bf-177">运行此程序时，会动态调整这些阈值。</span><span class="sxs-lookup"><span data-stu-id="868bf-177">These thresholds are dynamically tuned as the program runs.</span></span>

  <span data-ttu-id="868bf-178">这是典型情况，大部分 GC 执行都因为托管堆上的分配。</span><span class="sxs-lookup"><span data-stu-id="868bf-178">This is the typical case; most GCs happen because of allocations on the managed heap.</span></span>

- <span data-ttu-id="868bf-179">调用 <xref:System.GC.Collect%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="868bf-179">The <xref:System.GC.Collect%2A?displayProperty=nameWithType> method is called.</span></span>

  <span data-ttu-id="868bf-180">如果调用无参数 <xref:System.GC.Collect?displayProperty=nameWithType> 方法，或另一个重载作为参数传递到 <xref:System.GC.MaxGeneration?displayProperty=nameWithType>，将会一起收集 LOH 和剩余的托管堆。</span><span class="sxs-lookup"><span data-stu-id="868bf-180">If the parameterless <xref:System.GC.Collect?displayProperty=nameWithType> method is called or another overload is passed <xref:System.GC.MaxGeneration?displayProperty=nameWithType> as an argument, the LOH is collected along with the rest of the managed heap.</span></span>

- <span data-ttu-id="868bf-181">系统处于内存不足的状况。</span><span class="sxs-lookup"><span data-stu-id="868bf-181">The system is in low memory situation.</span></span>

  <span data-ttu-id="868bf-182">垃圾回收器收到来自操作系统 的高内存通知时，会发生以上情况。</span><span class="sxs-lookup"><span data-stu-id="868bf-182">This occurs when the garbage collector receives a high memory notification from the OS.</span></span> <span data-ttu-id="868bf-183">如果垃圾回收器认为执行第 2 代 GC 会有效率，它将触发第 2 代。</span><span class="sxs-lookup"><span data-stu-id="868bf-183">If the garbage collector thinks that doing a generation 2 GC will be productive, it triggers one.</span></span>

## <a name="loh-performance-implications"></a><span data-ttu-id="868bf-184">LOH 性能意义</span><span class="sxs-lookup"><span data-stu-id="868bf-184">LOH Performance Implications</span></span>

<span data-ttu-id="868bf-185">大型对象堆上的分配通过以下几种方式影响性能。</span><span class="sxs-lookup"><span data-stu-id="868bf-185">Allocations on the large object heap impact performance in the following ways.</span></span>

- <span data-ttu-id="868bf-186">分配成本。</span><span class="sxs-lookup"><span data-stu-id="868bf-186">Allocation cost.</span></span>

  <span data-ttu-id="868bf-187">CLR 确保清除了它提供的每个新对象的内存。</span><span class="sxs-lookup"><span data-stu-id="868bf-187">The CLR makes the guarantee that the memory for every new object it gives out is cleared.</span></span> <span data-ttu-id="868bf-188">这意味着大型对象的分配成本完全由清理的内存（除非触发了 GC）决定。</span><span class="sxs-lookup"><span data-stu-id="868bf-188">This means the allocation cost of a large object is completely dominated by memory clearing (unless it triggers a GC).</span></span> <span data-ttu-id="868bf-189">如果需要 2 轮才能清除一个字节，即需要 170,000 轮才能清除最小的大型对象。</span><span class="sxs-lookup"><span data-stu-id="868bf-189">If it takes 2 cycles to clear one byte, it takes 170,000 cycles to clear the smallest large object.</span></span> <span data-ttu-id="868bf-190">清除 2GHz 计算机上 16MB 对象的内存大约需要 16ms。</span><span class="sxs-lookup"><span data-stu-id="868bf-190">Clearing the memory of a 16MB object on a 2GHz machine takes approximately 16ms.</span></span> <span data-ttu-id="868bf-191">这些成本相当大。</span><span class="sxs-lookup"><span data-stu-id="868bf-191">That's a rather large cost.</span></span>

- <span data-ttu-id="868bf-192">回收成本。</span><span class="sxs-lookup"><span data-stu-id="868bf-192">Collection cost.</span></span>

  <span data-ttu-id="868bf-193">因为 LOH 和第 2 代一起回收，如果超出了它们之中任何一个的阈值，则触发第 2 代回收。</span><span class="sxs-lookup"><span data-stu-id="868bf-193">Because the LOH and generation 2 are collected together, if either one's threshold is exceeded, a generation 2 collection is triggered.</span></span> <span data-ttu-id="868bf-194">如果由于 LOH 触发第 2 代回收，第 2 代没有必要在 GC 后变得更小。</span><span class="sxs-lookup"><span data-stu-id="868bf-194">If a generation 2 collection is triggered because of the LOH, generation 2 won't necessarily be much smaller after the GC.</span></span> <span data-ttu-id="868bf-195">如果第 2 代上数据不多，则影响较小。</span><span class="sxs-lookup"><span data-stu-id="868bf-195">If there's not much data on generation 2, this has minimal impact.</span></span> <span data-ttu-id="868bf-196">但是，如果第 2 代很大，则触发多次第 2 代 GC 可能会产生性能问题。</span><span class="sxs-lookup"><span data-stu-id="868bf-196">But if generation 2 is large, it can cause performance problems if many generation 2 GCs are triggered.</span></span> <span data-ttu-id="868bf-197">如果很多大型对象都在非常短暂的基础上进行分配，并且拥有大型 SOH，则可能会花费太多时间来执行 GC。</span><span class="sxs-lookup"><span data-stu-id="868bf-197">If many large objects are allocated on a very temporary basis and you have a large SOH, you could be spending too much time doing GCs.</span></span> <span data-ttu-id="868bf-198">除此之外，如果连续分配并且释放真正的大型对象，那么分配成本可能会增加。</span><span class="sxs-lookup"><span data-stu-id="868bf-198">In addition, the allocation cost can really add up if you keep allocating and letting go of really large objects.</span></span>

- <span data-ttu-id="868bf-199">具有引用类型的数组元素。</span><span class="sxs-lookup"><span data-stu-id="868bf-199">Array elements with reference types.</span></span>

  <span data-ttu-id="868bf-200">LOH 上的特大型对象通常是数组（很少会有非常大的实例对象）。</span><span class="sxs-lookup"><span data-stu-id="868bf-200">Very large objects on the LOH are usually arrays (it's very rare to have an instance object that's really large).</span></span> <span data-ttu-id="868bf-201">如果数组的元素有丰富的引用，则可能产生成本；如果元素没有丰富的引用，将不会产生此类成本。</span><span class="sxs-lookup"><span data-stu-id="868bf-201">If the elements of an array are reference-rich, it incurs a cost that is not present if the elements are not reference-rich.</span></span> <span data-ttu-id="868bf-202">如果元素不包含任何引用，则垃圾回收器根本无需处理此数组。</span><span class="sxs-lookup"><span data-stu-id="868bf-202">If the element doesn’t contain any references, the garbage collector doesn’t need to go through the array at all.</span></span> <span data-ttu-id="868bf-203">例如，如果使用数组存储二进制树中的节点，一种实现方法是按实际节点引用某个节点的左侧节点和右侧节点：</span><span class="sxs-lookup"><span data-stu-id="868bf-203">For example, if you use an array to store nodes in a binary tree, one way to implement it is to refer to a node’s right and left node by the actual nodes:</span></span>

  ```csharp
  class Node
  {
     Data d;
     Node left;
     Node right;
  };

  Node[] binary_tr = new Node [num_nodes];
  ```

  <span data-ttu-id="868bf-204">如果 `num_nodes` 非常大，则垃圾回收器需要处理每个元素的至少两个引用。</span><span class="sxs-lookup"><span data-stu-id="868bf-204">If `num_nodes` is large, the garbage collector needs to go through at least two references per element.</span></span> <span data-ttu-id="868bf-205">另一种方法是存储左侧节点和右侧节点的索引：</span><span class="sxs-lookup"><span data-stu-id="868bf-205">An alternative approach is to store the index of the right and the left nodes:</span></span>

  ```csharp
  class Node
  {
     Data d;
     uint left_index;
     uint right_index;
  } ;
  ```

  <span data-ttu-id="868bf-206">不要将左侧节点的数据引用为 `left.d`，而是将其引用为 `binary_tr[left_index].d`。</span><span class="sxs-lookup"><span data-stu-id="868bf-206">Instead of referring the left node’s data as `left.d`, you refer to it as `binary_tr[left_index].d`.</span></span> <span data-ttu-id="868bf-207">而垃圾回收器无需查看左侧节点和右侧节点的任何引用。</span><span class="sxs-lookup"><span data-stu-id="868bf-207">And the garbage collector doesn’t need to look at any references for the left and right node.</span></span>

<span data-ttu-id="868bf-208">在这三种因素中，前两个通常比第三个更重要。</span><span class="sxs-lookup"><span data-stu-id="868bf-208">Out of the three factors, the first two are usually more significant than the third.</span></span> <span data-ttu-id="868bf-209">因此，建议分配重复使用的大型对象池，而不是分配临时大型对象。</span><span class="sxs-lookup"><span data-stu-id="868bf-209">Because of this, we recommend that you allocate a pool of large objects that you reuse instead of allocating temporary ones.</span></span>

## <a name="collecting-performance-data-for-the-loh"></a><span data-ttu-id="868bf-210">收集 LOH 的性能数据</span><span class="sxs-lookup"><span data-stu-id="868bf-210">Collecting performance data for the LOH</span></span>

<span data-ttu-id="868bf-211">收集特定区域的性能数据之前，应完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="868bf-211">Before you collect performance data for a specific area, you should already have done the following:</span></span>

1. <span data-ttu-id="868bf-212">找到应查看此区域的证据。</span><span class="sxs-lookup"><span data-stu-id="868bf-212">Found evidence that you should be looking at this area.</span></span>

2. <span data-ttu-id="868bf-213">排查你知道的其他区域，确保未发现可解释上述性能问题的内容。</span><span class="sxs-lookup"><span data-stu-id="868bf-213">Exhausted other areas that you know of without finding anything that could explain the performance problem you saw.</span></span>

<span data-ttu-id="868bf-214">参阅博客[尝试找出解决方案之前先了解问题](https://blogs.msdn.microsoft.com/maoni/2006/09/01/understand-the-problem-before-you-try-to-find-a-solution/)获取内存和 CPU 的基础知识的详细信息。</span><span class="sxs-lookup"><span data-stu-id="868bf-214">See the blog [Understand the problem before you try to find a solution](https://blogs.msdn.microsoft.com/maoni/2006/09/01/understand-the-problem-before-you-try-to-find-a-solution/) for more information on the fundamentals of memory and the CPU.</span></span>

<span data-ttu-id="868bf-215">可使用以下工具来收集 LOH 性能数据：</span><span class="sxs-lookup"><span data-stu-id="868bf-215">You can use the following tools to collect data on LOH performance:</span></span>

- [<span data-ttu-id="868bf-216">.NET CLR 内存性能计数器</span><span class="sxs-lookup"><span data-stu-id="868bf-216">.NET CLR memory performance counters</span></span>](#net-clr-memory-performance-counters)

- [<span data-ttu-id="868bf-217">ETW 事件</span><span class="sxs-lookup"><span data-stu-id="868bf-217">ETW events</span></span>](#etw-events)

- [<span data-ttu-id="868bf-218">调试器</span><span class="sxs-lookup"><span data-stu-id="868bf-218">A debugger</span></span>](#a-debugger)

### <a name="net-clr-memory-performance-counters"></a><span data-ttu-id="868bf-219">.NET CLR 内存性能计数器</span><span class="sxs-lookup"><span data-stu-id="868bf-219">.NET CLR Memory Performance counters</span></span>

<span data-ttu-id="868bf-220">这些性能计数器通常是调查性能问题的第一步（但是推荐使用 [ETW 事件](#etw)）。</span><span class="sxs-lookup"><span data-stu-id="868bf-220">These performance counters are usually a good first step in investigating performance issues (although we recommend that you use [ETW events](#etw)).</span></span> <span data-ttu-id="868bf-221">通过添加所需计数器配置性能监视器，如图 4 所示。</span><span class="sxs-lookup"><span data-stu-id="868bf-221">You configure Performance Monitor by adding the counters that you want, as Figure 4 shows.</span></span> <span data-ttu-id="868bf-222">与 LOH 相关的是：</span><span class="sxs-lookup"><span data-stu-id="868bf-222">The ones that are relevant for the LOH are:</span></span>

- <span data-ttu-id="868bf-223">第 2 代回收次数</span><span class="sxs-lookup"><span data-stu-id="868bf-223">**Gen 2 Collections**</span></span>

   <span data-ttu-id="868bf-224">显示自进程开始起第 2 代 GC 发生的次数。</span><span class="sxs-lookup"><span data-stu-id="868bf-224">Displays the number of times generation 2 GCs have occurred since the process started.</span></span> <span data-ttu-id="868bf-225">此计数器在第 2 代回收结束时递增（也称为完整垃圾回收）。</span><span class="sxs-lookup"><span data-stu-id="868bf-225">The counter is incremented at the end of a generation 2 collection (also called a full garbage collection).</span></span> <span data-ttu-id="868bf-226">此计数器显示上次观测的值。</span><span class="sxs-lookup"><span data-stu-id="868bf-226">This counter displays the last observed value.</span></span>

- <span data-ttu-id="868bf-227">**大型对象堆大小**</span><span class="sxs-lookup"><span data-stu-id="868bf-227">**Large Object Heap size**</span></span>

   <span data-ttu-id="868bf-228">以字节显示当前大小，包括 LOH 的可用空间。</span><span class="sxs-lookup"><span data-stu-id="868bf-228">Displays the current size, in bytes, including free space, of the LOH.</span></span> <span data-ttu-id="868bf-229">此计数器在垃圾回收结束时更新，不在每次分配时更新。</span><span class="sxs-lookup"><span data-stu-id="868bf-229">This counter is updated at the end of a garbage collection, not at each allocation.</span></span>

<span data-ttu-id="868bf-230">查看性能计数器的常用方法是使用性能监视器 (perfmon.exe)。</span><span class="sxs-lookup"><span data-stu-id="868bf-230">A common way to look at performance counters is with Performance Monitor (perfmon.exe).</span></span> <span data-ttu-id="868bf-231">使用“添加计数器”可为关注的进程添加感兴趣的计数器。</span><span class="sxs-lookup"><span data-stu-id="868bf-231">Use “Add Counters” to add the interesting counter for processes that you care about.</span></span> <span data-ttu-id="868bf-232">可将性能计数器数据保存在日志文件中，如图 4 所示。</span><span class="sxs-lookup"><span data-stu-id="868bf-232">You can save the performance counter data to a log file, as Figure 4 shows.</span></span>

![图 4：添加性能计数器。](media/loh/perfcounter.png)  
<span data-ttu-id="868bf-234">图 4：第 2 代 GC 后的 LOH</span><span class="sxs-lookup"><span data-stu-id="868bf-234">Figure 4: The LOH after a generation 2 GC</span></span>

<span data-ttu-id="868bf-235">也可以编程方式查询性能计数器。</span><span class="sxs-lookup"><span data-stu-id="868bf-235">Performance counters can also be queried programmatically.</span></span> <span data-ttu-id="868bf-236">大部分人在例行测试过程中都采用此方式进行收集。</span><span class="sxs-lookup"><span data-stu-id="868bf-236">Many people collect them this way as part of their routine testing process.</span></span> <span data-ttu-id="868bf-237">如果发现计数器显示的值不正常，则可以使用其他方法获得更多详细信息以帮助调查。</span><span class="sxs-lookup"><span data-stu-id="868bf-237">When they spot counters with values that are out of the ordinary, they use other means to get more detailed data to help with the investigation.</span></span>

> [!NOTE]
> <span data-ttu-id="868bf-238">建议使用 ETW 事件代替性能计数，因为 ETW 提供更丰富的信息。</span><span class="sxs-lookup"><span data-stu-id="868bf-238">We recommend that you to use ETW events instead of performance counters, because ETW provides much richer information.</span></span>

### <a name="etw"></a><span data-ttu-id="868bf-239">ETW</span><span class="sxs-lookup"><span data-stu-id="868bf-239">ETW</span></span>

<span data-ttu-id="868bf-240">垃圾回收器提供丰富的 ETW 事件集，帮助了解堆的工作内容和工作原理。</span><span class="sxs-lookup"><span data-stu-id="868bf-240">The garbage collector provides a rich set of ETW events to help you understand what the heap is doing and why.</span></span> <span data-ttu-id="868bf-241">以下博客文章演示了如何使用 ETW 收集和了解 GC 事件：</span><span class="sxs-lookup"><span data-stu-id="868bf-241">The following blog posts show how to collect and understand GC events with ETW:</span></span>

- [<span data-ttu-id="868bf-242">GC ETW 事件 - 1</span><span class="sxs-lookup"><span data-stu-id="868bf-242">GC ETW Events - 1</span></span>](https://blogs.msdn.microsoft.com/maoni/2014/12/22/gc-etw-events-1/)

- [<span data-ttu-id="868bf-243">GC ETW 事件 - 2</span><span class="sxs-lookup"><span data-stu-id="868bf-243">GC ETW Events - 2</span></span>](https://blogs.msdn.microsoft.com/maoni/2014/12/25/gc-etw-events-2/)

- [<span data-ttu-id="868bf-244">GC ETW 事件 - 3</span><span class="sxs-lookup"><span data-stu-id="868bf-244">GC ETW Events - 3</span></span>](https://blogs.msdn.microsoft.com/maoni/2014/12/25/gc-etw-events-3/)

- [<span data-ttu-id="868bf-245">GC ETW 事件 - 4</span><span class="sxs-lookup"><span data-stu-id="868bf-245">GC ETW Events - 4</span></span>](https://blogs.msdn.microsoft.com/maoni/2014/12/30/gc-etw-events-4/)

<span data-ttu-id="868bf-246">若要标识由临时 LOH 分配造成的过多第 2 代 GC 次数，请查看 GC 的“触发原因”列。</span><span class="sxs-lookup"><span data-stu-id="868bf-246">To identify excessive generation 2 GCs caused by temporary LOH allocations, look at the Trigger Reason column for GCs.</span></span> <span data-ttu-id="868bf-247">有关仅分配临时大型对象的简单测试，可使用以下 [PerfView](https://www.microsoft.com/download/details.aspx?id=28567) 命令行收集 ETW 事件的信息：</span><span class="sxs-lookup"><span data-stu-id="868bf-247">For a simple test that only allocates temporary large objects, you can collect information on ETW events with the following [PerfView](https://www.microsoft.com/download/details.aspx?id=28567) command line:</span></span>

```console
perfview /GCCollectOnly /AcceptEULA /nogui collect
```

<span data-ttu-id="868bf-248">结果类似于以下类容：</span><span class="sxs-lookup"><span data-stu-id="868bf-248">The result is something like this:</span></span>

![图 5：使用 PerfView 检查 ETW 事件](media/loh/perfview.png)  
<span data-ttu-id="868bf-250">图 5：使用 PerfView 显示的 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="868bf-250">Figure 5: ETW events shown using PerfView</span></span>

<span data-ttu-id="868bf-251">如下所示，所有 GC 都是第 2 代 GC，并且都由 AllocLarge 触发，这表示分配大型对象会触发此 GC。</span><span class="sxs-lookup"><span data-stu-id="868bf-251">As you can see, all GCs are generation 2 GCs, and they are all triggered by AllocLarge, which means that allocating a large object triggered this GC.</span></span> <span data-ttu-id="868bf-252">我们知道这些分配是临时的，因为“LOH 未清理率 %”列显示为 1%。</span><span class="sxs-lookup"><span data-stu-id="868bf-252">We know that these allocations are temporary because the **LOH Survival Rate %** column says 1%.</span></span>

<span data-ttu-id="868bf-253">可以收集显示分配这些大写对象的人员的其他 ETW 事件。</span><span class="sxs-lookup"><span data-stu-id="868bf-253">You can collect additional ETW events that tell you who allocated these large objects.</span></span> <span data-ttu-id="868bf-254">以下命令行：</span><span class="sxs-lookup"><span data-stu-id="868bf-254">The following command line:</span></span>

```console
perfview /GCOnly /AcceptEULA /nogui collect
```

<span data-ttu-id="868bf-255">收集 AllocationTick 事件，大约每 10 万次分配就会触发该事件。</span><span class="sxs-lookup"><span data-stu-id="868bf-255">collects an AllocationTick event which is fired approximately every 100k worth of allocations.</span></span> <span data-ttu-id="868bf-256">换句话说，每次分配大型对象都会触发事件。</span><span class="sxs-lookup"><span data-stu-id="868bf-256">In other words, an event is fired each time a large object is allocated.</span></span> <span data-ttu-id="868bf-257">然后可查看某个 GC 堆分配视图，该视图显示分配大型对象的调用堆栈：</span><span class="sxs-lookup"><span data-stu-id="868bf-257">You can then look at one of the GC Heap Alloc views which show you the callstacks that allocated large objects:</span></span>

![图 6：GC 堆分配视图](media/loh/perfview2.png)  
<span data-ttu-id="868bf-259">图 6：GC 堆分配视图</span><span class="sxs-lookup"><span data-stu-id="868bf-259">Figure 6: A GC Heap Alloc view</span></span>

<span data-ttu-id="868bf-260">如图所示，这是从 `Main` 方法分配大型对象的简单测试。</span><span class="sxs-lookup"><span data-stu-id="868bf-260">As you can see, this is a very simple test that just allocates large objects from its `Main` method.</span></span>

### <a name="a-debugger"></a><span data-ttu-id="868bf-261">调试器</span><span class="sxs-lookup"><span data-stu-id="868bf-261">A debugger</span></span>

<span data-ttu-id="868bf-262">如果只有内存转储，则需要查看 LOH 上实际有哪些对象，你可使用 .NET 提供的 [SoS 调试器扩展](http://msdn2.microsoft.com/ms404370.aspx)来查看。</span><span class="sxs-lookup"><span data-stu-id="868bf-262">If all you have is a memory dump and you need to look at what objects are actually on the LOH, you can use the [SoS debugger extension](http://msdn2.microsoft.com/ms404370.aspx) provided by .NET.</span></span>

> [!NOTE]
> <span data-ttu-id="868bf-263">此部分提到的调试命令适用于 [Windows 调试器](https://www.microsoft.com/whdc/devtools/debugging/default.mspx)。</span><span class="sxs-lookup"><span data-stu-id="868bf-263">The debugging commands mentioned in this section are applicable to the [Windows Debuggers](https://www.microsoft.com/whdc/devtools/debugging/default.mspx).</span></span>

<span data-ttu-id="868bf-264">以下内容显示了分析 LOH 的示例输出：</span><span class="sxs-lookup"><span data-stu-id="868bf-264">The following shows sample output from analyzing the LOH:</span></span>

```
0:003> .loadby sos mscorwks
0:003> !eeheap -gc
Number of GC Heaps: 1
generation 0 starts at 0x013e35ec
sdgeneration 1 starts at 0x013e1b6c
generation 2 starts at 0x013e1000
ephemeral segment allocation context: none
segment   begin allocated     size
0018f2d0 790d5588 790f4b38 0x0001f5b0(128432)
013e0000 013e1000 013e35f8 0x000025f8(9720)
Large object heap starts at 0x023e1000
segment   begin allocated     size
023e0000 023e1000 033db630 0x00ffa630(16754224)
033e0000 033e1000 043cdf98 0x00fecf98(16699288)
043e0000 043e1000 05368b58 0x00f87b58(16284504)
Total Size 0x2f90cc8(49876168)
------------------------------
GC Heap Size 0x2f90cc8(49876168)
0:003> !dumpheap -stat 023e1000 033db630
total 133 objects
Statistics:
MT   Count   TotalSize Class Name
001521d0       66     2081792     Free
7912273c       63     6663696 System.Byte[]
7912254c       4     8008736 System.Object[]
Total 133 objects
```

<span data-ttu-id="868bf-265">LOH 堆大小为 (16,754,224 + 16,699,288 + 16,284,504) = 49,738,016 字节。</span><span class="sxs-lookup"><span data-stu-id="868bf-265">The LOH heap size is (16,754,224 + 16,699,288 + 16,284,504) = 49,738,016 bytes.</span></span> <span data-ttu-id="868bf-266">在地址 023e1000 和地址 033db630 之间，8,008,736 字节由 <xref:System.Object?displayProperty=nameWithType> 对象的数组占用，6,663,696 字节由 <xref:System.Byte?displayProperty=nameWithType> 对象的数组占用，2,081,792 字节由可用空间占用。</span><span class="sxs-lookup"><span data-stu-id="868bf-266">Between addresses 023e1000 and 033db630, 8,008,736 bytes are occupied by an array of <xref:System.Object?displayProperty=nameWithType> objects, 6,663,696 bytes are occupied by an array of <xref:System.Byte?displayProperty=nameWithType>  objects, and 2,081,792 bytes are occupied by free space.</span></span>

<span data-ttu-id="868bf-267">有时，调试器显示 LOH 的总大小少于 85,000 个字节。</span><span class="sxs-lookup"><span data-stu-id="868bf-267">Sometimes, the debugger shows that the total size of the LOH is less than 85,000 bytes.</span></span> <span data-ttu-id="868bf-268">这是由于运行时本身使用 LOH 分配某些小于大型对象的对象引起的。</span><span class="sxs-lookup"><span data-stu-id="868bf-268">This happens because the runtime itself uses the LOH to allocate some objects that are smaller than a large object.</span></span>

<span data-ttu-id="868bf-269">因为不会压缩 LOH，有时会怀疑 LOH 是碎片源。</span><span class="sxs-lookup"><span data-stu-id="868bf-269">Because the LOH is not compacted, sometimes the LOH is thoought to be the source of fragmentation.</span></span> <span data-ttu-id="868bf-270">碎片表示：</span><span class="sxs-lookup"><span data-stu-id="868bf-270">Fragmentation means:</span></span>

- <span data-ttu-id="868bf-271">托管堆的碎片由托管对象之间的可用空间量来表示。</span><span class="sxs-lookup"><span data-stu-id="868bf-271">Fragmentation of the managed heap, which is indicated by the amount of free space between managed objects.</span></span> <span data-ttu-id="868bf-272">在 SoS 中，`!dumpheap –type Free` 命令显示托管对象之间的可用空间量。</span><span class="sxs-lookup"><span data-stu-id="868bf-272">In SoS, the `!dumpheap –type Free` command displays the amount of free space between managed objects.</span></span>

- <span data-ttu-id="868bf-273">虚拟内存 (VM) 地址空间的碎片是标识为 `MEM_FREE` 的内存。</span><span class="sxs-lookup"><span data-stu-id="868bf-273">Fragmentation of the virtual memory (VM) address space, which is the memory marked as `MEM_FREE`.</span></span> <span data-ttu-id="868bf-274">可在 windbg 中使用各种调试器命令来获取碎片。</span><span class="sxs-lookup"><span data-stu-id="868bf-274">You can get it by using various debugger commands in windbg.</span></span>

   <span data-ttu-id="868bf-275">以下示例显示 VM 空间中的碎片：</span><span class="sxs-lookup"><span data-stu-id="868bf-275">The following example shows fragmentation in the VM space:</span></span>

   ```
   0:000> !address
   00000000 : 00000000 - 00010000
   Type     00000000
   Protect 00000001 PAGE_NOACCESS
   State   00010000 MEM_FREE
   Usage   RegionUsageFree
   00010000 : 00010000 - 00002000
   Type     00020000 MEM_PRIVATE
   Protect 00000004 PAGE_READWRITE
   State   00001000 MEM_COMMIT
   Usage   RegionUsageEnvironmentBlock
   00012000 : 00012000 - 0000e000
   Type     00000000
   Protect 00000001 PAGE_NOACCESS
   State   00010000 MEM_FREE
   Usage   RegionUsageFree
   … [omitted]
   -------------------- Usage SUMMARY --------------------------
   TotSize (     KB)   Pct(Tots) Pct(Busy)   Usage
   701000 (   7172) : 00.34%   20.69%   : RegionUsageIsVAD
   7de15000 ( 2062420) : 98.35%   00.00%   : RegionUsageFree
   1452000 (   20808) : 00.99%   60.02%   : RegionUsageImage
   300000 (   3072) : 00.15%   08.86%   : RegionUsageStack
   3000 (     12) : 00.00%   00.03%   : RegionUsageTeb
   381000 (   3588) : 00.17%   10.35%   : RegionUsageHeap
   0 (       0) : 00.00%   00.00%   : RegionUsagePageHeap
   1000 (       4) : 00.00%   00.01%   : RegionUsagePeb
   1000 (       4) : 00.00%   00.01%   : RegionUsageProcessParametrs
   2000 (       8) : 00.00%   00.02%   : RegionUsageEnvironmentBlock
   Tot: 7fff0000 (2097088 KB) Busy: 021db000 (34668 KB)

   -------------------- Type SUMMARY --------------------------
   TotSize (     KB)   Pct(Tots) Usage
   7de15000 ( 2062420) : 98.35%   : <free>
   1452000 (   20808) : 00.99%   : MEM_IMAGE
   69f000 (   6780) : 00.32%   : MEM_MAPPED
   6ea000 (   7080) : 00.34%   : MEM_PRIVATE

   -------------------- State SUMMARY --------------------------
   TotSize (     KB)   Pct(Tots) Usage
   1a58000 (   26976) : 01.29%   : MEM_COMMIT
   7de15000 ( 2062420) : 98.35%   : MEM_FREE
   783000 (   7692) : 00.37%   : MEM_RESERVE

   Largest free region: Base 01432000 - Size 707ee000 (1843128 KB)
   ```

<span data-ttu-id="868bf-276">通常看到的更多是由临时大型对象导致的 VM 碎片，这些对象要求垃圾回收器频繁从操作系统获取新的托管堆段，并将空托管堆段释放回操作系统。</span><span class="sxs-lookup"><span data-stu-id="868bf-276">It’s more common to see VM fragmentation caused by temporary large objects that require the garbage collector to frequently acquire new managed heap segments from the OS and to release empty ones back to the OS.</span></span>

<span data-ttu-id="868bf-277">要验证 LOH 是否会生成 VM 碎片，可在 [VirtualAlloc](https://msdn.microsoft.com/library/windows/desktop/aa366887(v=vs.85).aspx) 和 [VirtualFree](https://msdn.microsoft.com/library/windows/desktop/aa366892(v=vs.85).aspx) 上设置一个断点，查看是谁调用了它们。</span><span class="sxs-lookup"><span data-stu-id="868bf-277">To verify whether the LOH is causing VM fragmentation, you can set a breakpoint on [VirtualAlloc](https://msdn.microsoft.com/library/windows/desktop/aa366887(v=vs.85).aspx) and [VirtualFree](https://msdn.microsoft.com/library/windows/desktop/aa366892(v=vs.85).aspx) to see who call them.</span></span> <span data-ttu-id="868bf-278">例如，如果想知道谁曾尝试从操作系统分配大于 8MBB 的虚拟内存块，可按以下方式设置断点：</span><span class="sxs-lookup"><span data-stu-id="868bf-278">For example, to see who tried to allocate virtual memory chunks larger than 8MBB from the OS, you can set a breakpoint like this:</span></span>

```console
bp kernel32!virtualalloc "j (dwo(@esp+8)>800000) 'kb';'g'"
```

<span data-ttu-id="868bf-279">只有在分配大小大于 8MB (0x800000) 的情况下调用 [VirtualAlloc](https://msdn.microsoft.com/library/windows/desktop/aa366887(v=vs.85).aspx) 时，此命令才会进入调试器并显示调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="868bf-279">This command breaks into the debugger and shows the callstack only if [VirtualAlloc](https://msdn.microsoft.com/library/windows/desktop/aa366887(v=vs.85).aspx) is called with an allocation size greater than 8MB (0x800000).</span></span>

<span data-ttu-id="868bf-280">CLR 2.0 增加了称为“VM 囤积”的功能，用于频繁获取和释放段（包括在大型和小型对象堆上）的情况。</span><span class="sxs-lookup"><span data-stu-id="868bf-280">CLR 2.0 added a feature called *VM Hoarding* that can be useful for scenarious where segments (including on the large and small object heaps) are frequently acquired and released.</span></span> <span data-ttu-id="868bf-281">若要指定 VM 囤积，可通过托管 API 指定称为 `STARTUP_HOARD_GC_VM` 的启动标记。</span><span class="sxs-lookup"><span data-stu-id="868bf-281">To specify VM Hoarding, you specify a startup flag called `STARTUP_HOARD_GC_VM` via the hosting API.</span></span> <span data-ttu-id="868bf-282">CLR 退回这些段上的内存并将其添加到备用列表中，而不会将该空段释放回操作系统。</span><span class="sxs-lookup"><span data-stu-id="868bf-282">Instead of releasing empty segments back to the OS, the CLR decommits the memory on these segments and puts them on a standby list.</span></span> <span data-ttu-id="868bf-283">（请注意 CLR 不会针对太大型的段执行此操作。）CLR 稍后将使用这些段来满足新段请求。</span><span class="sxs-lookup"><span data-stu-id="868bf-283">(Note that the CLR doesn't do this for segments that are too large.) The CLR later uses those segments to satisfy new segment requests.</span></span> <span data-ttu-id="868bf-284">下一次应用需要新段时，CLR 将使用此备用列表中的某个足够大的段。</span><span class="sxs-lookup"><span data-stu-id="868bf-284">The next time that your app needs a new segment, the CLR uses one from this standby list if it can find one that’s big enough.</span></span>

<span data-ttu-id="868bf-285">VM 囤积还可用于想要保存已获取的段的应用程序（例如属于系统上运行的主要应用的部分服务器应用），以避免内存不足的异常。</span><span class="sxs-lookup"><span data-stu-id="868bf-285">VM hoarding is also useful for applications that want to hold onto the segments that they already acquired, such as some server apps that are the dominant apps running on the system, to avoid out of memory exceptions.</span></span>

<span data-ttu-id="868bf-286">强烈建议你在使用此功能时认真测试应用程序，以确保应用程序的内存使用情况比较稳定。</span><span class="sxs-lookup"><span data-stu-id="868bf-286">We strongly recommend that you carefully test your application when you use this feature to ensure your application has fairly stable memory usage.</span></span>
