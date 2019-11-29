---
title: 垃圾回收的基本知识
description: 了解垃圾回收器的工作原理以及如何配置它以获得最佳性能。
ms.date: 11/15/2019
ms.technology: dotnet-standard
helpviewer_keywords:
- garbage collection, generations
- garbage collection, background
- garbage collection, concurrent
- garbage collection, server
- garbage collection, workstation
- garbage collection, managed heap
ms.assetid: 67c5a20d-1be1-4ea7-8a9a-92b0b08658d2
ms.openlocfilehash: ea8aef03d2f5837f35ecb31209e57853c0c8257b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330421"
---
# <a name="fundamentals-of-garbage-collection"></a><span data-ttu-id="2ca49-103">垃圾回收的基本知识</span><span class="sxs-lookup"><span data-stu-id="2ca49-103">Fundamentals of garbage collection</span></span>

<span data-ttu-id="2ca49-104">在公共语言运行时 (CLR) 中，垃圾回收器 (GC) 用作自动内存管理器。</span><span class="sxs-lookup"><span data-stu-id="2ca49-104">In the common language runtime (CLR), the garbage collector (GC) serves as an automatic memory manager.</span></span> <span data-ttu-id="2ca49-105">它提供如下优点：</span><span class="sxs-lookup"><span data-stu-id="2ca49-105">It provides the following benefits:</span></span>

- <span data-ttu-id="2ca49-106">使你可以在开发应用程序时不必手动释放内存。</span><span class="sxs-lookup"><span data-stu-id="2ca49-106">Enables you to develop your application without having to manually free memory.</span></span>

- <span data-ttu-id="2ca49-107">有效分配托管堆上的对象。</span><span class="sxs-lookup"><span data-stu-id="2ca49-107">Allocates objects on the managed heap efficiently.</span></span>

- <span data-ttu-id="2ca49-108">回收不再使用的对象，清除它们的内存，并保留内存以用于将来分配。</span><span class="sxs-lookup"><span data-stu-id="2ca49-108">Reclaims objects that are no longer being used, clears their memory, and keeps the memory available for future allocations.</span></span> <span data-ttu-id="2ca49-109">托管对象会自动获取干净的内容来开始，因此，它们的构造函数不必对每个数据字段进行初始化。</span><span class="sxs-lookup"><span data-stu-id="2ca49-109">Managed objects automatically get clean content to start with, so their constructors do not have to initialize every data field.</span></span>

- <span data-ttu-id="2ca49-110">通过确保对象不能使用另一个对象的内容来提供内存安全。</span><span class="sxs-lookup"><span data-stu-id="2ca49-110">Provides memory safety by making sure that an object cannot use the content of another object.</span></span>

<span data-ttu-id="2ca49-111">本文章介绍垃圾回收的核心概念。</span><span class="sxs-lookup"><span data-stu-id="2ca49-111">This article describes the core concepts of garbage collection.</span></span>

## <a name="fundamentals-of-memory"></a><span data-ttu-id="2ca49-112">内存基础知识</span><span class="sxs-lookup"><span data-stu-id="2ca49-112">Fundamentals of memory</span></span>

<span data-ttu-id="2ca49-113">下面的列表总结了重要的 CLR 内存概念。</span><span class="sxs-lookup"><span data-stu-id="2ca49-113">The following list summarizes important CLR memory concepts.</span></span>

- <span data-ttu-id="2ca49-114">每个进程都有其自己单独的虚拟地址空间。</span><span class="sxs-lookup"><span data-stu-id="2ca49-114">Each process has its own, separate virtual address space.</span></span> <span data-ttu-id="2ca49-115">同一台计算机上的所有进程共享相同的物理内存和页文件（如果有）。</span><span class="sxs-lookup"><span data-stu-id="2ca49-115">All processes on the same computer share the same physical memory and the page file, if there is one.</span></span>

- <span data-ttu-id="2ca49-116">默认情况下，32 位计算机上的每个进程都具有 2 GB 的用户模式虚拟地址空间。</span><span class="sxs-lookup"><span data-stu-id="2ca49-116">By default, on 32-bit computers, each process has a 2-GB user-mode virtual address space.</span></span>

- <span data-ttu-id="2ca49-117">作为一名应用程序开发人员，你只能使用虚拟地址空间，请勿直接操控物理内存。</span><span class="sxs-lookup"><span data-stu-id="2ca49-117">As an application developer, you work only with virtual address space and never manipulate physical memory directly.</span></span> <span data-ttu-id="2ca49-118">垃圾回收器为你分配和释放托管堆上的虚拟内存。</span><span class="sxs-lookup"><span data-stu-id="2ca49-118">The garbage collector allocates and frees virtual memory for you on the managed heap.</span></span>

  <span data-ttu-id="2ca49-119">如果你编写的是本机代码，请使用 Windows 函数处理虚拟地址空间。</span><span class="sxs-lookup"><span data-stu-id="2ca49-119">If you are writing native code, you use Windows functions to work with the virtual address space.</span></span> <span data-ttu-id="2ca49-120">这些函数为你分配和释放本机堆上的虚拟内存。</span><span class="sxs-lookup"><span data-stu-id="2ca49-120">These functions allocate and free virtual memory for you on native heaps.</span></span>

- <span data-ttu-id="2ca49-121">虚拟内存有三种状态：</span><span class="sxs-lookup"><span data-stu-id="2ca49-121">Virtual memory can be in three states:</span></span>

  - <span data-ttu-id="2ca49-122">可用。</span><span class="sxs-lookup"><span data-stu-id="2ca49-122">Free.</span></span> <span data-ttu-id="2ca49-123">该内存块没有引用关系，可用于分配。</span><span class="sxs-lookup"><span data-stu-id="2ca49-123">The block of memory has no references to it and is available for allocation.</span></span>

  - <span data-ttu-id="2ca49-124">保留。</span><span class="sxs-lookup"><span data-stu-id="2ca49-124">Reserved.</span></span> <span data-ttu-id="2ca49-125">内存块可供你使用，并且不能用于任何其他分配请求。</span><span class="sxs-lookup"><span data-stu-id="2ca49-125">The block of memory is available for your use and cannot be used for any other allocation request.</span></span> <span data-ttu-id="2ca49-126">但是，在该内存块提交之前，你无法将数据存储到其中。</span><span class="sxs-lookup"><span data-stu-id="2ca49-126">However, you cannot store data to this memory block until it is committed.</span></span>

  - <span data-ttu-id="2ca49-127">提交。</span><span class="sxs-lookup"><span data-stu-id="2ca49-127">Committed.</span></span> <span data-ttu-id="2ca49-128">内存块已指派给物理存储。</span><span class="sxs-lookup"><span data-stu-id="2ca49-128">The block of memory is assigned to physical storage.</span></span>

- <span data-ttu-id="2ca49-129">可能会存在虚拟地址空间碎片。</span><span class="sxs-lookup"><span data-stu-id="2ca49-129">Virtual address space can get fragmented.</span></span> <span data-ttu-id="2ca49-130">就是说地址空间中存在一些被称为孔的可用块。</span><span class="sxs-lookup"><span data-stu-id="2ca49-130">This means that there are free blocks, also known as holes, in the address space.</span></span> <span data-ttu-id="2ca49-131">当请求虚拟内存分配时，虚拟内存管理器必须找到满足该分配请求的足够大的单个可用块。</span><span class="sxs-lookup"><span data-stu-id="2ca49-131">When a virtual memory allocation is requested, the virtual memory manager has to find a single free block that is large enough to satisfy that allocation request.</span></span> <span data-ttu-id="2ca49-132">即使有 2GB 可用空间，2GB 分配请求也会失败，除非所有这些可用空间都位于一个地址块中。</span><span class="sxs-lookup"><span data-stu-id="2ca49-132">Even if you have 2 GB of free space, the allocation that requires 2 GB will be unsuccessful unless all of that free space is in a single address block.</span></span>

