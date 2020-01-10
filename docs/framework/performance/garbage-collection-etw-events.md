---
title: 垃圾回收 ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- GC events
- garbage collection events [.NET Framework]
- ETW, garbage collection events (CLR)
ms.assetid: f14b6fd7-0966-4d87-bc89-54ef3a44a94a
ms.openlocfilehash: 5ff214314b92796f4a4a89ddd33a976d8b1f21d1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716072"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="fbe14-102">垃圾回收 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-102">Garbage Collection ETW Events</span></span>

<span data-ttu-id="fbe14-103">这些事件可收集有关垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="fbe14-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="fbe14-104">它们可帮助进行诊断和调试，包括确定垃圾回收执行的次数、垃圾回收期间释放的内存量等。</span><span class="sxs-lookup"><span data-stu-id="fbe14-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>

<span data-ttu-id="fbe14-105">此类别包含以下事件：</span><span class="sxs-lookup"><span data-stu-id="fbe14-105">This category consists of the following events:</span></span>

- [<span data-ttu-id="fbe14-106">GCStart_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-106">GCStart_V1 Event</span></span>](#gcstart_v1-event)
- [<span data-ttu-id="fbe14-107">GCEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-107">GCEnd_V1 Event</span></span>](#gcend_v1-event)
- [<span data-ttu-id="fbe14-108">GCHeapStats_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1-event)
- [<span data-ttu-id="fbe14-109">GCCreateSegment_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1-event)
- [<span data-ttu-id="fbe14-110">GCFreeSegment_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1-event)
- [<span data-ttu-id="fbe14-111">GCRestartEEBegin_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1-event)
- [<span data-ttu-id="fbe14-112">GCRestartEEEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1-event)
- [<span data-ttu-id="fbe14-113">GCSuspendEE_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1-event)
- [<span data-ttu-id="fbe14-114">GCSuspendEEEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1-event)
- [<span data-ttu-id="fbe14-115">GCAllocationTick_V2 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2-event)
- [<span data-ttu-id="fbe14-116">GCFinalizersBegin_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1-event)
- [<span data-ttu-id="fbe14-117">GCFinalizersEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1-event)
- [<span data-ttu-id="fbe14-118">GCCreateConcurrentThread_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1-event)
- [<span data-ttu-id="fbe14-119">GCTerminateConcurrentThread_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1-event)

## <a name="gcstart_v1-event"></a><span data-ttu-id="fbe14-120">GCStart_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-120">GCStart_V1 Event</span></span>  

<span data-ttu-id="fbe14-121">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="fbe14-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="fbe14-122">有关详细信息，请参阅[CLR ETW 关键字和级别](clr-etw-keywords-and-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="fbe14-122">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="fbe14-123">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="fbe14-123">Keyword for raising the event</span></span>|<span data-ttu-id="fbe14-124">Level</span><span class="sxs-lookup"><span data-stu-id="fbe14-124">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="fbe14-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="fbe14-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="fbe14-126">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="fbe14-126">Informational (4)</span></span>|

<span data-ttu-id="fbe14-127">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="fbe14-127">The following table shows the event information:</span></span>

|<span data-ttu-id="fbe14-128">Event</span><span class="sxs-lookup"><span data-stu-id="fbe14-128">Event</span></span>|<span data-ttu-id="fbe14-129">事件 ID</span><span class="sxs-lookup"><span data-stu-id="fbe14-129">Event ID</span></span>|<span data-ttu-id="fbe14-130">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="fbe14-130">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCStart_V1`|<span data-ttu-id="fbe14-131">1</span><span class="sxs-lookup"><span data-stu-id="fbe14-131">1</span></span>|<span data-ttu-id="fbe14-132">垃圾回收已启动。</span><span class="sxs-lookup"><span data-stu-id="fbe14-132">A garbage collection has started.</span></span>|

<span data-ttu-id="fbe14-133">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="fbe14-133">The following table shows the event data:</span></span>

|<span data-ttu-id="fbe14-134">字段名</span><span class="sxs-lookup"><span data-stu-id="fbe14-134">Field name</span></span>|<span data-ttu-id="fbe14-135">数据类型</span><span class="sxs-lookup"><span data-stu-id="fbe14-135">Data type</span></span>|<span data-ttu-id="fbe14-136">描述</span><span class="sxs-lookup"><span data-stu-id="fbe14-136">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="fbe14-137">计数</span><span class="sxs-lookup"><span data-stu-id="fbe14-137">Count</span></span>|<span data-ttu-id="fbe14-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="fbe14-138">win:UInt32</span></span>|<span data-ttu-id="fbe14-139">第 *n*代垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="fbe14-139">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="fbe14-140">深度</span><span class="sxs-lookup"><span data-stu-id="fbe14-140">Depth</span></span>|<span data-ttu-id="fbe14-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="fbe14-141">win:UInt32</span></span>|<span data-ttu-id="fbe14-142">正在回收的代。</span><span class="sxs-lookup"><span data-stu-id="fbe14-142">The generation that is being collected.</span></span>|
|<span data-ttu-id="fbe14-143">原因</span><span class="sxs-lookup"><span data-stu-id="fbe14-143">Reason</span></span>|<span data-ttu-id="fbe14-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="fbe14-144">win:UInt32</span></span>|<span data-ttu-id="fbe14-145">垃圾回收的触发原因：</span><span class="sxs-lookup"><span data-stu-id="fbe14-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="fbe14-146">0x0 - 小型对象堆分配。</span><span class="sxs-lookup"><span data-stu-id="fbe14-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="fbe14-147">0x1 - 已引发。</span><span class="sxs-lookup"><span data-stu-id="fbe14-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="fbe14-148">0x2 - 内存不足。</span><span class="sxs-lookup"><span data-stu-id="fbe14-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="fbe14-149">0x3 - 空。</span><span class="sxs-lookup"><span data-stu-id="fbe14-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="fbe14-150">0x4 - 大型对象堆分配。</span><span class="sxs-lookup"><span data-stu-id="fbe14-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="fbe14-151">0x5 - 空间不足（针对小型对象堆）。</span><span class="sxs-lookup"><span data-stu-id="fbe14-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="fbe14-152">0x6 - 空间不足（针对大型对象堆）。</span><span class="sxs-lookup"><span data-stu-id="fbe14-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="fbe14-153">0x7 - 已引发，但未强制为阻止。</span><span class="sxs-lookup"><span data-stu-id="fbe14-153">0x7 - Induced but not forced as blocking.</span></span>|
|<span data-ttu-id="fbe14-154">类型</span><span class="sxs-lookup"><span data-stu-id="fbe14-154">Type</span></span>|<span data-ttu-id="fbe14-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="fbe14-155">win:UInt32</span></span>|<span data-ttu-id="fbe14-156">0x0 - 在后台垃圾回收外部发生了垃圾回收阻止。</span><span class="sxs-lookup"><span data-stu-id="fbe14-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="fbe14-157">0x1 - 后台垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="fbe14-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="fbe14-158">0x0 - 后台垃圾回收期间发生了垃圾回收阻止。</span><span class="sxs-lookup"><span data-stu-id="fbe14-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|
|<span data-ttu-id="fbe14-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="fbe14-159">ClrInstanceID</span></span>|<span data-ttu-id="fbe14-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="fbe14-160">win:UInt16</span></span>|<span data-ttu-id="fbe14-161">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="fbe14-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcend_v1-event"></a><span data-ttu-id="fbe14-162">GCEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-162">GCEnd_V1 Event</span></span>

<span data-ttu-id="fbe14-163">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="fbe14-163">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="fbe14-164">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="fbe14-164">Keyword for raising the event</span></span>|<span data-ttu-id="fbe14-165">Level</span><span class="sxs-lookup"><span data-stu-id="fbe14-165">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="fbe14-166">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="fbe14-166">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="fbe14-167">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="fbe14-167">Informational (4)</span></span>|

<span data-ttu-id="fbe14-168">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="fbe14-168">The following table shows the event information:</span></span>

|<span data-ttu-id="fbe14-169">Event</span><span class="sxs-lookup"><span data-stu-id="fbe14-169">Event</span></span>|<span data-ttu-id="fbe14-170">事件 ID</span><span class="sxs-lookup"><span data-stu-id="fbe14-170">Event ID</span></span>|<span data-ttu-id="fbe14-171">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="fbe14-171">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCEnd_V1`|<span data-ttu-id="fbe14-172">2</span><span class="sxs-lookup"><span data-stu-id="fbe14-172">2</span></span>|<span data-ttu-id="fbe14-173">垃圾回收已结束。</span><span class="sxs-lookup"><span data-stu-id="fbe14-173">The garbage collection has ended.</span></span>|

<span data-ttu-id="fbe14-174">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="fbe14-174">The following table shows the event data:</span></span>

|<span data-ttu-id="fbe14-175">字段名</span><span class="sxs-lookup"><span data-stu-id="fbe14-175">Field name</span></span>|<span data-ttu-id="fbe14-176">数据类型</span><span class="sxs-lookup"><span data-stu-id="fbe14-176">Data type</span></span>|<span data-ttu-id="fbe14-177">描述</span><span class="sxs-lookup"><span data-stu-id="fbe14-177">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="fbe14-178">计数</span><span class="sxs-lookup"><span data-stu-id="fbe14-178">Count</span></span>|<span data-ttu-id="fbe14-179">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="fbe14-179">win:UInt32</span></span>|<span data-ttu-id="fbe14-180">第 *n*代垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="fbe14-180">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="fbe14-181">深度</span><span class="sxs-lookup"><span data-stu-id="fbe14-181">Depth</span></span>|<span data-ttu-id="fbe14-182">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="fbe14-182">win:UInt32</span></span>|<span data-ttu-id="fbe14-183">已回收的代。</span><span class="sxs-lookup"><span data-stu-id="fbe14-183">The generation that was collected.</span></span>|
|<span data-ttu-id="fbe14-184">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="fbe14-184">ClrInstanceID</span></span>|<span data-ttu-id="fbe14-185">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="fbe14-185">win:UInt16</span></span>|<span data-ttu-id="fbe14-186">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="fbe14-186">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcheapstats_v1-event"></a><span data-ttu-id="fbe14-187">GCHeapStats_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-187">GCHeapStats_V1 Event</span></span>

<span data-ttu-id="fbe14-188">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="fbe14-188">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="fbe14-189">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="fbe14-189">Keyword for raising the event</span></span>|<span data-ttu-id="fbe14-190">Level</span><span class="sxs-lookup"><span data-stu-id="fbe14-190">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="fbe14-191">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="fbe14-191">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="fbe14-192">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="fbe14-192">Informational (4)</span></span>|

<span data-ttu-id="fbe14-193">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="fbe14-193">The following table shows the event information:</span></span>

|<span data-ttu-id="fbe14-194">Event</span><span class="sxs-lookup"><span data-stu-id="fbe14-194">Event</span></span>|<span data-ttu-id="fbe14-195">事件 ID</span><span class="sxs-lookup"><span data-stu-id="fbe14-195">Event ID</span></span>|<span data-ttu-id="fbe14-196">描述</span><span class="sxs-lookup"><span data-stu-id="fbe14-196">Description</span></span>|
|-----------|--------------|-----------------|
|`GCHeapStats_V1`|<span data-ttu-id="fbe14-197">4</span><span class="sxs-lookup"><span data-stu-id="fbe14-197">4</span></span>|<span data-ttu-id="fbe14-198">在每次垃圾回收结束时显示堆统计信息。</span><span class="sxs-lookup"><span data-stu-id="fbe14-198">Shows the heap statistics at the end of each garbage collection.</span></span>|

<span data-ttu-id="fbe14-199">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="fbe14-199">The following table shows the event data:</span></span>

|<span data-ttu-id="fbe14-200">字段名</span><span class="sxs-lookup"><span data-stu-id="fbe14-200">Field name</span></span>|<span data-ttu-id="fbe14-201">数据类型</span><span class="sxs-lookup"><span data-stu-id="fbe14-201">Data type</span></span>|<span data-ttu-id="fbe14-202">描述</span><span class="sxs-lookup"><span data-stu-id="fbe14-202">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="fbe14-203">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="fbe14-203">GenerationSize0</span></span>|<span data-ttu-id="fbe14-204">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="fbe14-204">win:UInt64</span></span>|<span data-ttu-id="fbe14-205">第 0 代内存的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="fbe14-205">The size, in bytes, of generation 0 memory.</span></span>|
|<span data-ttu-id="fbe14-206">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="fbe14-206">TotalPromotedSize0</span></span>|<span data-ttu-id="fbe14-207">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="fbe14-207">win:UInt64</span></span>|<span data-ttu-id="fbe14-208">从第 0 代提升到第 1 代的字节数。</span><span class="sxs-lookup"><span data-stu-id="fbe14-208">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|
|<span data-ttu-id="fbe14-209">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="fbe14-209">GenerationSize1</span></span>|<span data-ttu-id="fbe14-210">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="fbe14-210">win:UInt64</span></span>|<span data-ttu-id="fbe14-211">第 1 代内存的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="fbe14-211">The size, in bytes, of generation 1 memory.</span></span>|
|<span data-ttu-id="fbe14-212">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="fbe14-212">TotalPromotedSize1</span></span>|<span data-ttu-id="fbe14-213">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="fbe14-213">win:UInt64</span></span>|<span data-ttu-id="fbe14-214">从第 1 代提升到第 2 代的字节数。</span><span class="sxs-lookup"><span data-stu-id="fbe14-214">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|
|<span data-ttu-id="fbe14-215">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="fbe14-215">GenerationSize2</span></span>|<span data-ttu-id="fbe14-216">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="fbe14-216">win:UInt64</span></span>|<span data-ttu-id="fbe14-217">第 2 代内存的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="fbe14-217">The size, in bytes, of generation 2 memory.</span></span>|
|<span data-ttu-id="fbe14-218">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="fbe14-218">TotalPromotedSize2</span></span>|<span data-ttu-id="fbe14-219">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="fbe14-219">win:UInt64</span></span>|<span data-ttu-id="fbe14-220">上次回收后仍存在于第 2 代中的字节数。</span><span class="sxs-lookup"><span data-stu-id="fbe14-220">The number of bytes that survived in generation 2 after the last collection.</span></span>|
|<span data-ttu-id="fbe14-221">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="fbe14-221">GenerationSize3</span></span>|<span data-ttu-id="fbe14-222">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="fbe14-222">win:UInt64</span></span>|<span data-ttu-id="fbe14-223">大型对象堆的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="fbe14-223">The size, in bytes, of the large object heap.</span></span>|
|<span data-ttu-id="fbe14-224">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="fbe14-224">TotalPromotedSize3</span></span>|<span data-ttu-id="fbe14-225">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="fbe14-225">win:UInt64</span></span>|<span data-ttu-id="fbe14-226">上次回收后仍存在于大型对象堆中的字节数。</span><span class="sxs-lookup"><span data-stu-id="fbe14-226">The number of bytes that survived in the large object heap after the last collection.</span></span>|
|<span data-ttu-id="fbe14-227">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="fbe14-227">FinalizationPromotedSize</span></span>|<span data-ttu-id="fbe14-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="fbe14-228">win:UInt64</span></span>|<span data-ttu-id="fbe14-229">准备终结的对象的总大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="fbe14-229">The total size, in bytes, of the objects that are ready for finalization.</span></span>|
|<span data-ttu-id="fbe14-230">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="fbe14-230">FinalizationPromotedCount</span></span>|<span data-ttu-id="fbe14-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="fbe14-231">win:UInt64</span></span>|<span data-ttu-id="fbe14-232">已准备好进行终结的对象的数目。</span><span class="sxs-lookup"><span data-stu-id="fbe14-232">The number of objects that are ready for finalization.</span></span>|
|<span data-ttu-id="fbe14-233">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="fbe14-233">PinnedObjectCount</span></span>|<span data-ttu-id="fbe14-234">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="fbe14-234">win:UInt32</span></span>|<span data-ttu-id="fbe14-235">固定（不可移动）对象的数目。</span><span class="sxs-lookup"><span data-stu-id="fbe14-235">The number of pinned (unmovable) objects.</span></span>|
|<span data-ttu-id="fbe14-236">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="fbe14-236">SinkBlockCount</span></span>|<span data-ttu-id="fbe14-237">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="fbe14-237">win:UInt32</span></span>|<span data-ttu-id="fbe14-238">正在使用的同步块的数目。</span><span class="sxs-lookup"><span data-stu-id="fbe14-238">The number of synchronization blocks in use.</span></span>|
|<span data-ttu-id="fbe14-239">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="fbe14-239">GCHandleCount</span></span>|<span data-ttu-id="fbe14-240">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="fbe14-240">win:UInt32</span></span>|<span data-ttu-id="fbe14-241">使用中的垃圾回收句柄的数目。</span><span class="sxs-lookup"><span data-stu-id="fbe14-241">The number of garbage collection handles in use.</span></span>|
|<span data-ttu-id="fbe14-242">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="fbe14-242">ClrInstanceID</span></span>|<span data-ttu-id="fbe14-243">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="fbe14-243">win:UInt16</span></span>|<span data-ttu-id="fbe14-244">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="fbe14-244">Unique ID for the instance of CLR or CoreCLR.</span></span>|
  
## <a name="gccreatesegment_v1-event"></a><span data-ttu-id="fbe14-245">GCCreateSegment_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-245">GCCreateSegment_V1 Event</span></span>

<span data-ttu-id="fbe14-246">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="fbe14-246">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="fbe14-247">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="fbe14-247">Keyword for raising the event</span></span>|<span data-ttu-id="fbe14-248">Level</span><span class="sxs-lookup"><span data-stu-id="fbe14-248">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="fbe14-249">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="fbe14-249">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="fbe14-250">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="fbe14-250">Informational (4)</span></span>|

<span data-ttu-id="fbe14-251">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="fbe14-251">The following table shows the event information:</span></span>

|<span data-ttu-id="fbe14-252">Event</span><span class="sxs-lookup"><span data-stu-id="fbe14-252">Event</span></span>|<span data-ttu-id="fbe14-253">事件 ID</span><span class="sxs-lookup"><span data-stu-id="fbe14-253">Event ID</span></span>|<span data-ttu-id="fbe14-254">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="fbe14-254">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateSegment_V1`|<span data-ttu-id="fbe14-255">5</span><span class="sxs-lookup"><span data-stu-id="fbe14-255">5</span></span>|<span data-ttu-id="fbe14-256">已创建的新的垃圾回收段。</span><span class="sxs-lookup"><span data-stu-id="fbe14-256">A new garbage collection segment has been created.</span></span> <span data-ttu-id="fbe14-257">此外，当在已运行的进程中启用跟踪时，将为每个现有段引发此事件。</span><span class="sxs-lookup"><span data-stu-id="fbe14-257">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|

<span data-ttu-id="fbe14-258">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="fbe14-258">The following table shows the event data:</span></span>

|<span data-ttu-id="fbe14-259">字段名</span><span class="sxs-lookup"><span data-stu-id="fbe14-259">Field name</span></span>|<span data-ttu-id="fbe14-260">数据类型</span><span class="sxs-lookup"><span data-stu-id="fbe14-260">Data type</span></span>|<span data-ttu-id="fbe14-261">描述</span><span class="sxs-lookup"><span data-stu-id="fbe14-261">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="fbe14-262">Address</span><span class="sxs-lookup"><span data-stu-id="fbe14-262">Address</span></span>|<span data-ttu-id="fbe14-263">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="fbe14-263">win:UInt64</span></span>|<span data-ttu-id="fbe14-264">段的地址。</span><span class="sxs-lookup"><span data-stu-id="fbe14-264">The address of the segment.</span></span>|
|<span data-ttu-id="fbe14-265">大小</span><span class="sxs-lookup"><span data-stu-id="fbe14-265">Size</span></span>|<span data-ttu-id="fbe14-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="fbe14-266">win:UInt64</span></span>|<span data-ttu-id="fbe14-267">段的大小。</span><span class="sxs-lookup"><span data-stu-id="fbe14-267">The size of the segment.</span></span>|
|<span data-ttu-id="fbe14-268">类型</span><span class="sxs-lookup"><span data-stu-id="fbe14-268">Type</span></span>|<span data-ttu-id="fbe14-269">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="fbe14-269">win:UInt32</span></span>|<span data-ttu-id="fbe14-270">0x0 - 小型对象堆。</span><span class="sxs-lookup"><span data-stu-id="fbe14-270">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="fbe14-271">0x0 - 大型对象堆。</span><span class="sxs-lookup"><span data-stu-id="fbe14-271">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="fbe14-272">0x2 - 只读堆。</span><span class="sxs-lookup"><span data-stu-id="fbe14-272">0x2 - Read-only heap.</span></span>|
|<span data-ttu-id="fbe14-273">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="fbe14-273">ClrInstanceID</span></span>|<span data-ttu-id="fbe14-274">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="fbe14-274">win:UInt16</span></span>|<span data-ttu-id="fbe14-275">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="fbe14-275">Unique ID for the instance of CLR or CoreCLR.</span></span>|

<span data-ttu-id="fbe14-276">请注意，由垃圾回收器分配的段的大小特定于实现，且随时可能更改（包括定期更新）。</span><span class="sxs-lookup"><span data-stu-id="fbe14-276">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="fbe14-277">应用程序不应假设特定段的大小或依赖于此大小，也不应尝试配置段分配可用的内存量。</span><span class="sxs-lookup"><span data-stu-id="fbe14-277">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

## <a name="gcfreesegment_v1-event"></a><span data-ttu-id="fbe14-278">GCFreeSegment_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-278">GCFreeSegment_V1 Event</span></span>

<span data-ttu-id="fbe14-279">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="fbe14-279">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="fbe14-280">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="fbe14-280">Keyword for raising the event</span></span>|<span data-ttu-id="fbe14-281">Level</span><span class="sxs-lookup"><span data-stu-id="fbe14-281">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="fbe14-282">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="fbe14-282">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="fbe14-283">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="fbe14-283">Informational (4)</span></span>|

<span data-ttu-id="fbe14-284">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="fbe14-284">The following table shows the event information:</span></span>

|<span data-ttu-id="fbe14-285">Event</span><span class="sxs-lookup"><span data-stu-id="fbe14-285">Event</span></span>|<span data-ttu-id="fbe14-286">事件 ID</span><span class="sxs-lookup"><span data-stu-id="fbe14-286">Event ID</span></span>|<span data-ttu-id="fbe14-287">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="fbe14-287">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFreeSegment_V1`|<span data-ttu-id="fbe14-288">6</span><span class="sxs-lookup"><span data-stu-id="fbe14-288">6</span></span>|<span data-ttu-id="fbe14-289">已释放垃圾回收段。</span><span class="sxs-lookup"><span data-stu-id="fbe14-289">A garbage collection segment has been released.</span></span>|

<span data-ttu-id="fbe14-290">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="fbe14-290">The following table shows the event data:</span></span>

|<span data-ttu-id="fbe14-291">字段名</span><span class="sxs-lookup"><span data-stu-id="fbe14-291">Field name</span></span>|<span data-ttu-id="fbe14-292">数据类型</span><span class="sxs-lookup"><span data-stu-id="fbe14-292">Data type</span></span>|<span data-ttu-id="fbe14-293">描述</span><span class="sxs-lookup"><span data-stu-id="fbe14-293">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="fbe14-294">Address</span><span class="sxs-lookup"><span data-stu-id="fbe14-294">Address</span></span>|<span data-ttu-id="fbe14-295">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="fbe14-295">win:UInt64</span></span>|<span data-ttu-id="fbe14-296">段的地址。</span><span class="sxs-lookup"><span data-stu-id="fbe14-296">The address of the segment.</span></span>|
|<span data-ttu-id="fbe14-297">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="fbe14-297">ClrInstanceID</span></span>|<span data-ttu-id="fbe14-298">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="fbe14-298">win:UInt16</span></span>|<span data-ttu-id="fbe14-299">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="fbe14-299">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcrestarteebegin_v1-event"></a><span data-ttu-id="fbe14-300">GCRestartEEBegin_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-300">GCRestartEEBegin_V1 Event</span></span>

<span data-ttu-id="fbe14-301">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="fbe14-301">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="fbe14-302">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="fbe14-302">Keyword for raising the event</span></span>|<span data-ttu-id="fbe14-303">Level</span><span class="sxs-lookup"><span data-stu-id="fbe14-303">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="fbe14-304">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="fbe14-304">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="fbe14-305">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="fbe14-305">Informational (4)</span></span>|

<span data-ttu-id="fbe14-306">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="fbe14-306">The following table shows the event information:</span></span>

|<span data-ttu-id="fbe14-307">Event</span><span class="sxs-lookup"><span data-stu-id="fbe14-307">Event</span></span>|<span data-ttu-id="fbe14-308">事件 ID</span><span class="sxs-lookup"><span data-stu-id="fbe14-308">Event ID</span></span>|<span data-ttu-id="fbe14-309">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="fbe14-309">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEBegin_V1`|<span data-ttu-id="fbe14-310">7</span><span class="sxs-lookup"><span data-stu-id="fbe14-310">7</span></span>|<span data-ttu-id="fbe14-311">已开始从公共语言运行时挂起进行恢复。</span><span class="sxs-lookup"><span data-stu-id="fbe14-311">Resumption from common language runtime suspension has begun.</span></span>|

<span data-ttu-id="fbe14-312">无事件数据。</span><span class="sxs-lookup"><span data-stu-id="fbe14-312">No event data.</span></span>

## <a name="gcrestarteeend_v1-event"></a><span data-ttu-id="fbe14-313">GCRestartEEEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-313">GCRestartEEEnd_V1 Event</span></span>

<span data-ttu-id="fbe14-314">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="fbe14-314">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="fbe14-315">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="fbe14-315">Keyword for raising the event</span></span>|<span data-ttu-id="fbe14-316">Level</span><span class="sxs-lookup"><span data-stu-id="fbe14-316">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="fbe14-317">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="fbe14-317">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="fbe14-318">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="fbe14-318">Informational (4)</span></span>|

<span data-ttu-id="fbe14-319">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="fbe14-319">The following table shows the event information:</span></span>

|<span data-ttu-id="fbe14-320">Event</span><span class="sxs-lookup"><span data-stu-id="fbe14-320">Event</span></span>|<span data-ttu-id="fbe14-321">事件 ID</span><span class="sxs-lookup"><span data-stu-id="fbe14-321">Event Id</span></span>|<span data-ttu-id="fbe14-322">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="fbe14-322">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEEnd_V1`|<span data-ttu-id="fbe14-323">3</span><span class="sxs-lookup"><span data-stu-id="fbe14-323">3</span></span>|<span data-ttu-id="fbe14-324">从公共语言运行时挂起进行的恢复已结束。</span><span class="sxs-lookup"><span data-stu-id="fbe14-324">Resumption from common language runtime suspension has ended.</span></span>|

<span data-ttu-id="fbe14-325">无事件数据。</span><span class="sxs-lookup"><span data-stu-id="fbe14-325">No event data.</span></span>

## <a name="gcsuspendee_v1-event"></a><span data-ttu-id="fbe14-326">GCSuspendEE_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-326">GCSuspendEE_V1 Event</span></span>

<span data-ttu-id="fbe14-327">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="fbe14-327">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="fbe14-328">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="fbe14-328">Keyword for raising the event</span></span>|<span data-ttu-id="fbe14-329">Level</span><span class="sxs-lookup"><span data-stu-id="fbe14-329">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="fbe14-330">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="fbe14-330">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="fbe14-331">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="fbe14-331">Informational (4)</span></span>|

<span data-ttu-id="fbe14-332">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="fbe14-332">The following table shows the event information:</span></span>

|<span data-ttu-id="fbe14-333">Event</span><span class="sxs-lookup"><span data-stu-id="fbe14-333">Event</span></span>|<span data-ttu-id="fbe14-334">事件 ID</span><span class="sxs-lookup"><span data-stu-id="fbe14-334">Event ID</span></span>|<span data-ttu-id="fbe14-335">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="fbe14-335">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEE_V1`|<span data-ttu-id="fbe14-336">9</span><span class="sxs-lookup"><span data-stu-id="fbe14-336">9</span></span>|<span data-ttu-id="fbe14-337">开始挂起垃圾回收的执行引擎。</span><span class="sxs-lookup"><span data-stu-id="fbe14-337">Start of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="fbe14-338">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="fbe14-338">The following table shows the event data:</span></span>

|<span data-ttu-id="fbe14-339">字段名</span><span class="sxs-lookup"><span data-stu-id="fbe14-339">Field name</span></span>|<span data-ttu-id="fbe14-340">数据类型</span><span class="sxs-lookup"><span data-stu-id="fbe14-340">Data type</span></span>|<span data-ttu-id="fbe14-341">描述</span><span class="sxs-lookup"><span data-stu-id="fbe14-341">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="fbe14-342">原因</span><span class="sxs-lookup"><span data-stu-id="fbe14-342">Reason</span></span>|<span data-ttu-id="fbe14-343">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="fbe14-343">win:UInt16</span></span>|<span data-ttu-id="fbe14-344">0x0 - 其他。</span><span class="sxs-lookup"><span data-stu-id="fbe14-344">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="fbe14-345">0x1 - 垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="fbe14-345">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="fbe14-346">0x2 - 应用程序域关闭。</span><span class="sxs-lookup"><span data-stu-id="fbe14-346">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="fbe14-347">0x3 - 代码间距调整。</span><span class="sxs-lookup"><span data-stu-id="fbe14-347">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="fbe14-348">0x4 - 关闭。</span><span class="sxs-lookup"><span data-stu-id="fbe14-348">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="fbe14-349">0x5 - 调试器。</span><span class="sxs-lookup"><span data-stu-id="fbe14-349">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="fbe14-350">0x6 - 准备垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="fbe14-350">0x6 - Preparation for garbage collection.</span></span>|
|<span data-ttu-id="fbe14-351">计数</span><span class="sxs-lookup"><span data-stu-id="fbe14-351">Count</span></span>|<span data-ttu-id="fbe14-352">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="fbe14-352">win:UInt32</span></span>|<span data-ttu-id="fbe14-353">此时的 GC 计数。</span><span class="sxs-lookup"><span data-stu-id="fbe14-353">The GC count at the time.</span></span> <span data-ttu-id="fbe14-354">通常情况下，会在这之后看到后续 GC 开始事件，且在垃圾回收期间增加 GC 索引时，其计数会增加 1。</span><span class="sxs-lookup"><span data-stu-id="fbe14-354">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|
|<span data-ttu-id="fbe14-355">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="fbe14-355">ClrInstanceID</span></span>|<span data-ttu-id="fbe14-356">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="fbe14-356">win:UInt16</span></span>|<span data-ttu-id="fbe14-357">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="fbe14-357">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcsuspendeeend_v1-event"></a><span data-ttu-id="fbe14-358">GCSuspendEEEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-358">GCSuspendEEEnd_V1 Event</span></span>

<span data-ttu-id="fbe14-359">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="fbe14-359">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="fbe14-360">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="fbe14-360">Keyword for raising the event</span></span>|<span data-ttu-id="fbe14-361">Level</span><span class="sxs-lookup"><span data-stu-id="fbe14-361">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="fbe14-362">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="fbe14-362">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="fbe14-363">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="fbe14-363">Informational (4)</span></span>|

<span data-ttu-id="fbe14-364">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="fbe14-364">The following table shows the event information:</span></span>

|<span data-ttu-id="fbe14-365">Event</span><span class="sxs-lookup"><span data-stu-id="fbe14-365">Event</span></span>|<span data-ttu-id="fbe14-366">事件 ID</span><span class="sxs-lookup"><span data-stu-id="fbe14-366">Event ID</span></span>|<span data-ttu-id="fbe14-367">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="fbe14-367">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEEnd_V1`|<span data-ttu-id="fbe14-368">8</span><span class="sxs-lookup"><span data-stu-id="fbe14-368">8</span></span>|<span data-ttu-id="fbe14-369">结束垃圾回收执行引擎的挂起。</span><span class="sxs-lookup"><span data-stu-id="fbe14-369">End of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="fbe14-370">无事件数据。</span><span class="sxs-lookup"><span data-stu-id="fbe14-370">No event data.</span></span>

## <a name="gcallocationtick_v2-event"></a><span data-ttu-id="fbe14-371">GCAllocationTick_V2 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-371">GCAllocationTick_V2 Event</span></span>

<span data-ttu-id="fbe14-372">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="fbe14-372">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="fbe14-373">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="fbe14-373">Keyword for raising the event</span></span>|<span data-ttu-id="fbe14-374">Level</span><span class="sxs-lookup"><span data-stu-id="fbe14-374">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="fbe14-375">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="fbe14-375">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="fbe14-376">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="fbe14-376">Informational (4)</span></span>|

<span data-ttu-id="fbe14-377">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="fbe14-377">The following table shows the event information:</span></span>

|<span data-ttu-id="fbe14-378">Event</span><span class="sxs-lookup"><span data-stu-id="fbe14-378">Event</span></span>|<span data-ttu-id="fbe14-379">事件 ID</span><span class="sxs-lookup"><span data-stu-id="fbe14-379">Event ID</span></span>|<span data-ttu-id="fbe14-380">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="fbe14-380">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCAllocationTick_V2`|<span data-ttu-id="fbe14-381">10</span><span class="sxs-lookup"><span data-stu-id="fbe14-381">10</span></span>|<span data-ttu-id="fbe14-382">每次大约分配 100 KB。</span><span class="sxs-lookup"><span data-stu-id="fbe14-382">Each time approximately 100 KB is allocated.</span></span>|

<span data-ttu-id="fbe14-383">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="fbe14-383">The following table shows the event data:</span></span>

|<span data-ttu-id="fbe14-384">字段名</span><span class="sxs-lookup"><span data-stu-id="fbe14-384">Field name</span></span>|<span data-ttu-id="fbe14-385">数据类型</span><span class="sxs-lookup"><span data-stu-id="fbe14-385">Data type</span></span>|<span data-ttu-id="fbe14-386">描述</span><span class="sxs-lookup"><span data-stu-id="fbe14-386">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="fbe14-387">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="fbe14-387">AllocationAmount</span></span>|<span data-ttu-id="fbe14-388">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="fbe14-388">win:UInt32</span></span>|<span data-ttu-id="fbe14-389">分配大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="fbe14-389">The allocation size, in bytes.</span></span> <span data-ttu-id="fbe14-390">对于小于 ULONG（4,294,967,295 字节）长度的分配，此值为精确值。</span><span class="sxs-lookup"><span data-stu-id="fbe14-390">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="fbe14-391">如果分配长度更大，则此字段包含了截断的值。</span><span class="sxs-lookup"><span data-stu-id="fbe14-391">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="fbe14-392">对于非常大的分配使用 `AllocationAmount64` 。</span><span class="sxs-lookup"><span data-stu-id="fbe14-392">Use `AllocationAmount64` for very large allocations.</span></span>|
|<span data-ttu-id="fbe14-393">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="fbe14-393">AllocationKind</span></span>|<span data-ttu-id="fbe14-394">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="fbe14-394">win:UInt32</span></span>|<span data-ttu-id="fbe14-395">0x0 - 小型对象分配（小型对象堆中的分配）。</span><span class="sxs-lookup"><span data-stu-id="fbe14-395">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="fbe14-396">0x0 - 大型对象分配（大型对象堆中的分配）。</span><span class="sxs-lookup"><span data-stu-id="fbe14-396">0x1 - Large object allocation (allocation is in large object heap).</span></span>|
|<span data-ttu-id="fbe14-397">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="fbe14-397">ClrInstanceID</span></span>|<span data-ttu-id="fbe14-398">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="fbe14-398">win:UInt16</span></span>|<span data-ttu-id="fbe14-399">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="fbe14-399">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|<span data-ttu-id="fbe14-400">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="fbe14-400">AllocationAmount64</span></span>|<span data-ttu-id="fbe14-401">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="fbe14-401">win:UInt64</span></span>|<span data-ttu-id="fbe14-402">分配大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="fbe14-402">The allocation size, in bytes.</span></span> <span data-ttu-id="fbe14-403">对于非常大的分配，此值为精确值。</span><span class="sxs-lookup"><span data-stu-id="fbe14-403">This value is accurate for very large allocations.</span></span>|
|<span data-ttu-id="fbe14-404">类型 ID</span><span class="sxs-lookup"><span data-stu-id="fbe14-404">TypeId</span></span>|<span data-ttu-id="fbe14-405">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="fbe14-405">win:Pointer</span></span>|<span data-ttu-id="fbe14-406">MethodTable 的地址。</span><span class="sxs-lookup"><span data-stu-id="fbe14-406">The address of the MethodTable.</span></span> <span data-ttu-id="fbe14-407">如果在此事件期间分配了几种类型的对象，则此地址为对应于分配的最后一个对象（导致超过 100 KB 阙值的对象）的 MethodTable 地址。</span><span class="sxs-lookup"><span data-stu-id="fbe14-407">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="fbe14-408">TypeName</span><span class="sxs-lookup"><span data-stu-id="fbe14-408">TypeName</span></span>|<span data-ttu-id="fbe14-409">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="fbe14-409">win:UnicodeString</span></span>|<span data-ttu-id="fbe14-410">已分配的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="fbe14-410">The name of the type that was allocated.</span></span> <span data-ttu-id="fbe14-411">如果在此事件期间分配了几种类型的对象，则此地址为对应于分配的最后一个类型（导致超过 100 KB 阙值的对象）。</span><span class="sxs-lookup"><span data-stu-id="fbe14-411">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="fbe14-412">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="fbe14-412">HeapIndex</span></span>|<span data-ttu-id="fbe14-413">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="fbe14-413">win:UInt32</span></span>|<span data-ttu-id="fbe14-414">此对象所分配到的堆。</span><span class="sxs-lookup"><span data-stu-id="fbe14-414">The heap where the object was allocated.</span></span> <span data-ttu-id="fbe14-415">与工作站垃圾回收一起运行时，此值为 0（零）。</span><span class="sxs-lookup"><span data-stu-id="fbe14-415">This value is 0 (zero) when running with workstation garbage collection.</span></span>|

## <a name="gcfinalizersbegin_v1-event"></a><span data-ttu-id="fbe14-416">GCFinalizersBegin_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-416">GCFinalizersBegin_V1 Event</span></span>

<span data-ttu-id="fbe14-417">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="fbe14-417">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="fbe14-418">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="fbe14-418">Keyword for raising the event</span></span>|<span data-ttu-id="fbe14-419">Level</span><span class="sxs-lookup"><span data-stu-id="fbe14-419">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="fbe14-420">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="fbe14-420">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="fbe14-421">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="fbe14-421">Informational (4)</span></span>|

<span data-ttu-id="fbe14-422">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="fbe14-422">The following table shows the event information:</span></span>

|<span data-ttu-id="fbe14-423">Event</span><span class="sxs-lookup"><span data-stu-id="fbe14-423">Event</span></span>|<span data-ttu-id="fbe14-424">事件 ID</span><span class="sxs-lookup"><span data-stu-id="fbe14-424">Event ID</span></span>|<span data-ttu-id="fbe14-425">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="fbe14-425">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersBegin_V1`|<span data-ttu-id="fbe14-426">14</span><span class="sxs-lookup"><span data-stu-id="fbe14-426">14</span></span>|<span data-ttu-id="fbe14-427">开始运行终结器。</span><span class="sxs-lookup"><span data-stu-id="fbe14-427">The start of running finalizers.</span></span>|

<span data-ttu-id="fbe14-428">无事件数据。</span><span class="sxs-lookup"><span data-stu-id="fbe14-428">No event data.</span></span>

## <a name="gcfinalizersend_v1-event"></a><span data-ttu-id="fbe14-429">GCFinalizersEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-429">GCFinalizersEnd_V1 Event</span></span>

<span data-ttu-id="fbe14-430">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="fbe14-430">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="fbe14-431">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="fbe14-431">Keyword for raising the event</span></span>|<span data-ttu-id="fbe14-432">Level</span><span class="sxs-lookup"><span data-stu-id="fbe14-432">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="fbe14-433">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="fbe14-433">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="fbe14-434">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="fbe14-434">Informational (4)</span></span>|

<span data-ttu-id="fbe14-435">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="fbe14-435">The following table shows the event information:</span></span>

|<span data-ttu-id="fbe14-436">Event</span><span class="sxs-lookup"><span data-stu-id="fbe14-436">Event</span></span>|<span data-ttu-id="fbe14-437">事件 ID</span><span class="sxs-lookup"><span data-stu-id="fbe14-437">Event ID</span></span>|<span data-ttu-id="fbe14-438">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="fbe14-438">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersEnd_V1`|<span data-ttu-id="fbe14-439">13</span><span class="sxs-lookup"><span data-stu-id="fbe14-439">13</span></span>|<span data-ttu-id="fbe14-440">结束运行终结器。</span><span class="sxs-lookup"><span data-stu-id="fbe14-440">The end of running finalizers.</span></span>|

<span data-ttu-id="fbe14-441">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="fbe14-441">The following table shows the event data:</span></span>

|<span data-ttu-id="fbe14-442">字段名</span><span class="sxs-lookup"><span data-stu-id="fbe14-442">Field name</span></span>|<span data-ttu-id="fbe14-443">数据类型</span><span class="sxs-lookup"><span data-stu-id="fbe14-443">Data type</span></span>|<span data-ttu-id="fbe14-444">描述</span><span class="sxs-lookup"><span data-stu-id="fbe14-444">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="fbe14-445">计数</span><span class="sxs-lookup"><span data-stu-id="fbe14-445">Count</span></span>|<span data-ttu-id="fbe14-446">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="fbe14-446">win:UInt32</span></span>|<span data-ttu-id="fbe14-447">运行的终结器数。</span><span class="sxs-lookup"><span data-stu-id="fbe14-447">The number of finalizers that were run.</span></span>|
|<span data-ttu-id="fbe14-448">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="fbe14-448">ClrInstanceID</span></span>|<span data-ttu-id="fbe14-449">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="fbe14-449">win:UInt16</span></span>|<span data-ttu-id="fbe14-450">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="fbe14-450">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gccreateconcurrentthread_v1-event"></a><span data-ttu-id="fbe14-451">GCCreateConcurrentThread_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-451">GCCreateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="fbe14-452">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="fbe14-452">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="fbe14-453">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="fbe14-453">Keyword for raising the event</span></span>|<span data-ttu-id="fbe14-454">Level</span><span class="sxs-lookup"><span data-stu-id="fbe14-454">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="fbe14-455">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="fbe14-455">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="fbe14-456">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="fbe14-456">Informational (4)</span></span>|
|<span data-ttu-id="fbe14-457">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="fbe14-457">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="fbe14-458">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="fbe14-458">Informational (4)</span></span>|

<span data-ttu-id="fbe14-459">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="fbe14-459">The following table shows the event information:</span></span>

|<span data-ttu-id="fbe14-460">Event</span><span class="sxs-lookup"><span data-stu-id="fbe14-460">Event</span></span>|<span data-ttu-id="fbe14-461">事件 ID</span><span class="sxs-lookup"><span data-stu-id="fbe14-461">Event ID</span></span>|<span data-ttu-id="fbe14-462">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="fbe14-462">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="fbe14-463">11</span><span class="sxs-lookup"><span data-stu-id="fbe14-463">11</span></span>|<span data-ttu-id="fbe14-464">已创建并发垃圾回收线程。</span><span class="sxs-lookup"><span data-stu-id="fbe14-464">Concurrent garbage collection thread was created.</span></span>|

<span data-ttu-id="fbe14-465">无事件数据。</span><span class="sxs-lookup"><span data-stu-id="fbe14-465">No event data.</span></span>

## <a name="gcterminateconcurrentthread_v1-event"></a><span data-ttu-id="fbe14-466">GCTerminateConcurrentThread_V1 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-466">GCTerminateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="fbe14-467">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="fbe14-467">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="fbe14-468">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="fbe14-468">Keyword for raising the event</span></span>|<span data-ttu-id="fbe14-469">Level</span><span class="sxs-lookup"><span data-stu-id="fbe14-469">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="fbe14-470">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="fbe14-470">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="fbe14-471">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="fbe14-471">Informational (4)</span></span>|
|<span data-ttu-id="fbe14-472">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="fbe14-472">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="fbe14-473">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="fbe14-473">Informational (4)</span></span>|

<span data-ttu-id="fbe14-474">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="fbe14-474">The following table shows the event information:</span></span>

|<span data-ttu-id="fbe14-475">Event</span><span class="sxs-lookup"><span data-stu-id="fbe14-475">Event</span></span>|<span data-ttu-id="fbe14-476">事件 ID</span><span class="sxs-lookup"><span data-stu-id="fbe14-476">Event ID</span></span>|<span data-ttu-id="fbe14-477">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="fbe14-477">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="fbe14-478">12</span><span class="sxs-lookup"><span data-stu-id="fbe14-478">12</span></span>|<span data-ttu-id="fbe14-479">已终止并发垃圾回收线程。</span><span class="sxs-lookup"><span data-stu-id="fbe14-479">Concurrent garbage collection thread was terminated.</span></span>|

<span data-ttu-id="fbe14-480">无事件数据。</span><span class="sxs-lookup"><span data-stu-id="fbe14-480">No event data.</span></span>

## <a name="see-also"></a><span data-ttu-id="fbe14-481">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fbe14-481">See also</span></span>

- [<span data-ttu-id="fbe14-482">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="fbe14-482">CLR ETW Events</span></span>](clr-etw-events.md)
