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
ms.openlocfilehash: e5e10a1dc1ad3230213a20b850741a6ec0468294
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64616426"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="784c0-102">垃圾回收 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-102">Garbage Collection ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="784c0-103">这些事件可收集有关垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="784c0-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="784c0-104">它们可帮助进行诊断和调试，包括确定垃圾回收执行的次数、垃圾回收期间释放的内存量等。</span><span class="sxs-lookup"><span data-stu-id="784c0-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>  
  
 <span data-ttu-id="784c0-105">此类别包含以下事件：</span><span class="sxs-lookup"><span data-stu-id="784c0-105">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="784c0-106">GCStart_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-106">GCStart_V1 Event</span></span>](#gcstart_v1_event)  
  
- [<span data-ttu-id="784c0-107">GCEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-107">GCEnd_V1 Event</span></span>](#gcend_v1_event)  
  
- [<span data-ttu-id="784c0-108">GCHeapStats_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1_event)  
  
- [<span data-ttu-id="784c0-109">GCCreateSegment_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1_event)  
  
- [<span data-ttu-id="784c0-110">GCFreeSegment_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1_event)  
  
- [<span data-ttu-id="784c0-111">GCRestartEEBegin_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1_event)  
  
- [<span data-ttu-id="784c0-112">GCRestartEEEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1_event)  
  
- [<span data-ttu-id="784c0-113">GCSuspendEE_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1_event)  
  
- [<span data-ttu-id="784c0-114">GCSuspendEEEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1_event)  
  
- [<span data-ttu-id="784c0-115">GCAllocationTick_V2 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2_event)  
  
- [<span data-ttu-id="784c0-116">GCFinalizersBegin_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1_event)  
  
- [<span data-ttu-id="784c0-117">GCFinalizersEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1_event)  
  
- [<span data-ttu-id="784c0-118">GCCreateConcurrentThread_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1_event)  
  
- [<span data-ttu-id="784c0-119">GCTerminateConcurrentThread_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1_event)  
  
<a name="gcstart_v1_event"></a>   
## <a name="gcstartv1-event"></a><span data-ttu-id="784c0-120">GCStart_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-120">GCStart_V1 Event</span></span>  
 <span data-ttu-id="784c0-121">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="784c0-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="784c0-122">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="784c0-122">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="784c0-123">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="784c0-123">Keyword for raising the event</span></span>|<span data-ttu-id="784c0-124">级别</span><span class="sxs-lookup"><span data-stu-id="784c0-124">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="784c0-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="784c0-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="784c0-126">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="784c0-126">Informational (4)</span></span>|  
  
 <span data-ttu-id="784c0-127">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="784c0-127">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="784c0-128">Event</span><span class="sxs-lookup"><span data-stu-id="784c0-128">Event</span></span>|<span data-ttu-id="784c0-129">事件 ID</span><span class="sxs-lookup"><span data-stu-id="784c0-129">Event ID</span></span>|<span data-ttu-id="784c0-130">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="784c0-130">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCStart_V1`|<span data-ttu-id="784c0-131">1</span><span class="sxs-lookup"><span data-stu-id="784c0-131">1</span></span>|<span data-ttu-id="784c0-132">垃圾回收已启动。</span><span class="sxs-lookup"><span data-stu-id="784c0-132">A garbage collection has started.</span></span>|  
  
 <span data-ttu-id="784c0-133">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="784c0-133">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="784c0-134">字段名</span><span class="sxs-lookup"><span data-stu-id="784c0-134">Field name</span></span>|<span data-ttu-id="784c0-135">数据类型</span><span class="sxs-lookup"><span data-stu-id="784c0-135">Data type</span></span>|<span data-ttu-id="784c0-136">描述</span><span class="sxs-lookup"><span data-stu-id="784c0-136">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="784c0-137">计数</span><span class="sxs-lookup"><span data-stu-id="784c0-137">Count</span></span>|<span data-ttu-id="784c0-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="784c0-138">win:UInt32</span></span>|<span data-ttu-id="784c0-139">第 *n*代垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="784c0-139">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="784c0-140">深度</span><span class="sxs-lookup"><span data-stu-id="784c0-140">Depth</span></span>|<span data-ttu-id="784c0-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="784c0-141">win:UInt32</span></span>|<span data-ttu-id="784c0-142">正在回收的代。</span><span class="sxs-lookup"><span data-stu-id="784c0-142">The generation that is being collected.</span></span>|  
|<span data-ttu-id="784c0-143">原因</span><span class="sxs-lookup"><span data-stu-id="784c0-143">Reason</span></span>|<span data-ttu-id="784c0-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="784c0-144">win:UInt32</span></span>|<span data-ttu-id="784c0-145">垃圾回收的触发原因：</span><span class="sxs-lookup"><span data-stu-id="784c0-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="784c0-146">0x0 - 小型对象堆分配。</span><span class="sxs-lookup"><span data-stu-id="784c0-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="784c0-147">0x1 - 已引发。</span><span class="sxs-lookup"><span data-stu-id="784c0-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="784c0-148">0x2 - 内存不足。</span><span class="sxs-lookup"><span data-stu-id="784c0-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="784c0-149">0x3 - 空。</span><span class="sxs-lookup"><span data-stu-id="784c0-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="784c0-150">0x4 - 大型对象堆分配。</span><span class="sxs-lookup"><span data-stu-id="784c0-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="784c0-151">0x5 - 空间不足（针对小型对象堆）。</span><span class="sxs-lookup"><span data-stu-id="784c0-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="784c0-152">0x6 - 空间不足（针对大型对象堆）。</span><span class="sxs-lookup"><span data-stu-id="784c0-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="784c0-153">0x7 - 已引发，但未强制为阻止。</span><span class="sxs-lookup"><span data-stu-id="784c0-153">0x7 - Induced but not forced as blocking.</span></span>|  
|<span data-ttu-id="784c0-154">类型</span><span class="sxs-lookup"><span data-stu-id="784c0-154">Type</span></span>|<span data-ttu-id="784c0-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="784c0-155">win:UInt32</span></span>|<span data-ttu-id="784c0-156">0x0 - 在后台垃圾回收外部发生了垃圾回收阻止。</span><span class="sxs-lookup"><span data-stu-id="784c0-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="784c0-157">0x1 - 后台垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="784c0-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="784c0-158">0x0 - 后台垃圾回收期间发生了垃圾回收阻止。</span><span class="sxs-lookup"><span data-stu-id="784c0-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|  
|<span data-ttu-id="784c0-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="784c0-159">ClrInstanceID</span></span>|<span data-ttu-id="784c0-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="784c0-160">win:UInt16</span></span>|<span data-ttu-id="784c0-161">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="784c0-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="784c0-162">返回页首</span><span class="sxs-lookup"><span data-stu-id="784c0-162">Back to top</span></span>](#top)  
  
<a name="gcend_v1_event"></a>   
## <a name="gcendv1-event"></a><span data-ttu-id="784c0-163">GCEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-163">GCEnd_V1 Event</span></span>  
 <span data-ttu-id="784c0-164">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="784c0-164">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="784c0-165">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="784c0-165">Keyword for raising the event</span></span>|<span data-ttu-id="784c0-166">级别</span><span class="sxs-lookup"><span data-stu-id="784c0-166">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="784c0-167">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="784c0-167">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="784c0-168">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="784c0-168">Informational (4)</span></span>|  
  
 <span data-ttu-id="784c0-169">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="784c0-169">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="784c0-170">Event</span><span class="sxs-lookup"><span data-stu-id="784c0-170">Event</span></span>|<span data-ttu-id="784c0-171">事件 ID</span><span class="sxs-lookup"><span data-stu-id="784c0-171">Event ID</span></span>|<span data-ttu-id="784c0-172">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="784c0-172">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCEnd_V1`|<span data-ttu-id="784c0-173">2</span><span class="sxs-lookup"><span data-stu-id="784c0-173">2</span></span>|<span data-ttu-id="784c0-174">垃圾回收已结束。</span><span class="sxs-lookup"><span data-stu-id="784c0-174">The garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="784c0-175">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="784c0-175">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="784c0-176">字段名</span><span class="sxs-lookup"><span data-stu-id="784c0-176">Field name</span></span>|<span data-ttu-id="784c0-177">数据类型</span><span class="sxs-lookup"><span data-stu-id="784c0-177">Data type</span></span>|<span data-ttu-id="784c0-178">描述</span><span class="sxs-lookup"><span data-stu-id="784c0-178">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="784c0-179">计数</span><span class="sxs-lookup"><span data-stu-id="784c0-179">Count</span></span>|<span data-ttu-id="784c0-180">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="784c0-180">win:UInt32</span></span>|<span data-ttu-id="784c0-181">第 *n*代垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="784c0-181">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="784c0-182">深度</span><span class="sxs-lookup"><span data-stu-id="784c0-182">Depth</span></span>|<span data-ttu-id="784c0-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="784c0-183">win:UInt32</span></span>|<span data-ttu-id="784c0-184">已回收的代。</span><span class="sxs-lookup"><span data-stu-id="784c0-184">The generation that was collected.</span></span>|  
|<span data-ttu-id="784c0-185">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="784c0-185">ClrInstanceID</span></span>|<span data-ttu-id="784c0-186">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="784c0-186">win:UInt16</span></span>|<span data-ttu-id="784c0-187">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="784c0-187">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="784c0-188">返回页首</span><span class="sxs-lookup"><span data-stu-id="784c0-188">Back to top</span></span>](#top)  
  
<a name="gcheapstats_v1_event"></a>   
## <a name="gcheapstatsv1-event"></a><span data-ttu-id="784c0-189">GCHeapStats_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-189">GCHeapStats_V1 Event</span></span>  
 <span data-ttu-id="784c0-190">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="784c0-190">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="784c0-191">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="784c0-191">Keyword for raising the event</span></span>|<span data-ttu-id="784c0-192">级别</span><span class="sxs-lookup"><span data-stu-id="784c0-192">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="784c0-193">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="784c0-193">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="784c0-194">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="784c0-194">Informational (4)</span></span>|  
  
 <span data-ttu-id="784c0-195">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="784c0-195">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="784c0-196">Event</span><span class="sxs-lookup"><span data-stu-id="784c0-196">Event</span></span>|<span data-ttu-id="784c0-197">事件 ID</span><span class="sxs-lookup"><span data-stu-id="784c0-197">Event ID</span></span>|<span data-ttu-id="784c0-198">描述</span><span class="sxs-lookup"><span data-stu-id="784c0-198">Description</span></span>|  
|-----------|--------------|-----------------|  
|`GCHeapStats_V1`|<span data-ttu-id="784c0-199">4</span><span class="sxs-lookup"><span data-stu-id="784c0-199">4</span></span>|<span data-ttu-id="784c0-200">在每次垃圾回收结束时显示堆统计信息。</span><span class="sxs-lookup"><span data-stu-id="784c0-200">Shows the heap statistics at the end of each garbage collection.</span></span>|  
  
 <span data-ttu-id="784c0-201">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="784c0-201">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="784c0-202">字段名</span><span class="sxs-lookup"><span data-stu-id="784c0-202">Field name</span></span>|<span data-ttu-id="784c0-203">数据类型</span><span class="sxs-lookup"><span data-stu-id="784c0-203">Data type</span></span>|<span data-ttu-id="784c0-204">描述</span><span class="sxs-lookup"><span data-stu-id="784c0-204">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="784c0-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="784c0-205">GenerationSize0</span></span>|<span data-ttu-id="784c0-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="784c0-206">win:UInt64</span></span>|<span data-ttu-id="784c0-207">第 0 代内存的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="784c0-207">The size, in bytes, of generation 0 memory.</span></span>|  
|<span data-ttu-id="784c0-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="784c0-208">TotalPromotedSize0</span></span>|<span data-ttu-id="784c0-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="784c0-209">win:UInt64</span></span>|<span data-ttu-id="784c0-210">从第 0 代提升到第 1 代的字节数。</span><span class="sxs-lookup"><span data-stu-id="784c0-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|  
|<span data-ttu-id="784c0-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="784c0-211">GenerationSize1</span></span>|<span data-ttu-id="784c0-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="784c0-212">win:UInt64</span></span>|<span data-ttu-id="784c0-213">第 1 代内存的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="784c0-213">The size, in bytes, of generation 1 memory.</span></span>|  
|<span data-ttu-id="784c0-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="784c0-214">TotalPromotedSize1</span></span>|<span data-ttu-id="784c0-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="784c0-215">win:UInt64</span></span>|<span data-ttu-id="784c0-216">从第 1 代提升到第 2 代的字节数。</span><span class="sxs-lookup"><span data-stu-id="784c0-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|  
|<span data-ttu-id="784c0-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="784c0-217">GenerationSize2</span></span>|<span data-ttu-id="784c0-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="784c0-218">win:UInt64</span></span>|<span data-ttu-id="784c0-219">第 2 代内存的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="784c0-219">The size, in bytes, of generation 2 memory.</span></span>|  
|<span data-ttu-id="784c0-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="784c0-220">TotalPromotedSize2</span></span>|<span data-ttu-id="784c0-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="784c0-221">win:UInt64</span></span>|<span data-ttu-id="784c0-222">上次回收后仍存在于第 2 代中的字节数。</span><span class="sxs-lookup"><span data-stu-id="784c0-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|  
|<span data-ttu-id="784c0-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="784c0-223">GenerationSize3</span></span>|<span data-ttu-id="784c0-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="784c0-224">win:UInt64</span></span>|<span data-ttu-id="784c0-225">大型对象堆的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="784c0-225">The size, in bytes, of the large object heap.</span></span>|  
|<span data-ttu-id="784c0-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="784c0-226">TotalPromotedSize3</span></span>|<span data-ttu-id="784c0-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="784c0-227">win:UInt64</span></span>|<span data-ttu-id="784c0-228">上次回收后仍存在于大型对象堆中的字节数。</span><span class="sxs-lookup"><span data-stu-id="784c0-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|  
|<span data-ttu-id="784c0-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="784c0-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="784c0-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="784c0-230">win:UInt64</span></span>|<span data-ttu-id="784c0-231">准备终结的对象的总大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="784c0-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="784c0-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="784c0-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="784c0-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="784c0-233">win:UInt64</span></span>|<span data-ttu-id="784c0-234">已准备好进行终结的对象的数目。</span><span class="sxs-lookup"><span data-stu-id="784c0-234">The number of objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="784c0-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="784c0-235">PinnedObjectCount</span></span>|<span data-ttu-id="784c0-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="784c0-236">win:UInt32</span></span>|<span data-ttu-id="784c0-237">固定（不可移动）对象的数目。</span><span class="sxs-lookup"><span data-stu-id="784c0-237">The number of pinned (unmovable) objects.</span></span>|  
|<span data-ttu-id="784c0-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="784c0-238">SinkBlockCount</span></span>|<span data-ttu-id="784c0-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="784c0-239">win:UInt32</span></span>|<span data-ttu-id="784c0-240">正在使用的同步块的数目。</span><span class="sxs-lookup"><span data-stu-id="784c0-240">The number of synchronization blocks in use.</span></span>|  
|<span data-ttu-id="784c0-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="784c0-241">GCHandleCount</span></span>|<span data-ttu-id="784c0-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="784c0-242">win:UInt32</span></span>|<span data-ttu-id="784c0-243">使用中的垃圾回收句柄的数目。</span><span class="sxs-lookup"><span data-stu-id="784c0-243">The number of garbage collection handles in use.</span></span>|  
|<span data-ttu-id="784c0-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="784c0-244">ClrInstanceID</span></span>|<span data-ttu-id="784c0-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="784c0-245">win:UInt16</span></span>|<span data-ttu-id="784c0-246">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="784c0-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="784c0-247">返回页首</span><span class="sxs-lookup"><span data-stu-id="784c0-247">Back to top</span></span>](#top)  
  
<a name="gccreatesegment_v1_event"></a>   
## <a name="gccreatesegmentv1-event"></a><span data-ttu-id="784c0-248">GCCreateSegment_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-248">GCCreateSegment_V1 Event</span></span>  
 <span data-ttu-id="784c0-249">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="784c0-249">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="784c0-250">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="784c0-250">Keyword for raising the event</span></span>|<span data-ttu-id="784c0-251">级别</span><span class="sxs-lookup"><span data-stu-id="784c0-251">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="784c0-252">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="784c0-252">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="784c0-253">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="784c0-253">Informational (4)</span></span>|  
  
 <span data-ttu-id="784c0-254">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="784c0-254">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="784c0-255">Event</span><span class="sxs-lookup"><span data-stu-id="784c0-255">Event</span></span>|<span data-ttu-id="784c0-256">事件 ID</span><span class="sxs-lookup"><span data-stu-id="784c0-256">Event ID</span></span>|<span data-ttu-id="784c0-257">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="784c0-257">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateSegment_V1`|<span data-ttu-id="784c0-258">5</span><span class="sxs-lookup"><span data-stu-id="784c0-258">5</span></span>|<span data-ttu-id="784c0-259">已创建的新的垃圾回收段。</span><span class="sxs-lookup"><span data-stu-id="784c0-259">A new garbage collection segment has been created.</span></span> <span data-ttu-id="784c0-260">此外，当在已运行的进程中启用跟踪时，将为每个现有段引发此事件。</span><span class="sxs-lookup"><span data-stu-id="784c0-260">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|  
  
 <span data-ttu-id="784c0-261">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="784c0-261">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="784c0-262">字段名</span><span class="sxs-lookup"><span data-stu-id="784c0-262">Field name</span></span>|<span data-ttu-id="784c0-263">数据类型</span><span class="sxs-lookup"><span data-stu-id="784c0-263">Data type</span></span>|<span data-ttu-id="784c0-264">描述</span><span class="sxs-lookup"><span data-stu-id="784c0-264">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="784c0-265">Address</span><span class="sxs-lookup"><span data-stu-id="784c0-265">Address</span></span>|<span data-ttu-id="784c0-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="784c0-266">win:UInt64</span></span>|<span data-ttu-id="784c0-267">段的地址。</span><span class="sxs-lookup"><span data-stu-id="784c0-267">The address of the segment.</span></span>|  
|<span data-ttu-id="784c0-268">大小</span><span class="sxs-lookup"><span data-stu-id="784c0-268">Size</span></span>|<span data-ttu-id="784c0-269">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="784c0-269">win:UInt64</span></span>|<span data-ttu-id="784c0-270">段的大小。</span><span class="sxs-lookup"><span data-stu-id="784c0-270">The size of the segment.</span></span>|  
|<span data-ttu-id="784c0-271">类型</span><span class="sxs-lookup"><span data-stu-id="784c0-271">Type</span></span>|<span data-ttu-id="784c0-272">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="784c0-272">win:UInt32</span></span>|<span data-ttu-id="784c0-273">0x0 - 小型对象堆。</span><span class="sxs-lookup"><span data-stu-id="784c0-273">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="784c0-274">0x0 - 大型对象堆。</span><span class="sxs-lookup"><span data-stu-id="784c0-274">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="784c0-275">0x2 - 只读堆。</span><span class="sxs-lookup"><span data-stu-id="784c0-275">0x2 - Read-only heap.</span></span>|  
|<span data-ttu-id="784c0-276">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="784c0-276">ClrInstanceID</span></span>|<span data-ttu-id="784c0-277">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="784c0-277">win:UInt16</span></span>|<span data-ttu-id="784c0-278">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="784c0-278">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 <span data-ttu-id="784c0-279">请注意，由垃圾回收器分配的段的大小特定于实现，且随时可能更改（包括定期更新）。</span><span class="sxs-lookup"><span data-stu-id="784c0-279">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="784c0-280">应用程序不应假设特定段的大小或依赖于此大小，也不应尝试配置段分配可用的内存量。</span><span class="sxs-lookup"><span data-stu-id="784c0-280">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>  
  
 [<span data-ttu-id="784c0-281">返回页首</span><span class="sxs-lookup"><span data-stu-id="784c0-281">Back to top</span></span>](#top)  
  
<a name="gcfreesegment_v1_event"></a>   
## <a name="gcfreesegmentv1-event"></a><span data-ttu-id="784c0-282">GCFreeSegment_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-282">GCFreeSegment_V1 Event</span></span>  
 <span data-ttu-id="784c0-283">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="784c0-283">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="784c0-284">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="784c0-284">Keyword for raising the event</span></span>|<span data-ttu-id="784c0-285">级别</span><span class="sxs-lookup"><span data-stu-id="784c0-285">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="784c0-286">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="784c0-286">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="784c0-287">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="784c0-287">Informational (4)</span></span>|  
  
 <span data-ttu-id="784c0-288">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="784c0-288">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="784c0-289">Event</span><span class="sxs-lookup"><span data-stu-id="784c0-289">Event</span></span>|<span data-ttu-id="784c0-290">事件 ID</span><span class="sxs-lookup"><span data-stu-id="784c0-290">Event ID</span></span>|<span data-ttu-id="784c0-291">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="784c0-291">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFreeSegment_V1`|<span data-ttu-id="784c0-292">6</span><span class="sxs-lookup"><span data-stu-id="784c0-292">6</span></span>|<span data-ttu-id="784c0-293">已释放垃圾回收段。</span><span class="sxs-lookup"><span data-stu-id="784c0-293">A garbage collection segment has been released.</span></span>|  
  
 <span data-ttu-id="784c0-294">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="784c0-294">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="784c0-295">字段名</span><span class="sxs-lookup"><span data-stu-id="784c0-295">Field name</span></span>|<span data-ttu-id="784c0-296">数据类型</span><span class="sxs-lookup"><span data-stu-id="784c0-296">Data type</span></span>|<span data-ttu-id="784c0-297">描述</span><span class="sxs-lookup"><span data-stu-id="784c0-297">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="784c0-298">Address</span><span class="sxs-lookup"><span data-stu-id="784c0-298">Address</span></span>|<span data-ttu-id="784c0-299">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="784c0-299">win:UInt64</span></span>|<span data-ttu-id="784c0-300">段的地址。</span><span class="sxs-lookup"><span data-stu-id="784c0-300">The address of the segment.</span></span>|  
|<span data-ttu-id="784c0-301">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="784c0-301">ClrInstanceID</span></span>|<span data-ttu-id="784c0-302">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="784c0-302">win:UInt16</span></span>|<span data-ttu-id="784c0-303">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="784c0-303">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="784c0-304">返回页首</span><span class="sxs-lookup"><span data-stu-id="784c0-304">Back to top</span></span>](#top)  
  
<a name="gcrestarteebegin_v1_event"></a>   
## <a name="gcrestarteebeginv1-event"></a><span data-ttu-id="784c0-305">GCRestartEEBegin_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-305">GCRestartEEBegin_V1 Event</span></span>  
 <span data-ttu-id="784c0-306">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="784c0-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="784c0-307">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="784c0-307">Keyword for raising the event</span></span>|<span data-ttu-id="784c0-308">级别</span><span class="sxs-lookup"><span data-stu-id="784c0-308">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="784c0-309">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="784c0-309">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="784c0-310">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="784c0-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="784c0-311">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="784c0-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="784c0-312">Event</span><span class="sxs-lookup"><span data-stu-id="784c0-312">Event</span></span>|<span data-ttu-id="784c0-313">事件 ID</span><span class="sxs-lookup"><span data-stu-id="784c0-313">Event ID</span></span>|<span data-ttu-id="784c0-314">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="784c0-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEBegin_V1`|<span data-ttu-id="784c0-315">7</span><span class="sxs-lookup"><span data-stu-id="784c0-315">7</span></span>|<span data-ttu-id="784c0-316">已开始从公共语言运行时挂起进行恢复。</span><span class="sxs-lookup"><span data-stu-id="784c0-316">Resumption from common language runtime suspension has begun.</span></span>|  
  
 <span data-ttu-id="784c0-317">无事件数据。</span><span class="sxs-lookup"><span data-stu-id="784c0-317">No event data.</span></span>  
  
 [<span data-ttu-id="784c0-318">返回页首</span><span class="sxs-lookup"><span data-stu-id="784c0-318">Back to top</span></span>](#top)  
  
<a name="gcrestarteeend_v1_event"></a>   
## <a name="gcrestarteeendv1-event"></a><span data-ttu-id="784c0-319">GCRestartEEEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-319">GCRestartEEEnd_V1 Event</span></span>  
 <span data-ttu-id="784c0-320">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="784c0-320">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="784c0-321">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="784c0-321">Keyword for raising the event</span></span>|<span data-ttu-id="784c0-322">级别</span><span class="sxs-lookup"><span data-stu-id="784c0-322">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="784c0-323">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="784c0-323">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="784c0-324">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="784c0-324">Informational (4)</span></span>|  
  
 <span data-ttu-id="784c0-325">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="784c0-325">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="784c0-326">Event</span><span class="sxs-lookup"><span data-stu-id="784c0-326">Event</span></span>|<span data-ttu-id="784c0-327">事件 ID</span><span class="sxs-lookup"><span data-stu-id="784c0-327">Event Id</span></span>|<span data-ttu-id="784c0-328">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="784c0-328">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEEnd_V1`|<span data-ttu-id="784c0-329">3</span><span class="sxs-lookup"><span data-stu-id="784c0-329">3</span></span>|<span data-ttu-id="784c0-330">从公共语言运行时挂起进行的恢复已结束。</span><span class="sxs-lookup"><span data-stu-id="784c0-330">Resumption from common language runtime suspension has ended.</span></span>|  
  
 <span data-ttu-id="784c0-331">无事件数据。</span><span class="sxs-lookup"><span data-stu-id="784c0-331">No event data.</span></span>  
  
 [<span data-ttu-id="784c0-332">返回页首</span><span class="sxs-lookup"><span data-stu-id="784c0-332">Back to top</span></span>](#top)  
  
<a name="gcsuspendee_v1_event"></a>   
## <a name="gcsuspendeev1-event"></a><span data-ttu-id="784c0-333">GCSuspendEE_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-333">GCSuspendEE_V1 Event</span></span>  
 <span data-ttu-id="784c0-334">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="784c0-334">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="784c0-335">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="784c0-335">Keyword for raising the event</span></span>|<span data-ttu-id="784c0-336">级别</span><span class="sxs-lookup"><span data-stu-id="784c0-336">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="784c0-337">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="784c0-337">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="784c0-338">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="784c0-338">Informational (4)</span></span>|  
  
 <span data-ttu-id="784c0-339">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="784c0-339">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="784c0-340">Event</span><span class="sxs-lookup"><span data-stu-id="784c0-340">Event</span></span>|<span data-ttu-id="784c0-341">事件 ID</span><span class="sxs-lookup"><span data-stu-id="784c0-341">Event ID</span></span>|<span data-ttu-id="784c0-342">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="784c0-342">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEE_V1`|<span data-ttu-id="784c0-343">9</span><span class="sxs-lookup"><span data-stu-id="784c0-343">9</span></span>|<span data-ttu-id="784c0-344">开始挂起垃圾回收的执行引擎。</span><span class="sxs-lookup"><span data-stu-id="784c0-344">Start of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="784c0-345">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="784c0-345">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="784c0-346">字段名</span><span class="sxs-lookup"><span data-stu-id="784c0-346">Field name</span></span>|<span data-ttu-id="784c0-347">数据类型</span><span class="sxs-lookup"><span data-stu-id="784c0-347">Data type</span></span>|<span data-ttu-id="784c0-348">描述</span><span class="sxs-lookup"><span data-stu-id="784c0-348">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="784c0-349">原因</span><span class="sxs-lookup"><span data-stu-id="784c0-349">Reason</span></span>|<span data-ttu-id="784c0-350">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="784c0-350">win:UInt16</span></span>|<span data-ttu-id="784c0-351">0x0 - 其他。</span><span class="sxs-lookup"><span data-stu-id="784c0-351">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="784c0-352">0x1 - 垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="784c0-352">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="784c0-353">0x2 - 应用程序域关闭。</span><span class="sxs-lookup"><span data-stu-id="784c0-353">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="784c0-354">0x3 - 代码间距调整。</span><span class="sxs-lookup"><span data-stu-id="784c0-354">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="784c0-355">0x4 - 关闭。</span><span class="sxs-lookup"><span data-stu-id="784c0-355">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="784c0-356">0x5 - 调试器。</span><span class="sxs-lookup"><span data-stu-id="784c0-356">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="784c0-357">0x6 - 准备垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="784c0-357">0x6 - Preparation for garbage collection.</span></span>|  
|<span data-ttu-id="784c0-358">计数</span><span class="sxs-lookup"><span data-stu-id="784c0-358">Count</span></span>|<span data-ttu-id="784c0-359">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="784c0-359">win:UInt32</span></span>|<span data-ttu-id="784c0-360">此时的 GC 计数。</span><span class="sxs-lookup"><span data-stu-id="784c0-360">The GC count at the time.</span></span> <span data-ttu-id="784c0-361">通常情况下，会在这之后看到后续 GC 开始事件，且在垃圾回收期间增加 GC 索引时，其计数会增加 1。</span><span class="sxs-lookup"><span data-stu-id="784c0-361">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|  
|<span data-ttu-id="784c0-362">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="784c0-362">ClrInstanceID</span></span>|<span data-ttu-id="784c0-363">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="784c0-363">win:UInt16</span></span>|<span data-ttu-id="784c0-364">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="784c0-364">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="784c0-365">返回页首</span><span class="sxs-lookup"><span data-stu-id="784c0-365">Back to top</span></span>](#top)  
  
<a name="gcsuspendeeend_v1_event"></a>   
## <a name="gcsuspendeeendv1-event"></a><span data-ttu-id="784c0-366">GCSuspendEEEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-366">GCSuspendEEEnd_V1 Event</span></span>  
 <span data-ttu-id="784c0-367">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="784c0-367">The following table shows the keyword and level:</span></span>  
  
|<span data-ttu-id="784c0-368">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="784c0-368">Keyword for raising the event</span></span>|<span data-ttu-id="784c0-369">级别</span><span class="sxs-lookup"><span data-stu-id="784c0-369">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="784c0-370">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="784c0-370">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="784c0-371">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="784c0-371">Informational (4)</span></span>|  
  
 <span data-ttu-id="784c0-372">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="784c0-372">The following table shows the event information:</span></span>  
  
|<span data-ttu-id="784c0-373">Event</span><span class="sxs-lookup"><span data-stu-id="784c0-373">Event</span></span>|<span data-ttu-id="784c0-374">事件 ID</span><span class="sxs-lookup"><span data-stu-id="784c0-374">Event ID</span></span>|<span data-ttu-id="784c0-375">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="784c0-375">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEEEnd_V1`|<span data-ttu-id="784c0-376">8</span><span class="sxs-lookup"><span data-stu-id="784c0-376">8</span></span>|<span data-ttu-id="784c0-377">结束垃圾回收执行引擎的挂起。</span><span class="sxs-lookup"><span data-stu-id="784c0-377">End of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="784c0-378">无事件数据。</span><span class="sxs-lookup"><span data-stu-id="784c0-378">No event data.</span></span>  
  
 [<span data-ttu-id="784c0-379">返回页首</span><span class="sxs-lookup"><span data-stu-id="784c0-379">Back to top</span></span>](#top)  
  
<a name="gcallocationtick_v2_event"></a>   
## <a name="gcallocationtickv2-event"></a><span data-ttu-id="784c0-380">GCAllocationTick_V2 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-380">GCAllocationTick_V2 Event</span></span>  
 <span data-ttu-id="784c0-381">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="784c0-381">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="784c0-382">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="784c0-382">Keyword for raising the event</span></span>|<span data-ttu-id="784c0-383">级别</span><span class="sxs-lookup"><span data-stu-id="784c0-383">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="784c0-384">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="784c0-384">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="784c0-385">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="784c0-385">Informational (4)</span></span>|  
  
 <span data-ttu-id="784c0-386">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="784c0-386">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="784c0-387">Event</span><span class="sxs-lookup"><span data-stu-id="784c0-387">Event</span></span>|<span data-ttu-id="784c0-388">事件 ID</span><span class="sxs-lookup"><span data-stu-id="784c0-388">Event ID</span></span>|<span data-ttu-id="784c0-389">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="784c0-389">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCAllocationTick_V2`|<span data-ttu-id="784c0-390">10</span><span class="sxs-lookup"><span data-stu-id="784c0-390">10</span></span>|<span data-ttu-id="784c0-391">每次大约分配 100 KB。</span><span class="sxs-lookup"><span data-stu-id="784c0-391">Each time approximately 100 KB is allocated.</span></span>|  
  
 <span data-ttu-id="784c0-392">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="784c0-392">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="784c0-393">字段名</span><span class="sxs-lookup"><span data-stu-id="784c0-393">Field name</span></span>|<span data-ttu-id="784c0-394">数据类型</span><span class="sxs-lookup"><span data-stu-id="784c0-394">Data type</span></span>|<span data-ttu-id="784c0-395">描述</span><span class="sxs-lookup"><span data-stu-id="784c0-395">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="784c0-396">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="784c0-396">AllocationAmount</span></span>|<span data-ttu-id="784c0-397">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="784c0-397">win:UInt32</span></span>|<span data-ttu-id="784c0-398">分配大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="784c0-398">The allocation size, in bytes.</span></span> <span data-ttu-id="784c0-399">对于小于 ULONG（4,294,967,295 字节）长度的分配，此值为精确值。</span><span class="sxs-lookup"><span data-stu-id="784c0-399">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="784c0-400">如果分配长度更大，则此字段包含了截断的值。</span><span class="sxs-lookup"><span data-stu-id="784c0-400">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="784c0-401">对于非常大的分配使用 `AllocationAmount64` 。</span><span class="sxs-lookup"><span data-stu-id="784c0-401">Use `AllocationAmount64` for very large allocations.</span></span>|  
|<span data-ttu-id="784c0-402">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="784c0-402">AllocationKind</span></span>|<span data-ttu-id="784c0-403">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="784c0-403">win:UInt32</span></span>|<span data-ttu-id="784c0-404">0x0 - 小型对象分配（小型对象堆中的分配）。</span><span class="sxs-lookup"><span data-stu-id="784c0-404">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="784c0-405">0x0 - 大型对象分配（大型对象堆中的分配）。</span><span class="sxs-lookup"><span data-stu-id="784c0-405">0x1 - Large object allocation (allocation is in large object heap).</span></span>|  
|<span data-ttu-id="784c0-406">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="784c0-406">ClrInstanceID</span></span>|<span data-ttu-id="784c0-407">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="784c0-407">win:UInt16</span></span>|<span data-ttu-id="784c0-408">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="784c0-408">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
|<span data-ttu-id="784c0-409">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="784c0-409">AllocationAmount64</span></span>|<span data-ttu-id="784c0-410">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="784c0-410">win:UInt64</span></span>|<span data-ttu-id="784c0-411">分配大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="784c0-411">The allocation size, in bytes.</span></span> <span data-ttu-id="784c0-412">对于非常大的分配，此值为精确值。</span><span class="sxs-lookup"><span data-stu-id="784c0-412">This value is accurate for very large allocations.</span></span>|  
|<span data-ttu-id="784c0-413">TypeId</span><span class="sxs-lookup"><span data-stu-id="784c0-413">TypeId</span></span>|<span data-ttu-id="784c0-414">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="784c0-414">win:Pointer</span></span>|<span data-ttu-id="784c0-415">MethodTable 的地址。</span><span class="sxs-lookup"><span data-stu-id="784c0-415">The address of the MethodTable.</span></span> <span data-ttu-id="784c0-416">如果在此事件期间分配了几种类型的对象，则此地址为对应于分配的最后一个对象（导致超过 100 KB 阙值的对象）的 MethodTable 地址。</span><span class="sxs-lookup"><span data-stu-id="784c0-416">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="784c0-417">TypeName</span><span class="sxs-lookup"><span data-stu-id="784c0-417">TypeName</span></span>|<span data-ttu-id="784c0-418">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="784c0-418">win:UnicodeString</span></span>|<span data-ttu-id="784c0-419">已分配的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="784c0-419">The name of the type that was allocated.</span></span> <span data-ttu-id="784c0-420">如果在此事件期间分配了几种类型的对象，则此地址为对应于分配的最后一个类型（导致超过 100 KB 阙值的对象）。</span><span class="sxs-lookup"><span data-stu-id="784c0-420">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="784c0-421">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="784c0-421">HeapIndex</span></span>|<span data-ttu-id="784c0-422">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="784c0-422">win:UInt32</span></span>|<span data-ttu-id="784c0-423">此对象所分配到的堆。</span><span class="sxs-lookup"><span data-stu-id="784c0-423">The heap where the object was allocated.</span></span> <span data-ttu-id="784c0-424">与工作站垃圾回收一起运行时，此值为 0（零）。</span><span class="sxs-lookup"><span data-stu-id="784c0-424">This value is 0 (zero) when running with workstation garbage collection.</span></span>|  
  
 [<span data-ttu-id="784c0-425">返回页首</span><span class="sxs-lookup"><span data-stu-id="784c0-425">Back to top</span></span>](#top)  
  
<a name="gcfinalizersbegin_v1_event"></a>   
## <a name="gcfinalizersbeginv1-event"></a><span data-ttu-id="784c0-426">GCFinalizersBegin_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-426">GCFinalizersBegin_V1 Event</span></span>  
 <span data-ttu-id="784c0-427">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="784c0-427">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="784c0-428">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="784c0-428">Keyword for raising the event</span></span>|<span data-ttu-id="784c0-429">级别</span><span class="sxs-lookup"><span data-stu-id="784c0-429">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="784c0-430">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="784c0-430">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="784c0-431">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="784c0-431">Informational (4)</span></span>|  
  
 <span data-ttu-id="784c0-432">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="784c0-432">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="784c0-433">Event</span><span class="sxs-lookup"><span data-stu-id="784c0-433">Event</span></span>|<span data-ttu-id="784c0-434">事件 ID</span><span class="sxs-lookup"><span data-stu-id="784c0-434">Event ID</span></span>|<span data-ttu-id="784c0-435">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="784c0-435">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersBegin_V1`|<span data-ttu-id="784c0-436">14</span><span class="sxs-lookup"><span data-stu-id="784c0-436">14</span></span>|<span data-ttu-id="784c0-437">开始运行终结器。</span><span class="sxs-lookup"><span data-stu-id="784c0-437">The start of running finalizers.</span></span>|  
  
 <span data-ttu-id="784c0-438">无事件数据。</span><span class="sxs-lookup"><span data-stu-id="784c0-438">No event data.</span></span>  
  
 [<span data-ttu-id="784c0-439">返回页首</span><span class="sxs-lookup"><span data-stu-id="784c0-439">Back to top</span></span>](#top)  
  
<a name="gcfinalizersend_v1_event"></a>   
## <a name="gcfinalizersendv1-event"></a><span data-ttu-id="784c0-440">GCFinalizersEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-440">GCFinalizersEnd_V1 Event</span></span>  
 <span data-ttu-id="784c0-441">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="784c0-441">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="784c0-442">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="784c0-442">Keyword for raising the event</span></span>|<span data-ttu-id="784c0-443">级别</span><span class="sxs-lookup"><span data-stu-id="784c0-443">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="784c0-444">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="784c0-444">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="784c0-445">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="784c0-445">Informational (4)</span></span>|  
  
 <span data-ttu-id="784c0-446">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="784c0-446">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="784c0-447">Event</span><span class="sxs-lookup"><span data-stu-id="784c0-447">Event</span></span>|<span data-ttu-id="784c0-448">事件 ID</span><span class="sxs-lookup"><span data-stu-id="784c0-448">Event ID</span></span>|<span data-ttu-id="784c0-449">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="784c0-449">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersEnd_V1`|<span data-ttu-id="784c0-450">13</span><span class="sxs-lookup"><span data-stu-id="784c0-450">13</span></span>|<span data-ttu-id="784c0-451">结束运行终结器。</span><span class="sxs-lookup"><span data-stu-id="784c0-451">The end of running finalizers.</span></span>|  
  
 <span data-ttu-id="784c0-452">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="784c0-452">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="784c0-453">字段名</span><span class="sxs-lookup"><span data-stu-id="784c0-453">Field name</span></span>|<span data-ttu-id="784c0-454">数据类型</span><span class="sxs-lookup"><span data-stu-id="784c0-454">Data type</span></span>|<span data-ttu-id="784c0-455">描述</span><span class="sxs-lookup"><span data-stu-id="784c0-455">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="784c0-456">计数</span><span class="sxs-lookup"><span data-stu-id="784c0-456">Count</span></span>|<span data-ttu-id="784c0-457">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="784c0-457">win:UInt32</span></span>|<span data-ttu-id="784c0-458">运行的终结器数。</span><span class="sxs-lookup"><span data-stu-id="784c0-458">The number of finalizers that were run.</span></span>|  
|<span data-ttu-id="784c0-459">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="784c0-459">ClrInstanceID</span></span>|<span data-ttu-id="784c0-460">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="784c0-460">win:UInt16</span></span>|<span data-ttu-id="784c0-461">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="784c0-461">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="784c0-462">返回页首</span><span class="sxs-lookup"><span data-stu-id="784c0-462">Back to top</span></span>](#top)  
  
<a name="gccreateconcurrentthread_v1_event"></a>   
## <a name="gccreateconcurrentthreadv1-event"></a><span data-ttu-id="784c0-463">GCCreateConcurrentThread_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-463">GCCreateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="784c0-464">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="784c0-464">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="784c0-465">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="784c0-465">Keyword for raising the event</span></span>|<span data-ttu-id="784c0-466">级别</span><span class="sxs-lookup"><span data-stu-id="784c0-466">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="784c0-467">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="784c0-467">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="784c0-468">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="784c0-468">Informational (4)</span></span>|  
|<span data-ttu-id="784c0-469">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="784c0-469">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="784c0-470">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="784c0-470">Informational (4)</span></span>|  
  
 <span data-ttu-id="784c0-471">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="784c0-471">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="784c0-472">Event</span><span class="sxs-lookup"><span data-stu-id="784c0-472">Event</span></span>|<span data-ttu-id="784c0-473">事件 ID</span><span class="sxs-lookup"><span data-stu-id="784c0-473">Event ID</span></span>|<span data-ttu-id="784c0-474">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="784c0-474">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="784c0-475">11</span><span class="sxs-lookup"><span data-stu-id="784c0-475">11</span></span>|<span data-ttu-id="784c0-476">已创建并发垃圾回收线程。</span><span class="sxs-lookup"><span data-stu-id="784c0-476">Concurrent garbage collection thread was created.</span></span>|  
  
 <span data-ttu-id="784c0-477">无事件数据。</span><span class="sxs-lookup"><span data-stu-id="784c0-477">No event data.</span></span>  
  
 [<span data-ttu-id="784c0-478">返回页首</span><span class="sxs-lookup"><span data-stu-id="784c0-478">Back to top</span></span>](#top)  
  
<a name="gcterminateconcurrentthread_v1_event"></a>   
## <a name="gcterminateconcurrentthreadv1-event"></a><span data-ttu-id="784c0-479">GCTerminateConcurrentThread_V1 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-479">GCTerminateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="784c0-480">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="784c0-480">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="784c0-481">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="784c0-481">Keyword for raising the event</span></span>|<span data-ttu-id="784c0-482">级别</span><span class="sxs-lookup"><span data-stu-id="784c0-482">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="784c0-483">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="784c0-483">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="784c0-484">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="784c0-484">Informational (4)</span></span>|  
|<span data-ttu-id="784c0-485">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="784c0-485">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="784c0-486">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="784c0-486">Informational (4)</span></span>|  
  
 <span data-ttu-id="784c0-487">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="784c0-487">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="784c0-488">Event</span><span class="sxs-lookup"><span data-stu-id="784c0-488">Event</span></span>|<span data-ttu-id="784c0-489">事件 ID</span><span class="sxs-lookup"><span data-stu-id="784c0-489">Event ID</span></span>|<span data-ttu-id="784c0-490">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="784c0-490">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="784c0-491">12</span><span class="sxs-lookup"><span data-stu-id="784c0-491">12</span></span>|<span data-ttu-id="784c0-492">已终止并发垃圾回收线程。</span><span class="sxs-lookup"><span data-stu-id="784c0-492">Concurrent garbage collection thread was terminated.</span></span>|  
  
 <span data-ttu-id="784c0-493">无事件数据。</span><span class="sxs-lookup"><span data-stu-id="784c0-493">No event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="784c0-494">请参阅</span><span class="sxs-lookup"><span data-stu-id="784c0-494">See also</span></span>

- [<span data-ttu-id="784c0-495">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="784c0-495">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