- <span data-ttu-id="2ca49-133">如果没有足够的可供保留的虚拟地址空间或可供提交的物理空间，则可能会用尽内存。</span><span class="sxs-lookup"><span data-stu-id="2ca49-133">You can run out of memory if there isn't enough virtual address space to reserve or physical space to commit.</span></span>

  <span data-ttu-id="2ca49-134">即使在物理内存压力（即物理内存的需求）较低的情况下也会使用页文件。</span><span class="sxs-lookup"><span data-stu-id="2ca49-134">The page file is used even if physical memory pressure (that is, demand for physical memory) is low.</span></span> <span data-ttu-id="2ca49-135">首次出现物理内存压力较高的情况时，操作系统必须在物理内存中腾出空间来存储数据，并将物理内存中的部分数据备份到页文件中。</span><span class="sxs-lookup"><span data-stu-id="2ca49-135">The first time physical memory pressure is high, the operating system must make room in physical memory to store data, and it backs up some of the data that is in physical memory to the page file.</span></span> <span data-ttu-id="2ca49-136">该数据只会在需要时进行分页，所以在物理内存压力较低的情况下也可能会进行分页。</span><span class="sxs-lookup"><span data-stu-id="2ca49-136">That data is not paged until it's needed, so it's possible to encounter paging in situations where the physical memory pressure is low.</span></span>

## <a name="conditions-for-a-garbage-collection"></a><span data-ttu-id="2ca49-137">垃圾回收的条件</span><span class="sxs-lookup"><span data-stu-id="2ca49-137">Conditions for a garbage collection</span></span>

<span data-ttu-id="2ca49-138">当满足以下条件之一时将发生垃圾回收：</span><span class="sxs-lookup"><span data-stu-id="2ca49-138">Garbage collection occurs when one of the following conditions is true:</span></span>

- <span data-ttu-id="2ca49-139">系统具有低的物理内存。</span><span class="sxs-lookup"><span data-stu-id="2ca49-139">The system has low physical memory.</span></span> <span data-ttu-id="2ca49-140">这是通过 OS 的内存不足通知或主机指示的内存不足检测出来。</span><span class="sxs-lookup"><span data-stu-id="2ca49-140">This is detected by either the low memory notification from the OS or low memory as indicated by the host.</span></span>

- <span data-ttu-id="2ca49-141">由托管堆上已分配的对象使用的内存超出了可接受的阈值。</span><span class="sxs-lookup"><span data-stu-id="2ca49-141">The memory that is used by allocated objects on the managed heap surpasses an acceptable threshold.</span></span> <span data-ttu-id="2ca49-142">随着进程的运行，此阈值会不断地进行调整。</span><span class="sxs-lookup"><span data-stu-id="2ca49-142">This threshold is continuously adjusted as the process runs.</span></span>

- <span data-ttu-id="2ca49-143">调用 <xref:System.GC.Collect%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="2ca49-143">The <xref:System.GC.Collect%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="2ca49-144">几乎在所有情况下，你都不必调用此方法，因为垃圾回收器会持续运行。</span><span class="sxs-lookup"><span data-stu-id="2ca49-144">In almost all cases, you do not have to call this method, because the garbage collector runs continuously.</span></span> <span data-ttu-id="2ca49-145">此方法主要用于特殊情况和测试。</span><span class="sxs-lookup"><span data-stu-id="2ca49-145">This method is primarily used for unique situations and testing.</span></span>

## <a name="the-managed-heap"></a><span data-ttu-id="2ca49-146">托管堆</span><span class="sxs-lookup"><span data-stu-id="2ca49-146">The managed heap</span></span>

<span data-ttu-id="2ca49-147">在垃圾回收器由 CLR 初始化之后，它会分配一段内存用于存储和管理对象。</span><span class="sxs-lookup"><span data-stu-id="2ca49-147">After the garbage collector is initialized by the CLR, it allocates a segment of memory to store and manage objects.</span></span> <span data-ttu-id="2ca49-148">此内存称为托管堆（与操作系统中的本机堆相对）。</span><span class="sxs-lookup"><span data-stu-id="2ca49-148">This memory is called the managed heap, as opposed to a native heap in the operating system.</span></span>

<span data-ttu-id="2ca49-149">每个托管进程都有一个托管堆。</span><span class="sxs-lookup"><span data-stu-id="2ca49-149">There is a managed heap for each managed process.</span></span> <span data-ttu-id="2ca49-150">进程中的所有线程都在同一堆上为对象分配内存。</span><span class="sxs-lookup"><span data-stu-id="2ca49-150">All threads in the process allocate memory for objects on the same heap.</span></span>

<span data-ttu-id="2ca49-151">若要保留内存，垃圾回收器会调用 Windows [VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc) 函数，并且每次为托管应用保留一个内存段。</span><span class="sxs-lookup"><span data-stu-id="2ca49-151">To reserve memory, the garbage collector calls the Windows [VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc) function and reserves one segment of memory at a time for managed applications.</span></span> <span data-ttu-id="2ca49-152">垃圾回收器还会根据需要保留内存段，并调用 Windows [VirtualFree](/windows/desktop/api/memoryapi/nf-memoryapi-virtualfree) 函数，将内存段释放回操作系统（在清除所有对象的内存段后）。</span><span class="sxs-lookup"><span data-stu-id="2ca49-152">The garbage collector also reserves segments, as needed, and releases segments back to the operating system (after clearing them of any objects) by calling the Windows [VirtualFree](/windows/desktop/api/memoryapi/nf-memoryapi-virtualfree) function.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ca49-153">垃圾回收器分配的段大小特定于实现，并且随时可能更改（包括定期更新）。</span><span class="sxs-lookup"><span data-stu-id="2ca49-153">The size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="2ca49-154">应用程序不应假设特定段的大小或依赖于此大小，也不应尝试配置段分配可用的内存量。</span><span class="sxs-lookup"><span data-stu-id="2ca49-154">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

<span data-ttu-id="2ca49-155">堆上分配的对象越少，垃圾回收器必须执行的工作就越少。</span><span class="sxs-lookup"><span data-stu-id="2ca49-155">The fewer objects allocated on the heap, the less work the garbage collector has to do.</span></span> <span data-ttu-id="2ca49-156">分配对象时，请勿使用超出你需求的舍入值，例如在仅需要 15 个字节的情况下分配了 32 个字节的数组。</span><span class="sxs-lookup"><span data-stu-id="2ca49-156">When you allocate objects, do not use rounded-up values that exceed your needs, such as allocating an array of 32 bytes when you need only 15 bytes.</span></span>

<span data-ttu-id="2ca49-157">当触发垃圾回收时，垃圾回收器将回收由死对象占用的内存。</span><span class="sxs-lookup"><span data-stu-id="2ca49-157">When a garbage collection is triggered, the garbage collector reclaims the memory that is occupied by dead objects.</span></span> <span data-ttu-id="2ca49-158">回收进程会对活动对象进行压缩，以便将它们一起移动，并移除死空间，从而使堆更小一些。</span><span class="sxs-lookup"><span data-stu-id="2ca49-158">The reclaiming process compacts live objects so that they are moved together, and the dead space is removed, thereby making the heap smaller.</span></span> <span data-ttu-id="2ca49-159">这将确保一起分配的对象全都位于托管堆上，从而保留它们的局部性。</span><span class="sxs-lookup"><span data-stu-id="2ca49-159">This ensures that objects that are allocated together stay together on the managed heap, to preserve their locality.</span></span>

