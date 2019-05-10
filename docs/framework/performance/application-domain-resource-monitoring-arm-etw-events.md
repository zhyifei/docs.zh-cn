---
title: 应用程序域资源监视 (ARM) ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ac396e1a5b83f33068266553024c37ef436c150d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64616638"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="2efc8-102">应用程序域资源监视 (ARM) ETW 事件</span><span class="sxs-lookup"><span data-stu-id="2efc8-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="2efc8-103">这些事件提供有关应用程序域的状态的详细诊断信息。</span><span class="sxs-lookup"><span data-stu-id="2efc8-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="2efc8-104">你可以使用这些事件，或使用应用程序域资源监视 (ARM) 功能来获取相同的信息。</span><span class="sxs-lookup"><span data-stu-id="2efc8-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="2efc8-105">此类别包含以下事件：</span><span class="sxs-lookup"><span data-stu-id="2efc8-105">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="2efc8-106">ThreadCreated 事件</span><span class="sxs-lookup"><span data-stu-id="2efc8-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
- [<span data-ttu-id="2efc8-107">AppDomainMemAllocated 事件</span><span class="sxs-lookup"><span data-stu-id="2efc8-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
- [<span data-ttu-id="2efc8-108">AppDomainMemSurvived 事件</span><span class="sxs-lookup"><span data-stu-id="2efc8-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
- [<span data-ttu-id="2efc8-109">ThreadAppDomainEnter 事件</span><span class="sxs-lookup"><span data-stu-id="2efc8-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
- [<span data-ttu-id="2efc8-110">ThreadTerminated 事件</span><span class="sxs-lookup"><span data-stu-id="2efc8-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="2efc8-111">ThreadCreated 事件</span><span class="sxs-lookup"><span data-stu-id="2efc8-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="2efc8-112">在断开的提供程序下此事件也会作为 `ThreadDC` 引发（在 `AppDomainResourceManagementRundownKeyword` 关键字下）。</span><span class="sxs-lookup"><span data-stu-id="2efc8-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="2efc8-113">这是此类别的断开提供程序下引发的唯一事件。</span><span class="sxs-lookup"><span data-stu-id="2efc8-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="2efc8-114">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="2efc8-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="2efc8-115">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="2efc8-115">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="2efc8-116">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="2efc8-116">Keyword for raising the event</span></span>|<span data-ttu-id="2efc8-117">级别</span><span class="sxs-lookup"><span data-stu-id="2efc8-117">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="2efc8-118">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="2efc8-118">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="2efc8-119">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2efc8-119">Informational(4)</span></span>|  
|<span data-ttu-id="2efc8-120">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2efc8-120">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2efc8-121">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2efc8-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="2efc8-122">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="2efc8-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2efc8-123">Event</span><span class="sxs-lookup"><span data-stu-id="2efc8-123">Event</span></span>|<span data-ttu-id="2efc8-124">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2efc8-124">Event ID</span></span>|<span data-ttu-id="2efc8-125">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="2efc8-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="2efc8-126">85</span><span class="sxs-lookup"><span data-stu-id="2efc8-126">85</span></span>|<span data-ttu-id="2efc8-127">已为应用程序域创建了一个线程。</span><span class="sxs-lookup"><span data-stu-id="2efc8-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="2efc8-128">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="2efc8-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2efc8-129">字段名</span><span class="sxs-lookup"><span data-stu-id="2efc8-129">Field name</span></span>|<span data-ttu-id="2efc8-130">数据类型</span><span class="sxs-lookup"><span data-stu-id="2efc8-130">Data type</span></span>|<span data-ttu-id="2efc8-131">描述</span><span class="sxs-lookup"><span data-stu-id="2efc8-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2efc8-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="2efc8-132">ThreadID</span></span>|<span data-ttu-id="2efc8-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2efc8-133">win:UInt64</span></span>|<span data-ttu-id="2efc8-134">已创建的线程 ID。</span><span class="sxs-lookup"><span data-stu-id="2efc8-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="2efc8-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="2efc8-135">AppDomainID</span></span>|<span data-ttu-id="2efc8-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2efc8-136">win:UInt64</span></span>|<span data-ttu-id="2efc8-137">正在报告其线程活动的应用程序域的标识符。</span><span class="sxs-lookup"><span data-stu-id="2efc8-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="2efc8-138">标志</span><span class="sxs-lookup"><span data-stu-id="2efc8-138">Flags</span></span>|<span data-ttu-id="2efc8-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2efc8-139">win:UInt32</span></span>|<span data-ttu-id="2efc8-140">线程创建标志。</span><span class="sxs-lookup"><span data-stu-id="2efc8-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="2efc8-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="2efc8-141">ManagedThreadIndex</span></span>|<span data-ttu-id="2efc8-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2efc8-142">win:UInt32</span></span>|<span data-ttu-id="2efc8-143">已创建线程的托管索引。</span><span class="sxs-lookup"><span data-stu-id="2efc8-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="2efc8-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="2efc8-144">OSThreadID</span></span>|<span data-ttu-id="2efc8-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2efc8-145">win:UInt32</span></span>|<span data-ttu-id="2efc8-146">已创建线程的操作系统 ID。</span><span class="sxs-lookup"><span data-stu-id="2efc8-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="2efc8-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2efc8-147">ClrInstanceID</span></span>|<span data-ttu-id="2efc8-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2efc8-148">win:UInt16</span></span>|<span data-ttu-id="2efc8-149">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="2efc8-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="2efc8-150">返回页首</span><span class="sxs-lookup"><span data-stu-id="2efc8-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="2efc8-151">AppDomainMemAllocated 事件</span><span class="sxs-lookup"><span data-stu-id="2efc8-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="2efc8-152">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="2efc8-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2efc8-153">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="2efc8-153">Keyword for raising the event</span></span>|<span data-ttu-id="2efc8-154">级别</span><span class="sxs-lookup"><span data-stu-id="2efc8-154">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="2efc8-155">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="2efc8-155">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="2efc8-156">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2efc8-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="2efc8-157">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="2efc8-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2efc8-158">Event</span><span class="sxs-lookup"><span data-stu-id="2efc8-158">Event</span></span>|<span data-ttu-id="2efc8-159">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2efc8-159">Event ID</span></span>|<span data-ttu-id="2efc8-160">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="2efc8-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="2efc8-161">83</span><span class="sxs-lookup"><span data-stu-id="2efc8-161">83</span></span>|<span data-ttu-id="2efc8-162">应用程序域中分配每 4 MB 的内存（大约）。</span><span class="sxs-lookup"><span data-stu-id="2efc8-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="2efc8-163">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="2efc8-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2efc8-164">字段名</span><span class="sxs-lookup"><span data-stu-id="2efc8-164">Field name</span></span>|<span data-ttu-id="2efc8-165">数据类型</span><span class="sxs-lookup"><span data-stu-id="2efc8-165">Data type</span></span>|<span data-ttu-id="2efc8-166">描述</span><span class="sxs-lookup"><span data-stu-id="2efc8-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2efc8-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="2efc8-167">AppDomainID</span></span>|<span data-ttu-id="2efc8-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2efc8-168">win:UInt64</span></span>|<span data-ttu-id="2efc8-169">正在报告其资源使用情况的应用程序域的标识符。</span><span class="sxs-lookup"><span data-stu-id="2efc8-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="2efc8-170">已分配</span><span class="sxs-lookup"><span data-stu-id="2efc8-170">Allocated</span></span>|<span data-ttu-id="2efc8-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2efc8-171">win:UInt64</span></span>|<span data-ttu-id="2efc8-172">自应用程序域创建以来在此应用程序域中分配的字节总数（不减去已释放的内存量）。</span><span class="sxs-lookup"><span data-stu-id="2efc8-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="2efc8-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2efc8-173">ClrInstanceID</span></span>|<span data-ttu-id="2efc8-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2efc8-174">win:UInt16</span></span>|<span data-ttu-id="2efc8-175">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="2efc8-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="2efc8-176">返回页首</span><span class="sxs-lookup"><span data-stu-id="2efc8-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="2efc8-177">AppDomainMemSurvived 事件</span><span class="sxs-lookup"><span data-stu-id="2efc8-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="2efc8-178">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="2efc8-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2efc8-179">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="2efc8-179">Keyword for raising the event</span></span>|<span data-ttu-id="2efc8-180">级别</span><span class="sxs-lookup"><span data-stu-id="2efc8-180">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="2efc8-181">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="2efc8-181">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="2efc8-182">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2efc8-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="2efc8-183">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="2efc8-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2efc8-184">Event</span><span class="sxs-lookup"><span data-stu-id="2efc8-184">Event</span></span>|<span data-ttu-id="2efc8-185">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2efc8-185">Event ID</span></span>|<span data-ttu-id="2efc8-186">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="2efc8-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="2efc8-187">84</span><span class="sxs-lookup"><span data-stu-id="2efc8-187">84</span></span>|<span data-ttu-id="2efc8-188">每个垃圾回收已结束。</span><span class="sxs-lookup"><span data-stu-id="2efc8-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="2efc8-189">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="2efc8-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2efc8-190">字段名</span><span class="sxs-lookup"><span data-stu-id="2efc8-190">Field name</span></span>|<span data-ttu-id="2efc8-191">数据类型</span><span class="sxs-lookup"><span data-stu-id="2efc8-191">Data type</span></span>|<span data-ttu-id="2efc8-192">描述</span><span class="sxs-lookup"><span data-stu-id="2efc8-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2efc8-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="2efc8-193">AppDomainID</span></span>|<span data-ttu-id="2efc8-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2efc8-194">win:UInt64</span></span>|<span data-ttu-id="2efc8-195">正在报告其资源使用情况的域的标识符。</span><span class="sxs-lookup"><span data-stu-id="2efc8-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="2efc8-196">已保留</span><span class="sxs-lookup"><span data-stu-id="2efc8-196">Survived</span></span>|<span data-ttu-id="2efc8-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2efc8-197">win:UInt64</span></span>|<span data-ttu-id="2efc8-198">上次回收后保留下来的、已知由此应用程序域保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="2efc8-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="2efc8-199">此数字在完整回收之后准确且完整，但在暂时的回收之后可能不完整。</span><span class="sxs-lookup"><span data-stu-id="2efc8-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="2efc8-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="2efc8-200">ProcessSurvived</span></span>|<span data-ttu-id="2efc8-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2efc8-201">win:UInt64</span></span>|<span data-ttu-id="2efc8-202">从上一次回收中保留的总字节数。</span><span class="sxs-lookup"><span data-stu-id="2efc8-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="2efc8-203">完整回收之后，该数字表示托管堆中实时保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="2efc8-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="2efc8-204">暂时回收之后，该数字表示暂时生成中实时保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="2efc8-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="2efc8-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2efc8-205">ClrInstanceID</span></span>|<span data-ttu-id="2efc8-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2efc8-206">win:UInt16</span></span>|<span data-ttu-id="2efc8-207">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="2efc8-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="2efc8-208">返回页首</span><span class="sxs-lookup"><span data-stu-id="2efc8-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="2efc8-209">ThreadAppDomainEnter 事件</span><span class="sxs-lookup"><span data-stu-id="2efc8-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="2efc8-210">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="2efc8-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2efc8-211">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="2efc8-211">Keyword for raising the event</span></span>|<span data-ttu-id="2efc8-212">级别</span><span class="sxs-lookup"><span data-stu-id="2efc8-212">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="2efc8-213">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="2efc8-213">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="2efc8-214">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2efc8-214">Informational(4)</span></span>|  
|<span data-ttu-id="2efc8-215">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2efc8-215">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2efc8-216">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2efc8-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="2efc8-217">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="2efc8-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2efc8-218">Event</span><span class="sxs-lookup"><span data-stu-id="2efc8-218">Event</span></span>|<span data-ttu-id="2efc8-219">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2efc8-219">Event ID</span></span>|<span data-ttu-id="2efc8-220">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="2efc8-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="2efc8-221">87</span><span class="sxs-lookup"><span data-stu-id="2efc8-221">87</span></span>|<span data-ttu-id="2efc8-222">线程进入应用程序域。</span><span class="sxs-lookup"><span data-stu-id="2efc8-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="2efc8-223">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="2efc8-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2efc8-224">字段名</span><span class="sxs-lookup"><span data-stu-id="2efc8-224">Field name</span></span>|<span data-ttu-id="2efc8-225">数据类型</span><span class="sxs-lookup"><span data-stu-id="2efc8-225">Data type</span></span>|<span data-ttu-id="2efc8-226">描述</span><span class="sxs-lookup"><span data-stu-id="2efc8-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2efc8-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="2efc8-227">ThreadID</span></span>|<span data-ttu-id="2efc8-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2efc8-228">win:UInt64</span></span>|<span data-ttu-id="2efc8-229">线程标识符。</span><span class="sxs-lookup"><span data-stu-id="2efc8-229">The thread identifier.</span></span>|  
|<span data-ttu-id="2efc8-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="2efc8-230">AppDomainID</span></span>|<span data-ttu-id="2efc8-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2efc8-231">win:UInt64</span></span>|<span data-ttu-id="2efc8-232">应用程序域标识符。</span><span class="sxs-lookup"><span data-stu-id="2efc8-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="2efc8-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2efc8-233">ClrInstanceID</span></span>|<span data-ttu-id="2efc8-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2efc8-234">win:UInt16</span></span>|<span data-ttu-id="2efc8-235">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="2efc8-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="2efc8-236">返回页首</span><span class="sxs-lookup"><span data-stu-id="2efc8-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="2efc8-237">ThreadTerminated 事件</span><span class="sxs-lookup"><span data-stu-id="2efc8-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="2efc8-238">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="2efc8-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2efc8-239">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="2efc8-239">Keyword for raising the event</span></span>|<span data-ttu-id="2efc8-240">级别</span><span class="sxs-lookup"><span data-stu-id="2efc8-240">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="2efc8-241">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="2efc8-241">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="2efc8-242">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2efc8-242">Informational(4)</span></span>|  
|<span data-ttu-id="2efc8-243">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2efc8-243">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2efc8-244">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="2efc8-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="2efc8-245">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="2efc8-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2efc8-246">Event</span><span class="sxs-lookup"><span data-stu-id="2efc8-246">Event</span></span>|<span data-ttu-id="2efc8-247">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2efc8-247">Event ID</span></span>|<span data-ttu-id="2efc8-248">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="2efc8-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="2efc8-249">86</span><span class="sxs-lookup"><span data-stu-id="2efc8-249">86</span></span>|<span data-ttu-id="2efc8-250">线程终止。</span><span class="sxs-lookup"><span data-stu-id="2efc8-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="2efc8-251">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="2efc8-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="2efc8-252">字段名</span><span class="sxs-lookup"><span data-stu-id="2efc8-252">Field name</span></span>|<span data-ttu-id="2efc8-253">数据类型</span><span class="sxs-lookup"><span data-stu-id="2efc8-253">Data type</span></span>|<span data-ttu-id="2efc8-254">描述</span><span class="sxs-lookup"><span data-stu-id="2efc8-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2efc8-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="2efc8-255">ThreadID</span></span>|<span data-ttu-id="2efc8-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2efc8-256">win:UInt64</span></span>|<span data-ttu-id="2efc8-257">线程标识符。</span><span class="sxs-lookup"><span data-stu-id="2efc8-257">The thread identifier.</span></span>|  
|<span data-ttu-id="2efc8-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="2efc8-258">AppDomainID</span></span>|<span data-ttu-id="2efc8-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2efc8-259">win:UInt64</span></span>|<span data-ttu-id="2efc8-260">应用程序域标识符。</span><span class="sxs-lookup"><span data-stu-id="2efc8-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="2efc8-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2efc8-261">ClrInstanceID</span></span>|<span data-ttu-id="2efc8-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2efc8-262">win:UInt16</span></span>|<span data-ttu-id="2efc8-263">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="2efc8-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2efc8-264">请参阅</span><span class="sxs-lookup"><span data-stu-id="2efc8-264">See also</span></span>

- [<span data-ttu-id="2efc8-265">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="2efc8-265">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
