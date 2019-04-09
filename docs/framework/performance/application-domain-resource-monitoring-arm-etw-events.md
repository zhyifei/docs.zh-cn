---
title: 应用程序域资源监视 (ARM) ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2bb2b0dd95877fc6492f6d23a19c14688cd78f7c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133817"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="a9f19-102">应用程序域资源监视 (ARM) ETW 事件</span><span class="sxs-lookup"><span data-stu-id="a9f19-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="a9f19-103">这些事件提供有关应用程序域的状态的详细诊断信息。</span><span class="sxs-lookup"><span data-stu-id="a9f19-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="a9f19-104">你可以使用这些事件，或使用应用程序域资源监视 (ARM) 功能来获取相同的信息。</span><span class="sxs-lookup"><span data-stu-id="a9f19-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="a9f19-105">此类别包含以下事件：</span><span class="sxs-lookup"><span data-stu-id="a9f19-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="a9f19-106">ThreadCreated 事件</span><span class="sxs-lookup"><span data-stu-id="a9f19-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
-   [<span data-ttu-id="a9f19-107">AppDomainMemAllocated 事件</span><span class="sxs-lookup"><span data-stu-id="a9f19-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
-   [<span data-ttu-id="a9f19-108">AppDomainMemSurvived 事件</span><span class="sxs-lookup"><span data-stu-id="a9f19-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
-   [<span data-ttu-id="a9f19-109">ThreadAppDomainEnter 事件</span><span class="sxs-lookup"><span data-stu-id="a9f19-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
-   [<span data-ttu-id="a9f19-110">ThreadTerminated 事件</span><span class="sxs-lookup"><span data-stu-id="a9f19-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="a9f19-111">ThreadCreated 事件</span><span class="sxs-lookup"><span data-stu-id="a9f19-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="a9f19-112">在断开的提供程序下此事件也会作为 `ThreadDC` 引发（在 `AppDomainResourceManagementRundownKeyword` 关键字下）。</span><span class="sxs-lookup"><span data-stu-id="a9f19-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="a9f19-113">这是此类别的断开提供程序下引发的唯一事件。</span><span class="sxs-lookup"><span data-stu-id="a9f19-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="a9f19-114">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a9f19-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="a9f19-115">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="a9f19-115">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="a9f19-116">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a9f19-116">Keyword for raising the event</span></span>|<span data-ttu-id="a9f19-117">级别</span><span class="sxs-lookup"><span data-stu-id="a9f19-117">Level</span></span>|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` <span data-ttu-id="a9f19-118">(0x800)</span><span class="sxs-lookup"><span data-stu-id="a9f19-118">(0x800)</span></span>|<span data-ttu-id="a9f19-119">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a9f19-119">Informational(4)</span></span>|  
|`ThreadingKeyword` <span data-ttu-id="a9f19-120">(0x10000)</span><span class="sxs-lookup"><span data-stu-id="a9f19-120">(0x10000)</span></span>|<span data-ttu-id="a9f19-121">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a9f19-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="a9f19-122">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a9f19-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a9f19-123">Event</span><span class="sxs-lookup"><span data-stu-id="a9f19-123">Event</span></span>|<span data-ttu-id="a9f19-124">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a9f19-124">Event ID</span></span>|<span data-ttu-id="a9f19-125">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a9f19-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="a9f19-126">85</span><span class="sxs-lookup"><span data-stu-id="a9f19-126">85</span></span>|<span data-ttu-id="a9f19-127">已为应用程序域创建了一个线程。</span><span class="sxs-lookup"><span data-stu-id="a9f19-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="a9f19-128">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="a9f19-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a9f19-129">字段名</span><span class="sxs-lookup"><span data-stu-id="a9f19-129">Field name</span></span>|<span data-ttu-id="a9f19-130">数据类型</span><span class="sxs-lookup"><span data-stu-id="a9f19-130">Data type</span></span>|<span data-ttu-id="a9f19-131">描述</span><span class="sxs-lookup"><span data-stu-id="a9f19-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a9f19-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="a9f19-132">ThreadID</span></span>|<span data-ttu-id="a9f19-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a9f19-133">win:UInt64</span></span>|<span data-ttu-id="a9f19-134">已创建的线程 ID。</span><span class="sxs-lookup"><span data-stu-id="a9f19-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="a9f19-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="a9f19-135">AppDomainID</span></span>|<span data-ttu-id="a9f19-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a9f19-136">win:UInt64</span></span>|<span data-ttu-id="a9f19-137">正在报告其线程活动的应用程序域的标识符。</span><span class="sxs-lookup"><span data-stu-id="a9f19-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="a9f19-138">标志</span><span class="sxs-lookup"><span data-stu-id="a9f19-138">Flags</span></span>|<span data-ttu-id="a9f19-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a9f19-139">win:UInt32</span></span>|<span data-ttu-id="a9f19-140">线程创建标志。</span><span class="sxs-lookup"><span data-stu-id="a9f19-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="a9f19-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="a9f19-141">ManagedThreadIndex</span></span>|<span data-ttu-id="a9f19-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a9f19-142">win:UInt32</span></span>|<span data-ttu-id="a9f19-143">已创建线程的托管索引。</span><span class="sxs-lookup"><span data-stu-id="a9f19-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="a9f19-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="a9f19-144">OSThreadID</span></span>|<span data-ttu-id="a9f19-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a9f19-145">win:UInt32</span></span>|<span data-ttu-id="a9f19-146">已创建线程的操作系统 ID。</span><span class="sxs-lookup"><span data-stu-id="a9f19-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="a9f19-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a9f19-147">ClrInstanceID</span></span>|<span data-ttu-id="a9f19-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a9f19-148">win:UInt16</span></span>|<span data-ttu-id="a9f19-149">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a9f19-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a9f19-150">返回页首</span><span class="sxs-lookup"><span data-stu-id="a9f19-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="a9f19-151">AppDomainMemAllocated 事件</span><span class="sxs-lookup"><span data-stu-id="a9f19-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="a9f19-152">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a9f19-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a9f19-153">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a9f19-153">Keyword for raising the event</span></span>|<span data-ttu-id="a9f19-154">级别</span><span class="sxs-lookup"><span data-stu-id="a9f19-154">Level</span></span>|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` <span data-ttu-id="a9f19-155">(0x800)</span><span class="sxs-lookup"><span data-stu-id="a9f19-155">(0x800)</span></span>|<span data-ttu-id="a9f19-156">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a9f19-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="a9f19-157">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a9f19-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a9f19-158">Event</span><span class="sxs-lookup"><span data-stu-id="a9f19-158">Event</span></span>|<span data-ttu-id="a9f19-159">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a9f19-159">Event ID</span></span>|<span data-ttu-id="a9f19-160">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a9f19-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="a9f19-161">83</span><span class="sxs-lookup"><span data-stu-id="a9f19-161">83</span></span>|<span data-ttu-id="a9f19-162">应用程序域中分配每 4 MB 的内存（大约）。</span><span class="sxs-lookup"><span data-stu-id="a9f19-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="a9f19-163">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="a9f19-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a9f19-164">字段名</span><span class="sxs-lookup"><span data-stu-id="a9f19-164">Field name</span></span>|<span data-ttu-id="a9f19-165">数据类型</span><span class="sxs-lookup"><span data-stu-id="a9f19-165">Data type</span></span>|<span data-ttu-id="a9f19-166">描述</span><span class="sxs-lookup"><span data-stu-id="a9f19-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a9f19-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="a9f19-167">AppDomainID</span></span>|<span data-ttu-id="a9f19-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a9f19-168">win:UInt64</span></span>|<span data-ttu-id="a9f19-169">正在报告其资源使用情况的应用程序域的标识符。</span><span class="sxs-lookup"><span data-stu-id="a9f19-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="a9f19-170">已分配</span><span class="sxs-lookup"><span data-stu-id="a9f19-170">Allocated</span></span>|<span data-ttu-id="a9f19-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a9f19-171">win:UInt64</span></span>|<span data-ttu-id="a9f19-172">自应用程序域创建以来在此应用程序域中分配的字节总数（不减去已释放的内存量）。</span><span class="sxs-lookup"><span data-stu-id="a9f19-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="a9f19-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a9f19-173">ClrInstanceID</span></span>|<span data-ttu-id="a9f19-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a9f19-174">win:UInt16</span></span>|<span data-ttu-id="a9f19-175">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a9f19-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a9f19-176">返回页首</span><span class="sxs-lookup"><span data-stu-id="a9f19-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="a9f19-177">AppDomainMemSurvived 事件</span><span class="sxs-lookup"><span data-stu-id="a9f19-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="a9f19-178">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a9f19-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a9f19-179">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a9f19-179">Keyword for raising the event</span></span>|<span data-ttu-id="a9f19-180">级别</span><span class="sxs-lookup"><span data-stu-id="a9f19-180">Level</span></span>|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` <span data-ttu-id="a9f19-181">(0x800)</span><span class="sxs-lookup"><span data-stu-id="a9f19-181">(0x800)</span></span>|<span data-ttu-id="a9f19-182">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a9f19-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="a9f19-183">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a9f19-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a9f19-184">Event</span><span class="sxs-lookup"><span data-stu-id="a9f19-184">Event</span></span>|<span data-ttu-id="a9f19-185">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a9f19-185">Event ID</span></span>|<span data-ttu-id="a9f19-186">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a9f19-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="a9f19-187">84</span><span class="sxs-lookup"><span data-stu-id="a9f19-187">84</span></span>|<span data-ttu-id="a9f19-188">每个垃圾回收已结束。</span><span class="sxs-lookup"><span data-stu-id="a9f19-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="a9f19-189">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="a9f19-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a9f19-190">字段名</span><span class="sxs-lookup"><span data-stu-id="a9f19-190">Field name</span></span>|<span data-ttu-id="a9f19-191">数据类型</span><span class="sxs-lookup"><span data-stu-id="a9f19-191">Data type</span></span>|<span data-ttu-id="a9f19-192">描述</span><span class="sxs-lookup"><span data-stu-id="a9f19-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a9f19-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="a9f19-193">AppDomainID</span></span>|<span data-ttu-id="a9f19-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a9f19-194">win:UInt64</span></span>|<span data-ttu-id="a9f19-195">正在报告其资源使用情况的域的标识符。</span><span class="sxs-lookup"><span data-stu-id="a9f19-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="a9f19-196">已保留</span><span class="sxs-lookup"><span data-stu-id="a9f19-196">Survived</span></span>|<span data-ttu-id="a9f19-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a9f19-197">win:UInt64</span></span>|<span data-ttu-id="a9f19-198">上次回收后保留下来的、已知由此应用程序域保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="a9f19-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="a9f19-199">此数字在完整回收之后准确且完整，但在暂时的回收之后可能不完整。</span><span class="sxs-lookup"><span data-stu-id="a9f19-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="a9f19-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="a9f19-200">ProcessSurvived</span></span>|<span data-ttu-id="a9f19-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a9f19-201">win:UInt64</span></span>|<span data-ttu-id="a9f19-202">从上一次回收中保留的总字节数。</span><span class="sxs-lookup"><span data-stu-id="a9f19-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="a9f19-203">完整回收之后，该数字表示托管堆中实时保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="a9f19-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="a9f19-204">暂时回收之后，该数字表示暂时生成中实时保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="a9f19-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="a9f19-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a9f19-205">ClrInstanceID</span></span>|<span data-ttu-id="a9f19-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a9f19-206">win:UInt16</span></span>|<span data-ttu-id="a9f19-207">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a9f19-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a9f19-208">返回页首</span><span class="sxs-lookup"><span data-stu-id="a9f19-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="a9f19-209">ThreadAppDomainEnter 事件</span><span class="sxs-lookup"><span data-stu-id="a9f19-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="a9f19-210">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a9f19-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a9f19-211">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a9f19-211">Keyword for raising the event</span></span>|<span data-ttu-id="a9f19-212">级别</span><span class="sxs-lookup"><span data-stu-id="a9f19-212">Level</span></span>|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` <span data-ttu-id="a9f19-213">(0x800)</span><span class="sxs-lookup"><span data-stu-id="a9f19-213">(0x800)</span></span>|<span data-ttu-id="a9f19-214">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a9f19-214">Informational(4)</span></span>|  
|`ThreadingKeyword` <span data-ttu-id="a9f19-215">(0x10000)</span><span class="sxs-lookup"><span data-stu-id="a9f19-215">(0x10000)</span></span>|<span data-ttu-id="a9f19-216">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a9f19-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="a9f19-217">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a9f19-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a9f19-218">Event</span><span class="sxs-lookup"><span data-stu-id="a9f19-218">Event</span></span>|<span data-ttu-id="a9f19-219">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a9f19-219">Event ID</span></span>|<span data-ttu-id="a9f19-220">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a9f19-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="a9f19-221">87</span><span class="sxs-lookup"><span data-stu-id="a9f19-221">87</span></span>|<span data-ttu-id="a9f19-222">线程进入应用程序域。</span><span class="sxs-lookup"><span data-stu-id="a9f19-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="a9f19-223">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="a9f19-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a9f19-224">字段名</span><span class="sxs-lookup"><span data-stu-id="a9f19-224">Field name</span></span>|<span data-ttu-id="a9f19-225">数据类型</span><span class="sxs-lookup"><span data-stu-id="a9f19-225">Data type</span></span>|<span data-ttu-id="a9f19-226">描述</span><span class="sxs-lookup"><span data-stu-id="a9f19-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a9f19-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="a9f19-227">ThreadID</span></span>|<span data-ttu-id="a9f19-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a9f19-228">win:UInt64</span></span>|<span data-ttu-id="a9f19-229">线程标识符。</span><span class="sxs-lookup"><span data-stu-id="a9f19-229">The thread identifier.</span></span>|  
|<span data-ttu-id="a9f19-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="a9f19-230">AppDomainID</span></span>|<span data-ttu-id="a9f19-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a9f19-231">win:UInt64</span></span>|<span data-ttu-id="a9f19-232">应用程序域标识符。</span><span class="sxs-lookup"><span data-stu-id="a9f19-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="a9f19-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a9f19-233">ClrInstanceID</span></span>|<span data-ttu-id="a9f19-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a9f19-234">win:UInt16</span></span>|<span data-ttu-id="a9f19-235">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a9f19-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a9f19-236">返回页首</span><span class="sxs-lookup"><span data-stu-id="a9f19-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="a9f19-237">ThreadTerminated 事件</span><span class="sxs-lookup"><span data-stu-id="a9f19-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="a9f19-238">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a9f19-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a9f19-239">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a9f19-239">Keyword for raising the event</span></span>|<span data-ttu-id="a9f19-240">级别</span><span class="sxs-lookup"><span data-stu-id="a9f19-240">Level</span></span>|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` <span data-ttu-id="a9f19-241">(0x800)</span><span class="sxs-lookup"><span data-stu-id="a9f19-241">(0x800)</span></span>|<span data-ttu-id="a9f19-242">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a9f19-242">Informational(4)</span></span>|  
|`ThreadingKeyword` <span data-ttu-id="a9f19-243">(0x10000)</span><span class="sxs-lookup"><span data-stu-id="a9f19-243">(0x10000)</span></span>|<span data-ttu-id="a9f19-244">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a9f19-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="a9f19-245">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a9f19-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a9f19-246">Event</span><span class="sxs-lookup"><span data-stu-id="a9f19-246">Event</span></span>|<span data-ttu-id="a9f19-247">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a9f19-247">Event ID</span></span>|<span data-ttu-id="a9f19-248">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a9f19-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="a9f19-249">86</span><span class="sxs-lookup"><span data-stu-id="a9f19-249">86</span></span>|<span data-ttu-id="a9f19-250">线程终止。</span><span class="sxs-lookup"><span data-stu-id="a9f19-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="a9f19-251">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="a9f19-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="a9f19-252">字段名</span><span class="sxs-lookup"><span data-stu-id="a9f19-252">Field name</span></span>|<span data-ttu-id="a9f19-253">数据类型</span><span class="sxs-lookup"><span data-stu-id="a9f19-253">Data type</span></span>|<span data-ttu-id="a9f19-254">描述</span><span class="sxs-lookup"><span data-stu-id="a9f19-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a9f19-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="a9f19-255">ThreadID</span></span>|<span data-ttu-id="a9f19-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a9f19-256">win:UInt64</span></span>|<span data-ttu-id="a9f19-257">线程标识符。</span><span class="sxs-lookup"><span data-stu-id="a9f19-257">The thread identifier.</span></span>|  
|<span data-ttu-id="a9f19-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="a9f19-258">AppDomainID</span></span>|<span data-ttu-id="a9f19-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a9f19-259">win:UInt64</span></span>|<span data-ttu-id="a9f19-260">应用程序域标识符。</span><span class="sxs-lookup"><span data-stu-id="a9f19-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="a9f19-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a9f19-261">ClrInstanceID</span></span>|<span data-ttu-id="a9f19-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a9f19-262">win:UInt16</span></span>|<span data-ttu-id="a9f19-263">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a9f19-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a9f19-264">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9f19-264">See also</span></span>

- [<span data-ttu-id="a9f19-265">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="a9f19-265">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