<span data-ttu-id="2ca49-160">垃圾回收的侵入性（频率和持续时间）是由分配的数量和托管堆上保留的内存数量决定的。</span><span class="sxs-lookup"><span data-stu-id="2ca49-160">The intrusiveness (frequency and duration) of garbage collections is the result of the volume of allocations and the amount of survived memory on the managed heap.</span></span>

<span data-ttu-id="2ca49-161">此堆可视为两个堆的累计：[大对象堆](large-object-heap.md)和小对象堆。</span><span class="sxs-lookup"><span data-stu-id="2ca49-161">The heap can be considered as the accumulation of two heaps: the [large object heap](large-object-heap.md) and the small object heap.</span></span>

<span data-ttu-id="2ca49-162">[大对象堆](large-object-heap.md)包含大小为 85,000 个字节和更多字节的大型对象。</span><span class="sxs-lookup"><span data-stu-id="2ca49-162">The [large object heap](large-object-heap.md) contains very large objects that are 85,000 bytes and larger.</span></span> <span data-ttu-id="2ca49-163">大对象堆上的对象通常是数组。</span><span class="sxs-lookup"><span data-stu-id="2ca49-163">The objects on the large object heap are usually arrays.</span></span> <span data-ttu-id="2ca49-164">非常大的实例对象是很少见的。</span><span class="sxs-lookup"><span data-stu-id="2ca49-164">It is rare for an instance object to be extremely large.</span></span>

