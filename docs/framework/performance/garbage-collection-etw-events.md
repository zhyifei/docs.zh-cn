---
title: 垃圾回收 ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- GC events
- garbage collection events [.NET Framework]
- ETW, garbage collection events (CLR)
ms.assetid: f14b6fd7-0966-4d87-bc89-54ef3a44a94a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cd4a4699f115c5b134ea60e703607ff36c229a78
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040584"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="c8ead-102">垃圾回收 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-102">Garbage Collection ETW Events</span></span>

<span data-ttu-id="c8ead-103">这些事件可收集有关垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="c8ead-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="c8ead-104">它们可帮助进行诊断和调试，包括确定垃圾回收执行的次数、垃圾回收期间释放的内存量等。</span><span class="sxs-lookup"><span data-stu-id="c8ead-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>

<span data-ttu-id="c8ead-105">此类别包含以下事件：</span><span class="sxs-lookup"><span data-stu-id="c8ead-105">This category consists of the following events:</span></span>

- [<span data-ttu-id="c8ead-106">GCStart_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-106">GCStart_V1 Event</span></span>](#gcstart_v1-event)
- [<span data-ttu-id="c8ead-107">GCEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-107">GCEnd_V1 Event</span></span>](#gcend_v1-event)
- [<span data-ttu-id="c8ead-108">GCHeapStats_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1-event)
- [<span data-ttu-id="c8ead-109">GCCreateSegment_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1-event)
- [<span data-ttu-id="c8ead-110">GCFreeSegment_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1-event)
- [<span data-ttu-id="c8ead-111">GCRestartEEBegin_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1-event)
- [<span data-ttu-id="c8ead-112">GCRestartEEEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1-event)
- [<span data-ttu-id="c8ead-113">GCSuspendEE_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1-event)
- [<span data-ttu-id="c8ead-114">GCSuspendEEEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1-event)
- [<span data-ttu-id="c8ead-115">GCAllocationTick_V2 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2-event)
- [<span data-ttu-id="c8ead-116">GCFinalizersBegin_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1-event)
- [<span data-ttu-id="c8ead-117">GCFinalizersEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1-event)
- [<span data-ttu-id="c8ead-118">GCCreateConcurrentThread_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1-event)
- [<span data-ttu-id="c8ead-119">GCTerminateConcurrentThread_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1-event)

## <a name="gcstart_v1-event"></a><span data-ttu-id="c8ead-120">GCStart_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-120">GCStart_V1 Event</span></span>  

<span data-ttu-id="c8ead-121">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="c8ead-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="c8ead-122">有关详细信息，请参阅[CLR ETW 关键字和级别](clr-etw-keywords-and-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="c8ead-122">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="c8ead-123">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="c8ead-123">Keyword for raising the event</span></span>|<span data-ttu-id="c8ead-124">层次</span><span class="sxs-lookup"><span data-stu-id="c8ead-124">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8ead-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8ead-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8ead-126">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="c8ead-126">Informational (4)</span></span>|

<span data-ttu-id="c8ead-127">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="c8ead-127">The following table shows the event information:</span></span>

|<span data-ttu-id="c8ead-128">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-128">Event</span></span>|<span data-ttu-id="c8ead-129">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c8ead-129">Event ID</span></span>|<span data-ttu-id="c8ead-130">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="c8ead-130">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCStart_V1`|<span data-ttu-id="c8ead-131">1</span><span class="sxs-lookup"><span data-stu-id="c8ead-131">1</span></span>|<span data-ttu-id="c8ead-132">垃圾回收已启动。</span><span class="sxs-lookup"><span data-stu-id="c8ead-132">A garbage collection has started.</span></span>|

<span data-ttu-id="c8ead-133">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="c8ead-133">The following table shows the event data:</span></span>

|<span data-ttu-id="c8ead-134">字段名</span><span class="sxs-lookup"><span data-stu-id="c8ead-134">Field name</span></span>|<span data-ttu-id="c8ead-135">数据类型</span><span class="sxs-lookup"><span data-stu-id="c8ead-135">Data type</span></span>|<span data-ttu-id="c8ead-136">描述</span><span class="sxs-lookup"><span data-stu-id="c8ead-136">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="c8ead-137">计数</span><span class="sxs-lookup"><span data-stu-id="c8ead-137">Count</span></span>|<span data-ttu-id="c8ead-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8ead-138">win:UInt32</span></span>|<span data-ttu-id="c8ead-139">第 *n*代垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="c8ead-139">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="c8ead-140">深度</span><span class="sxs-lookup"><span data-stu-id="c8ead-140">Depth</span></span>|<span data-ttu-id="c8ead-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8ead-141">win:UInt32</span></span>|<span data-ttu-id="c8ead-142">正在回收的代。</span><span class="sxs-lookup"><span data-stu-id="c8ead-142">The generation that is being collected.</span></span>|
|<span data-ttu-id="c8ead-143">原因</span><span class="sxs-lookup"><span data-stu-id="c8ead-143">Reason</span></span>|<span data-ttu-id="c8ead-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8ead-144">win:UInt32</span></span>|<span data-ttu-id="c8ead-145">垃圾回收的触发原因：</span><span class="sxs-lookup"><span data-stu-id="c8ead-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="c8ead-146">0x0 - 小型对象堆分配。</span><span class="sxs-lookup"><span data-stu-id="c8ead-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="c8ead-147">0x1 - 已引发。</span><span class="sxs-lookup"><span data-stu-id="c8ead-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="c8ead-148">0x2 - 内存不足。</span><span class="sxs-lookup"><span data-stu-id="c8ead-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="c8ead-149">0x3 - 空。</span><span class="sxs-lookup"><span data-stu-id="c8ead-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="c8ead-150">0x4 - 大型对象堆分配。</span><span class="sxs-lookup"><span data-stu-id="c8ead-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="c8ead-151">0x5 - 空间不足（针对小型对象堆）。</span><span class="sxs-lookup"><span data-stu-id="c8ead-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="c8ead-152">0x6 - 空间不足（针对大型对象堆）。</span><span class="sxs-lookup"><span data-stu-id="c8ead-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="c8ead-153">0x7 - 已引发，但未强制为阻止。</span><span class="sxs-lookup"><span data-stu-id="c8ead-153">0x7 - Induced but not forced as blocking.</span></span>|
|<span data-ttu-id="c8ead-154">键入</span><span class="sxs-lookup"><span data-stu-id="c8ead-154">Type</span></span>|<span data-ttu-id="c8ead-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8ead-155">win:UInt32</span></span>|<span data-ttu-id="c8ead-156">0x0 - 在后台垃圾回收外部发生了垃圾回收阻止。</span><span class="sxs-lookup"><span data-stu-id="c8ead-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="c8ead-157">0x1 - 后台垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="c8ead-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="c8ead-158">0x0 - 后台垃圾回收期间发生了垃圾回收阻止。</span><span class="sxs-lookup"><span data-stu-id="c8ead-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|
|<span data-ttu-id="c8ead-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c8ead-159">ClrInstanceID</span></span>|<span data-ttu-id="c8ead-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c8ead-160">win:UInt16</span></span>|<span data-ttu-id="c8ead-161">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="c8ead-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcend_v1-event"></a><span data-ttu-id="c8ead-162">GCEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-162">GCEnd_V1 Event</span></span>

<span data-ttu-id="c8ead-163">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="c8ead-163">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8ead-164">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="c8ead-164">Keyword for raising the event</span></span>|<span data-ttu-id="c8ead-165">层次</span><span class="sxs-lookup"><span data-stu-id="c8ead-165">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8ead-166">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8ead-166">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8ead-167">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="c8ead-167">Informational (4)</span></span>|

<span data-ttu-id="c8ead-168">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="c8ead-168">The following table shows the event information:</span></span>

|<span data-ttu-id="c8ead-169">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-169">Event</span></span>|<span data-ttu-id="c8ead-170">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c8ead-170">Event ID</span></span>|<span data-ttu-id="c8ead-171">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="c8ead-171">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCEnd_V1`|<span data-ttu-id="c8ead-172">2</span><span class="sxs-lookup"><span data-stu-id="c8ead-172">2</span></span>|<span data-ttu-id="c8ead-173">垃圾回收已结束。</span><span class="sxs-lookup"><span data-stu-id="c8ead-173">The garbage collection has ended.</span></span>|

<span data-ttu-id="c8ead-174">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="c8ead-174">The following table shows the event data:</span></span>

|<span data-ttu-id="c8ead-175">字段名</span><span class="sxs-lookup"><span data-stu-id="c8ead-175">Field name</span></span>|<span data-ttu-id="c8ead-176">数据类型</span><span class="sxs-lookup"><span data-stu-id="c8ead-176">Data type</span></span>|<span data-ttu-id="c8ead-177">描述</span><span class="sxs-lookup"><span data-stu-id="c8ead-177">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="c8ead-178">计数</span><span class="sxs-lookup"><span data-stu-id="c8ead-178">Count</span></span>|<span data-ttu-id="c8ead-179">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8ead-179">win:UInt32</span></span>|<span data-ttu-id="c8ead-180">第 *n*代垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="c8ead-180">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="c8ead-181">深度</span><span class="sxs-lookup"><span data-stu-id="c8ead-181">Depth</span></span>|<span data-ttu-id="c8ead-182">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8ead-182">win:UInt32</span></span>|<span data-ttu-id="c8ead-183">已回收的代。</span><span class="sxs-lookup"><span data-stu-id="c8ead-183">The generation that was collected.</span></span>|
|<span data-ttu-id="c8ead-184">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c8ead-184">ClrInstanceID</span></span>|<span data-ttu-id="c8ead-185">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c8ead-185">win:UInt16</span></span>|<span data-ttu-id="c8ead-186">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="c8ead-186">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcheapstats_v1-event"></a><span data-ttu-id="c8ead-187">GCHeapStats_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-187">GCHeapStats_V1 Event</span></span>

<span data-ttu-id="c8ead-188">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="c8ead-188">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8ead-189">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="c8ead-189">Keyword for raising the event</span></span>|<span data-ttu-id="c8ead-190">层次</span><span class="sxs-lookup"><span data-stu-id="c8ead-190">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8ead-191">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8ead-191">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8ead-192">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="c8ead-192">Informational (4)</span></span>|

<span data-ttu-id="c8ead-193">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="c8ead-193">The following table shows the event information:</span></span>

|<span data-ttu-id="c8ead-194">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-194">Event</span></span>|<span data-ttu-id="c8ead-195">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c8ead-195">Event ID</span></span>|<span data-ttu-id="c8ead-196">描述</span><span class="sxs-lookup"><span data-stu-id="c8ead-196">Description</span></span>|
|-----------|--------------|-----------------|
|`GCHeapStats_V1`|<span data-ttu-id="c8ead-197">4</span><span class="sxs-lookup"><span data-stu-id="c8ead-197">4</span></span>|<span data-ttu-id="c8ead-198">在每次垃圾回收结束时显示堆统计信息。</span><span class="sxs-lookup"><span data-stu-id="c8ead-198">Shows the heap statistics at the end of each garbage collection.</span></span>|

<span data-ttu-id="c8ead-199">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="c8ead-199">The following table shows the event data:</span></span>

|<span data-ttu-id="c8ead-200">字段名</span><span class="sxs-lookup"><span data-stu-id="c8ead-200">Field name</span></span>|<span data-ttu-id="c8ead-201">数据类型</span><span class="sxs-lookup"><span data-stu-id="c8ead-201">Data type</span></span>|<span data-ttu-id="c8ead-202">描述</span><span class="sxs-lookup"><span data-stu-id="c8ead-202">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="c8ead-203">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="c8ead-203">GenerationSize0</span></span>|<span data-ttu-id="c8ead-204">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8ead-204">win:UInt64</span></span>|<span data-ttu-id="c8ead-205">第 0 代内存的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="c8ead-205">The size, in bytes, of generation 0 memory.</span></span>|
|<span data-ttu-id="c8ead-206">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="c8ead-206">TotalPromotedSize0</span></span>|<span data-ttu-id="c8ead-207">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8ead-207">win:UInt64</span></span>|<span data-ttu-id="c8ead-208">从第 0 代提升到第 1 代的字节数。</span><span class="sxs-lookup"><span data-stu-id="c8ead-208">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|
|<span data-ttu-id="c8ead-209">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="c8ead-209">GenerationSize1</span></span>|<span data-ttu-id="c8ead-210">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8ead-210">win:UInt64</span></span>|<span data-ttu-id="c8ead-211">第 1 代内存的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="c8ead-211">The size, in bytes, of generation 1 memory.</span></span>|
|<span data-ttu-id="c8ead-212">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="c8ead-212">TotalPromotedSize1</span></span>|<span data-ttu-id="c8ead-213">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8ead-213">win:UInt64</span></span>|<span data-ttu-id="c8ead-214">从第 1 代提升到第 2 代的字节数。</span><span class="sxs-lookup"><span data-stu-id="c8ead-214">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|
|<span data-ttu-id="c8ead-215">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="c8ead-215">GenerationSize2</span></span>|<span data-ttu-id="c8ead-216">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8ead-216">win:UInt64</span></span>|<span data-ttu-id="c8ead-217">第 2 代内存的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="c8ead-217">The size, in bytes, of generation 2 memory.</span></span>|
|<span data-ttu-id="c8ead-218">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="c8ead-218">TotalPromotedSize2</span></span>|<span data-ttu-id="c8ead-219">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8ead-219">win:UInt64</span></span>|<span data-ttu-id="c8ead-220">上次回收后仍存在于第 2 代中的字节数。</span><span class="sxs-lookup"><span data-stu-id="c8ead-220">The number of bytes that survived in generation 2 after the last collection.</span></span>|
|<span data-ttu-id="c8ead-221">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="c8ead-221">GenerationSize3</span></span>|<span data-ttu-id="c8ead-222">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8ead-222">win:UInt64</span></span>|<span data-ttu-id="c8ead-223">大型对象堆的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="c8ead-223">The size, in bytes, of the large object heap.</span></span>|
|<span data-ttu-id="c8ead-224">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="c8ead-224">TotalPromotedSize3</span></span>|<span data-ttu-id="c8ead-225">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8ead-225">win:UInt64</span></span>|<span data-ttu-id="c8ead-226">上次回收后仍存在于大型对象堆中的字节数。</span><span class="sxs-lookup"><span data-stu-id="c8ead-226">The number of bytes that survived in the large object heap after the last collection.</span></span>|
|<span data-ttu-id="c8ead-227">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="c8ead-227">FinalizationPromotedSize</span></span>|<span data-ttu-id="c8ead-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8ead-228">win:UInt64</span></span>|<span data-ttu-id="c8ead-229">准备终结的对象的总大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="c8ead-229">The total size, in bytes, of the objects that are ready for finalization.</span></span>|
|<span data-ttu-id="c8ead-230">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="c8ead-230">FinalizationPromotedCount</span></span>|<span data-ttu-id="c8ead-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8ead-231">win:UInt64</span></span>|<span data-ttu-id="c8ead-232">已准备好进行终结的对象的数目。</span><span class="sxs-lookup"><span data-stu-id="c8ead-232">The number of objects that are ready for finalization.</span></span>|
|<span data-ttu-id="c8ead-233">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="c8ead-233">PinnedObjectCount</span></span>|<span data-ttu-id="c8ead-234">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8ead-234">win:UInt32</span></span>|<span data-ttu-id="c8ead-235">固定（不可移动）对象的数目。</span><span class="sxs-lookup"><span data-stu-id="c8ead-235">The number of pinned (unmovable) objects.</span></span>|
|<span data-ttu-id="c8ead-236">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="c8ead-236">SinkBlockCount</span></span>|<span data-ttu-id="c8ead-237">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8ead-237">win:UInt32</span></span>|<span data-ttu-id="c8ead-238">正在使用的同步块的数目。</span><span class="sxs-lookup"><span data-stu-id="c8ead-238">The number of synchronization blocks in use.</span></span>|
|<span data-ttu-id="c8ead-239">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="c8ead-239">GCHandleCount</span></span>|<span data-ttu-id="c8ead-240">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8ead-240">win:UInt32</span></span>|<span data-ttu-id="c8ead-241">使用中的垃圾回收句柄的数目。</span><span class="sxs-lookup"><span data-stu-id="c8ead-241">The number of garbage collection handles in use.</span></span>|
|<span data-ttu-id="c8ead-242">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c8ead-242">ClrInstanceID</span></span>|<span data-ttu-id="c8ead-243">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c8ead-243">win:UInt16</span></span>|<span data-ttu-id="c8ead-244">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="c8ead-244">Unique ID for the instance of CLR or CoreCLR.</span></span>|
  
## <a name="gccreatesegment_v1-event"></a><span data-ttu-id="c8ead-245">GCCreateSegment_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-245">GCCreateSegment_V1 Event</span></span>

<span data-ttu-id="c8ead-246">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="c8ead-246">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8ead-247">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="c8ead-247">Keyword for raising the event</span></span>|<span data-ttu-id="c8ead-248">层次</span><span class="sxs-lookup"><span data-stu-id="c8ead-248">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8ead-249">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8ead-249">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8ead-250">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="c8ead-250">Informational (4)</span></span>|

<span data-ttu-id="c8ead-251">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="c8ead-251">The following table shows the event information:</span></span>

|<span data-ttu-id="c8ead-252">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-252">Event</span></span>|<span data-ttu-id="c8ead-253">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c8ead-253">Event ID</span></span>|<span data-ttu-id="c8ead-254">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="c8ead-254">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateSegment_V1`|<span data-ttu-id="c8ead-255">5</span><span class="sxs-lookup"><span data-stu-id="c8ead-255">5</span></span>|<span data-ttu-id="c8ead-256">已创建的新的垃圾回收段。</span><span class="sxs-lookup"><span data-stu-id="c8ead-256">A new garbage collection segment has been created.</span></span> <span data-ttu-id="c8ead-257">此外，当在已运行的进程中启用跟踪时，将为每个现有段引发此事件。</span><span class="sxs-lookup"><span data-stu-id="c8ead-257">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|

<span data-ttu-id="c8ead-258">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="c8ead-258">The following table shows the event data:</span></span>

|<span data-ttu-id="c8ead-259">字段名</span><span class="sxs-lookup"><span data-stu-id="c8ead-259">Field name</span></span>|<span data-ttu-id="c8ead-260">数据类型</span><span class="sxs-lookup"><span data-stu-id="c8ead-260">Data type</span></span>|<span data-ttu-id="c8ead-261">描述</span><span class="sxs-lookup"><span data-stu-id="c8ead-261">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="c8ead-262">Address</span><span class="sxs-lookup"><span data-stu-id="c8ead-262">Address</span></span>|<span data-ttu-id="c8ead-263">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8ead-263">win:UInt64</span></span>|<span data-ttu-id="c8ead-264">段的地址。</span><span class="sxs-lookup"><span data-stu-id="c8ead-264">The address of the segment.</span></span>|
|<span data-ttu-id="c8ead-265">大小</span><span class="sxs-lookup"><span data-stu-id="c8ead-265">Size</span></span>|<span data-ttu-id="c8ead-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8ead-266">win:UInt64</span></span>|<span data-ttu-id="c8ead-267">段的大小。</span><span class="sxs-lookup"><span data-stu-id="c8ead-267">The size of the segment.</span></span>|
|<span data-ttu-id="c8ead-268">键入</span><span class="sxs-lookup"><span data-stu-id="c8ead-268">Type</span></span>|<span data-ttu-id="c8ead-269">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8ead-269">win:UInt32</span></span>|<span data-ttu-id="c8ead-270">0x0 - 小型对象堆。</span><span class="sxs-lookup"><span data-stu-id="c8ead-270">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="c8ead-271">0x0 - 大型对象堆。</span><span class="sxs-lookup"><span data-stu-id="c8ead-271">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="c8ead-272">0x2 - 只读堆。</span><span class="sxs-lookup"><span data-stu-id="c8ead-272">0x2 - Read-only heap.</span></span>|
|<span data-ttu-id="c8ead-273">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c8ead-273">ClrInstanceID</span></span>|<span data-ttu-id="c8ead-274">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c8ead-274">win:UInt16</span></span>|<span data-ttu-id="c8ead-275">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="c8ead-275">Unique ID for the instance of CLR or CoreCLR.</span></span>|

<span data-ttu-id="c8ead-276">请注意，由垃圾回收器分配的段的大小特定于实现，且随时可能更改（包括定期更新）。</span><span class="sxs-lookup"><span data-stu-id="c8ead-276">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="c8ead-277">应用程序不应假设特定段的大小或依赖于此大小，也不应尝试配置段分配可用的内存量。</span><span class="sxs-lookup"><span data-stu-id="c8ead-277">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

## <a name="gcfreesegment_v1-event"></a><span data-ttu-id="c8ead-278">GCFreeSegment_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-278">GCFreeSegment_V1 Event</span></span>

<span data-ttu-id="c8ead-279">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="c8ead-279">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8ead-280">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="c8ead-280">Keyword for raising the event</span></span>|<span data-ttu-id="c8ead-281">层次</span><span class="sxs-lookup"><span data-stu-id="c8ead-281">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8ead-282">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8ead-282">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8ead-283">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="c8ead-283">Informational (4)</span></span>|

<span data-ttu-id="c8ead-284">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="c8ead-284">The following table shows the event information:</span></span>

|<span data-ttu-id="c8ead-285">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-285">Event</span></span>|<span data-ttu-id="c8ead-286">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c8ead-286">Event ID</span></span>|<span data-ttu-id="c8ead-287">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="c8ead-287">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFreeSegment_V1`|<span data-ttu-id="c8ead-288">6</span><span class="sxs-lookup"><span data-stu-id="c8ead-288">6</span></span>|<span data-ttu-id="c8ead-289">已释放垃圾回收段。</span><span class="sxs-lookup"><span data-stu-id="c8ead-289">A garbage collection segment has been released.</span></span>|

<span data-ttu-id="c8ead-290">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="c8ead-290">The following table shows the event data:</span></span>

|<span data-ttu-id="c8ead-291">字段名</span><span class="sxs-lookup"><span data-stu-id="c8ead-291">Field name</span></span>|<span data-ttu-id="c8ead-292">数据类型</span><span class="sxs-lookup"><span data-stu-id="c8ead-292">Data type</span></span>|<span data-ttu-id="c8ead-293">描述</span><span class="sxs-lookup"><span data-stu-id="c8ead-293">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="c8ead-294">Address</span><span class="sxs-lookup"><span data-stu-id="c8ead-294">Address</span></span>|<span data-ttu-id="c8ead-295">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8ead-295">win:UInt64</span></span>|<span data-ttu-id="c8ead-296">段的地址。</span><span class="sxs-lookup"><span data-stu-id="c8ead-296">The address of the segment.</span></span>|
|<span data-ttu-id="c8ead-297">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c8ead-297">ClrInstanceID</span></span>|<span data-ttu-id="c8ead-298">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c8ead-298">win:UInt16</span></span>|<span data-ttu-id="c8ead-299">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="c8ead-299">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcrestarteebegin_v1-event"></a><span data-ttu-id="c8ead-300">GCRestartEEBegin_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-300">GCRestartEEBegin_V1 Event</span></span>

<span data-ttu-id="c8ead-301">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="c8ead-301">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8ead-302">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="c8ead-302">Keyword for raising the event</span></span>|<span data-ttu-id="c8ead-303">层次</span><span class="sxs-lookup"><span data-stu-id="c8ead-303">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8ead-304">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8ead-304">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8ead-305">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="c8ead-305">Informational (4)</span></span>|

<span data-ttu-id="c8ead-306">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="c8ead-306">The following table shows the event information:</span></span>

|<span data-ttu-id="c8ead-307">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-307">Event</span></span>|<span data-ttu-id="c8ead-308">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c8ead-308">Event ID</span></span>|<span data-ttu-id="c8ead-309">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="c8ead-309">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEBegin_V1`|<span data-ttu-id="c8ead-310">7</span><span class="sxs-lookup"><span data-stu-id="c8ead-310">7</span></span>|<span data-ttu-id="c8ead-311">已开始从公共语言运行时挂起进行恢复。</span><span class="sxs-lookup"><span data-stu-id="c8ead-311">Resumption from common language runtime suspension has begun.</span></span>|

<span data-ttu-id="c8ead-312">无事件数据。</span><span class="sxs-lookup"><span data-stu-id="c8ead-312">No event data.</span></span>

## <a name="gcrestarteeend_v1-event"></a><span data-ttu-id="c8ead-313">GCRestartEEEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-313">GCRestartEEEnd_V1 Event</span></span>

<span data-ttu-id="c8ead-314">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="c8ead-314">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8ead-315">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="c8ead-315">Keyword for raising the event</span></span>|<span data-ttu-id="c8ead-316">层次</span><span class="sxs-lookup"><span data-stu-id="c8ead-316">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8ead-317">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8ead-317">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8ead-318">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="c8ead-318">Informational (4)</span></span>|

<span data-ttu-id="c8ead-319">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="c8ead-319">The following table shows the event information:</span></span>

|<span data-ttu-id="c8ead-320">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-320">Event</span></span>|<span data-ttu-id="c8ead-321">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c8ead-321">Event Id</span></span>|<span data-ttu-id="c8ead-322">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="c8ead-322">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEEnd_V1`|<span data-ttu-id="c8ead-323">3</span><span class="sxs-lookup"><span data-stu-id="c8ead-323">3</span></span>|<span data-ttu-id="c8ead-324">从公共语言运行时挂起进行的恢复已结束。</span><span class="sxs-lookup"><span data-stu-id="c8ead-324">Resumption from common language runtime suspension has ended.</span></span>|

<span data-ttu-id="c8ead-325">无事件数据。</span><span class="sxs-lookup"><span data-stu-id="c8ead-325">No event data.</span></span>

## <a name="gcsuspendee_v1-event"></a><span data-ttu-id="c8ead-326">GCSuspendEE_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-326">GCSuspendEE_V1 Event</span></span>

<span data-ttu-id="c8ead-327">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="c8ead-327">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8ead-328">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="c8ead-328">Keyword for raising the event</span></span>|<span data-ttu-id="c8ead-329">层次</span><span class="sxs-lookup"><span data-stu-id="c8ead-329">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8ead-330">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8ead-330">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8ead-331">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="c8ead-331">Informational (4)</span></span>|

<span data-ttu-id="c8ead-332">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="c8ead-332">The following table shows the event information:</span></span>

|<span data-ttu-id="c8ead-333">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-333">Event</span></span>|<span data-ttu-id="c8ead-334">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c8ead-334">Event ID</span></span>|<span data-ttu-id="c8ead-335">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="c8ead-335">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEE_V1`|<span data-ttu-id="c8ead-336">9</span><span class="sxs-lookup"><span data-stu-id="c8ead-336">9</span></span>|<span data-ttu-id="c8ead-337">开始挂起垃圾回收的执行引擎。</span><span class="sxs-lookup"><span data-stu-id="c8ead-337">Start of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="c8ead-338">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="c8ead-338">The following table shows the event data:</span></span>

|<span data-ttu-id="c8ead-339">字段名</span><span class="sxs-lookup"><span data-stu-id="c8ead-339">Field name</span></span>|<span data-ttu-id="c8ead-340">数据类型</span><span class="sxs-lookup"><span data-stu-id="c8ead-340">Data type</span></span>|<span data-ttu-id="c8ead-341">描述</span><span class="sxs-lookup"><span data-stu-id="c8ead-341">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="c8ead-342">原因</span><span class="sxs-lookup"><span data-stu-id="c8ead-342">Reason</span></span>|<span data-ttu-id="c8ead-343">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c8ead-343">win:UInt16</span></span>|<span data-ttu-id="c8ead-344">0x0 - 其他。</span><span class="sxs-lookup"><span data-stu-id="c8ead-344">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="c8ead-345">0x1 - 垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="c8ead-345">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="c8ead-346">0x2 - 应用程序域关闭。</span><span class="sxs-lookup"><span data-stu-id="c8ead-346">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="c8ead-347">0x3 - 代码间距调整。</span><span class="sxs-lookup"><span data-stu-id="c8ead-347">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="c8ead-348">0x4 - 关闭。</span><span class="sxs-lookup"><span data-stu-id="c8ead-348">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="c8ead-349">0x5 - 调试器。</span><span class="sxs-lookup"><span data-stu-id="c8ead-349">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="c8ead-350">0x6 - 准备垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="c8ead-350">0x6 - Preparation for garbage collection.</span></span>|
|<span data-ttu-id="c8ead-351">计数</span><span class="sxs-lookup"><span data-stu-id="c8ead-351">Count</span></span>|<span data-ttu-id="c8ead-352">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8ead-352">win:UInt32</span></span>|<span data-ttu-id="c8ead-353">此时的 GC 计数。</span><span class="sxs-lookup"><span data-stu-id="c8ead-353">The GC count at the time.</span></span> <span data-ttu-id="c8ead-354">通常情况下，会在这之后看到后续 GC 开始事件，且在垃圾回收期间增加 GC 索引时，其计数会增加 1。</span><span class="sxs-lookup"><span data-stu-id="c8ead-354">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|
|<span data-ttu-id="c8ead-355">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c8ead-355">ClrInstanceID</span></span>|<span data-ttu-id="c8ead-356">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c8ead-356">win:UInt16</span></span>|<span data-ttu-id="c8ead-357">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="c8ead-357">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcsuspendeeend_v1-event"></a><span data-ttu-id="c8ead-358">GCSuspendEEEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-358">GCSuspendEEEnd_V1 Event</span></span>

<span data-ttu-id="c8ead-359">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="c8ead-359">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8ead-360">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="c8ead-360">Keyword for raising the event</span></span>|<span data-ttu-id="c8ead-361">层次</span><span class="sxs-lookup"><span data-stu-id="c8ead-361">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8ead-362">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8ead-362">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8ead-363">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="c8ead-363">Informational (4)</span></span>|

<span data-ttu-id="c8ead-364">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="c8ead-364">The following table shows the event information:</span></span>

|<span data-ttu-id="c8ead-365">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-365">Event</span></span>|<span data-ttu-id="c8ead-366">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c8ead-366">Event ID</span></span>|<span data-ttu-id="c8ead-367">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="c8ead-367">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEEnd_V1`|<span data-ttu-id="c8ead-368">8</span><span class="sxs-lookup"><span data-stu-id="c8ead-368">8</span></span>|<span data-ttu-id="c8ead-369">结束垃圾回收执行引擎的挂起。</span><span class="sxs-lookup"><span data-stu-id="c8ead-369">End of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="c8ead-370">无事件数据。</span><span class="sxs-lookup"><span data-stu-id="c8ead-370">No event data.</span></span>

## <a name="gcallocationtick_v2-event"></a><span data-ttu-id="c8ead-371">GCAllocationTick_V2 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-371">GCAllocationTick_V2 Event</span></span>

<span data-ttu-id="c8ead-372">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="c8ead-372">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8ead-373">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="c8ead-373">Keyword for raising the event</span></span>|<span data-ttu-id="c8ead-374">层次</span><span class="sxs-lookup"><span data-stu-id="c8ead-374">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8ead-375">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8ead-375">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8ead-376">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="c8ead-376">Informational (4)</span></span>|

<span data-ttu-id="c8ead-377">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="c8ead-377">The following table shows the event information:</span></span>

|<span data-ttu-id="c8ead-378">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-378">Event</span></span>|<span data-ttu-id="c8ead-379">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c8ead-379">Event ID</span></span>|<span data-ttu-id="c8ead-380">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="c8ead-380">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCAllocationTick_V2`|<span data-ttu-id="c8ead-381">10</span><span class="sxs-lookup"><span data-stu-id="c8ead-381">10</span></span>|<span data-ttu-id="c8ead-382">每次大约分配 100 KB。</span><span class="sxs-lookup"><span data-stu-id="c8ead-382">Each time approximately 100 KB is allocated.</span></span>|

<span data-ttu-id="c8ead-383">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="c8ead-383">The following table shows the event data:</span></span>

|<span data-ttu-id="c8ead-384">字段名</span><span class="sxs-lookup"><span data-stu-id="c8ead-384">Field name</span></span>|<span data-ttu-id="c8ead-385">数据类型</span><span class="sxs-lookup"><span data-stu-id="c8ead-385">Data type</span></span>|<span data-ttu-id="c8ead-386">描述</span><span class="sxs-lookup"><span data-stu-id="c8ead-386">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="c8ead-387">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="c8ead-387">AllocationAmount</span></span>|<span data-ttu-id="c8ead-388">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8ead-388">win:UInt32</span></span>|<span data-ttu-id="c8ead-389">分配大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="c8ead-389">The allocation size, in bytes.</span></span> <span data-ttu-id="c8ead-390">对于小于 ULONG（4,294,967,295 字节）长度的分配，此值为精确值。</span><span class="sxs-lookup"><span data-stu-id="c8ead-390">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="c8ead-391">如果分配长度更大，则此字段包含了截断的值。</span><span class="sxs-lookup"><span data-stu-id="c8ead-391">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="c8ead-392">对于非常大的分配使用 `AllocationAmount64` 。</span><span class="sxs-lookup"><span data-stu-id="c8ead-392">Use `AllocationAmount64` for very large allocations.</span></span>|
|<span data-ttu-id="c8ead-393">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="c8ead-393">AllocationKind</span></span>|<span data-ttu-id="c8ead-394">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8ead-394">win:UInt32</span></span>|<span data-ttu-id="c8ead-395">0x0 - 小型对象分配（小型对象堆中的分配）。</span><span class="sxs-lookup"><span data-stu-id="c8ead-395">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="c8ead-396">0x0 - 大型对象分配（大型对象堆中的分配）。</span><span class="sxs-lookup"><span data-stu-id="c8ead-396">0x1 - Large object allocation (allocation is in large object heap).</span></span>|
|<span data-ttu-id="c8ead-397">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c8ead-397">ClrInstanceID</span></span>|<span data-ttu-id="c8ead-398">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c8ead-398">win:UInt16</span></span>|<span data-ttu-id="c8ead-399">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="c8ead-399">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|<span data-ttu-id="c8ead-400">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="c8ead-400">AllocationAmount64</span></span>|<span data-ttu-id="c8ead-401">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8ead-401">win:UInt64</span></span>|<span data-ttu-id="c8ead-402">分配大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="c8ead-402">The allocation size, in bytes.</span></span> <span data-ttu-id="c8ead-403">对于非常大的分配，此值为精确值。</span><span class="sxs-lookup"><span data-stu-id="c8ead-403">This value is accurate for very large allocations.</span></span>|
|<span data-ttu-id="c8ead-404">TypeId</span><span class="sxs-lookup"><span data-stu-id="c8ead-404">TypeId</span></span>|<span data-ttu-id="c8ead-405">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="c8ead-405">win:Pointer</span></span>|<span data-ttu-id="c8ead-406">MethodTable 的地址。</span><span class="sxs-lookup"><span data-stu-id="c8ead-406">The address of the MethodTable.</span></span> <span data-ttu-id="c8ead-407">如果在此事件期间分配了几种类型的对象，则此地址为对应于分配的最后一个对象（导致超过 100 KB 阙值的对象）的 MethodTable 地址。</span><span class="sxs-lookup"><span data-stu-id="c8ead-407">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="c8ead-408">TypeName</span><span class="sxs-lookup"><span data-stu-id="c8ead-408">TypeName</span></span>|<span data-ttu-id="c8ead-409">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="c8ead-409">win:UnicodeString</span></span>|<span data-ttu-id="c8ead-410">已分配的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="c8ead-410">The name of the type that was allocated.</span></span> <span data-ttu-id="c8ead-411">如果在此事件期间分配了几种类型的对象，则此地址为对应于分配的最后一个类型（导致超过 100 KB 阙值的对象）。</span><span class="sxs-lookup"><span data-stu-id="c8ead-411">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="c8ead-412">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="c8ead-412">HeapIndex</span></span>|<span data-ttu-id="c8ead-413">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8ead-413">win:UInt32</span></span>|<span data-ttu-id="c8ead-414">此对象所分配到的堆。</span><span class="sxs-lookup"><span data-stu-id="c8ead-414">The heap where the object was allocated.</span></span> <span data-ttu-id="c8ead-415">与工作站垃圾回收一起运行时，此值为 0（零）。</span><span class="sxs-lookup"><span data-stu-id="c8ead-415">This value is 0 (zero) when running with workstation garbage collection.</span></span>|

## <a name="gcfinalizersbegin_v1-event"></a><span data-ttu-id="c8ead-416">GCFinalizersBegin_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-416">GCFinalizersBegin_V1 Event</span></span>

<span data-ttu-id="c8ead-417">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="c8ead-417">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8ead-418">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="c8ead-418">Keyword for raising the event</span></span>|<span data-ttu-id="c8ead-419">层次</span><span class="sxs-lookup"><span data-stu-id="c8ead-419">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8ead-420">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8ead-420">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8ead-421">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="c8ead-421">Informational (4)</span></span>|

<span data-ttu-id="c8ead-422">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="c8ead-422">The following table shows the event information:</span></span>

|<span data-ttu-id="c8ead-423">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-423">Event</span></span>|<span data-ttu-id="c8ead-424">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c8ead-424">Event ID</span></span>|<span data-ttu-id="c8ead-425">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="c8ead-425">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersBegin_V1`|<span data-ttu-id="c8ead-426">14</span><span class="sxs-lookup"><span data-stu-id="c8ead-426">14</span></span>|<span data-ttu-id="c8ead-427">开始运行终结器。</span><span class="sxs-lookup"><span data-stu-id="c8ead-427">The start of running finalizers.</span></span>|

<span data-ttu-id="c8ead-428">无事件数据。</span><span class="sxs-lookup"><span data-stu-id="c8ead-428">No event data.</span></span>

## <a name="gcfinalizersend_v1-event"></a><span data-ttu-id="c8ead-429">GCFinalizersEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-429">GCFinalizersEnd_V1 Event</span></span>

<span data-ttu-id="c8ead-430">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="c8ead-430">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8ead-431">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="c8ead-431">Keyword for raising the event</span></span>|<span data-ttu-id="c8ead-432">层次</span><span class="sxs-lookup"><span data-stu-id="c8ead-432">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8ead-433">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8ead-433">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8ead-434">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="c8ead-434">Informational (4)</span></span>|

<span data-ttu-id="c8ead-435">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="c8ead-435">The following table shows the event information:</span></span>

|<span data-ttu-id="c8ead-436">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-436">Event</span></span>|<span data-ttu-id="c8ead-437">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c8ead-437">Event ID</span></span>|<span data-ttu-id="c8ead-438">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="c8ead-438">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersEnd_V1`|<span data-ttu-id="c8ead-439">13</span><span class="sxs-lookup"><span data-stu-id="c8ead-439">13</span></span>|<span data-ttu-id="c8ead-440">结束运行终结器。</span><span class="sxs-lookup"><span data-stu-id="c8ead-440">The end of running finalizers.</span></span>|

<span data-ttu-id="c8ead-441">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="c8ead-441">The following table shows the event data:</span></span>

|<span data-ttu-id="c8ead-442">字段名</span><span class="sxs-lookup"><span data-stu-id="c8ead-442">Field name</span></span>|<span data-ttu-id="c8ead-443">数据类型</span><span class="sxs-lookup"><span data-stu-id="c8ead-443">Data type</span></span>|<span data-ttu-id="c8ead-444">描述</span><span class="sxs-lookup"><span data-stu-id="c8ead-444">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="c8ead-445">计数</span><span class="sxs-lookup"><span data-stu-id="c8ead-445">Count</span></span>|<span data-ttu-id="c8ead-446">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8ead-446">win:UInt32</span></span>|<span data-ttu-id="c8ead-447">运行的终结器数。</span><span class="sxs-lookup"><span data-stu-id="c8ead-447">The number of finalizers that were run.</span></span>|
|<span data-ttu-id="c8ead-448">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c8ead-448">ClrInstanceID</span></span>|<span data-ttu-id="c8ead-449">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c8ead-449">win:UInt16</span></span>|<span data-ttu-id="c8ead-450">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="c8ead-450">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gccreateconcurrentthread_v1-event"></a><span data-ttu-id="c8ead-451">GCCreateConcurrentThread_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-451">GCCreateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="c8ead-452">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="c8ead-452">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8ead-453">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="c8ead-453">Keyword for raising the event</span></span>|<span data-ttu-id="c8ead-454">层次</span><span class="sxs-lookup"><span data-stu-id="c8ead-454">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8ead-455">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8ead-455">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8ead-456">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="c8ead-456">Informational (4)</span></span>|
|<span data-ttu-id="c8ead-457">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="c8ead-457">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="c8ead-458">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="c8ead-458">Informational (4)</span></span>|

<span data-ttu-id="c8ead-459">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="c8ead-459">The following table shows the event information:</span></span>

|<span data-ttu-id="c8ead-460">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-460">Event</span></span>|<span data-ttu-id="c8ead-461">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c8ead-461">Event ID</span></span>|<span data-ttu-id="c8ead-462">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="c8ead-462">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="c8ead-463">11</span><span class="sxs-lookup"><span data-stu-id="c8ead-463">11</span></span>|<span data-ttu-id="c8ead-464">已创建并发垃圾回收线程。</span><span class="sxs-lookup"><span data-stu-id="c8ead-464">Concurrent garbage collection thread was created.</span></span>|

<span data-ttu-id="c8ead-465">无事件数据。</span><span class="sxs-lookup"><span data-stu-id="c8ead-465">No event data.</span></span>

## <a name="gcterminateconcurrentthread_v1-event"></a><span data-ttu-id="c8ead-466">GCTerminateConcurrentThread_V1 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-466">GCTerminateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="c8ead-467">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="c8ead-467">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8ead-468">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="c8ead-468">Keyword for raising the event</span></span>|<span data-ttu-id="c8ead-469">层次</span><span class="sxs-lookup"><span data-stu-id="c8ead-469">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8ead-470">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8ead-470">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8ead-471">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="c8ead-471">Informational (4)</span></span>|
|<span data-ttu-id="c8ead-472">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="c8ead-472">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="c8ead-473">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="c8ead-473">Informational (4)</span></span>|

<span data-ttu-id="c8ead-474">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="c8ead-474">The following table shows the event information:</span></span>

|<span data-ttu-id="c8ead-475">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-475">Event</span></span>|<span data-ttu-id="c8ead-476">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c8ead-476">Event ID</span></span>|<span data-ttu-id="c8ead-477">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="c8ead-477">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="c8ead-478">12</span><span class="sxs-lookup"><span data-stu-id="c8ead-478">12</span></span>|<span data-ttu-id="c8ead-479">已终止并发垃圾回收线程。</span><span class="sxs-lookup"><span data-stu-id="c8ead-479">Concurrent garbage collection thread was terminated.</span></span>|

<span data-ttu-id="c8ead-480">无事件数据。</span><span class="sxs-lookup"><span data-stu-id="c8ead-480">No event data.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8ead-481">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8ead-481">See also</span></span>

- [<span data-ttu-id="c8ead-482">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="c8ead-482">CLR ETW Events</span></span>](clr-etw-events.md)
