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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133817"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="2c904-102">应用程序域资源监视 (ARM) ETW 事件</span><span class="sxs-lookup"><span data-stu-id="2c904-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="2c904-103">这些事件提供有关应用程序域的状态的详细诊断信息。</span><span class="sxs-lookup"><span data-stu-id="2c904-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="2c904-104">你可以使用这些事件，或使用应用程序域资源监视 (ARM) 功能来获取相同的信息。</span><span class="sxs-lookup"><span data-stu-id="2c904-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="2c904-105">此类别包含以下事件：</span><span class="sxs-lookup"><span data-stu-id="2c904-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="2c904-106">ThreadCreated 事件</span><span class="sxs-lookup"><span data-stu-id="2c904-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
-   [<span data-ttu-id="2c904-107">AppDomainMemAllocated 事件</span><span class="sxs-lookup"><span data-stu-id="2c904-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
-   [<span data-ttu-id="2c904-108">AppDomainMemSurvived 事件</span><span class="sxs-lookup"><span data-stu-id="2c904-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
-   [<span data-ttu-id="2c904-109">ThreadAppDomainEnter 事件</span><span class="sxs-lookup"><span data-stu-id="2c904-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
-   [<span data-ttu-id="2c904-110">ThreadTerminated 事件</span><span class="sxs-lookup"><span data-stu-id="2c904-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="2c904-111">ThreadCreated 事件</span><span class="sxs-lookup"><span data-stu-id="2c904-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="2c904-112">在断开的提供程序下此事件也会作为 `ThreadDC` 引发（在 `AppDomainResourceManagementRundownKeyword` 关键字下）。</span><span class="sxs-lookup"><span data-stu-id="2c904-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="2c904-113">这是此类别的断开提供程序下引发的唯一事件。</span><span class="sxs-lookup"><span data-stu-id="2c904-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="2c904-114">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="2c904-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="2c904-115">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="2c904-115">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="2c904-116">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="2c904-116">Keyword for raising the event</span></span>|<span data-ttu-id="2c904-117">级别</span><span class="sxs-lookup"><span data-stu-id="2c904-117">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="2c904-118">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="2c904-118">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="2c904-119">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2c904-119">Informational(4)</span></span>|  
|<span data-ttu-id="2c904-120">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2c904-120">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2c904-121">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2c904-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="2c904-122">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="2c904-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2c904-123">Event</span><span class="sxs-lookup"><span data-stu-id="2c904-123">Event</span></span>|<span data-ttu-id="2c904-124">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2c904-124">Event ID</span></span>|<span data-ttu-id="2c904-125">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="2c904-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="2c904-126">85</span><span class="sxs-lookup"><span data-stu-id="2c904-126">85</span></span>|<span data-ttu-id="2c904-127">已为应用程序域创建了一个线程。</span><span class="sxs-lookup"><span data-stu-id="2c904-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="2c904-128">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="2c904-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2c904-129">字段名</span><span class="sxs-lookup"><span data-stu-id="2c904-129">Field name</span></span>|<span data-ttu-id="2c904-130">数据类型</span><span class="sxs-lookup"><span data-stu-id="2c904-130">Data type</span></span>|<span data-ttu-id="2c904-131">描述</span><span class="sxs-lookup"><span data-stu-id="2c904-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2c904-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="2c904-132">ThreadID</span></span>|<span data-ttu-id="2c904-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2c904-133">win:UInt64</span></span>|<span data-ttu-id="2c904-134">已创建的线程 ID。</span><span class="sxs-lookup"><span data-stu-id="2c904-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="2c904-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="2c904-135">AppDomainID</span></span>|<span data-ttu-id="2c904-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2c904-136">win:UInt64</span></span>|<span data-ttu-id="2c904-137">正在报告其线程活动的应用程序域的标识符。</span><span class="sxs-lookup"><span data-stu-id="2c904-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="2c904-138">标志</span><span class="sxs-lookup"><span data-stu-id="2c904-138">Flags</span></span>|<span data-ttu-id="2c904-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2c904-139">win:UInt32</span></span>|<span data-ttu-id="2c904-140">线程创建标志。</span><span class="sxs-lookup"><span data-stu-id="2c904-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="2c904-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="2c904-141">ManagedThreadIndex</span></span>|<span data-ttu-id="2c904-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2c904-142">win:UInt32</span></span>|<span data-ttu-id="2c904-143">已创建线程的托管索引。</span><span class="sxs-lookup"><span data-stu-id="2c904-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="2c904-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="2c904-144">OSThreadID</span></span>|<span data-ttu-id="2c904-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2c904-145">win:UInt32</span></span>|<span data-ttu-id="2c904-146">已创建线程的操作系统 ID。</span><span class="sxs-lookup"><span data-stu-id="2c904-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="2c904-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2c904-147">ClrInstanceID</span></span>|<span data-ttu-id="2c904-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2c904-148">win:UInt16</span></span>|<span data-ttu-id="2c904-149">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="2c904-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="2c904-150">返回页首</span><span class="sxs-lookup"><span data-stu-id="2c904-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="2c904-151">AppDomainMemAllocated 事件</span><span class="sxs-lookup"><span data-stu-id="2c904-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="2c904-152">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="2c904-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2c904-153">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="2c904-153">Keyword for raising the event</span></span>|<span data-ttu-id="2c904-154">级别</span><span class="sxs-lookup"><span data-stu-id="2c904-154">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="2c904-155">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="2c904-155">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="2c904-156">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2c904-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="2c904-157">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="2c904-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2c904-158">Event</span><span class="sxs-lookup"><span data-stu-id="2c904-158">Event</span></span>|<span data-ttu-id="2c904-159">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2c904-159">Event ID</span></span>|<span data-ttu-id="2c904-160">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="2c904-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="2c904-161">83</span><span class="sxs-lookup"><span data-stu-id="2c904-161">83</span></span>|<span data-ttu-id="2c904-162">应用程序域中分配每 4 MB 的内存（大约）。</span><span class="sxs-lookup"><span data-stu-id="2c904-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="2c904-163">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="2c904-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2c904-164">字段名</span><span class="sxs-lookup"><span data-stu-id="2c904-164">Field name</span></span>|<span data-ttu-id="2c904-165">数据类型</span><span class="sxs-lookup"><span data-stu-id="2c904-165">Data type</span></span>|<span data-ttu-id="2c904-166">描述</span><span class="sxs-lookup"><span data-stu-id="2c904-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2c904-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="2c904-167">AppDomainID</span></span>|<span data-ttu-id="2c904-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2c904-168">win:UInt64</span></span>|<span data-ttu-id="2c904-169">正在报告其资源使用情况的应用程序域的标识符。</span><span class="sxs-lookup"><span data-stu-id="2c904-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="2c904-170">已分配</span><span class="sxs-lookup"><span data-stu-id="2c904-170">Allocated</span></span>|<span data-ttu-id="2c904-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2c904-171">win:UInt64</span></span>|<span data-ttu-id="2c904-172">自应用程序域创建以来在此应用程序域中分配的字节总数（不减去已释放的内存量）。</span><span class="sxs-lookup"><span data-stu-id="2c904-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="2c904-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2c904-173">ClrInstanceID</span></span>|<span data-ttu-id="2c904-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2c904-174">win:UInt16</span></span>|<span data-ttu-id="2c904-175">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="2c904-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="2c904-176">返回页首</span><span class="sxs-lookup"><span data-stu-id="2c904-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="2c904-177">AppDomainMemSurvived 事件</span><span class="sxs-lookup"><span data-stu-id="2c904-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="2c904-178">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="2c904-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2c904-179">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="2c904-179">Keyword for raising the event</span></span>|<span data-ttu-id="2c904-180">级别</span><span class="sxs-lookup"><span data-stu-id="2c904-180">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="2c904-181">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="2c904-181">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="2c904-182">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2c904-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="2c904-183">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="2c904-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2c904-184">Event</span><span class="sxs-lookup"><span data-stu-id="2c904-184">Event</span></span>|<span data-ttu-id="2c904-185">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2c904-185">Event ID</span></span>|<span data-ttu-id="2c904-186">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="2c904-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="2c904-187">84</span><span class="sxs-lookup"><span data-stu-id="2c904-187">84</span></span>|<span data-ttu-id="2c904-188">每个垃圾回收已结束。</span><span class="sxs-lookup"><span data-stu-id="2c904-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="2c904-189">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="2c904-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2c904-190">字段名</span><span class="sxs-lookup"><span data-stu-id="2c904-190">Field name</span></span>|<span data-ttu-id="2c904-191">数据类型</span><span class="sxs-lookup"><span data-stu-id="2c904-191">Data type</span></span>|<span data-ttu-id="2c904-192">描述</span><span class="sxs-lookup"><span data-stu-id="2c904-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2c904-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="2c904-193">AppDomainID</span></span>|<span data-ttu-id="2c904-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2c904-194">win:UInt64</span></span>|<span data-ttu-id="2c904-195">正在报告其资源使用情况的域的标识符。</span><span class="sxs-lookup"><span data-stu-id="2c904-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="2c904-196">已保留</span><span class="sxs-lookup"><span data-stu-id="2c904-196">Survived</span></span>|<span data-ttu-id="2c904-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2c904-197">win:UInt64</span></span>|<span data-ttu-id="2c904-198">上次回收后保留下来的、已知由此应用程序域保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="2c904-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="2c904-199">此数字在完整回收之后准确且完整，但在暂时的回收之后可能不完整。</span><span class="sxs-lookup"><span data-stu-id="2c904-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="2c904-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="2c904-200">ProcessSurvived</span></span>|<span data-ttu-id="2c904-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2c904-201">win:UInt64</span></span>|<span data-ttu-id="2c904-202">从上一次回收中保留的总字节数。</span><span class="sxs-lookup"><span data-stu-id="2c904-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="2c904-203">完整回收之后，该数字表示托管堆中实时保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="2c904-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="2c904-204">暂时回收之后，该数字表示暂时生成中实时保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="2c904-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="2c904-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2c904-205">ClrInstanceID</span></span>|<span data-ttu-id="2c904-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2c904-206">win:UInt16</span></span>|<span data-ttu-id="2c904-207">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="2c904-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="2c904-208">返回页首</span><span class="sxs-lookup"><span data-stu-id="2c904-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="2c904-209">ThreadAppDomainEnter 事件</span><span class="sxs-lookup"><span data-stu-id="2c904-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="2c904-210">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="2c904-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2c904-211">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="2c904-211">Keyword for raising the event</span></span>|<span data-ttu-id="2c904-212">级别</span><span class="sxs-lookup"><span data-stu-id="2c904-212">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="2c904-213">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="2c904-213">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="2c904-214">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2c904-214">Informational(4)</span></span>|  
|<span data-ttu-id="2c904-215">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2c904-215">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2c904-216">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2c904-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="2c904-217">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="2c904-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2c904-218">Event</span><span class="sxs-lookup"><span data-stu-id="2c904-218">Event</span></span>|<span data-ttu-id="2c904-219">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2c904-219">Event ID</span></span>|<span data-ttu-id="2c904-220">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="2c904-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="2c904-221">87</span><span class="sxs-lookup"><span data-stu-id="2c904-221">87</span></span>|<span data-ttu-id="2c904-222">线程进入应用程序域。</span><span class="sxs-lookup"><span data-stu-id="2c904-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="2c904-223">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="2c904-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2c904-224">字段名</span><span class="sxs-lookup"><span data-stu-id="2c904-224">Field name</span></span>|<span data-ttu-id="2c904-225">数据类型</span><span class="sxs-lookup"><span data-stu-id="2c904-225">Data type</span></span>|<span data-ttu-id="2c904-226">描述</span><span class="sxs-lookup"><span data-stu-id="2c904-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2c904-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="2c904-227">ThreadID</span></span>|<span data-ttu-id="2c904-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2c904-228">win:UInt64</span></span>|<span data-ttu-id="2c904-229">线程标识符。</span><span class="sxs-lookup"><span data-stu-id="2c904-229">The thread identifier.</span></span>|  
|<span data-ttu-id="2c904-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="2c904-230">AppDomainID</span></span>|<span data-ttu-id="2c904-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2c904-231">win:UInt64</span></span>|<span data-ttu-id="2c904-232">应用程序域标识符。</span><span class="sxs-lookup"><span data-stu-id="2c904-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="2c904-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2c904-233">ClrInstanceID</span></span>|<span data-ttu-id="2c904-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2c904-234">win:UInt16</span></span>|<span data-ttu-id="2c904-235">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="2c904-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="2c904-236">返回页首</span><span class="sxs-lookup"><span data-stu-id="2c904-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="2c904-237">ThreadTerminated 事件</span><span class="sxs-lookup"><span data-stu-id="2c904-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="2c904-238">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="2c904-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2c904-239">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="2c904-239">Keyword for raising the event</span></span>|<span data-ttu-id="2c904-240">级别</span><span class="sxs-lookup"><span data-stu-id="2c904-240">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="2c904-241">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="2c904-241">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="2c904-242">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2c904-242">Informational(4)</span></span>|  
|<span data-ttu-id="2c904-243">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2c904-243">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2c904-244">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2c904-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="2c904-245">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="2c904-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2c904-246">Event</span><span class="sxs-lookup"><span data-stu-id="2c904-246">Event</span></span>|<span data-ttu-id="2c904-247">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2c904-247">Event ID</span></span>|<span data-ttu-id="2c904-248">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="2c904-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="2c904-249">86</span><span class="sxs-lookup"><span data-stu-id="2c904-249">86</span></span>|<span data-ttu-id="2c904-250">线程终止。</span><span class="sxs-lookup"><span data-stu-id="2c904-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="2c904-251">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="2c904-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="2c904-252">字段名</span><span class="sxs-lookup"><span data-stu-id="2c904-252">Field name</span></span>|<span data-ttu-id="2c904-253">数据类型</span><span class="sxs-lookup"><span data-stu-id="2c904-253">Data type</span></span>|<span data-ttu-id="2c904-254">描述</span><span class="sxs-lookup"><span data-stu-id="2c904-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2c904-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="2c904-255">ThreadID</span></span>|<span data-ttu-id="2c904-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2c904-256">win:UInt64</span></span>|<span data-ttu-id="2c904-257">线程标识符。</span><span class="sxs-lookup"><span data-stu-id="2c904-257">The thread identifier.</span></span>|  
|<span data-ttu-id="2c904-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="2c904-258">AppDomainID</span></span>|<span data-ttu-id="2c904-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2c904-259">win:UInt64</span></span>|<span data-ttu-id="2c904-260">应用程序域标识符。</span><span class="sxs-lookup"><span data-stu-id="2c904-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="2c904-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2c904-261">ClrInstanceID</span></span>|<span data-ttu-id="2c904-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2c904-262">win:UInt16</span></span>|<span data-ttu-id="2c904-263">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="2c904-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2c904-264">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c904-264">See also</span></span>

- [<span data-ttu-id="2c904-265">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="2c904-265">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