> [!TIP]
> <span data-ttu-id="2ca49-165">可以[配置阈值大小](../../core/run-time-config/garbage-collector.md#large-object-heap-threshold)，以使对象能够进入大型对象堆。</span><span class="sxs-lookup"><span data-stu-id="2ca49-165">You can [configure the threshold size](../../core/run-time-config/garbage-collector.md#large-object-heap-threshold) for objects to go on the large object heap.</span></span>

## <a name="generations"></a><span data-ttu-id="2ca49-166">代数</span><span class="sxs-lookup"><span data-stu-id="2ca49-166">Generations</span></span>

<span data-ttu-id="2ca49-167">堆按代进行组织，因此它可以处理长生存期的对象和短生存期的对象。</span><span class="sxs-lookup"><span data-stu-id="2ca49-167">The heap is organized into generations so it can handle long-lived and short-lived objects.</span></span> <span data-ttu-id="2ca49-168">垃圾回收主要在回收通常只占用一小部分堆的短生存期对象时发生。</span><span class="sxs-lookup"><span data-stu-id="2ca49-168">Garbage collection primarily occurs with the reclamation of short-lived objects that typically occupy only a small part of the heap.</span></span> <span data-ttu-id="2ca49-169">堆上的对象有三代：</span><span class="sxs-lookup"><span data-stu-id="2ca49-169">There are three generations of objects on the heap:</span></span>

- <span data-ttu-id="2ca49-170">**第 0 代**。</span><span class="sxs-lookup"><span data-stu-id="2ca49-170">**Generation 0**.</span></span> <span data-ttu-id="2ca49-171">这是最年轻的代，其中包含短生存期对象。</span><span class="sxs-lookup"><span data-stu-id="2ca49-171">This is the youngest generation and contains short-lived objects.</span></span> <span data-ttu-id="2ca49-172">短生存期对象的一个示例是临时变量。</span><span class="sxs-lookup"><span data-stu-id="2ca49-172">An example of a short-lived object is a temporary variable.</span></span> <span data-ttu-id="2ca49-173">垃圾回收最常发生在此代中。</span><span class="sxs-lookup"><span data-stu-id="2ca49-173">Garbage collection occurs most frequently in this generation.</span></span>

  <span data-ttu-id="2ca49-174">新分配的对象构成新一代对象，并隐式地成为第 0 代集合。</span><span class="sxs-lookup"><span data-stu-id="2ca49-174">Newly allocated objects form a new generation of objects and are implicitly generation 0 collections.</span></span> <span data-ttu-id="2ca49-175">但是，如果它们是大型对象，它们将延续到第 2 代集合中的大型对象堆。</span><span class="sxs-lookup"><span data-stu-id="2ca49-175">However, if they are large objects, they go on the large object heap in a generation 2 collection.</span></span>

  <span data-ttu-id="2ca49-176">大多数对象通过第 0 代中的垃圾回收进行回收，不会保留到下一代。</span><span class="sxs-lookup"><span data-stu-id="2ca49-176">Most objects are reclaimed for garbage collection in generation 0 and do not survive to the next generation.</span></span>

- <span data-ttu-id="2ca49-177">**第 1 代**。</span><span class="sxs-lookup"><span data-stu-id="2ca49-177">**Generation 1**.</span></span> <span data-ttu-id="2ca49-178">这一代包含短生存期对象并用作短生存期对象和长生存期对象之间的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="2ca49-178">This generation contains short-lived objects and serves as a buffer between short-lived objects and long-lived objects.</span></span>

- <span data-ttu-id="2ca49-179">**第 2 代**。</span><span class="sxs-lookup"><span data-stu-id="2ca49-179">**Generation 2**.</span></span> <span data-ttu-id="2ca49-180">这一代包含长生存期对象。</span><span class="sxs-lookup"><span data-stu-id="2ca49-180">This generation contains long-lived objects.</span></span> <span data-ttu-id="2ca49-181">长生存期对象的一个示例是服务器应用程序中的一个包含在进程期间处于活动状态的静态数据的对象。</span><span class="sxs-lookup"><span data-stu-id="2ca49-181">An example of a long-lived object is an object in a server application that contains static data that's live for the duration of the process.</span></span>

<span data-ttu-id="2ca49-182">当条件得到满足时，垃圾回收将在特定代上发生。</span><span class="sxs-lookup"><span data-stu-id="2ca49-182">Garbage collections occur on specific generations as conditions warrant.</span></span> <span data-ttu-id="2ca49-183">回收某个代意味着回收此代中的对象及其所有更年轻的代。</span><span class="sxs-lookup"><span data-stu-id="2ca49-183">Collecting a generation means collecting objects in that generation and all its younger generations.</span></span> <span data-ttu-id="2ca49-184">第 2 代垃圾回收也称为完整垃圾回收，因为它回收所有代上的所有对象（即，托管堆中的所有对象）。</span><span class="sxs-lookup"><span data-stu-id="2ca49-184">A generation 2 garbage collection is also known as a full garbage collection, because it reclaims all objects in all generations (that is, all objects in the managed heap).</span></span>

### <a name="survival-and-promotions"></a><span data-ttu-id="2ca49-185">幸存和提升</span><span class="sxs-lookup"><span data-stu-id="2ca49-185">Survival and promotions</span></span>

<span data-ttu-id="2ca49-186">垃圾回收中未回收的对象也称为幸存者，并会被提升到下一代。</span><span class="sxs-lookup"><span data-stu-id="2ca49-186">Objects that are not reclaimed in a garbage collection are known as survivors and are promoted to the next generation.</span></span> <span data-ttu-id="2ca49-187">在第 0 代垃圾回收中幸存的对象将被提升到第 1 代；在第 1 代垃圾回收中幸存的对象将被提升到第 2 代；而在第 2 代垃圾回收中幸存的对象将仍为第 2 代。</span><span class="sxs-lookup"><span data-stu-id="2ca49-187">Objects that survive a generation 0 garbage collection are promoted to generation 1; objects that survive a generation 1 garbage collection are promoted to generation 2; and objects that survive a generation 2 garbage collection remain in generation 2.</span></span>

<span data-ttu-id="2ca49-188">当垃圾回收器检测到某个代中的幸存率很高时，它会增加该代的分配阈值。</span><span class="sxs-lookup"><span data-stu-id="2ca49-188">When the garbage collector detects that the survival rate is high in a generation, it increases the threshold of allocations for that generation.</span></span> <span data-ttu-id="2ca49-189">下次回收将回收非常大的内存。</span><span class="sxs-lookup"><span data-stu-id="2ca49-189">The next collection gets a substantial size of reclaimed memory.</span></span> <span data-ttu-id="2ca49-190">CLR 持续在以下两个优先级之间进行平衡：不允许通过延迟垃圾回收，让应用程序的工作集获取太大内存，以及不允许垃圾回收过于频繁地运行。</span><span class="sxs-lookup"><span data-stu-id="2ca49-190">The CLR continually balances two priorities: not letting an application's working set get too large by delaying garbage collection and not letting the garbage collection run too frequently.</span></span>

### <a name="ephemeral-generations-and-segments"></a><span data-ttu-id="2ca49-191">暂时代和暂时段</span><span class="sxs-lookup"><span data-stu-id="2ca49-191">Ephemeral generations and segments</span></span>

<span data-ttu-id="2ca49-192">因为第 0 代和第 1 代中的对象的生存期较短，因此，这些代被称为暂时代。</span><span class="sxs-lookup"><span data-stu-id="2ca49-192">Because objects in generations 0 and 1 are short-lived, these generations are known as the ephemeral generations.</span></span>

<span data-ttu-id="2ca49-193">暂时代必须在称为暂时段的内存段中进行分配。</span><span class="sxs-lookup"><span data-stu-id="2ca49-193">Ephemeral generations must be allocated in the memory segment that is known as the ephemeral segment.</span></span> <span data-ttu-id="2ca49-194">垃圾回收器获取的每个新段将成为新的暂时段，并包含在第 0 代垃圾回收中幸存的对象。</span><span class="sxs-lookup"><span data-stu-id="2ca49-194">Each new segment acquired by the garbage collector becomes the new ephemeral segment and contains the objects that survived a generation 0 garbage collection.</span></span> <span data-ttu-id="2ca49-195">旧的暂时段将成为新的第 2 代段。</span><span class="sxs-lookup"><span data-stu-id="2ca49-195">The old ephemeral segment becomes the new generation 2 segment.</span></span>

<span data-ttu-id="2ca49-196">根据系统为 32 位还是 64 位以及它正在哪种类型的垃圾回收器上运行，暂时段的大小发生相应变化。</span><span class="sxs-lookup"><span data-stu-id="2ca49-196">The size of the ephemeral segment varies depending on whether a system is 32-bit or 64-bit, and on the type of garbage collector it is running.</span></span> <span data-ttu-id="2ca49-197">下表列出了默认值。</span><span class="sxs-lookup"><span data-stu-id="2ca49-197">Default values are shown in the following table.</span></span>

||<span data-ttu-id="2ca49-198">32 位</span><span class="sxs-lookup"><span data-stu-id="2ca49-198">32-bit</span></span>|<span data-ttu-id="2ca49-199">64 位</span><span class="sxs-lookup"><span data-stu-id="2ca49-199">64-bit</span></span>|
|-|-------------|-------------|
|<span data-ttu-id="2ca49-200">工作站 GC</span><span class="sxs-lookup"><span data-stu-id="2ca49-200">Workstation GC</span></span>|<span data-ttu-id="2ca49-201">16 MB</span><span class="sxs-lookup"><span data-stu-id="2ca49-201">16 MB</span></span>|<span data-ttu-id="2ca49-202">256 MB</span><span class="sxs-lookup"><span data-stu-id="2ca49-202">256 MB</span></span>|
|<span data-ttu-id="2ca49-203">服务器 GC</span><span class="sxs-lookup"><span data-stu-id="2ca49-203">Server GC</span></span>|<span data-ttu-id="2ca49-204">64 MB</span><span class="sxs-lookup"><span data-stu-id="2ca49-204">64 MB</span></span>|<span data-ttu-id="2ca49-205">4 GB</span><span class="sxs-lookup"><span data-stu-id="2ca49-205">4 GB</span></span>|
|<span data-ttu-id="2ca49-206">服务器 GC（具有 4 个以上的逻辑 CPU）</span><span class="sxs-lookup"><span data-stu-id="2ca49-206">Server GC with > 4 logical CPUs</span></span>|<span data-ttu-id="2ca49-207">32 MB</span><span class="sxs-lookup"><span data-stu-id="2ca49-207">32 MB</span></span>|<span data-ttu-id="2ca49-208">2 GB</span><span class="sxs-lookup"><span data-stu-id="2ca49-208">2 GB</span></span>|
|<span data-ttu-id="2ca49-209">服务器 GC（具有 8 个以上的逻辑 CPU）</span><span class="sxs-lookup"><span data-stu-id="2ca49-209">Server GC with > 8 logical CPUs</span></span>|<span data-ttu-id="2ca49-210">16 MB</span><span class="sxs-lookup"><span data-stu-id="2ca49-210">16 MB</span></span>|<span data-ttu-id="2ca49-211">1 GB</span><span class="sxs-lookup"><span data-stu-id="2ca49-211">1 GB</span></span>|

<span data-ttu-id="2ca49-212">暂时段可以包含第 2 代对象。</span><span class="sxs-lookup"><span data-stu-id="2ca49-212">The ephemeral segment can include generation 2 objects.</span></span> <span data-ttu-id="2ca49-213">第 2 代对象可使用多个段（在内存允许的情况下进程所需的任意数量）。</span><span class="sxs-lookup"><span data-stu-id="2ca49-213">Generation 2 objects can use multiple segments (as many as your process requires and memory allows for).</span></span>

<span data-ttu-id="2ca49-214">从暂时垃圾回收中释放的内存量限制为暂时段的大小。</span><span class="sxs-lookup"><span data-stu-id="2ca49-214">The amount of freed memory from an ephemeral garbage collection is limited to the size of the ephemeral segment.</span></span> <span data-ttu-id="2ca49-215">释放的内存量与死对象占用的空间成比例。</span><span class="sxs-lookup"><span data-stu-id="2ca49-215">The amount of memory that is freed is proportional to the space that was occupied by the dead objects.</span></span>

## <a name="what-happens-during-a-garbage-collection"></a><span data-ttu-id="2ca49-216">垃圾回收过程中发生的情况</span><span class="sxs-lookup"><span data-stu-id="2ca49-216">What happens during a garbage collection</span></span>

<span data-ttu-id="2ca49-217">垃圾回收分为以下几个阶段：</span><span class="sxs-lookup"><span data-stu-id="2ca49-217">A garbage collection has the following phases:</span></span>

- <span data-ttu-id="2ca49-218">标记阶段，找到并创建所有活动对象的列表。</span><span class="sxs-lookup"><span data-stu-id="2ca49-218">A marking phase that finds and creates a list of all live objects.</span></span>

- <span data-ttu-id="2ca49-219">重定位阶段，用于更新对将要压缩的对象的引用。</span><span class="sxs-lookup"><span data-stu-id="2ca49-219">A relocating phase that updates the references to the objects that will be compacted.</span></span>

- <span data-ttu-id="2ca49-220">压缩阶段，用于回收由死对象占用的空间，并压缩幸存的对象。</span><span class="sxs-lookup"><span data-stu-id="2ca49-220">A compacting phase that reclaims the space occupied by the dead objects and compacts the surviving objects.</span></span> <span data-ttu-id="2ca49-221">压缩阶段将垃圾回收中幸存下来的对象移至段中时间较早的一端。</span><span class="sxs-lookup"><span data-stu-id="2ca49-221">The compacting phase moves objects that have survived a garbage collection toward the older end of the segment.</span></span>

  <span data-ttu-id="2ca49-222">因为第 2 代回收可以占用多个段，所以可以将已提升到第 2 代中的对象移动到时间较早的段中。</span><span class="sxs-lookup"><span data-stu-id="2ca49-222">Because generation 2 collections can occupy multiple segments, objects that are promoted into generation 2 can be moved into an older segment.</span></span> <span data-ttu-id="2ca49-223">可以将第 1 代幸存者和第 2 代幸存者都移动到不同的段，因为它们已被提升到第 2 代。</span><span class="sxs-lookup"><span data-stu-id="2ca49-223">Both generation 1 and generation 2 survivors can be moved to a different segment, because they are promoted to generation 2.</span></span>

  <span data-ttu-id="2ca49-224">通常，由于复制大型对象会造成性能代偿，因此不会压缩大型对象堆 (LOH)。</span><span class="sxs-lookup"><span data-stu-id="2ca49-224">Ordinarily, the large object heap (LOH) is not compacted, because copying large objects imposes a performance penalty.</span></span> <span data-ttu-id="2ca49-225">但是，在 .NET Core 和 .NET Framework 4.5.1 及更高版本中，可以根据需要使用 <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType> 属性按需压缩大型对象堆。</span><span class="sxs-lookup"><span data-stu-id="2ca49-225">However, in .NET Core and in .NET Framework 4.5.1 and later, you can use the <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType> property to compact the large object heap on demand.</span></span> <span data-ttu-id="2ca49-226">此外，当通过指定以下任一项设置硬限制时，将自动压缩 LOH：</span><span class="sxs-lookup"><span data-stu-id="2ca49-226">In addition, the LOH is automatically compacted when a hard limit is set by specifying either:</span></span>

  - <span data-ttu-id="2ca49-227">针对容器的内存限制，或</span><span class="sxs-lookup"><span data-stu-id="2ca49-227">a memory limit on a container, or</span></span>
  - <span data-ttu-id="2ca49-228">[GCHeapHardLimit](../../core/run-time-config/garbage-collector.md#systemgcheaphardlimitcomplus_gcheaphardlimit) 或 [GCHeapHardLimitPercent](../../core/run-time-config/garbage-collector.md#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) 运行时配置选项</span><span class="sxs-lookup"><span data-stu-id="2ca49-228">the [GCHeapHardLimit](../../core/run-time-config/garbage-collector.md#systemgcheaphardlimitcomplus_gcheaphardlimit) or [GCHeapHardLimitPercent](../../core/run-time-config/garbage-collector.md#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) run-time configuration options</span></span>

<span data-ttu-id="2ca49-229">垃圾回收器使用以下信息来确定对象是否为活动对象：</span><span class="sxs-lookup"><span data-stu-id="2ca49-229">The garbage collector uses the following information to determine whether objects are live:</span></span>

- <span data-ttu-id="2ca49-230">**堆栈根**。</span><span class="sxs-lookup"><span data-stu-id="2ca49-230">**Stack roots**.</span></span> <span data-ttu-id="2ca49-231">由实时 (JIT) 编译器和堆栈查看器提供的堆栈变量。</span><span class="sxs-lookup"><span data-stu-id="2ca49-231">Stack variables provided by the just-in-time (JIT) compiler and stack walker.</span></span> <span data-ttu-id="2ca49-232">JIT 优化可以延长或缩短报告给垃圾回收器的堆栈变量内的代码的区域。</span><span class="sxs-lookup"><span data-stu-id="2ca49-232">JIT optimizations can lengthen or shorten regions of code within which stack variables are reported to the garbage collector.</span></span>

- <span data-ttu-id="2ca49-233">**垃圾回收句柄**。</span><span class="sxs-lookup"><span data-stu-id="2ca49-233">**Garbage collection handles**.</span></span> <span data-ttu-id="2ca49-234">指向托管对象且可由用户代码或公共语言运行时分配的句柄。</span><span class="sxs-lookup"><span data-stu-id="2ca49-234">Handles that point to managed objects and that can be allocated by user code or by the common language runtime.</span></span>

- <span data-ttu-id="2ca49-235">**静态数据**。</span><span class="sxs-lookup"><span data-stu-id="2ca49-235">**Static data**.</span></span> <span data-ttu-id="2ca49-236">应用程序域中可能引用其他对象的静态对象。</span><span class="sxs-lookup"><span data-stu-id="2ca49-236">Static objects in application domains that could be referencing other objects.</span></span> <span data-ttu-id="2ca49-237">每个应用程序域都会跟踪其静态对象。</span><span class="sxs-lookup"><span data-stu-id="2ca49-237">Each application domain keeps track of its static objects.</span></span>

<span data-ttu-id="2ca49-238">在垃圾回收启动之前，除了触发垃圾回收的线程以外的所有托管线程均会挂起。</span><span class="sxs-lookup"><span data-stu-id="2ca49-238">Before a garbage collection starts, all managed threads are suspended except for the thread that triggered the garbage collection.</span></span>

<span data-ttu-id="2ca49-239">下图演示了触发垃圾回收并导致其他线程挂起的线程。</span><span class="sxs-lookup"><span data-stu-id="2ca49-239">The following illustration shows a thread that triggers a garbage collection and causes the other threads to be suspended.</span></span>

![线程触发垃圾回收时](./media/gc-triggered.png)

## <a name="manipulate-unmanaged-resources"></a><span data-ttu-id="2ca49-241">操作非托管资源</span><span class="sxs-lookup"><span data-stu-id="2ca49-241">Manipulate unmanaged resources</span></span>

<span data-ttu-id="2ca49-242">如果托管对象使用非托管对象的本机文件句柄来引用非托管对象，则必须显式释放非托管对象，因为垃圾回收器仅跟踪托管堆上的内存。</span><span class="sxs-lookup"><span data-stu-id="2ca49-242">If managed objects reference unmanaged objects by using their native file handles, you have to explicitly free the unmanaged objects, because the garbage collector only tracks memory on the managed heap.</span></span>

<span data-ttu-id="2ca49-243">托管对象的用户可能不会释放由该对象使用的本机资源。</span><span class="sxs-lookup"><span data-stu-id="2ca49-243">Users of the managed object may not dispose the native resources used by the object.</span></span> <span data-ttu-id="2ca49-244">为了执行清理，可以使托管对象成为可终结的。</span><span class="sxs-lookup"><span data-stu-id="2ca49-244">To perform the cleanup, you can make the managed object finalizable.</span></span> <span data-ttu-id="2ca49-245">终结由不再使用对象时执行的清理操作组成。</span><span class="sxs-lookup"><span data-stu-id="2ca49-245">Finalization consists of cleanup actions that execute when the object is no longer in use.</span></span> <span data-ttu-id="2ca49-246">当托管对象不活动时，它将执行在其终结器方法中指定的清理操作。</span><span class="sxs-lookup"><span data-stu-id="2ca49-246">When the managed object dies, it performs cleanup actions that are specified in its finalizer method.</span></span>

<span data-ttu-id="2ca49-247">当发现某个可终结对象处于不活动状态时，则会将其终结器放入队列中，以便执行其清理操作，但要将该对象自身提升到下一代。</span><span class="sxs-lookup"><span data-stu-id="2ca49-247">When a finalizable object is discovered to be dead, its finalizer is put in a queue so that its cleanup actions are executed, but the object itself is promoted to the next generation.</span></span> <span data-ttu-id="2ca49-248">因此，你必须等待该代上发生下一次垃圾回收（并不一定是下一次垃圾回收），以确定对象是否已收回。</span><span class="sxs-lookup"><span data-stu-id="2ca49-248">Therefore, you have to wait until the next garbage collection that occurs on that generation (which is not necessarily the next garbage collection) to determine whether the object has been reclaimed.</span></span>

<span data-ttu-id="2ca49-249">有关终结版的详细信息，请参见 <xref:System.Object.Finalize?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="2ca49-249">For more information about finalization, see <xref:System.Object.Finalize?displayProperty=nameWithType>.</span></span>

## <a name="workstation-and-server-garbage-collection"></a><span data-ttu-id="2ca49-250">工作站和服务器垃圾回收</span><span class="sxs-lookup"><span data-stu-id="2ca49-250">Workstation and server garbage collection</span></span>

<span data-ttu-id="2ca49-251">垃圾回收器可自行优化并且适用于多种方案。</span><span class="sxs-lookup"><span data-stu-id="2ca49-251">The garbage collector is self-tuning and can work in a wide variety of scenarios.</span></span> <span data-ttu-id="2ca49-252">你可使用[配置文件设置](../../core/run-time-config/garbage-collector.md#flavors-of-garbage-collection)来基于工作负荷的特征设置垃圾回收的类型。</span><span class="sxs-lookup"><span data-stu-id="2ca49-252">You can use a [configuration file setting](../../core/run-time-config/garbage-collector.md#flavors-of-garbage-collection) to set the type of garbage collection based on the characteristics of the workload.</span></span> <span data-ttu-id="2ca49-253">CLR 提供了以下类型的垃圾回收：</span><span class="sxs-lookup"><span data-stu-id="2ca49-253">The CLR provides the following types of garbage collection:</span></span>

- <span data-ttu-id="2ca49-254">工作站垃圾回收 (GC) 是为客户端应用为设计的。</span><span class="sxs-lookup"><span data-stu-id="2ca49-254">Workstation garbage collection (GC) is designed for client apps.</span></span> <span data-ttu-id="2ca49-255">它是独立应用的默认 GC 风格。</span><span class="sxs-lookup"><span data-stu-id="2ca49-255">It is the default GC flavor for standalone apps.</span></span> <span data-ttu-id="2ca49-256">对于托管应用（例如由 ASP.NET 托管的应用），由主机确定默认 GC 风格。</span><span class="sxs-lookup"><span data-stu-id="2ca49-256">For hosted apps, for example, those hosted by ASP.NET, the host determines the default GC flavor.</span></span>

  <span data-ttu-id="2ca49-257">工作站垃圾回收既可以是并发的，也可以是非并发的。</span><span class="sxs-lookup"><span data-stu-id="2ca49-257">Workstation garbage collection can be concurrent or non-concurrent.</span></span> <span data-ttu-id="2ca49-258">并发垃圾回收使托管线程能够在垃圾回收期间继续操作。</span><span class="sxs-lookup"><span data-stu-id="2ca49-258">Concurrent garbage collection enables managed threads to continue operations during a garbage collection.</span></span> <span data-ttu-id="2ca49-259">[后台垃圾回收](#background-workstation-garbage-collection)替换 .NET Framework 4 及更高版本中的[并行垃圾回收](#concurrent-garbage-collection)。</span><span class="sxs-lookup"><span data-stu-id="2ca49-259">[Background garbage collection](#background-workstation-garbage-collection) replaces [concurrent garbage collection](#concurrent-garbage-collection) in .NET Framework 4 and later versions.</span></span>

- <span data-ttu-id="2ca49-260">服务器垃圾回收，用于需要高吞吐量和可伸缩性的服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="2ca49-260">Server garbage collection, which is intended for server applications that need high throughput and scalability.</span></span>

  - <span data-ttu-id="2ca49-261">在 .NET Core 中，服务器垃圾回收既可以是非并发也可以是后台执行。</span><span class="sxs-lookup"><span data-stu-id="2ca49-261">In .NET Core, server garbage collection can be non-concurrent or background.</span></span>

  - <span data-ttu-id="2ca49-262">在 .NET Framework 4.5 及更高版本中，服务器垃圾回收可以非并行运行，还可在后台运行（后台垃圾回收可取代并行垃圾回收）。</span><span class="sxs-lookup"><span data-stu-id="2ca49-262">In .NET Framework 4.5 and later versions, server garbage collection can be non-concurrent or background (background garbage collection replaces concurrent garbage collection).</span></span> <span data-ttu-id="2ca49-263">在 .NET Framework 4 和以前的版本中，服务器垃圾回收非并行运行。</span><span class="sxs-lookup"><span data-stu-id="2ca49-263">In .NET Framework 4 and previous versions, server garbage collection is non-concurrent.</span></span>

<span data-ttu-id="2ca49-264">下图演示了服务器上执行垃圾回收的专用线程：</span><span class="sxs-lookup"><span data-stu-id="2ca49-264">The following illustration shows the dedicated threads that perform the garbage collection on a server:</span></span>

![服务器垃圾回收线程](./media/gc-server.png)

### <a name="compare-workstation-and-server-garbage-collection"></a><span data-ttu-id="2ca49-266">比较工作站和服务器垃圾回收</span><span class="sxs-lookup"><span data-stu-id="2ca49-266">Compare workstation and server garbage collection</span></span>

<span data-ttu-id="2ca49-267">以下是工作站垃圾回收的线程处理和性能注意事项：</span><span class="sxs-lookup"><span data-stu-id="2ca49-267">The following are threading and performance considerations for workstation garbage collection:</span></span>

- <span data-ttu-id="2ca49-268">回收发生在触发垃圾回收的用户线程上，并保留相同优先级。</span><span class="sxs-lookup"><span data-stu-id="2ca49-268">The collection occurs on the user thread that triggered the garbage collection and remains at the same priority.</span></span> <span data-ttu-id="2ca49-269">因为用户线程通常以普通优先级运行，所以垃圾回收器（在普通优先级线程上运行）必须与其他线程竞争 CPU 时间。</span><span class="sxs-lookup"><span data-stu-id="2ca49-269">Because user threads typically run at normal priority, the garbage collector (which runs on a normal priority thread) must compete with other threads for CPU time.</span></span> <span data-ttu-id="2ca49-270">（运行本机代码的线程不会由于服务器或工作站垃圾回收而挂起。）</span><span class="sxs-lookup"><span data-stu-id="2ca49-270">(Threads that run native code are not suspended on either server or workstation garbage collection.)</span></span>

- <span data-ttu-id="2ca49-271">工作站垃圾回收始终用于只有一个处理器的计算机，无论[配置设置](../../core/run-time-config/garbage-collector.md#systemgcservercomplus_gcserver)如何。</span><span class="sxs-lookup"><span data-stu-id="2ca49-271">Workstation garbage collection is always used on a computer that has only one processor, regardless of the [configuration setting](../../core/run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).</span></span>

<span data-ttu-id="2ca49-272">以下是服务器垃圾回收的线程处理和性能注意事项：</span><span class="sxs-lookup"><span data-stu-id="2ca49-272">The following are threading and performance considerations for server garbage collection:</span></span>

- <span data-ttu-id="2ca49-273">回收发生在以 `THREAD_PRIORITY_HIGHEST` 优先级运行的多个专用线程上。</span><span class="sxs-lookup"><span data-stu-id="2ca49-273">The collection occurs on multiple dedicated threads that are running at `THREAD_PRIORITY_HIGHEST` priority level.</span></span>

- <span data-ttu-id="2ca49-274">为每个 CPU 提供一个用于执行垃圾回收的一个堆和专用线程，并将同时回收这些堆。</span><span class="sxs-lookup"><span data-stu-id="2ca49-274">A heap and a dedicated thread to perform garbage collection are provided for each CPU, and the heaps are collected at the same time.</span></span> <span data-ttu-id="2ca49-275">每个堆都包含一个小对象堆和一个大对象堆，并且所有的堆都可由用户代码访问。</span><span class="sxs-lookup"><span data-stu-id="2ca49-275">Each heap contains a small object heap and a large object heap, and all heaps can be accessed by user code.</span></span> <span data-ttu-id="2ca49-276">不同堆上的对象可以相互引用。</span><span class="sxs-lookup"><span data-stu-id="2ca49-276">Objects on different heaps can refer to each other.</span></span>

- <span data-ttu-id="2ca49-277">因为多个垃圾回收线程一起工作，所以对于相同大小的堆，服务器垃圾回收比工作站垃圾回收更快一些。</span><span class="sxs-lookup"><span data-stu-id="2ca49-277">Because multiple garbage collection threads work together, server garbage collection is faster than workstation garbage collection on the same size heap.</span></span>

- <span data-ttu-id="2ca49-278">服务器垃圾回收通常具有更大的段。</span><span class="sxs-lookup"><span data-stu-id="2ca49-278">Server garbage collection often has larger size segments.</span></span> <span data-ttu-id="2ca49-279">但是，这是通常情况：段大小特定于实现且可能更改。</span><span class="sxs-lookup"><span data-stu-id="2ca49-279">However, this is only a generalization: segment size is implementation-specific and is subject to change.</span></span> <span data-ttu-id="2ca49-280">调整应用程序时，不要假设垃圾回收器分配的段大小。</span><span class="sxs-lookup"><span data-stu-id="2ca49-280">Don't make assumptions about the size of segments allocated by the garbage collector when tuning your app.</span></span>

- <span data-ttu-id="2ca49-281">服务器垃圾回收会占用大量资源。</span><span class="sxs-lookup"><span data-stu-id="2ca49-281">Server garbage collection can be resource-intensive.</span></span> <span data-ttu-id="2ca49-282">例如，假设在一台有 4 个处理器的计算机上，运行着 12 个使用服务器 GC 的进程。</span><span class="sxs-lookup"><span data-stu-id="2ca49-282">For example, imagine that there are 12 processes that use server GC running on a computer that has 4 processors.</span></span> <span data-ttu-id="2ca49-283">如果所有进程碰巧同时回收垃圾，它们会相互干扰，因为将在同一个处理器上调度 12 个线程。</span><span class="sxs-lookup"><span data-stu-id="2ca49-283">If all the processes happen to collect garbage at the same time, they would interfere with each other, as there would be 12 threads scheduled on the same processor.</span></span> <span data-ttu-id="2ca49-284">如果进程处于活动状态，则最好不要让它们都使用服务器 GC。</span><span class="sxs-lookup"><span data-stu-id="2ca49-284">If the processes are active, it's not a good idea to have them all use server GC.</span></span>

<span data-ttu-id="2ca49-285">如果运行应用程序的数百个实例，请考虑使用工作站垃圾回收并禁用并发垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="2ca49-285">If you're running hundreds of instances of an application, consider using workstation garbage collection with concurrent garbage collection disabled.</span></span> <span data-ttu-id="2ca49-286">这可以减少上下文切换，从而提高性能。</span><span class="sxs-lookup"><span data-stu-id="2ca49-286">This will result in less context switching, which can improve performance.</span></span>

## <a name="background-workstation-garbage-collection"></a><span data-ttu-id="2ca49-287">后台工作站垃圾回收</span><span class="sxs-lookup"><span data-stu-id="2ca49-287">Background workstation garbage collection</span></span>

<span data-ttu-id="2ca49-288">在后台工作站垃圾回收中，在进行第 2 代回收的过程中，将会根据需要收集暂时代（第 0 代和第 1 代）。</span><span class="sxs-lookup"><span data-stu-id="2ca49-288">In background workstation garbage collection, ephemeral generations (0 and 1) are collected as needed while the collection of generation 2 is in progress.</span></span> <span data-ttu-id="2ca49-289">后台工作站垃圾回收是在一个专用线程上执行的并且只适用于第 2 代回收。</span><span class="sxs-lookup"><span data-stu-id="2ca49-289">Background workstation garbage collection is performed on a dedicated thread and applies only to generation 2 collections.</span></span>

<span data-ttu-id="2ca49-290">默认启用后台垃圾回收，并且可以在 .NET Framework 应用程序中使用 [gcConcurrent](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) 配置设置或 .NET Framework 应用中的 [System.GC.Concurrent](../../core/run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent) 来启用或禁用后台垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="2ca49-290">Background garbage collection is enabled by default and can be enabled or disabled with the [gcConcurrent](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) configuration setting in .NET Framework apps or the [System.GC.Concurrent](../../core/run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent) setting in .NET Core apps.</span></span>

> [!NOTE]
> <span data-ttu-id="2ca49-291">后台垃圾回收替换在 .NET Framework 4 及更高版本中可用的[并行垃圾回收](#concurrent-garbage-collection)。</span><span class="sxs-lookup"><span data-stu-id="2ca49-291">Background garbage collection replaces [concurrent garbage collection](#concurrent-garbage-collection) and is available in .NET Framework 4 and later versions.</span></span> <span data-ttu-id="2ca49-292">在 .NET Framework 4 中，仅支持工作站垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="2ca49-292">In .NET Framework 4, it's supported only for workstation garbage collection.</span></span> <span data-ttu-id="2ca49-293">从 .NET Framework 4.5 开始，后台垃圾回收可用于工作站和服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="2ca49-293">Starting with .NET Framework 4.5, background garbage collection is available for both workstation and server garbage collection.</span></span>

<span data-ttu-id="2ca49-294">后台垃圾回收期间对暂时代的回收称为前台垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="2ca49-294">A collection on ephemeral generations during background garbage collection is known as foreground garbage collection.</span></span> <span data-ttu-id="2ca49-295">发生前台垃圾回收时，所有托管线程都将被挂起。</span><span class="sxs-lookup"><span data-stu-id="2ca49-295">When foreground garbage collections occur, all managed threads are suspended.</span></span>

<span data-ttu-id="2ca49-296">当后台垃圾回收正在进行并且你已在第 0 代中分配了足够的对象时，CLR 将执行第 0 代或第 1 代前台垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="2ca49-296">When background garbage collection is in progress and you've allocated enough objects in generation 0, the CLR performs a generation 0 or generation 1 foreground garbage collection.</span></span> <span data-ttu-id="2ca49-297">专用的后台垃圾回收线程将在常见的安全点上进行检查以确定是否存在对前台垃圾回收的请求。</span><span class="sxs-lookup"><span data-stu-id="2ca49-297">The dedicated background garbage collection thread checks at frequent safe points to determine whether there is a request for foreground garbage collection.</span></span> <span data-ttu-id="2ca49-298">如果存在，则后台回收将挂起自身以便前台垃圾回收可以发生。</span><span class="sxs-lookup"><span data-stu-id="2ca49-298">If there is, the background collection suspends itself so that foreground garbage collection can occur.</span></span> <span data-ttu-id="2ca49-299">在前台垃圾回收完成之后，专用的后台垃圾回收线程和用户线程将继续。</span><span class="sxs-lookup"><span data-stu-id="2ca49-299">After the foreground garbage collection is completed, the dedicated background garbage collection thread and user threads resume.</span></span>

<span data-ttu-id="2ca49-300">后台垃圾回收可以消除并发垃圾回收所带来的分配限制，因为在后台垃圾回收期间，可发生暂时垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="2ca49-300">Background garbage collection removes allocation restrictions imposed by concurrent garbage collection, because ephemeral garbage collections can occur during background garbage collection.</span></span> <span data-ttu-id="2ca49-301">后台垃圾回收可以删除暂存世代中的死对象。</span><span class="sxs-lookup"><span data-stu-id="2ca49-301">Background garbage collection can remove dead objects in ephemeral generations.</span></span> <span data-ttu-id="2ca49-302">如果需要，它还可以在第 1 代垃圾回收期间扩展堆。</span><span class="sxs-lookup"><span data-stu-id="2ca49-302">It can also expand the heap if needed during a generation 1 garbage collection.</span></span>

<span data-ttu-id="2ca49-303">下图显示对工作站上的独立专用线程执行的后台垃圾回收：</span><span class="sxs-lookup"><span data-stu-id="2ca49-303">The following illustration shows background garbage collection performed on a separate dedicated thread on a workstation:</span></span>

![后台工作站垃圾回收](./media/fundamentals/background-workstation-garbage-collection.png)

### <a name="background-server-garbage-collection"></a><span data-ttu-id="2ca49-305">后台服务器垃圾回收</span><span class="sxs-lookup"><span data-stu-id="2ca49-305">Background server garbage collection</span></span>

<span data-ttu-id="2ca49-306">从 .NET Framework 4.5 开始，后台服务器垃圾回收是服务器垃圾回收的默认模式。</span><span class="sxs-lookup"><span data-stu-id="2ca49-306">Starting with .NET Framework 4.5, background server garbage collection is the default mode for server garbage collection.</span></span>

<span data-ttu-id="2ca49-307">后台服务器垃圾回收与后台工作站垃圾回收（如上一章节所描述）具有类似功能，但有一些不同之处：</span><span class="sxs-lookup"><span data-stu-id="2ca49-307">Background server garbage collection functions similarly to background workstation garbage collection, described in the previous section, but there are a few differences:</span></span>

- <span data-ttu-id="2ca49-308">后台工作区域垃圾回收使用一个专用的后台垃圾回收线程，而后台服务器垃圾回收使用多个线程。</span><span class="sxs-lookup"><span data-stu-id="2ca49-308">Background workstation garbage collection uses one dedicated background garbage collection thread, whereas background server garbage collection uses multiple threads.</span></span> <span data-ttu-id="2ca49-309">通常一个逻辑处理器有一个专用线程。</span><span class="sxs-lookup"><span data-stu-id="2ca49-309">Typically, there's a dedicated thread for each logical processor.</span></span>

- <span data-ttu-id="2ca49-310">不同于工作站后台垃圾回收线程，这些线程不会超时。</span><span class="sxs-lookup"><span data-stu-id="2ca49-310">Unlike the workstation background garbage collection thread, these threads do not time out.</span></span>

<span data-ttu-id="2ca49-311">下图显示对服务器上的独立专用线程执行的后台垃圾回收：</span><span class="sxs-lookup"><span data-stu-id="2ca49-311">The following illustration shows background garbage collection performed on a separate dedicated thread on a server:</span></span>

![后台服务器垃圾回收](./media/fundamentals/background-server-garbage-collection.png)

## <a name="concurrent-garbage-collection"></a><span data-ttu-id="2ca49-313">并行垃圾回收</span><span class="sxs-lookup"><span data-stu-id="2ca49-313">Concurrent garbage collection</span></span>

> [!TIP]
> <span data-ttu-id="2ca49-314">本部分仅适用于：</span><span class="sxs-lookup"><span data-stu-id="2ca49-314">This section applies to:</span></span>
>
> - <span data-ttu-id="2ca49-315">用于工作站垃圾回收的 .NET Framework 3.5 及更早版本</span><span class="sxs-lookup"><span data-stu-id="2ca49-315">.NET Framework 3.5 and earlier for workstation garbage collection</span></span>
> - <span data-ttu-id="2ca49-316">用于服务器垃圾回收的 .NET Framework 4 及更早版本</span><span class="sxs-lookup"><span data-stu-id="2ca49-316">.NET Framework 4 and earlier for server garbage collection</span></span>
>
> <span data-ttu-id="2ca49-317">在更高的版本中，[后台垃圾回收](#background-workstation-garbage-collection)取代了并行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="2ca49-317">Concurrent garbage is replaced by [background garbage collection](#background-workstation-garbage-collection) in later versions.</span></span>

<span data-ttu-id="2ca49-318">在工作站或服务器垃圾回收中，你可以[启用并发垃圾回收](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md)，以便在大多数回收期间，让各线程与执行垃圾回收的专用线程并发运行。</span><span class="sxs-lookup"><span data-stu-id="2ca49-318">In workstation or server garbage collection, you can [enable concurrent garbage collection](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md), which enables threads to run concurrently with a dedicated thread that performs the garbage collection for most of the duration of the collection.</span></span> <span data-ttu-id="2ca49-319">此选项只影响第 2 代中的垃圾回收；第 0 代和第 1 代中的垃圾回收始终是非并发的，因为它们完成的速度非常快。</span><span class="sxs-lookup"><span data-stu-id="2ca49-319">This option affects only garbage collections in generation 2; generations 0 and 1 are always non-concurrent because they finish very fast.</span></span>

<span data-ttu-id="2ca49-320">并发垃圾回收通过最大程度地减少因回收引起的暂停，使交互应用程序能够更快地响应。</span><span class="sxs-lookup"><span data-stu-id="2ca49-320">Concurrent garbage collection enables interactive applications to be more responsive by minimizing pauses for a collection.</span></span> <span data-ttu-id="2ca49-321">在运行并发垃圾回收线程的大多数时间，托管线程可以继续运行。</span><span class="sxs-lookup"><span data-stu-id="2ca49-321">Managed threads can continue to run most of the time while the concurrent garbage collection thread is running.</span></span> <span data-ttu-id="2ca49-322">这可以使得在发生垃圾回收时的暂停时间更短。</span><span class="sxs-lookup"><span data-stu-id="2ca49-322">This results in shorter pauses while a garbage collection is occurring.</span></span>

<span data-ttu-id="2ca49-323">并发垃圾回收在一个专用线程上执行。</span><span class="sxs-lookup"><span data-stu-id="2ca49-323">Concurrent garbage collection is performed on a dedicated thread.</span></span> <span data-ttu-id="2ca49-324">默认情况下，CLR 将运行工作站垃圾回收并启用并发垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="2ca49-324">By default, the CLR runs workstation garbage collection with concurrent garbage collection enabled.</span></span> <span data-ttu-id="2ca49-325">对于单处理器计算机和多处理器计算机都是如此。</span><span class="sxs-lookup"><span data-stu-id="2ca49-325">This is true for single-processor and multi-processor computers.</span></span>

<span data-ttu-id="2ca49-326">下图演示了在单独的专用线程上执行的并发垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="2ca49-326">The following illustration shows concurrent garbage collection performed on a separate dedicated thread.</span></span>

![并发垃圾回收线程](./media/gc-concurrent.png)

## <a name="see-also"></a><span data-ttu-id="2ca49-328">请参阅</span><span class="sxs-lookup"><span data-stu-id="2ca49-328">See also</span></span>

- [<span data-ttu-id="2ca49-329">GC 的配置选项</span><span class="sxs-lookup"><span data-stu-id="2ca49-329">Configuration options for GC</span></span>](../../core/run-time-config/garbage-collector.md)
- [<span data-ttu-id="2ca49-330">垃圾回收</span><span class="sxs-lookup"><span data-stu-id="2ca49-330">Garbage collection</span></span>](index.md)
