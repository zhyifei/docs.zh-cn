---
title: "应用程序域资源监视 (ARM) ETW 事件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
caps.latest.revision: 8
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a93e8cc1ab0b7488f920b556d2073d2813c3b7a9
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="a49fd-102">应用程序域资源监视 (ARM) ETW 事件</span><span class="sxs-lookup"><span data-stu-id="a49fd-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<span data-ttu-id="a49fd-103"><a name="top"></a> 这些事件提供有关应用程序域的状态的详细诊断信息。</span><span class="sxs-lookup"><span data-stu-id="a49fd-103"><a name="top"></a> These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="a49fd-104">你可以使用这些事件，或使用应用程序域资源监视 (ARM) 功能来获取相同的信息。</span><span class="sxs-lookup"><span data-stu-id="a49fd-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="a49fd-105">此类别包含以下事件：</span><span class="sxs-lookup"><span data-stu-id="a49fd-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="a49fd-106">ThreadCreated 事件</span><span class="sxs-lookup"><span data-stu-id="a49fd-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
-   [<span data-ttu-id="a49fd-107">AppDomainMemAllocated 事件</span><span class="sxs-lookup"><span data-stu-id="a49fd-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
-   [<span data-ttu-id="a49fd-108">AppDomainMemSurvived 事件</span><span class="sxs-lookup"><span data-stu-id="a49fd-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
-   [<span data-ttu-id="a49fd-109">ThreadAppDomainEnter 事件</span><span class="sxs-lookup"><span data-stu-id="a49fd-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
-   [<span data-ttu-id="a49fd-110">ThreadTerminated 事件</span><span class="sxs-lookup"><span data-stu-id="a49fd-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="a49fd-111">ThreadCreated 事件</span><span class="sxs-lookup"><span data-stu-id="a49fd-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="a49fd-112">在断开的提供程序下此事件也会作为 `ThreadDC` 引发（在 `AppDomainResourceManagementRundownKeyword` 关键字下）。</span><span class="sxs-lookup"><span data-stu-id="a49fd-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="a49fd-113">这是此类别的断开提供程序下引发的唯一事件。</span><span class="sxs-lookup"><span data-stu-id="a49fd-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="a49fd-114">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a49fd-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="a49fd-115">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="a49fd-115">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="a49fd-116">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a49fd-116">Keyword for raising the event</span></span>|<span data-ttu-id="a49fd-117">级别</span><span class="sxs-lookup"><span data-stu-id="a49fd-117">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a49fd-118">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="a49fd-118">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="a49fd-119">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a49fd-119">Informational(4)</span></span>|  
|<span data-ttu-id="a49fd-120">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="a49fd-120">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a49fd-121">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a49fd-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="a49fd-122">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a49fd-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a49fd-123">Event</span><span class="sxs-lookup"><span data-stu-id="a49fd-123">Event</span></span>|<span data-ttu-id="a49fd-124">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a49fd-124">Event ID</span></span>|<span data-ttu-id="a49fd-125">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a49fd-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="a49fd-126">85</span><span class="sxs-lookup"><span data-stu-id="a49fd-126">85</span></span>|<span data-ttu-id="a49fd-127">已为应用程序域创建了一个线程。</span><span class="sxs-lookup"><span data-stu-id="a49fd-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="a49fd-128">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="a49fd-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a49fd-129">字段名</span><span class="sxs-lookup"><span data-stu-id="a49fd-129">Field name</span></span>|<span data-ttu-id="a49fd-130">数据类型</span><span class="sxs-lookup"><span data-stu-id="a49fd-130">Data type</span></span>|<span data-ttu-id="a49fd-131">说明</span><span class="sxs-lookup"><span data-stu-id="a49fd-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a49fd-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="a49fd-132">ThreadID</span></span>|<span data-ttu-id="a49fd-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a49fd-133">win:UInt64</span></span>|<span data-ttu-id="a49fd-134">已创建的线程 ID。</span><span class="sxs-lookup"><span data-stu-id="a49fd-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="a49fd-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="a49fd-135">AppDomainID</span></span>|<span data-ttu-id="a49fd-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a49fd-136">win:UInt64</span></span>|<span data-ttu-id="a49fd-137">正在报告其线程活动的应用程序域的标识符。</span><span class="sxs-lookup"><span data-stu-id="a49fd-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="a49fd-138">标志</span><span class="sxs-lookup"><span data-stu-id="a49fd-138">Flags</span></span>|<span data-ttu-id="a49fd-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a49fd-139">win:UInt32</span></span>|<span data-ttu-id="a49fd-140">线程创建标志。</span><span class="sxs-lookup"><span data-stu-id="a49fd-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="a49fd-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="a49fd-141">ManagedThreadIndex</span></span>|<span data-ttu-id="a49fd-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a49fd-142">win:UInt32</span></span>|<span data-ttu-id="a49fd-143">已创建线程的托管索引。</span><span class="sxs-lookup"><span data-stu-id="a49fd-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="a49fd-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="a49fd-144">OSThreadID</span></span>|<span data-ttu-id="a49fd-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a49fd-145">win:UInt32</span></span>|<span data-ttu-id="a49fd-146">已创建线程的操作系统 ID。</span><span class="sxs-lookup"><span data-stu-id="a49fd-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="a49fd-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a49fd-147">ClrInstanceID</span></span>|<span data-ttu-id="a49fd-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a49fd-148">win:UInt16</span></span>|<span data-ttu-id="a49fd-149">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a49fd-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a49fd-150">返回页首</span><span class="sxs-lookup"><span data-stu-id="a49fd-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="a49fd-151">AppDomainMemAllocated 事件</span><span class="sxs-lookup"><span data-stu-id="a49fd-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="a49fd-152">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a49fd-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a49fd-153">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a49fd-153">Keyword for raising the event</span></span>|<span data-ttu-id="a49fd-154">级别</span><span class="sxs-lookup"><span data-stu-id="a49fd-154">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a49fd-155">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="a49fd-155">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="a49fd-156">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a49fd-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="a49fd-157">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a49fd-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a49fd-158">Event</span><span class="sxs-lookup"><span data-stu-id="a49fd-158">Event</span></span>|<span data-ttu-id="a49fd-159">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a49fd-159">Event ID</span></span>|<span data-ttu-id="a49fd-160">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a49fd-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="a49fd-161">83</span><span class="sxs-lookup"><span data-stu-id="a49fd-161">83</span></span>|<span data-ttu-id="a49fd-162">应用程序域中分配每 4 MB 的内存（大约）。</span><span class="sxs-lookup"><span data-stu-id="a49fd-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="a49fd-163">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="a49fd-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a49fd-164">字段名</span><span class="sxs-lookup"><span data-stu-id="a49fd-164">Field name</span></span>|<span data-ttu-id="a49fd-165">数据类型</span><span class="sxs-lookup"><span data-stu-id="a49fd-165">Data type</span></span>|<span data-ttu-id="a49fd-166">说明</span><span class="sxs-lookup"><span data-stu-id="a49fd-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a49fd-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="a49fd-167">AppDomainID</span></span>|<span data-ttu-id="a49fd-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a49fd-168">win:UInt64</span></span>|<span data-ttu-id="a49fd-169">正在报告其资源使用情况的应用程序域的标识符。</span><span class="sxs-lookup"><span data-stu-id="a49fd-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="a49fd-170">已分配</span><span class="sxs-lookup"><span data-stu-id="a49fd-170">Allocated</span></span>|<span data-ttu-id="a49fd-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a49fd-171">win:UInt64</span></span>|<span data-ttu-id="a49fd-172">自应用程序域创建以来在此应用程序域中分配的字节总数（不减去已释放的内存量）。</span><span class="sxs-lookup"><span data-stu-id="a49fd-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="a49fd-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a49fd-173">ClrInstanceID</span></span>|<span data-ttu-id="a49fd-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a49fd-174">win:UInt16</span></span>|<span data-ttu-id="a49fd-175">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a49fd-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a49fd-176">返回页首</span><span class="sxs-lookup"><span data-stu-id="a49fd-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="a49fd-177">AppDomainMemSurvived 事件</span><span class="sxs-lookup"><span data-stu-id="a49fd-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="a49fd-178">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a49fd-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a49fd-179">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a49fd-179">Keyword for raising the event</span></span>|<span data-ttu-id="a49fd-180">级别</span><span class="sxs-lookup"><span data-stu-id="a49fd-180">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a49fd-181">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="a49fd-181">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="a49fd-182">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a49fd-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="a49fd-183">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a49fd-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a49fd-184">Event</span><span class="sxs-lookup"><span data-stu-id="a49fd-184">Event</span></span>|<span data-ttu-id="a49fd-185">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a49fd-185">Event ID</span></span>|<span data-ttu-id="a49fd-186">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a49fd-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="a49fd-187">84</span><span class="sxs-lookup"><span data-stu-id="a49fd-187">84</span></span>|<span data-ttu-id="a49fd-188">每个垃圾回收已结束。</span><span class="sxs-lookup"><span data-stu-id="a49fd-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="a49fd-189">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="a49fd-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a49fd-190">字段名</span><span class="sxs-lookup"><span data-stu-id="a49fd-190">Field name</span></span>|<span data-ttu-id="a49fd-191">数据类型</span><span class="sxs-lookup"><span data-stu-id="a49fd-191">Data type</span></span>|<span data-ttu-id="a49fd-192">说明</span><span class="sxs-lookup"><span data-stu-id="a49fd-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a49fd-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="a49fd-193">AppDomainID</span></span>|<span data-ttu-id="a49fd-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a49fd-194">win:UInt64</span></span>|<span data-ttu-id="a49fd-195">正在报告其资源使用情况的域的标识符。</span><span class="sxs-lookup"><span data-stu-id="a49fd-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="a49fd-196">已保留</span><span class="sxs-lookup"><span data-stu-id="a49fd-196">Survived</span></span>|<span data-ttu-id="a49fd-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a49fd-197">win:UInt64</span></span>|<span data-ttu-id="a49fd-198">上次回收后保留下来的、已知由此应用程序域保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="a49fd-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="a49fd-199">此数字在完整回收之后准确且完整，但在暂时的回收之后可能不完整。</span><span class="sxs-lookup"><span data-stu-id="a49fd-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="a49fd-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="a49fd-200">ProcessSurvived</span></span>|<span data-ttu-id="a49fd-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a49fd-201">win:UInt64</span></span>|<span data-ttu-id="a49fd-202">从上一次回收中保留的总字节数。</span><span class="sxs-lookup"><span data-stu-id="a49fd-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="a49fd-203">完整回收之后，该数字表示托管堆中实时保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="a49fd-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="a49fd-204">暂时回收之后，该数字表示暂时生成中实时保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="a49fd-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="a49fd-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a49fd-205">ClrInstanceID</span></span>|<span data-ttu-id="a49fd-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a49fd-206">win:UInt16</span></span>|<span data-ttu-id="a49fd-207">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a49fd-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a49fd-208">返回页首</span><span class="sxs-lookup"><span data-stu-id="a49fd-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="a49fd-209">ThreadAppDomainEnter 事件</span><span class="sxs-lookup"><span data-stu-id="a49fd-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="a49fd-210">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a49fd-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a49fd-211">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a49fd-211">Keyword for raising the event</span></span>|<span data-ttu-id="a49fd-212">级别</span><span class="sxs-lookup"><span data-stu-id="a49fd-212">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a49fd-213">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="a49fd-213">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="a49fd-214">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a49fd-214">Informational(4)</span></span>|  
|<span data-ttu-id="a49fd-215">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="a49fd-215">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a49fd-216">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a49fd-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="a49fd-217">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a49fd-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a49fd-218">Event</span><span class="sxs-lookup"><span data-stu-id="a49fd-218">Event</span></span>|<span data-ttu-id="a49fd-219">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a49fd-219">Event ID</span></span>|<span data-ttu-id="a49fd-220">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a49fd-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="a49fd-221">87</span><span class="sxs-lookup"><span data-stu-id="a49fd-221">87</span></span>|<span data-ttu-id="a49fd-222">线程进入应用程序域。</span><span class="sxs-lookup"><span data-stu-id="a49fd-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="a49fd-223">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="a49fd-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a49fd-224">字段名</span><span class="sxs-lookup"><span data-stu-id="a49fd-224">Field name</span></span>|<span data-ttu-id="a49fd-225">数据类型</span><span class="sxs-lookup"><span data-stu-id="a49fd-225">Data type</span></span>|<span data-ttu-id="a49fd-226">说明</span><span class="sxs-lookup"><span data-stu-id="a49fd-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a49fd-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="a49fd-227">ThreadID</span></span>|<span data-ttu-id="a49fd-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a49fd-228">win:UInt64</span></span>|<span data-ttu-id="a49fd-229">线程标识符。</span><span class="sxs-lookup"><span data-stu-id="a49fd-229">The thread identifier.</span></span>|  
|<span data-ttu-id="a49fd-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="a49fd-230">AppDomainID</span></span>|<span data-ttu-id="a49fd-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a49fd-231">win:UInt64</span></span>|<span data-ttu-id="a49fd-232">应用程序域标识符。</span><span class="sxs-lookup"><span data-stu-id="a49fd-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="a49fd-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a49fd-233">ClrInstanceID</span></span>|<span data-ttu-id="a49fd-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a49fd-234">win:UInt16</span></span>|<span data-ttu-id="a49fd-235">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a49fd-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a49fd-236">返回页首</span><span class="sxs-lookup"><span data-stu-id="a49fd-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="a49fd-237">ThreadTerminated 事件</span><span class="sxs-lookup"><span data-stu-id="a49fd-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="a49fd-238">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a49fd-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a49fd-239">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a49fd-239">Keyword for raising the event</span></span>|<span data-ttu-id="a49fd-240">级别</span><span class="sxs-lookup"><span data-stu-id="a49fd-240">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a49fd-241">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="a49fd-241">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="a49fd-242">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a49fd-242">Informational(4)</span></span>|  
|<span data-ttu-id="a49fd-243">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="a49fd-243">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a49fd-244">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a49fd-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="a49fd-245">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a49fd-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a49fd-246">Event</span><span class="sxs-lookup"><span data-stu-id="a49fd-246">Event</span></span>|<span data-ttu-id="a49fd-247">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a49fd-247">Event ID</span></span>|<span data-ttu-id="a49fd-248">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a49fd-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="a49fd-249">86</span><span class="sxs-lookup"><span data-stu-id="a49fd-249">86</span></span>|<span data-ttu-id="a49fd-250">线程终止。</span><span class="sxs-lookup"><span data-stu-id="a49fd-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="a49fd-251">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="a49fd-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="a49fd-252">字段名</span><span class="sxs-lookup"><span data-stu-id="a49fd-252">Field name</span></span>|<span data-ttu-id="a49fd-253">数据类型</span><span class="sxs-lookup"><span data-stu-id="a49fd-253">Data type</span></span>|<span data-ttu-id="a49fd-254">说明</span><span class="sxs-lookup"><span data-stu-id="a49fd-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a49fd-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="a49fd-255">ThreadID</span></span>|<span data-ttu-id="a49fd-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a49fd-256">win:UInt64</span></span>|<span data-ttu-id="a49fd-257">线程标识符。</span><span class="sxs-lookup"><span data-stu-id="a49fd-257">The thread identifier.</span></span>|  
|<span data-ttu-id="a49fd-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="a49fd-258">AppDomainID</span></span>|<span data-ttu-id="a49fd-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a49fd-259">win:UInt64</span></span>|<span data-ttu-id="a49fd-260">应用程序域标识符。</span><span class="sxs-lookup"><span data-stu-id="a49fd-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="a49fd-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a49fd-261">ClrInstanceID</span></span>|<span data-ttu-id="a49fd-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a49fd-262">win:UInt16</span></span>|<span data-ttu-id="a49fd-263">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a49fd-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a49fd-264">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a49fd-264">See Also</span></span>  
 [<span data-ttu-id="a49fd-265">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="a49fd-265">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)

