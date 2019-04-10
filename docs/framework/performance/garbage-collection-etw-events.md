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
ms.openlocfilehash: 7f9bf0e309ec8c77d4b1d6afbf111e7eeae629ac
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149729"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="2b3cf-102">垃圾回收 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-102">Garbage Collection ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="2b3cf-103">这些事件可收集有关垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="2b3cf-104">它们可帮助进行诊断和调试，包括确定垃圾回收执行的次数、垃圾回收期间释放的内存量等。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>  
  
 <span data-ttu-id="2b3cf-105">此类别包含以下事件：</span><span class="sxs-lookup"><span data-stu-id="2b3cf-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="2b3cf-106">GCStart_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-106">GCStart_V1 Event</span></span>](#gcstart_v1_event)  
  
-   [<span data-ttu-id="2b3cf-107">GCEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-107">GCEnd_V1 Event</span></span>](#gcend_v1_event)  
  
-   [<span data-ttu-id="2b3cf-108">GCHeapStats_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1_event)  
  
-   [<span data-ttu-id="2b3cf-109">GCCreateSegment_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1_event)  
  
-   [<span data-ttu-id="2b3cf-110">GCFreeSegment_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1_event)  
  
-   [<span data-ttu-id="2b3cf-111">GCRestartEEBegin_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1_event)  
  
-   [<span data-ttu-id="2b3cf-112">GCRestartEEEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1_event)  
  
-   [<span data-ttu-id="2b3cf-113">GCSuspendEE_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1_event)  
  
-   [<span data-ttu-id="2b3cf-114">GCSuspendEEEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1_event)  
  
-   [<span data-ttu-id="2b3cf-115">GCAllocationTick_V2 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2_event)  
  
-   [<span data-ttu-id="2b3cf-116">GCFinalizersBegin_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1_event)  
  
-   [<span data-ttu-id="2b3cf-117">GCFinalizersEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1_event)  
  
-   [<span data-ttu-id="2b3cf-118">GCCreateConcurrentThread_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1_event)  
  
-   [<span data-ttu-id="2b3cf-119">GCTerminateConcurrentThread_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1_event)  
  
<a name="gcstart_v1_event"></a>   
## <a name="gcstartv1-event"></a><span data-ttu-id="2b3cf-120">GCStart_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-120">GCStart_V1 Event</span></span>  
 <span data-ttu-id="2b3cf-121">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="2b3cf-122">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="2b3cf-122">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="2b3cf-123">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="2b3cf-123">Keyword for raising the event</span></span>|<span data-ttu-id="2b3cf-124">级别</span><span class="sxs-lookup"><span data-stu-id="2b3cf-124">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="2b3cf-125">(0x1)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-125">(0x1)</span></span>|<span data-ttu-id="2b3cf-126">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-126">Informational (4)</span></span>|  
  
 <span data-ttu-id="2b3cf-127">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-127">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2b3cf-128">Event</span><span class="sxs-lookup"><span data-stu-id="2b3cf-128">Event</span></span>|<span data-ttu-id="2b3cf-129">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2b3cf-129">Event ID</span></span>|<span data-ttu-id="2b3cf-130">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="2b3cf-130">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCStart_V1`|<span data-ttu-id="2b3cf-131">1</span><span class="sxs-lookup"><span data-stu-id="2b3cf-131">1</span></span>|<span data-ttu-id="2b3cf-132">垃圾回收已启动。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-132">A garbage collection has started.</span></span>|  
  
 <span data-ttu-id="2b3cf-133">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-133">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2b3cf-134">字段名</span><span class="sxs-lookup"><span data-stu-id="2b3cf-134">Field name</span></span>|<span data-ttu-id="2b3cf-135">数据类型</span><span class="sxs-lookup"><span data-stu-id="2b3cf-135">Data type</span></span>|<span data-ttu-id="2b3cf-136">描述</span><span class="sxs-lookup"><span data-stu-id="2b3cf-136">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2b3cf-137">计数</span><span class="sxs-lookup"><span data-stu-id="2b3cf-137">Count</span></span>|<span data-ttu-id="2b3cf-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2b3cf-138">win:UInt32</span></span>|<span data-ttu-id="2b3cf-139">第 *n*代垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-139">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="2b3cf-140">深度</span><span class="sxs-lookup"><span data-stu-id="2b3cf-140">Depth</span></span>|<span data-ttu-id="2b3cf-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2b3cf-141">win:UInt32</span></span>|<span data-ttu-id="2b3cf-142">正在回收的代。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-142">The generation that is being collected.</span></span>|  
|<span data-ttu-id="2b3cf-143">原因</span><span class="sxs-lookup"><span data-stu-id="2b3cf-143">Reason</span></span>|<span data-ttu-id="2b3cf-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2b3cf-144">win:UInt32</span></span>|<span data-ttu-id="2b3cf-145">垃圾回收的触发原因：</span><span class="sxs-lookup"><span data-stu-id="2b3cf-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="2b3cf-146">0x0 - 小型对象堆分配。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="2b3cf-147">0x1 - 已引发。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="2b3cf-148">0x2 - 内存不足。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="2b3cf-149">0x3 - 空。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="2b3cf-150">0x4 - 大型对象堆分配。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="2b3cf-151">0x5 - 空间不足（针对小型对象堆）。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="2b3cf-152">0x6 - 空间不足（针对大型对象堆）。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="2b3cf-153">0x7 - 已引发，但未强制为阻止。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-153">0x7 - Induced but not forced as blocking.</span></span>|  
|<span data-ttu-id="2b3cf-154">类型</span><span class="sxs-lookup"><span data-stu-id="2b3cf-154">Type</span></span>|<span data-ttu-id="2b3cf-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2b3cf-155">win:UInt32</span></span>|<span data-ttu-id="2b3cf-156">0x0 - 在后台垃圾回收外部发生了垃圾回收阻止。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="2b3cf-157">0x1 - 后台垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="2b3cf-158">0x0 - 后台垃圾回收期间发生了垃圾回收阻止。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|  
|<span data-ttu-id="2b3cf-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2b3cf-159">ClrInstanceID</span></span>|<span data-ttu-id="2b3cf-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2b3cf-160">win:UInt16</span></span>|<span data-ttu-id="2b3cf-161">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="2b3cf-162">返回页首</span><span class="sxs-lookup"><span data-stu-id="2b3cf-162">Back to top</span></span>](#top)  
  
<a name="gcend_v1_event"></a>   
## <a name="gcendv1-event"></a><span data-ttu-id="2b3cf-163">GCEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-163">GCEnd_V1 Event</span></span>  
 <span data-ttu-id="2b3cf-164">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-164">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2b3cf-165">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="2b3cf-165">Keyword for raising the event</span></span>|<span data-ttu-id="2b3cf-166">级别</span><span class="sxs-lookup"><span data-stu-id="2b3cf-166">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="2b3cf-167">(0x1)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-167">(0x1)</span></span>|<span data-ttu-id="2b3cf-168">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-168">Informational (4)</span></span>|  
  
 <span data-ttu-id="2b3cf-169">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-169">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2b3cf-170">Event</span><span class="sxs-lookup"><span data-stu-id="2b3cf-170">Event</span></span>|<span data-ttu-id="2b3cf-171">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2b3cf-171">Event ID</span></span>|<span data-ttu-id="2b3cf-172">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="2b3cf-172">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCEnd_V1`|<span data-ttu-id="2b3cf-173">2</span><span class="sxs-lookup"><span data-stu-id="2b3cf-173">2</span></span>|<span data-ttu-id="2b3cf-174">垃圾回收已结束。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-174">The garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="2b3cf-175">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-175">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2b3cf-176">字段名</span><span class="sxs-lookup"><span data-stu-id="2b3cf-176">Field name</span></span>|<span data-ttu-id="2b3cf-177">数据类型</span><span class="sxs-lookup"><span data-stu-id="2b3cf-177">Data type</span></span>|<span data-ttu-id="2b3cf-178">描述</span><span class="sxs-lookup"><span data-stu-id="2b3cf-178">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2b3cf-179">计数</span><span class="sxs-lookup"><span data-stu-id="2b3cf-179">Count</span></span>|<span data-ttu-id="2b3cf-180">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2b3cf-180">win:UInt32</span></span>|<span data-ttu-id="2b3cf-181">第 *n*代垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-181">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="2b3cf-182">深度</span><span class="sxs-lookup"><span data-stu-id="2b3cf-182">Depth</span></span>|<span data-ttu-id="2b3cf-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2b3cf-183">win:UInt32</span></span>|<span data-ttu-id="2b3cf-184">已回收的代。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-184">The generation that was collected.</span></span>|  
|<span data-ttu-id="2b3cf-185">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2b3cf-185">ClrInstanceID</span></span>|<span data-ttu-id="2b3cf-186">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2b3cf-186">win:UInt16</span></span>|<span data-ttu-id="2b3cf-187">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-187">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="2b3cf-188">返回页首</span><span class="sxs-lookup"><span data-stu-id="2b3cf-188">Back to top</span></span>](#top)  
  
<a name="gcheapstats_v1_event"></a>   
## <a name="gcheapstatsv1-event"></a><span data-ttu-id="2b3cf-189">GCHeapStats_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-189">GCHeapStats_V1 Event</span></span>  
 <span data-ttu-id="2b3cf-190">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-190">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2b3cf-191">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="2b3cf-191">Keyword for raising the event</span></span>|<span data-ttu-id="2b3cf-192">级别</span><span class="sxs-lookup"><span data-stu-id="2b3cf-192">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="2b3cf-193">(0x1)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-193">(0x1)</span></span>|<span data-ttu-id="2b3cf-194">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-194">Informational (4)</span></span>|  
  
 <span data-ttu-id="2b3cf-195">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-195">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2b3cf-196">Event</span><span class="sxs-lookup"><span data-stu-id="2b3cf-196">Event</span></span>|<span data-ttu-id="2b3cf-197">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2b3cf-197">Event ID</span></span>|<span data-ttu-id="2b3cf-198">描述</span><span class="sxs-lookup"><span data-stu-id="2b3cf-198">Description</span></span>|  
|-----------|--------------|-----------------|  
|`GCHeapStats_V1`|<span data-ttu-id="2b3cf-199">4</span><span class="sxs-lookup"><span data-stu-id="2b3cf-199">4</span></span>|<span data-ttu-id="2b3cf-200">在每次垃圾回收结束时显示堆统计信息。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-200">Shows the heap statistics at the end of each garbage collection.</span></span>|  
  
 <span data-ttu-id="2b3cf-201">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-201">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2b3cf-202">字段名</span><span class="sxs-lookup"><span data-stu-id="2b3cf-202">Field name</span></span>|<span data-ttu-id="2b3cf-203">数据类型</span><span class="sxs-lookup"><span data-stu-id="2b3cf-203">Data type</span></span>|<span data-ttu-id="2b3cf-204">描述</span><span class="sxs-lookup"><span data-stu-id="2b3cf-204">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2b3cf-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="2b3cf-205">GenerationSize0</span></span>|<span data-ttu-id="2b3cf-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2b3cf-206">win:UInt64</span></span>|<span data-ttu-id="2b3cf-207">第 0 代内存的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-207">The size, in bytes, of generation 0 memory.</span></span>|  
|<span data-ttu-id="2b3cf-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="2b3cf-208">TotalPromotedSize0</span></span>|<span data-ttu-id="2b3cf-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2b3cf-209">win:UInt64</span></span>|<span data-ttu-id="2b3cf-210">从第 0 代提升到第 1 代的字节数。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|  
|<span data-ttu-id="2b3cf-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="2b3cf-211">GenerationSize1</span></span>|<span data-ttu-id="2b3cf-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2b3cf-212">win:UInt64</span></span>|<span data-ttu-id="2b3cf-213">第 1 代内存的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-213">The size, in bytes, of generation 1 memory.</span></span>|  
|<span data-ttu-id="2b3cf-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="2b3cf-214">TotalPromotedSize1</span></span>|<span data-ttu-id="2b3cf-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2b3cf-215">win:UInt64</span></span>|<span data-ttu-id="2b3cf-216">从第 1 代提升到第 2 代的字节数。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|  
|<span data-ttu-id="2b3cf-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="2b3cf-217">GenerationSize2</span></span>|<span data-ttu-id="2b3cf-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2b3cf-218">win:UInt64</span></span>|<span data-ttu-id="2b3cf-219">第 2 代内存的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-219">The size, in bytes, of generation 2 memory.</span></span>|  
|<span data-ttu-id="2b3cf-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="2b3cf-220">TotalPromotedSize2</span></span>|<span data-ttu-id="2b3cf-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2b3cf-221">win:UInt64</span></span>|<span data-ttu-id="2b3cf-222">上次回收后仍存在于第 2 代中的字节数。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|  
|<span data-ttu-id="2b3cf-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="2b3cf-223">GenerationSize3</span></span>|<span data-ttu-id="2b3cf-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2b3cf-224">win:UInt64</span></span>|<span data-ttu-id="2b3cf-225">大型对象堆的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-225">The size, in bytes, of the large object heap.</span></span>|  
|<span data-ttu-id="2b3cf-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="2b3cf-226">TotalPromotedSize3</span></span>|<span data-ttu-id="2b3cf-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2b3cf-227">win:UInt64</span></span>|<span data-ttu-id="2b3cf-228">上次回收后仍存在于大型对象堆中的字节数。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|  
|<span data-ttu-id="2b3cf-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="2b3cf-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="2b3cf-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2b3cf-230">win:UInt64</span></span>|<span data-ttu-id="2b3cf-231">准备终结的对象的总大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="2b3cf-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="2b3cf-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="2b3cf-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2b3cf-233">win:UInt64</span></span>|<span data-ttu-id="2b3cf-234">已准备好进行终结的对象的数目。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-234">The number of objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="2b3cf-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="2b3cf-235">PinnedObjectCount</span></span>|<span data-ttu-id="2b3cf-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2b3cf-236">win:UInt32</span></span>|<span data-ttu-id="2b3cf-237">固定（不可移动）对象的数目。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-237">The number of pinned (unmovable) objects.</span></span>|  
|<span data-ttu-id="2b3cf-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="2b3cf-238">SinkBlockCount</span></span>|<span data-ttu-id="2b3cf-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2b3cf-239">win:UInt32</span></span>|<span data-ttu-id="2b3cf-240">正在使用的同步块的数目。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-240">The number of synchronization blocks in use.</span></span>|  
|<span data-ttu-id="2b3cf-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="2b3cf-241">GCHandleCount</span></span>|<span data-ttu-id="2b3cf-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2b3cf-242">win:UInt32</span></span>|<span data-ttu-id="2b3cf-243">使用中的垃圾回收句柄的数目。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-243">The number of garbage collection handles in use.</span></span>|  
|<span data-ttu-id="2b3cf-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2b3cf-244">ClrInstanceID</span></span>|<span data-ttu-id="2b3cf-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2b3cf-245">win:UInt16</span></span>|<span data-ttu-id="2b3cf-246">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="2b3cf-247">返回页首</span><span class="sxs-lookup"><span data-stu-id="2b3cf-247">Back to top</span></span>](#top)  
  
<a name="gccreatesegment_v1_event"></a>   
## <a name="gccreatesegmentv1-event"></a><span data-ttu-id="2b3cf-248">GCCreateSegment_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-248">GCCreateSegment_V1 Event</span></span>  
 <span data-ttu-id="2b3cf-249">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-249">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2b3cf-250">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="2b3cf-250">Keyword for raising the event</span></span>|<span data-ttu-id="2b3cf-251">级别</span><span class="sxs-lookup"><span data-stu-id="2b3cf-251">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="2b3cf-252">(0x1)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-252">(0x1)</span></span>|<span data-ttu-id="2b3cf-253">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-253">Informational (4)</span></span>|  
  
 <span data-ttu-id="2b3cf-254">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-254">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2b3cf-255">Event</span><span class="sxs-lookup"><span data-stu-id="2b3cf-255">Event</span></span>|<span data-ttu-id="2b3cf-256">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2b3cf-256">Event ID</span></span>|<span data-ttu-id="2b3cf-257">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="2b3cf-257">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateSegment_V1`|<span data-ttu-id="2b3cf-258">5</span><span class="sxs-lookup"><span data-stu-id="2b3cf-258">5</span></span>|<span data-ttu-id="2b3cf-259">已创建的新的垃圾回收段。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-259">A new garbage collection segment has been created.</span></span> <span data-ttu-id="2b3cf-260">此外，当在已运行的进程中启用跟踪时，将为每个现有段引发此事件。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-260">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|  
  
 <span data-ttu-id="2b3cf-261">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-261">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2b3cf-262">字段名</span><span class="sxs-lookup"><span data-stu-id="2b3cf-262">Field name</span></span>|<span data-ttu-id="2b3cf-263">数据类型</span><span class="sxs-lookup"><span data-stu-id="2b3cf-263">Data type</span></span>|<span data-ttu-id="2b3cf-264">描述</span><span class="sxs-lookup"><span data-stu-id="2b3cf-264">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2b3cf-265">Address</span><span class="sxs-lookup"><span data-stu-id="2b3cf-265">Address</span></span>|<span data-ttu-id="2b3cf-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2b3cf-266">win:UInt64</span></span>|<span data-ttu-id="2b3cf-267">段的地址。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-267">The address of the segment.</span></span>|  
|<span data-ttu-id="2b3cf-268">大小</span><span class="sxs-lookup"><span data-stu-id="2b3cf-268">Size</span></span>|<span data-ttu-id="2b3cf-269">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2b3cf-269">win:UInt64</span></span>|<span data-ttu-id="2b3cf-270">段的大小。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-270">The size of the segment.</span></span>|  
|<span data-ttu-id="2b3cf-271">类型</span><span class="sxs-lookup"><span data-stu-id="2b3cf-271">Type</span></span>|<span data-ttu-id="2b3cf-272">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2b3cf-272">win:UInt32</span></span>|<span data-ttu-id="2b3cf-273">0x0 - 小型对象堆。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-273">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="2b3cf-274">0x0 - 大型对象堆。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-274">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="2b3cf-275">0x2 - 只读堆。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-275">0x2 - Read-only heap.</span></span>|  
|<span data-ttu-id="2b3cf-276">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2b3cf-276">ClrInstanceID</span></span>|<span data-ttu-id="2b3cf-277">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2b3cf-277">win:UInt16</span></span>|<span data-ttu-id="2b3cf-278">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-278">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 <span data-ttu-id="2b3cf-279">请注意，由垃圾回收器分配的段的大小特定于实现，且随时可能更改（包括定期更新）。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-279">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="2b3cf-280">应用程序不应假设特定段的大小或依赖于此大小，也不应尝试配置段分配可用的内存量。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-280">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>  
  
 [<span data-ttu-id="2b3cf-281">返回页首</span><span class="sxs-lookup"><span data-stu-id="2b3cf-281">Back to top</span></span>](#top)  
  
<a name="gcfreesegment_v1_event"></a>   
## <a name="gcfreesegmentv1-event"></a><span data-ttu-id="2b3cf-282">GCFreeSegment_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-282">GCFreeSegment_V1 Event</span></span>  
 <span data-ttu-id="2b3cf-283">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-283">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2b3cf-284">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="2b3cf-284">Keyword for raising the event</span></span>|<span data-ttu-id="2b3cf-285">级别</span><span class="sxs-lookup"><span data-stu-id="2b3cf-285">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="2b3cf-286">(0x1)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-286">(0x1)</span></span>|<span data-ttu-id="2b3cf-287">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-287">Informational (4)</span></span>|  
  
 <span data-ttu-id="2b3cf-288">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-288">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2b3cf-289">Event</span><span class="sxs-lookup"><span data-stu-id="2b3cf-289">Event</span></span>|<span data-ttu-id="2b3cf-290">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2b3cf-290">Event ID</span></span>|<span data-ttu-id="2b3cf-291">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="2b3cf-291">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFreeSegment_V1`|<span data-ttu-id="2b3cf-292">6</span><span class="sxs-lookup"><span data-stu-id="2b3cf-292">6</span></span>|<span data-ttu-id="2b3cf-293">已释放垃圾回收段。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-293">A garbage collection segment has been released.</span></span>|  
  
 <span data-ttu-id="2b3cf-294">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-294">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2b3cf-295">字段名</span><span class="sxs-lookup"><span data-stu-id="2b3cf-295">Field name</span></span>|<span data-ttu-id="2b3cf-296">数据类型</span><span class="sxs-lookup"><span data-stu-id="2b3cf-296">Data type</span></span>|<span data-ttu-id="2b3cf-297">描述</span><span class="sxs-lookup"><span data-stu-id="2b3cf-297">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2b3cf-298">Address</span><span class="sxs-lookup"><span data-stu-id="2b3cf-298">Address</span></span>|<span data-ttu-id="2b3cf-299">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2b3cf-299">win:UInt64</span></span>|<span data-ttu-id="2b3cf-300">段的地址。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-300">The address of the segment.</span></span>|  
|<span data-ttu-id="2b3cf-301">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2b3cf-301">ClrInstanceID</span></span>|<span data-ttu-id="2b3cf-302">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2b3cf-302">win:UInt16</span></span>|<span data-ttu-id="2b3cf-303">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-303">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="2b3cf-304">返回页首</span><span class="sxs-lookup"><span data-stu-id="2b3cf-304">Back to top</span></span>](#top)  
  
<a name="gcrestarteebegin_v1_event"></a>   
## <a name="gcrestarteebeginv1-event"></a><span data-ttu-id="2b3cf-305">GCRestartEEBegin_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-305">GCRestartEEBegin_V1 Event</span></span>  
 <span data-ttu-id="2b3cf-306">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2b3cf-307">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="2b3cf-307">Keyword for raising the event</span></span>|<span data-ttu-id="2b3cf-308">级别</span><span class="sxs-lookup"><span data-stu-id="2b3cf-308">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="2b3cf-309">(0x1)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-309">(0x1)</span></span>|<span data-ttu-id="2b3cf-310">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="2b3cf-311">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2b3cf-312">Event</span><span class="sxs-lookup"><span data-stu-id="2b3cf-312">Event</span></span>|<span data-ttu-id="2b3cf-313">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2b3cf-313">Event ID</span></span>|<span data-ttu-id="2b3cf-314">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="2b3cf-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEBegin_V1`|<span data-ttu-id="2b3cf-315">7</span><span class="sxs-lookup"><span data-stu-id="2b3cf-315">7</span></span>|<span data-ttu-id="2b3cf-316">已开始从公共语言运行时挂起进行恢复。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-316">Resumption from common language runtime suspension has begun.</span></span>|  
  
 <span data-ttu-id="2b3cf-317">无事件数据。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-317">No event data.</span></span>  
  
 [<span data-ttu-id="2b3cf-318">返回页首</span><span class="sxs-lookup"><span data-stu-id="2b3cf-318">Back to top</span></span>](#top)  
  
<a name="gcrestarteeend_v1_event"></a>   
## <a name="gcrestarteeendv1-event"></a><span data-ttu-id="2b3cf-319">GCRestartEEEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-319">GCRestartEEEnd_V1 Event</span></span>  
 <span data-ttu-id="2b3cf-320">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-320">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2b3cf-321">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="2b3cf-321">Keyword for raising the event</span></span>|<span data-ttu-id="2b3cf-322">级别</span><span class="sxs-lookup"><span data-stu-id="2b3cf-322">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="2b3cf-323">(0x1)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-323">(0x1)</span></span>|<span data-ttu-id="2b3cf-324">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-324">Informational (4)</span></span>|  
  
 <span data-ttu-id="2b3cf-325">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-325">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2b3cf-326">Event</span><span class="sxs-lookup"><span data-stu-id="2b3cf-326">Event</span></span>|<span data-ttu-id="2b3cf-327">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2b3cf-327">Event Id</span></span>|<span data-ttu-id="2b3cf-328">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="2b3cf-328">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEEnd_V1`|<span data-ttu-id="2b3cf-329">3</span><span class="sxs-lookup"><span data-stu-id="2b3cf-329">3</span></span>|<span data-ttu-id="2b3cf-330">从公共语言运行时挂起进行的恢复已结束。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-330">Resumption from common language runtime suspension has ended.</span></span>|  
  
 <span data-ttu-id="2b3cf-331">无事件数据。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-331">No event data.</span></span>  
  
 [<span data-ttu-id="2b3cf-332">返回页首</span><span class="sxs-lookup"><span data-stu-id="2b3cf-332">Back to top</span></span>](#top)  
  
<a name="gcsuspendee_v1_event"></a>   
## <a name="gcsuspendeev1-event"></a><span data-ttu-id="2b3cf-333">GCSuspendEE_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-333">GCSuspendEE_V1 Event</span></span>  
 <span data-ttu-id="2b3cf-334">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-334">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2b3cf-335">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="2b3cf-335">Keyword for raising the event</span></span>|<span data-ttu-id="2b3cf-336">级别</span><span class="sxs-lookup"><span data-stu-id="2b3cf-336">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="2b3cf-337">(0x1)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-337">(0x1)</span></span>|<span data-ttu-id="2b3cf-338">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-338">Informational (4)</span></span>|  
  
 <span data-ttu-id="2b3cf-339">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-339">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2b3cf-340">Event</span><span class="sxs-lookup"><span data-stu-id="2b3cf-340">Event</span></span>|<span data-ttu-id="2b3cf-341">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2b3cf-341">Event ID</span></span>|<span data-ttu-id="2b3cf-342">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="2b3cf-342">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEE_V1`|<span data-ttu-id="2b3cf-343">9</span><span class="sxs-lookup"><span data-stu-id="2b3cf-343">9</span></span>|<span data-ttu-id="2b3cf-344">开始挂起垃圾回收的执行引擎。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-344">Start of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="2b3cf-345">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-345">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2b3cf-346">字段名</span><span class="sxs-lookup"><span data-stu-id="2b3cf-346">Field name</span></span>|<span data-ttu-id="2b3cf-347">数据类型</span><span class="sxs-lookup"><span data-stu-id="2b3cf-347">Data type</span></span>|<span data-ttu-id="2b3cf-348">描述</span><span class="sxs-lookup"><span data-stu-id="2b3cf-348">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2b3cf-349">原因</span><span class="sxs-lookup"><span data-stu-id="2b3cf-349">Reason</span></span>|<span data-ttu-id="2b3cf-350">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2b3cf-350">win:UInt16</span></span>|<span data-ttu-id="2b3cf-351">0x0 - 其他。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-351">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="2b3cf-352">0x1 - 垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-352">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="2b3cf-353">0x2 - 应用程序域关闭。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-353">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="2b3cf-354">0x3 - 代码间距调整。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-354">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="2b3cf-355">0x4 - 关闭。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-355">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="2b3cf-356">0x5 - 调试器。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-356">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="2b3cf-357">0x6 - 准备垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-357">0x6 - Preparation for garbage collection.</span></span>|  
|<span data-ttu-id="2b3cf-358">计数</span><span class="sxs-lookup"><span data-stu-id="2b3cf-358">Count</span></span>|<span data-ttu-id="2b3cf-359">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2b3cf-359">win:UInt32</span></span>|<span data-ttu-id="2b3cf-360">此时的 GC 计数。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-360">The GC count at the time.</span></span> <span data-ttu-id="2b3cf-361">通常情况下，会在这之后看到后续 GC 开始事件，且在垃圾回收期间增加 GC 索引时，其计数会增加 1。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-361">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|  
|<span data-ttu-id="2b3cf-362">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2b3cf-362">ClrInstanceID</span></span>|<span data-ttu-id="2b3cf-363">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2b3cf-363">win:UInt16</span></span>|<span data-ttu-id="2b3cf-364">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-364">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="2b3cf-365">返回页首</span><span class="sxs-lookup"><span data-stu-id="2b3cf-365">Back to top</span></span>](#top)  
  
<a name="gcsuspendeeend_v1_event"></a>   
## <a name="gcsuspendeeendv1-event"></a><span data-ttu-id="2b3cf-366">GCSuspendEEEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-366">GCSuspendEEEnd_V1 Event</span></span>  
 <span data-ttu-id="2b3cf-367">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="2b3cf-367">The following table shows the keyword and level:</span></span>  
  
|<span data-ttu-id="2b3cf-368">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="2b3cf-368">Keyword for raising the event</span></span>|<span data-ttu-id="2b3cf-369">级别</span><span class="sxs-lookup"><span data-stu-id="2b3cf-369">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="2b3cf-370">(0x1)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-370">(0x1)</span></span>|<span data-ttu-id="2b3cf-371">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-371">Informational (4)</span></span>|  
  
 <span data-ttu-id="2b3cf-372">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="2b3cf-372">The following table shows the event information:</span></span>  
  
|<span data-ttu-id="2b3cf-373">Event</span><span class="sxs-lookup"><span data-stu-id="2b3cf-373">Event</span></span>|<span data-ttu-id="2b3cf-374">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2b3cf-374">Event ID</span></span>|<span data-ttu-id="2b3cf-375">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="2b3cf-375">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEEEnd_V1`|<span data-ttu-id="2b3cf-376">8</span><span class="sxs-lookup"><span data-stu-id="2b3cf-376">8</span></span>|<span data-ttu-id="2b3cf-377">结束垃圾回收执行引擎的挂起。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-377">End of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="2b3cf-378">无事件数据。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-378">No event data.</span></span>  
  
 [<span data-ttu-id="2b3cf-379">返回页首</span><span class="sxs-lookup"><span data-stu-id="2b3cf-379">Back to top</span></span>](#top)  
  
<a name="gcallocationtick_v2_event"></a>   
## <a name="gcallocationtickv2-event"></a><span data-ttu-id="2b3cf-380">GCAllocationTick_V2 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-380">GCAllocationTick_V2 Event</span></span>  
 <span data-ttu-id="2b3cf-381">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-381">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2b3cf-382">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="2b3cf-382">Keyword for raising the event</span></span>|<span data-ttu-id="2b3cf-383">级别</span><span class="sxs-lookup"><span data-stu-id="2b3cf-383">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="2b3cf-384">(0x1)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-384">(0x1)</span></span>|<span data-ttu-id="2b3cf-385">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-385">Informational (4)</span></span>|  
  
 <span data-ttu-id="2b3cf-386">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-386">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2b3cf-387">Event</span><span class="sxs-lookup"><span data-stu-id="2b3cf-387">Event</span></span>|<span data-ttu-id="2b3cf-388">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2b3cf-388">Event ID</span></span>|<span data-ttu-id="2b3cf-389">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="2b3cf-389">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCAllocationTick_V2`|<span data-ttu-id="2b3cf-390">10</span><span class="sxs-lookup"><span data-stu-id="2b3cf-390">10</span></span>|<span data-ttu-id="2b3cf-391">每次大约分配 100 KB。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-391">Each time approximately 100 KB is allocated.</span></span>|  
  
 <span data-ttu-id="2b3cf-392">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-392">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2b3cf-393">字段名</span><span class="sxs-lookup"><span data-stu-id="2b3cf-393">Field name</span></span>|<span data-ttu-id="2b3cf-394">数据类型</span><span class="sxs-lookup"><span data-stu-id="2b3cf-394">Data type</span></span>|<span data-ttu-id="2b3cf-395">描述</span><span class="sxs-lookup"><span data-stu-id="2b3cf-395">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2b3cf-396">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="2b3cf-396">AllocationAmount</span></span>|<span data-ttu-id="2b3cf-397">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2b3cf-397">win:UInt32</span></span>|<span data-ttu-id="2b3cf-398">分配大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-398">The allocation size, in bytes.</span></span> <span data-ttu-id="2b3cf-399">对于小于 ULONG（4,294,967,295 字节）长度的分配，此值为精确值。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-399">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="2b3cf-400">如果分配长度更大，则此字段包含了截断的值。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-400">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="2b3cf-401">对于非常大的分配使用 `AllocationAmount64` 。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-401">Use `AllocationAmount64` for very large allocations.</span></span>|  
|<span data-ttu-id="2b3cf-402">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="2b3cf-402">AllocationKind</span></span>|<span data-ttu-id="2b3cf-403">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2b3cf-403">win:UInt32</span></span>|<span data-ttu-id="2b3cf-404">0x0 - 小型对象分配（小型对象堆中的分配）。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-404">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="2b3cf-405">0x0 - 大型对象分配（大型对象堆中的分配）。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-405">0x1 - Large object allocation (allocation is in large object heap).</span></span>|  
|<span data-ttu-id="2b3cf-406">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2b3cf-406">ClrInstanceID</span></span>|<span data-ttu-id="2b3cf-407">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2b3cf-407">win:UInt16</span></span>|<span data-ttu-id="2b3cf-408">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-408">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
|<span data-ttu-id="2b3cf-409">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="2b3cf-409">AllocationAmount64</span></span>|<span data-ttu-id="2b3cf-410">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2b3cf-410">win:UInt64</span></span>|<span data-ttu-id="2b3cf-411">分配大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-411">The allocation size, in bytes.</span></span> <span data-ttu-id="2b3cf-412">对于非常大的分配，此值为精确值。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-412">This value is accurate for very large allocations.</span></span>|  
|<span data-ttu-id="2b3cf-413">TypeId</span><span class="sxs-lookup"><span data-stu-id="2b3cf-413">TypeId</span></span>|<span data-ttu-id="2b3cf-414">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="2b3cf-414">win:Pointer</span></span>|<span data-ttu-id="2b3cf-415">MethodTable 的地址。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-415">The address of the MethodTable.</span></span> <span data-ttu-id="2b3cf-416">如果在此事件期间分配了几种类型的对象，则此地址为对应于分配的最后一个对象（导致超过 100 KB 阙值的对象）的 MethodTable 地址。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-416">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="2b3cf-417">TypeName</span><span class="sxs-lookup"><span data-stu-id="2b3cf-417">TypeName</span></span>|<span data-ttu-id="2b3cf-418">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="2b3cf-418">win:UnicodeString</span></span>|<span data-ttu-id="2b3cf-419">已分配的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-419">The name of the type that was allocated.</span></span> <span data-ttu-id="2b3cf-420">如果在此事件期间分配了几种类型的对象，则此地址为对应于分配的最后一个类型（导致超过 100 KB 阙值的对象）。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-420">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="2b3cf-421">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="2b3cf-421">HeapIndex</span></span>|<span data-ttu-id="2b3cf-422">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2b3cf-422">win:UInt32</span></span>|<span data-ttu-id="2b3cf-423">此对象所分配到的堆。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-423">The heap where the object was allocated.</span></span> <span data-ttu-id="2b3cf-424">与工作站垃圾回收一起运行时，此值为 0（零）。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-424">This value is 0 (zero) when running with workstation garbage collection.</span></span>|  
  
 [<span data-ttu-id="2b3cf-425">返回页首</span><span class="sxs-lookup"><span data-stu-id="2b3cf-425">Back to top</span></span>](#top)  
  
<a name="gcfinalizersbegin_v1_event"></a>   
## <a name="gcfinalizersbeginv1-event"></a><span data-ttu-id="2b3cf-426">GCFinalizersBegin_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-426">GCFinalizersBegin_V1 Event</span></span>  
 <span data-ttu-id="2b3cf-427">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-427">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2b3cf-428">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="2b3cf-428">Keyword for raising the event</span></span>|<span data-ttu-id="2b3cf-429">级别</span><span class="sxs-lookup"><span data-stu-id="2b3cf-429">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="2b3cf-430">(0x1)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-430">(0x1)</span></span>|<span data-ttu-id="2b3cf-431">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-431">Informational (4)</span></span>|  
  
 <span data-ttu-id="2b3cf-432">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-432">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2b3cf-433">Event</span><span class="sxs-lookup"><span data-stu-id="2b3cf-433">Event</span></span>|<span data-ttu-id="2b3cf-434">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2b3cf-434">Event ID</span></span>|<span data-ttu-id="2b3cf-435">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="2b3cf-435">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersBegin_V1`|<span data-ttu-id="2b3cf-436">14</span><span class="sxs-lookup"><span data-stu-id="2b3cf-436">14</span></span>|<span data-ttu-id="2b3cf-437">开始运行终结器。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-437">The start of running finalizers.</span></span>|  
  
 <span data-ttu-id="2b3cf-438">无事件数据。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-438">No event data.</span></span>  
  
 [<span data-ttu-id="2b3cf-439">返回页首</span><span class="sxs-lookup"><span data-stu-id="2b3cf-439">Back to top</span></span>](#top)  
  
<a name="gcfinalizersend_v1_event"></a>   
## <a name="gcfinalizersendv1-event"></a><span data-ttu-id="2b3cf-440">GCFinalizersEnd_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-440">GCFinalizersEnd_V1 Event</span></span>  
 <span data-ttu-id="2b3cf-441">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-441">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2b3cf-442">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="2b3cf-442">Keyword for raising the event</span></span>|<span data-ttu-id="2b3cf-443">级别</span><span class="sxs-lookup"><span data-stu-id="2b3cf-443">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="2b3cf-444">(0x1)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-444">(0x1)</span></span>|<span data-ttu-id="2b3cf-445">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-445">Informational (4)</span></span>|  
  
 <span data-ttu-id="2b3cf-446">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-446">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2b3cf-447">Event</span><span class="sxs-lookup"><span data-stu-id="2b3cf-447">Event</span></span>|<span data-ttu-id="2b3cf-448">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2b3cf-448">Event ID</span></span>|<span data-ttu-id="2b3cf-449">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="2b3cf-449">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersEnd_V1`|<span data-ttu-id="2b3cf-450">13</span><span class="sxs-lookup"><span data-stu-id="2b3cf-450">13</span></span>|<span data-ttu-id="2b3cf-451">结束运行终结器。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-451">The end of running finalizers.</span></span>|  
  
 <span data-ttu-id="2b3cf-452">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-452">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2b3cf-453">字段名</span><span class="sxs-lookup"><span data-stu-id="2b3cf-453">Field name</span></span>|<span data-ttu-id="2b3cf-454">数据类型</span><span class="sxs-lookup"><span data-stu-id="2b3cf-454">Data type</span></span>|<span data-ttu-id="2b3cf-455">描述</span><span class="sxs-lookup"><span data-stu-id="2b3cf-455">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2b3cf-456">计数</span><span class="sxs-lookup"><span data-stu-id="2b3cf-456">Count</span></span>|<span data-ttu-id="2b3cf-457">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2b3cf-457">win:UInt32</span></span>|<span data-ttu-id="2b3cf-458">运行的终结器数。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-458">The number of finalizers that were run.</span></span>|  
|<span data-ttu-id="2b3cf-459">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2b3cf-459">ClrInstanceID</span></span>|<span data-ttu-id="2b3cf-460">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2b3cf-460">win:UInt16</span></span>|<span data-ttu-id="2b3cf-461">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-461">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="2b3cf-462">返回页首</span><span class="sxs-lookup"><span data-stu-id="2b3cf-462">Back to top</span></span>](#top)  
  
<a name="gccreateconcurrentthread_v1_event"></a>   
## <a name="gccreateconcurrentthreadv1-event"></a><span data-ttu-id="2b3cf-463">GCCreateConcurrentThread_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-463">GCCreateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="2b3cf-464">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-464">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2b3cf-465">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="2b3cf-465">Keyword for raising the event</span></span>|<span data-ttu-id="2b3cf-466">级别</span><span class="sxs-lookup"><span data-stu-id="2b3cf-466">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="2b3cf-467">(0x1)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-467">(0x1)</span></span>|<span data-ttu-id="2b3cf-468">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-468">Informational (4)</span></span>|  
|`ThreadingKeyword` <span data-ttu-id="2b3cf-469">(0x10000)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-469">(0x10000)</span></span>|<span data-ttu-id="2b3cf-470">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-470">Informational (4)</span></span>|  
  
 <span data-ttu-id="2b3cf-471">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-471">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2b3cf-472">Event</span><span class="sxs-lookup"><span data-stu-id="2b3cf-472">Event</span></span>|<span data-ttu-id="2b3cf-473">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2b3cf-473">Event ID</span></span>|<span data-ttu-id="2b3cf-474">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="2b3cf-474">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="2b3cf-475">11</span><span class="sxs-lookup"><span data-stu-id="2b3cf-475">11</span></span>|<span data-ttu-id="2b3cf-476">已创建并发垃圾回收线程。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-476">Concurrent garbage collection thread was created.</span></span>|  
  
 <span data-ttu-id="2b3cf-477">无事件数据。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-477">No event data.</span></span>  
  
 [<span data-ttu-id="2b3cf-478">返回页首</span><span class="sxs-lookup"><span data-stu-id="2b3cf-478">Back to top</span></span>](#top)  
  
<a name="gcterminateconcurrentthread_v1_event"></a>   
## <a name="gcterminateconcurrentthreadv1-event"></a><span data-ttu-id="2b3cf-479">GCTerminateConcurrentThread_V1 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-479">GCTerminateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="2b3cf-480">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-480">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2b3cf-481">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="2b3cf-481">Keyword for raising the event</span></span>|<span data-ttu-id="2b3cf-482">级别</span><span class="sxs-lookup"><span data-stu-id="2b3cf-482">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="2b3cf-483">(0x1)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-483">(0x1)</span></span>|<span data-ttu-id="2b3cf-484">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-484">Informational (4)</span></span>|  
|`ThreadingKeyword` <span data-ttu-id="2b3cf-485">(0x10000)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-485">(0x10000)</span></span>|<span data-ttu-id="2b3cf-486">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2b3cf-486">Informational (4)</span></span>|  
  
 <span data-ttu-id="2b3cf-487">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-487">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2b3cf-488">Event</span><span class="sxs-lookup"><span data-stu-id="2b3cf-488">Event</span></span>|<span data-ttu-id="2b3cf-489">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2b3cf-489">Event ID</span></span>|<span data-ttu-id="2b3cf-490">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="2b3cf-490">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="2b3cf-491">12</span><span class="sxs-lookup"><span data-stu-id="2b3cf-491">12</span></span>|<span data-ttu-id="2b3cf-492">已终止并发垃圾回收线程。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-492">Concurrent garbage collection thread was terminated.</span></span>|  
  
 <span data-ttu-id="2b3cf-493">无事件数据。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-493">No event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b3cf-494">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b3cf-494">See also</span></span>

- [<span data-ttu-id="2b3cf-495">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="2b3cf-495">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
