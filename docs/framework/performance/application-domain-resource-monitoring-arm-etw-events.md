---
title: 应用程序域资源监视 (ARM) ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8442b8723476984b90f740beac912688719f1791
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689830"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="1a985-102">应用程序域资源监视 (ARM) ETW 事件</span><span class="sxs-lookup"><span data-stu-id="1a985-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="1a985-103">这些事件提供有关应用程序域的状态的详细诊断信息。</span><span class="sxs-lookup"><span data-stu-id="1a985-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="1a985-104">你可以使用这些事件，或使用应用程序域资源监视 (ARM) 功能来获取相同的信息。</span><span class="sxs-lookup"><span data-stu-id="1a985-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="1a985-105">此类别包含以下事件：</span><span class="sxs-lookup"><span data-stu-id="1a985-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="1a985-106">ThreadCreated 事件</span><span class="sxs-lookup"><span data-stu-id="1a985-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
-   [<span data-ttu-id="1a985-107">AppDomainMemAllocated 事件</span><span class="sxs-lookup"><span data-stu-id="1a985-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
-   [<span data-ttu-id="1a985-108">AppDomainMemSurvived 事件</span><span class="sxs-lookup"><span data-stu-id="1a985-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
-   [<span data-ttu-id="1a985-109">ThreadAppDomainEnter 事件</span><span class="sxs-lookup"><span data-stu-id="1a985-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
-   [<span data-ttu-id="1a985-110">ThreadTerminated 事件</span><span class="sxs-lookup"><span data-stu-id="1a985-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="1a985-111">ThreadCreated 事件</span><span class="sxs-lookup"><span data-stu-id="1a985-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="1a985-112">在断开的提供程序下此事件也会作为 `ThreadDC` 引发（在 `AppDomainResourceManagementRundownKeyword` 关键字下）。</span><span class="sxs-lookup"><span data-stu-id="1a985-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="1a985-113">这是此类别的断开提供程序下引发的唯一事件。</span><span class="sxs-lookup"><span data-stu-id="1a985-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="1a985-114">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="1a985-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="1a985-115">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="1a985-115">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="1a985-116">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="1a985-116">Keyword for raising the event</span></span>|<span data-ttu-id="1a985-117">级别</span><span class="sxs-lookup"><span data-stu-id="1a985-117">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="1a985-118">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="1a985-118">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="1a985-119">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="1a985-119">Informational(4)</span></span>|  
|<span data-ttu-id="1a985-120">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="1a985-120">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="1a985-121">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="1a985-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="1a985-122">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="1a985-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="1a985-123">Event</span><span class="sxs-lookup"><span data-stu-id="1a985-123">Event</span></span>|<span data-ttu-id="1a985-124">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1a985-124">Event ID</span></span>|<span data-ttu-id="1a985-125">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="1a985-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="1a985-126">85</span><span class="sxs-lookup"><span data-stu-id="1a985-126">85</span></span>|<span data-ttu-id="1a985-127">已为应用程序域创建了一个线程。</span><span class="sxs-lookup"><span data-stu-id="1a985-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="1a985-128">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="1a985-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="1a985-129">字段名</span><span class="sxs-lookup"><span data-stu-id="1a985-129">Field name</span></span>|<span data-ttu-id="1a985-130">数据类型</span><span class="sxs-lookup"><span data-stu-id="1a985-130">Data type</span></span>|<span data-ttu-id="1a985-131">描述</span><span class="sxs-lookup"><span data-stu-id="1a985-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="1a985-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="1a985-132">ThreadID</span></span>|<span data-ttu-id="1a985-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1a985-133">win:UInt64</span></span>|<span data-ttu-id="1a985-134">已创建的线程 ID。</span><span class="sxs-lookup"><span data-stu-id="1a985-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="1a985-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="1a985-135">AppDomainID</span></span>|<span data-ttu-id="1a985-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1a985-136">win:UInt64</span></span>|<span data-ttu-id="1a985-137">正在报告其线程活动的应用程序域的标识符。</span><span class="sxs-lookup"><span data-stu-id="1a985-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="1a985-138">标志</span><span class="sxs-lookup"><span data-stu-id="1a985-138">Flags</span></span>|<span data-ttu-id="1a985-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1a985-139">win:UInt32</span></span>|<span data-ttu-id="1a985-140">线程创建标志。</span><span class="sxs-lookup"><span data-stu-id="1a985-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="1a985-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="1a985-141">ManagedThreadIndex</span></span>|<span data-ttu-id="1a985-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1a985-142">win:UInt32</span></span>|<span data-ttu-id="1a985-143">已创建线程的托管索引。</span><span class="sxs-lookup"><span data-stu-id="1a985-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="1a985-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="1a985-144">OSThreadID</span></span>|<span data-ttu-id="1a985-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1a985-145">win:UInt32</span></span>|<span data-ttu-id="1a985-146">已创建线程的操作系统 ID。</span><span class="sxs-lookup"><span data-stu-id="1a985-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="1a985-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1a985-147">ClrInstanceID</span></span>|<span data-ttu-id="1a985-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1a985-148">win:UInt16</span></span>|<span data-ttu-id="1a985-149">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="1a985-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="1a985-150">返回页首</span><span class="sxs-lookup"><span data-stu-id="1a985-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="1a985-151">AppDomainMemAllocated 事件</span><span class="sxs-lookup"><span data-stu-id="1a985-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="1a985-152">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="1a985-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="1a985-153">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="1a985-153">Keyword for raising the event</span></span>|<span data-ttu-id="1a985-154">级别</span><span class="sxs-lookup"><span data-stu-id="1a985-154">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="1a985-155">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="1a985-155">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="1a985-156">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="1a985-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="1a985-157">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="1a985-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="1a985-158">Event</span><span class="sxs-lookup"><span data-stu-id="1a985-158">Event</span></span>|<span data-ttu-id="1a985-159">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1a985-159">Event ID</span></span>|<span data-ttu-id="1a985-160">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="1a985-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="1a985-161">83</span><span class="sxs-lookup"><span data-stu-id="1a985-161">83</span></span>|<span data-ttu-id="1a985-162">应用程序域中分配每 4 MB 的内存（大约）。</span><span class="sxs-lookup"><span data-stu-id="1a985-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="1a985-163">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="1a985-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="1a985-164">字段名</span><span class="sxs-lookup"><span data-stu-id="1a985-164">Field name</span></span>|<span data-ttu-id="1a985-165">数据类型</span><span class="sxs-lookup"><span data-stu-id="1a985-165">Data type</span></span>|<span data-ttu-id="1a985-166">描述</span><span class="sxs-lookup"><span data-stu-id="1a985-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="1a985-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="1a985-167">AppDomainID</span></span>|<span data-ttu-id="1a985-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1a985-168">win:UInt64</span></span>|<span data-ttu-id="1a985-169">正在报告其资源使用情况的应用程序域的标识符。</span><span class="sxs-lookup"><span data-stu-id="1a985-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="1a985-170">已分配</span><span class="sxs-lookup"><span data-stu-id="1a985-170">Allocated</span></span>|<span data-ttu-id="1a985-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1a985-171">win:UInt64</span></span>|<span data-ttu-id="1a985-172">自应用程序域创建以来在此应用程序域中分配的字节总数（不减去已释放的内存量）。</span><span class="sxs-lookup"><span data-stu-id="1a985-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="1a985-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1a985-173">ClrInstanceID</span></span>|<span data-ttu-id="1a985-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1a985-174">win:UInt16</span></span>|<span data-ttu-id="1a985-175">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="1a985-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="1a985-176">返回页首</span><span class="sxs-lookup"><span data-stu-id="1a985-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="1a985-177">AppDomainMemSurvived 事件</span><span class="sxs-lookup"><span data-stu-id="1a985-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="1a985-178">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="1a985-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="1a985-179">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="1a985-179">Keyword for raising the event</span></span>|<span data-ttu-id="1a985-180">级别</span><span class="sxs-lookup"><span data-stu-id="1a985-180">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="1a985-181">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="1a985-181">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="1a985-182">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="1a985-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="1a985-183">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="1a985-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="1a985-184">Event</span><span class="sxs-lookup"><span data-stu-id="1a985-184">Event</span></span>|<span data-ttu-id="1a985-185">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1a985-185">Event ID</span></span>|<span data-ttu-id="1a985-186">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="1a985-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="1a985-187">84</span><span class="sxs-lookup"><span data-stu-id="1a985-187">84</span></span>|<span data-ttu-id="1a985-188">每个垃圾回收已结束。</span><span class="sxs-lookup"><span data-stu-id="1a985-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="1a985-189">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="1a985-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="1a985-190">字段名</span><span class="sxs-lookup"><span data-stu-id="1a985-190">Field name</span></span>|<span data-ttu-id="1a985-191">数据类型</span><span class="sxs-lookup"><span data-stu-id="1a985-191">Data type</span></span>|<span data-ttu-id="1a985-192">描述</span><span class="sxs-lookup"><span data-stu-id="1a985-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="1a985-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="1a985-193">AppDomainID</span></span>|<span data-ttu-id="1a985-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1a985-194">win:UInt64</span></span>|<span data-ttu-id="1a985-195">正在报告其资源使用情况的域的标识符。</span><span class="sxs-lookup"><span data-stu-id="1a985-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="1a985-196">已保留</span><span class="sxs-lookup"><span data-stu-id="1a985-196">Survived</span></span>|<span data-ttu-id="1a985-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1a985-197">win:UInt64</span></span>|<span data-ttu-id="1a985-198">上次回收后保留下来的、已知由此应用程序域保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="1a985-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="1a985-199">此数字在完整回收之后准确且完整，但在暂时的回收之后可能不完整。</span><span class="sxs-lookup"><span data-stu-id="1a985-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="1a985-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="1a985-200">ProcessSurvived</span></span>|<span data-ttu-id="1a985-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1a985-201">win:UInt64</span></span>|<span data-ttu-id="1a985-202">从上一次回收中保留的总字节数。</span><span class="sxs-lookup"><span data-stu-id="1a985-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="1a985-203">完整回收之后，该数字表示托管堆中实时保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="1a985-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="1a985-204">暂时回收之后，该数字表示暂时生成中实时保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="1a985-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="1a985-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1a985-205">ClrInstanceID</span></span>|<span data-ttu-id="1a985-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1a985-206">win:UInt16</span></span>|<span data-ttu-id="1a985-207">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="1a985-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="1a985-208">返回页首</span><span class="sxs-lookup"><span data-stu-id="1a985-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="1a985-209">ThreadAppDomainEnter 事件</span><span class="sxs-lookup"><span data-stu-id="1a985-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="1a985-210">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="1a985-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="1a985-211">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="1a985-211">Keyword for raising the event</span></span>|<span data-ttu-id="1a985-212">级别</span><span class="sxs-lookup"><span data-stu-id="1a985-212">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="1a985-213">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="1a985-213">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="1a985-214">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="1a985-214">Informational(4)</span></span>|  
|<span data-ttu-id="1a985-215">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="1a985-215">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="1a985-216">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="1a985-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="1a985-217">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="1a985-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="1a985-218">Event</span><span class="sxs-lookup"><span data-stu-id="1a985-218">Event</span></span>|<span data-ttu-id="1a985-219">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1a985-219">Event ID</span></span>|<span data-ttu-id="1a985-220">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="1a985-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="1a985-221">87</span><span class="sxs-lookup"><span data-stu-id="1a985-221">87</span></span>|<span data-ttu-id="1a985-222">线程进入应用程序域。</span><span class="sxs-lookup"><span data-stu-id="1a985-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="1a985-223">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="1a985-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="1a985-224">字段名</span><span class="sxs-lookup"><span data-stu-id="1a985-224">Field name</span></span>|<span data-ttu-id="1a985-225">数据类型</span><span class="sxs-lookup"><span data-stu-id="1a985-225">Data type</span></span>|<span data-ttu-id="1a985-226">描述</span><span class="sxs-lookup"><span data-stu-id="1a985-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="1a985-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="1a985-227">ThreadID</span></span>|<span data-ttu-id="1a985-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1a985-228">win:UInt64</span></span>|<span data-ttu-id="1a985-229">线程标识符。</span><span class="sxs-lookup"><span data-stu-id="1a985-229">The thread identifier.</span></span>|  
|<span data-ttu-id="1a985-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="1a985-230">AppDomainID</span></span>|<span data-ttu-id="1a985-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1a985-231">win:UInt64</span></span>|<span data-ttu-id="1a985-232">应用程序域标识符。</span><span class="sxs-lookup"><span data-stu-id="1a985-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="1a985-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1a985-233">ClrInstanceID</span></span>|<span data-ttu-id="1a985-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1a985-234">win:UInt16</span></span>|<span data-ttu-id="1a985-235">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="1a985-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="1a985-236">返回页首</span><span class="sxs-lookup"><span data-stu-id="1a985-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="1a985-237">ThreadTerminated 事件</span><span class="sxs-lookup"><span data-stu-id="1a985-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="1a985-238">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="1a985-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="1a985-239">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="1a985-239">Keyword for raising the event</span></span>|<span data-ttu-id="1a985-240">级别</span><span class="sxs-lookup"><span data-stu-id="1a985-240">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="1a985-241">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="1a985-241">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="1a985-242">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="1a985-242">Informational(4)</span></span>|  
|<span data-ttu-id="1a985-243">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="1a985-243">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="1a985-244">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="1a985-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="1a985-245">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="1a985-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="1a985-246">Event</span><span class="sxs-lookup"><span data-stu-id="1a985-246">Event</span></span>|<span data-ttu-id="1a985-247">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1a985-247">Event ID</span></span>|<span data-ttu-id="1a985-248">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="1a985-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="1a985-249">86</span><span class="sxs-lookup"><span data-stu-id="1a985-249">86</span></span>|<span data-ttu-id="1a985-250">线程终止。</span><span class="sxs-lookup"><span data-stu-id="1a985-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="1a985-251">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="1a985-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="1a985-252">字段名</span><span class="sxs-lookup"><span data-stu-id="1a985-252">Field name</span></span>|<span data-ttu-id="1a985-253">数据类型</span><span class="sxs-lookup"><span data-stu-id="1a985-253">Data type</span></span>|<span data-ttu-id="1a985-254">描述</span><span class="sxs-lookup"><span data-stu-id="1a985-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="1a985-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="1a985-255">ThreadID</span></span>|<span data-ttu-id="1a985-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1a985-256">win:UInt64</span></span>|<span data-ttu-id="1a985-257">线程标识符。</span><span class="sxs-lookup"><span data-stu-id="1a985-257">The thread identifier.</span></span>|  
|<span data-ttu-id="1a985-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="1a985-258">AppDomainID</span></span>|<span data-ttu-id="1a985-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1a985-259">win:UInt64</span></span>|<span data-ttu-id="1a985-260">应用程序域标识符。</span><span class="sxs-lookup"><span data-stu-id="1a985-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="1a985-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1a985-261">ClrInstanceID</span></span>|<span data-ttu-id="1a985-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1a985-262">win:UInt16</span></span>|<span data-ttu-id="1a985-263">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="1a985-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1a985-264">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a985-264">See also</span></span>
- [<span data-ttu-id="1a985-265">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="1a985-265">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
