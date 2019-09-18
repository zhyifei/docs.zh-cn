---
title: 应用程序域资源监视 (ARM) ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0e4002ae248022a9e4380c79174109494b5e4ca
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046772"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="eaa09-102">应用程序域资源监视 (ARM) ETW 事件</span><span class="sxs-lookup"><span data-stu-id="eaa09-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="eaa09-103">这些事件提供有关应用程序域的状态的详细诊断信息。</span><span class="sxs-lookup"><span data-stu-id="eaa09-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="eaa09-104">你可以使用这些事件，或使用应用程序域资源监视 (ARM) 功能来获取相同的信息。</span><span class="sxs-lookup"><span data-stu-id="eaa09-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="eaa09-105">此类别包含以下事件：</span><span class="sxs-lookup"><span data-stu-id="eaa09-105">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="eaa09-106">ThreadCreated 事件</span><span class="sxs-lookup"><span data-stu-id="eaa09-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
- [<span data-ttu-id="eaa09-107">AppDomainMemAllocated 事件</span><span class="sxs-lookup"><span data-stu-id="eaa09-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
- [<span data-ttu-id="eaa09-108">AppDomainMemSurvived 事件</span><span class="sxs-lookup"><span data-stu-id="eaa09-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
- [<span data-ttu-id="eaa09-109">ThreadAppDomainEnter 事件</span><span class="sxs-lookup"><span data-stu-id="eaa09-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
- [<span data-ttu-id="eaa09-110">ThreadTerminated 事件</span><span class="sxs-lookup"><span data-stu-id="eaa09-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="eaa09-111">ThreadCreated 事件</span><span class="sxs-lookup"><span data-stu-id="eaa09-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="eaa09-112">在断开的提供程序下此事件也会作为 `ThreadDC` 引发（在 `AppDomainResourceManagementRundownKeyword` 关键字下）。</span><span class="sxs-lookup"><span data-stu-id="eaa09-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="eaa09-113">这是此类别的断开提供程序下引发的唯一事件。</span><span class="sxs-lookup"><span data-stu-id="eaa09-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="eaa09-114">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="eaa09-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="eaa09-115">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="eaa09-115">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="eaa09-116">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="eaa09-116">Keyword for raising the event</span></span>|<span data-ttu-id="eaa09-117">Level</span><span class="sxs-lookup"><span data-stu-id="eaa09-117">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="eaa09-118">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="eaa09-118">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="eaa09-119">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="eaa09-119">Informational(4)</span></span>|  
|<span data-ttu-id="eaa09-120">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="eaa09-120">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="eaa09-121">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="eaa09-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="eaa09-122">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="eaa09-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="eaa09-123">Event</span><span class="sxs-lookup"><span data-stu-id="eaa09-123">Event</span></span>|<span data-ttu-id="eaa09-124">事件 ID</span><span class="sxs-lookup"><span data-stu-id="eaa09-124">Event ID</span></span>|<span data-ttu-id="eaa09-125">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="eaa09-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="eaa09-126">85</span><span class="sxs-lookup"><span data-stu-id="eaa09-126">85</span></span>|<span data-ttu-id="eaa09-127">已为应用程序域创建了一个线程。</span><span class="sxs-lookup"><span data-stu-id="eaa09-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="eaa09-128">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="eaa09-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="eaa09-129">字段名</span><span class="sxs-lookup"><span data-stu-id="eaa09-129">Field name</span></span>|<span data-ttu-id="eaa09-130">数据类型</span><span class="sxs-lookup"><span data-stu-id="eaa09-130">Data type</span></span>|<span data-ttu-id="eaa09-131">描述</span><span class="sxs-lookup"><span data-stu-id="eaa09-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="eaa09-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="eaa09-132">ThreadID</span></span>|<span data-ttu-id="eaa09-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="eaa09-133">win:UInt64</span></span>|<span data-ttu-id="eaa09-134">已创建的线程 ID。</span><span class="sxs-lookup"><span data-stu-id="eaa09-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="eaa09-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="eaa09-135">AppDomainID</span></span>|<span data-ttu-id="eaa09-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="eaa09-136">win:UInt64</span></span>|<span data-ttu-id="eaa09-137">正在报告其线程活动的应用程序域的标识符。</span><span class="sxs-lookup"><span data-stu-id="eaa09-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="eaa09-138">标志</span><span class="sxs-lookup"><span data-stu-id="eaa09-138">Flags</span></span>|<span data-ttu-id="eaa09-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="eaa09-139">win:UInt32</span></span>|<span data-ttu-id="eaa09-140">线程创建标志。</span><span class="sxs-lookup"><span data-stu-id="eaa09-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="eaa09-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="eaa09-141">ManagedThreadIndex</span></span>|<span data-ttu-id="eaa09-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="eaa09-142">win:UInt32</span></span>|<span data-ttu-id="eaa09-143">已创建线程的托管索引。</span><span class="sxs-lookup"><span data-stu-id="eaa09-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="eaa09-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="eaa09-144">OSThreadID</span></span>|<span data-ttu-id="eaa09-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="eaa09-145">win:UInt32</span></span>|<span data-ttu-id="eaa09-146">已创建线程的操作系统 ID。</span><span class="sxs-lookup"><span data-stu-id="eaa09-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="eaa09-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="eaa09-147">ClrInstanceID</span></span>|<span data-ttu-id="eaa09-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="eaa09-148">win:UInt16</span></span>|<span data-ttu-id="eaa09-149">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="eaa09-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="eaa09-150">返回页首</span><span class="sxs-lookup"><span data-stu-id="eaa09-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="eaa09-151">AppDomainMemAllocated 事件</span><span class="sxs-lookup"><span data-stu-id="eaa09-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="eaa09-152">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="eaa09-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="eaa09-153">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="eaa09-153">Keyword for raising the event</span></span>|<span data-ttu-id="eaa09-154">Level</span><span class="sxs-lookup"><span data-stu-id="eaa09-154">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="eaa09-155">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="eaa09-155">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="eaa09-156">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="eaa09-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="eaa09-157">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="eaa09-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="eaa09-158">Event</span><span class="sxs-lookup"><span data-stu-id="eaa09-158">Event</span></span>|<span data-ttu-id="eaa09-159">事件 ID</span><span class="sxs-lookup"><span data-stu-id="eaa09-159">Event ID</span></span>|<span data-ttu-id="eaa09-160">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="eaa09-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="eaa09-161">83</span><span class="sxs-lookup"><span data-stu-id="eaa09-161">83</span></span>|<span data-ttu-id="eaa09-162">应用程序域中分配每 4 MB 的内存（大约）。</span><span class="sxs-lookup"><span data-stu-id="eaa09-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="eaa09-163">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="eaa09-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="eaa09-164">字段名</span><span class="sxs-lookup"><span data-stu-id="eaa09-164">Field name</span></span>|<span data-ttu-id="eaa09-165">数据类型</span><span class="sxs-lookup"><span data-stu-id="eaa09-165">Data type</span></span>|<span data-ttu-id="eaa09-166">描述</span><span class="sxs-lookup"><span data-stu-id="eaa09-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="eaa09-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="eaa09-167">AppDomainID</span></span>|<span data-ttu-id="eaa09-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="eaa09-168">win:UInt64</span></span>|<span data-ttu-id="eaa09-169">正在报告其资源使用情况的应用程序域的标识符。</span><span class="sxs-lookup"><span data-stu-id="eaa09-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="eaa09-170">已分配</span><span class="sxs-lookup"><span data-stu-id="eaa09-170">Allocated</span></span>|<span data-ttu-id="eaa09-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="eaa09-171">win:UInt64</span></span>|<span data-ttu-id="eaa09-172">自应用程序域创建以来在此应用程序域中分配的字节总数（不减去已释放的内存量）。</span><span class="sxs-lookup"><span data-stu-id="eaa09-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="eaa09-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="eaa09-173">ClrInstanceID</span></span>|<span data-ttu-id="eaa09-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="eaa09-174">win:UInt16</span></span>|<span data-ttu-id="eaa09-175">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="eaa09-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="eaa09-176">返回页首</span><span class="sxs-lookup"><span data-stu-id="eaa09-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="eaa09-177">AppDomainMemSurvived 事件</span><span class="sxs-lookup"><span data-stu-id="eaa09-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="eaa09-178">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="eaa09-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="eaa09-179">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="eaa09-179">Keyword for raising the event</span></span>|<span data-ttu-id="eaa09-180">Level</span><span class="sxs-lookup"><span data-stu-id="eaa09-180">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="eaa09-181">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="eaa09-181">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="eaa09-182">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="eaa09-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="eaa09-183">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="eaa09-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="eaa09-184">Event</span><span class="sxs-lookup"><span data-stu-id="eaa09-184">Event</span></span>|<span data-ttu-id="eaa09-185">事件 ID</span><span class="sxs-lookup"><span data-stu-id="eaa09-185">Event ID</span></span>|<span data-ttu-id="eaa09-186">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="eaa09-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="eaa09-187">84</span><span class="sxs-lookup"><span data-stu-id="eaa09-187">84</span></span>|<span data-ttu-id="eaa09-188">每个垃圾回收已结束。</span><span class="sxs-lookup"><span data-stu-id="eaa09-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="eaa09-189">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="eaa09-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="eaa09-190">字段名</span><span class="sxs-lookup"><span data-stu-id="eaa09-190">Field name</span></span>|<span data-ttu-id="eaa09-191">数据类型</span><span class="sxs-lookup"><span data-stu-id="eaa09-191">Data type</span></span>|<span data-ttu-id="eaa09-192">描述</span><span class="sxs-lookup"><span data-stu-id="eaa09-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="eaa09-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="eaa09-193">AppDomainID</span></span>|<span data-ttu-id="eaa09-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="eaa09-194">win:UInt64</span></span>|<span data-ttu-id="eaa09-195">正在报告其资源使用情况的域的标识符。</span><span class="sxs-lookup"><span data-stu-id="eaa09-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="eaa09-196">已保留</span><span class="sxs-lookup"><span data-stu-id="eaa09-196">Survived</span></span>|<span data-ttu-id="eaa09-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="eaa09-197">win:UInt64</span></span>|<span data-ttu-id="eaa09-198">上次回收后保留下来的、已知由此应用程序域保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="eaa09-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="eaa09-199">此数字在完整回收之后准确且完整，但在暂时的回收之后可能不完整。</span><span class="sxs-lookup"><span data-stu-id="eaa09-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="eaa09-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="eaa09-200">ProcessSurvived</span></span>|<span data-ttu-id="eaa09-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="eaa09-201">win:UInt64</span></span>|<span data-ttu-id="eaa09-202">从上一次回收中保留的总字节数。</span><span class="sxs-lookup"><span data-stu-id="eaa09-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="eaa09-203">完整回收之后，该数字表示托管堆中实时保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="eaa09-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="eaa09-204">暂时回收之后，该数字表示暂时生成中实时保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="eaa09-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="eaa09-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="eaa09-205">ClrInstanceID</span></span>|<span data-ttu-id="eaa09-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="eaa09-206">win:UInt16</span></span>|<span data-ttu-id="eaa09-207">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="eaa09-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="eaa09-208">返回页首</span><span class="sxs-lookup"><span data-stu-id="eaa09-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="eaa09-209">ThreadAppDomainEnter 事件</span><span class="sxs-lookup"><span data-stu-id="eaa09-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="eaa09-210">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="eaa09-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="eaa09-211">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="eaa09-211">Keyword for raising the event</span></span>|<span data-ttu-id="eaa09-212">Level</span><span class="sxs-lookup"><span data-stu-id="eaa09-212">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="eaa09-213">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="eaa09-213">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="eaa09-214">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="eaa09-214">Informational(4)</span></span>|  
|<span data-ttu-id="eaa09-215">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="eaa09-215">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="eaa09-216">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="eaa09-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="eaa09-217">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="eaa09-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="eaa09-218">Event</span><span class="sxs-lookup"><span data-stu-id="eaa09-218">Event</span></span>|<span data-ttu-id="eaa09-219">事件 ID</span><span class="sxs-lookup"><span data-stu-id="eaa09-219">Event ID</span></span>|<span data-ttu-id="eaa09-220">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="eaa09-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="eaa09-221">87</span><span class="sxs-lookup"><span data-stu-id="eaa09-221">87</span></span>|<span data-ttu-id="eaa09-222">线程进入应用程序域。</span><span class="sxs-lookup"><span data-stu-id="eaa09-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="eaa09-223">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="eaa09-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="eaa09-224">字段名</span><span class="sxs-lookup"><span data-stu-id="eaa09-224">Field name</span></span>|<span data-ttu-id="eaa09-225">数据类型</span><span class="sxs-lookup"><span data-stu-id="eaa09-225">Data type</span></span>|<span data-ttu-id="eaa09-226">描述</span><span class="sxs-lookup"><span data-stu-id="eaa09-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="eaa09-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="eaa09-227">ThreadID</span></span>|<span data-ttu-id="eaa09-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="eaa09-228">win:UInt64</span></span>|<span data-ttu-id="eaa09-229">线程标识符。</span><span class="sxs-lookup"><span data-stu-id="eaa09-229">The thread identifier.</span></span>|  
|<span data-ttu-id="eaa09-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="eaa09-230">AppDomainID</span></span>|<span data-ttu-id="eaa09-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="eaa09-231">win:UInt64</span></span>|<span data-ttu-id="eaa09-232">应用程序域标识符。</span><span class="sxs-lookup"><span data-stu-id="eaa09-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="eaa09-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="eaa09-233">ClrInstanceID</span></span>|<span data-ttu-id="eaa09-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="eaa09-234">win:UInt16</span></span>|<span data-ttu-id="eaa09-235">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="eaa09-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="eaa09-236">返回页首</span><span class="sxs-lookup"><span data-stu-id="eaa09-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="eaa09-237">ThreadTerminated 事件</span><span class="sxs-lookup"><span data-stu-id="eaa09-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="eaa09-238">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="eaa09-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="eaa09-239">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="eaa09-239">Keyword for raising the event</span></span>|<span data-ttu-id="eaa09-240">Level</span><span class="sxs-lookup"><span data-stu-id="eaa09-240">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="eaa09-241">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="eaa09-241">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="eaa09-242">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="eaa09-242">Informational(4)</span></span>|  
|<span data-ttu-id="eaa09-243">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="eaa09-243">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="eaa09-244">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="eaa09-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="eaa09-245">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="eaa09-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="eaa09-246">Event</span><span class="sxs-lookup"><span data-stu-id="eaa09-246">Event</span></span>|<span data-ttu-id="eaa09-247">事件 ID</span><span class="sxs-lookup"><span data-stu-id="eaa09-247">Event ID</span></span>|<span data-ttu-id="eaa09-248">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="eaa09-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="eaa09-249">86</span><span class="sxs-lookup"><span data-stu-id="eaa09-249">86</span></span>|<span data-ttu-id="eaa09-250">线程终止。</span><span class="sxs-lookup"><span data-stu-id="eaa09-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="eaa09-251">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="eaa09-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="eaa09-252">字段名</span><span class="sxs-lookup"><span data-stu-id="eaa09-252">Field name</span></span>|<span data-ttu-id="eaa09-253">数据类型</span><span class="sxs-lookup"><span data-stu-id="eaa09-253">Data type</span></span>|<span data-ttu-id="eaa09-254">描述</span><span class="sxs-lookup"><span data-stu-id="eaa09-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="eaa09-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="eaa09-255">ThreadID</span></span>|<span data-ttu-id="eaa09-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="eaa09-256">win:UInt64</span></span>|<span data-ttu-id="eaa09-257">线程标识符。</span><span class="sxs-lookup"><span data-stu-id="eaa09-257">The thread identifier.</span></span>|  
|<span data-ttu-id="eaa09-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="eaa09-258">AppDomainID</span></span>|<span data-ttu-id="eaa09-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="eaa09-259">win:UInt64</span></span>|<span data-ttu-id="eaa09-260">应用程序域标识符。</span><span class="sxs-lookup"><span data-stu-id="eaa09-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="eaa09-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="eaa09-261">ClrInstanceID</span></span>|<span data-ttu-id="eaa09-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="eaa09-262">win:UInt16</span></span>|<span data-ttu-id="eaa09-263">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="eaa09-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eaa09-264">请参阅</span><span class="sxs-lookup"><span data-stu-id="eaa09-264">See also</span></span>

- [<span data-ttu-id="eaa09-265">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="eaa09-265">CLR ETW Events</span></span>](clr-etw-events.md)
