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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788058"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="f4a15-102">应用程序域资源监视 (ARM) ETW 事件</span><span class="sxs-lookup"><span data-stu-id="f4a15-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="f4a15-103">这些事件提供有关应用程序域的状态的详细诊断信息。</span><span class="sxs-lookup"><span data-stu-id="f4a15-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="f4a15-104">你可以使用这些事件，或使用应用程序域资源监视 (ARM) 功能来获取相同的信息。</span><span class="sxs-lookup"><span data-stu-id="f4a15-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="f4a15-105">此类别包含以下事件：</span><span class="sxs-lookup"><span data-stu-id="f4a15-105">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="f4a15-106">ThreadCreated 事件</span><span class="sxs-lookup"><span data-stu-id="f4a15-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
- [<span data-ttu-id="f4a15-107">AppDomainMemAllocated 事件</span><span class="sxs-lookup"><span data-stu-id="f4a15-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
- [<span data-ttu-id="f4a15-108">AppDomainMemSurvived 事件</span><span class="sxs-lookup"><span data-stu-id="f4a15-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
- [<span data-ttu-id="f4a15-109">ThreadAppDomainEnter 事件</span><span class="sxs-lookup"><span data-stu-id="f4a15-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
- [<span data-ttu-id="f4a15-110">ThreadTerminated 事件</span><span class="sxs-lookup"><span data-stu-id="f4a15-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="f4a15-111">ThreadCreated 事件</span><span class="sxs-lookup"><span data-stu-id="f4a15-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="f4a15-112">在断开的提供程序下此事件也会作为 `ThreadDC` 引发（在 `AppDomainResourceManagementRundownKeyword` 关键字下）。</span><span class="sxs-lookup"><span data-stu-id="f4a15-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="f4a15-113">这是此类别的断开提供程序下引发的唯一事件。</span><span class="sxs-lookup"><span data-stu-id="f4a15-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="f4a15-114">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="f4a15-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="f4a15-115">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="f4a15-115">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="f4a15-116">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="f4a15-116">Keyword for raising the event</span></span>|<span data-ttu-id="f4a15-117">级别</span><span class="sxs-lookup"><span data-stu-id="f4a15-117">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f4a15-118">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="f4a15-118">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="f4a15-119">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="f4a15-119">Informational(4)</span></span>|  
|<span data-ttu-id="f4a15-120">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="f4a15-120">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="f4a15-121">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="f4a15-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="f4a15-122">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="f4a15-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f4a15-123">Event</span><span class="sxs-lookup"><span data-stu-id="f4a15-123">Event</span></span>|<span data-ttu-id="f4a15-124">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f4a15-124">Event ID</span></span>|<span data-ttu-id="f4a15-125">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="f4a15-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="f4a15-126">85</span><span class="sxs-lookup"><span data-stu-id="f4a15-126">85</span></span>|<span data-ttu-id="f4a15-127">已为应用程序域创建了一个线程。</span><span class="sxs-lookup"><span data-stu-id="f4a15-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="f4a15-128">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="f4a15-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f4a15-129">字段名</span><span class="sxs-lookup"><span data-stu-id="f4a15-129">Field name</span></span>|<span data-ttu-id="f4a15-130">数据类型</span><span class="sxs-lookup"><span data-stu-id="f4a15-130">Data type</span></span>|<span data-ttu-id="f4a15-131">描述</span><span class="sxs-lookup"><span data-stu-id="f4a15-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f4a15-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="f4a15-132">ThreadID</span></span>|<span data-ttu-id="f4a15-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f4a15-133">win:UInt64</span></span>|<span data-ttu-id="f4a15-134">已创建的线程 ID。</span><span class="sxs-lookup"><span data-stu-id="f4a15-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="f4a15-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="f4a15-135">AppDomainID</span></span>|<span data-ttu-id="f4a15-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f4a15-136">win:UInt64</span></span>|<span data-ttu-id="f4a15-137">正在报告其线程活动的应用程序域的标识符。</span><span class="sxs-lookup"><span data-stu-id="f4a15-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="f4a15-138">标志</span><span class="sxs-lookup"><span data-stu-id="f4a15-138">Flags</span></span>|<span data-ttu-id="f4a15-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f4a15-139">win:UInt32</span></span>|<span data-ttu-id="f4a15-140">线程创建标志。</span><span class="sxs-lookup"><span data-stu-id="f4a15-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="f4a15-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="f4a15-141">ManagedThreadIndex</span></span>|<span data-ttu-id="f4a15-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f4a15-142">win:UInt32</span></span>|<span data-ttu-id="f4a15-143">已创建线程的托管索引。</span><span class="sxs-lookup"><span data-stu-id="f4a15-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="f4a15-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="f4a15-144">OSThreadID</span></span>|<span data-ttu-id="f4a15-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f4a15-145">win:UInt32</span></span>|<span data-ttu-id="f4a15-146">已创建线程的操作系统 ID。</span><span class="sxs-lookup"><span data-stu-id="f4a15-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="f4a15-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f4a15-147">ClrInstanceID</span></span>|<span data-ttu-id="f4a15-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f4a15-148">win:UInt16</span></span>|<span data-ttu-id="f4a15-149">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="f4a15-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="f4a15-150">返回页首</span><span class="sxs-lookup"><span data-stu-id="f4a15-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="f4a15-151">AppDomainMemAllocated 事件</span><span class="sxs-lookup"><span data-stu-id="f4a15-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="f4a15-152">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="f4a15-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="f4a15-153">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="f4a15-153">Keyword for raising the event</span></span>|<span data-ttu-id="f4a15-154">级别</span><span class="sxs-lookup"><span data-stu-id="f4a15-154">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f4a15-155">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="f4a15-155">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="f4a15-156">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="f4a15-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="f4a15-157">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="f4a15-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f4a15-158">Event</span><span class="sxs-lookup"><span data-stu-id="f4a15-158">Event</span></span>|<span data-ttu-id="f4a15-159">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f4a15-159">Event ID</span></span>|<span data-ttu-id="f4a15-160">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="f4a15-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="f4a15-161">83</span><span class="sxs-lookup"><span data-stu-id="f4a15-161">83</span></span>|<span data-ttu-id="f4a15-162">应用程序域中分配每 4 MB 的内存（大约）。</span><span class="sxs-lookup"><span data-stu-id="f4a15-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="f4a15-163">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="f4a15-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f4a15-164">字段名</span><span class="sxs-lookup"><span data-stu-id="f4a15-164">Field name</span></span>|<span data-ttu-id="f4a15-165">数据类型</span><span class="sxs-lookup"><span data-stu-id="f4a15-165">Data type</span></span>|<span data-ttu-id="f4a15-166">描述</span><span class="sxs-lookup"><span data-stu-id="f4a15-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f4a15-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="f4a15-167">AppDomainID</span></span>|<span data-ttu-id="f4a15-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f4a15-168">win:UInt64</span></span>|<span data-ttu-id="f4a15-169">正在报告其资源使用情况的应用程序域的标识符。</span><span class="sxs-lookup"><span data-stu-id="f4a15-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="f4a15-170">已分配</span><span class="sxs-lookup"><span data-stu-id="f4a15-170">Allocated</span></span>|<span data-ttu-id="f4a15-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f4a15-171">win:UInt64</span></span>|<span data-ttu-id="f4a15-172">自应用程序域创建以来在此应用程序域中分配的字节总数（不减去已释放的内存量）。</span><span class="sxs-lookup"><span data-stu-id="f4a15-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="f4a15-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f4a15-173">ClrInstanceID</span></span>|<span data-ttu-id="f4a15-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f4a15-174">win:UInt16</span></span>|<span data-ttu-id="f4a15-175">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="f4a15-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="f4a15-176">返回页首</span><span class="sxs-lookup"><span data-stu-id="f4a15-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="f4a15-177">AppDomainMemSurvived 事件</span><span class="sxs-lookup"><span data-stu-id="f4a15-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="f4a15-178">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="f4a15-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="f4a15-179">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="f4a15-179">Keyword for raising the event</span></span>|<span data-ttu-id="f4a15-180">级别</span><span class="sxs-lookup"><span data-stu-id="f4a15-180">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f4a15-181">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="f4a15-181">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="f4a15-182">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="f4a15-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="f4a15-183">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="f4a15-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f4a15-184">Event</span><span class="sxs-lookup"><span data-stu-id="f4a15-184">Event</span></span>|<span data-ttu-id="f4a15-185">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f4a15-185">Event ID</span></span>|<span data-ttu-id="f4a15-186">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="f4a15-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="f4a15-187">84</span><span class="sxs-lookup"><span data-stu-id="f4a15-187">84</span></span>|<span data-ttu-id="f4a15-188">每个垃圾回收已结束。</span><span class="sxs-lookup"><span data-stu-id="f4a15-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="f4a15-189">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="f4a15-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f4a15-190">字段名</span><span class="sxs-lookup"><span data-stu-id="f4a15-190">Field name</span></span>|<span data-ttu-id="f4a15-191">数据类型</span><span class="sxs-lookup"><span data-stu-id="f4a15-191">Data type</span></span>|<span data-ttu-id="f4a15-192">描述</span><span class="sxs-lookup"><span data-stu-id="f4a15-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f4a15-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="f4a15-193">AppDomainID</span></span>|<span data-ttu-id="f4a15-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f4a15-194">win:UInt64</span></span>|<span data-ttu-id="f4a15-195">正在报告其资源使用情况的域的标识符。</span><span class="sxs-lookup"><span data-stu-id="f4a15-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="f4a15-196">已保留</span><span class="sxs-lookup"><span data-stu-id="f4a15-196">Survived</span></span>|<span data-ttu-id="f4a15-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f4a15-197">win:UInt64</span></span>|<span data-ttu-id="f4a15-198">上次回收后保留下来的、已知由此应用程序域保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="f4a15-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="f4a15-199">此数字在完整回收之后准确且完整，但在暂时的回收之后可能不完整。</span><span class="sxs-lookup"><span data-stu-id="f4a15-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="f4a15-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="f4a15-200">ProcessSurvived</span></span>|<span data-ttu-id="f4a15-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f4a15-201">win:UInt64</span></span>|<span data-ttu-id="f4a15-202">从上一次回收中保留的总字节数。</span><span class="sxs-lookup"><span data-stu-id="f4a15-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="f4a15-203">完整回收之后，该数字表示托管堆中实时保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="f4a15-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="f4a15-204">暂时回收之后，该数字表示暂时生成中实时保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="f4a15-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="f4a15-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f4a15-205">ClrInstanceID</span></span>|<span data-ttu-id="f4a15-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f4a15-206">win:UInt16</span></span>|<span data-ttu-id="f4a15-207">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="f4a15-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="f4a15-208">返回页首</span><span class="sxs-lookup"><span data-stu-id="f4a15-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="f4a15-209">ThreadAppDomainEnter 事件</span><span class="sxs-lookup"><span data-stu-id="f4a15-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="f4a15-210">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="f4a15-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="f4a15-211">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="f4a15-211">Keyword for raising the event</span></span>|<span data-ttu-id="f4a15-212">级别</span><span class="sxs-lookup"><span data-stu-id="f4a15-212">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f4a15-213">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="f4a15-213">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="f4a15-214">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="f4a15-214">Informational(4)</span></span>|  
|<span data-ttu-id="f4a15-215">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="f4a15-215">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="f4a15-216">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="f4a15-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="f4a15-217">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="f4a15-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f4a15-218">Event</span><span class="sxs-lookup"><span data-stu-id="f4a15-218">Event</span></span>|<span data-ttu-id="f4a15-219">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f4a15-219">Event ID</span></span>|<span data-ttu-id="f4a15-220">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="f4a15-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="f4a15-221">87</span><span class="sxs-lookup"><span data-stu-id="f4a15-221">87</span></span>|<span data-ttu-id="f4a15-222">线程进入应用程序域。</span><span class="sxs-lookup"><span data-stu-id="f4a15-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="f4a15-223">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="f4a15-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f4a15-224">字段名</span><span class="sxs-lookup"><span data-stu-id="f4a15-224">Field name</span></span>|<span data-ttu-id="f4a15-225">数据类型</span><span class="sxs-lookup"><span data-stu-id="f4a15-225">Data type</span></span>|<span data-ttu-id="f4a15-226">描述</span><span class="sxs-lookup"><span data-stu-id="f4a15-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f4a15-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="f4a15-227">ThreadID</span></span>|<span data-ttu-id="f4a15-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f4a15-228">win:UInt64</span></span>|<span data-ttu-id="f4a15-229">线程标识符。</span><span class="sxs-lookup"><span data-stu-id="f4a15-229">The thread identifier.</span></span>|  
|<span data-ttu-id="f4a15-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="f4a15-230">AppDomainID</span></span>|<span data-ttu-id="f4a15-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f4a15-231">win:UInt64</span></span>|<span data-ttu-id="f4a15-232">应用程序域标识符。</span><span class="sxs-lookup"><span data-stu-id="f4a15-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="f4a15-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f4a15-233">ClrInstanceID</span></span>|<span data-ttu-id="f4a15-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f4a15-234">win:UInt16</span></span>|<span data-ttu-id="f4a15-235">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="f4a15-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="f4a15-236">返回页首</span><span class="sxs-lookup"><span data-stu-id="f4a15-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="f4a15-237">ThreadTerminated 事件</span><span class="sxs-lookup"><span data-stu-id="f4a15-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="f4a15-238">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="f4a15-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="f4a15-239">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="f4a15-239">Keyword for raising the event</span></span>|<span data-ttu-id="f4a15-240">级别</span><span class="sxs-lookup"><span data-stu-id="f4a15-240">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f4a15-241">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="f4a15-241">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="f4a15-242">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="f4a15-242">Informational(4)</span></span>|  
|<span data-ttu-id="f4a15-243">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="f4a15-243">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="f4a15-244">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="f4a15-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="f4a15-245">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="f4a15-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f4a15-246">Event</span><span class="sxs-lookup"><span data-stu-id="f4a15-246">Event</span></span>|<span data-ttu-id="f4a15-247">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f4a15-247">Event ID</span></span>|<span data-ttu-id="f4a15-248">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="f4a15-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="f4a15-249">86</span><span class="sxs-lookup"><span data-stu-id="f4a15-249">86</span></span>|<span data-ttu-id="f4a15-250">线程终止。</span><span class="sxs-lookup"><span data-stu-id="f4a15-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="f4a15-251">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="f4a15-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="f4a15-252">字段名</span><span class="sxs-lookup"><span data-stu-id="f4a15-252">Field name</span></span>|<span data-ttu-id="f4a15-253">数据类型</span><span class="sxs-lookup"><span data-stu-id="f4a15-253">Data type</span></span>|<span data-ttu-id="f4a15-254">描述</span><span class="sxs-lookup"><span data-stu-id="f4a15-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f4a15-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="f4a15-255">ThreadID</span></span>|<span data-ttu-id="f4a15-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f4a15-256">win:UInt64</span></span>|<span data-ttu-id="f4a15-257">线程标识符。</span><span class="sxs-lookup"><span data-stu-id="f4a15-257">The thread identifier.</span></span>|  
|<span data-ttu-id="f4a15-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="f4a15-258">AppDomainID</span></span>|<span data-ttu-id="f4a15-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f4a15-259">win:UInt64</span></span>|<span data-ttu-id="f4a15-260">应用程序域标识符。</span><span class="sxs-lookup"><span data-stu-id="f4a15-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="f4a15-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f4a15-261">ClrInstanceID</span></span>|<span data-ttu-id="f4a15-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f4a15-262">win:UInt16</span></span>|<span data-ttu-id="f4a15-263">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="f4a15-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f4a15-264">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4a15-264">See also</span></span>

- [<span data-ttu-id="f4a15-265">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="f4a15-265">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
