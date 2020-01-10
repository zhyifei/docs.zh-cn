---
title: 应用程序域资源监视 (ARM) ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
ms.openlocfilehash: 0e453b2bafffd9e07a1bdddd97282c5b97f5483d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716217"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="a6cb2-102">应用程序域资源监视 (ARM) ETW 事件</span><span class="sxs-lookup"><span data-stu-id="a6cb2-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>

<span data-ttu-id="a6cb2-103">这些事件提供有关应用程序域的状态的详细诊断信息。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="a6cb2-104">你可以使用这些事件，或使用应用程序域资源监视 (ARM) 功能来获取相同的信息。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>

## <a name="threadcreated-event"></a><span data-ttu-id="a6cb2-105">ThreadCreated 事件</span><span class="sxs-lookup"><span data-stu-id="a6cb2-105">ThreadCreated Event</span></span>

<span data-ttu-id="a6cb2-106">在断开的提供程序下此事件也会作为 `ThreadDC` 引发（在 `AppDomainResourceManagementRundownKeyword` 关键字下）。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-106">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="a6cb2-107">这是此类别的断开提供程序下引发的唯一事件。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-107">This is the only event that is raised under the rundown provider in this category.</span></span>

<span data-ttu-id="a6cb2-108">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="a6cb2-109">有关详细信息，请参阅[CLR ETW 关键字和级别](clr-etw-keywords-and-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-109">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="a6cb2-110">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a6cb2-110">Keyword for raising the event</span></span>|<span data-ttu-id="a6cb2-111">Level</span><span class="sxs-lookup"><span data-stu-id="a6cb2-111">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="a6cb2-112">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="a6cb2-112">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="a6cb2-113">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a6cb2-113">Informational(4)</span></span>|
|<span data-ttu-id="a6cb2-114">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="a6cb2-114">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a6cb2-115">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a6cb2-115">Informational(4)</span></span>|

<span data-ttu-id="a6cb2-116">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="a6cb2-116">The following table shows the event information:</span></span>

|<span data-ttu-id="a6cb2-117">Event</span><span class="sxs-lookup"><span data-stu-id="a6cb2-117">Event</span></span>|<span data-ttu-id="a6cb2-118">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a6cb2-118">Event ID</span></span>|<span data-ttu-id="a6cb2-119">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a6cb2-119">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadCreated`|<span data-ttu-id="a6cb2-120">85</span><span class="sxs-lookup"><span data-stu-id="a6cb2-120">85</span></span>|<span data-ttu-id="a6cb2-121">已为应用程序域创建了一个线程。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-121">A thread was created for the application domain.</span></span>|

<span data-ttu-id="a6cb2-122">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="a6cb2-122">The following table shows the event data:</span></span>

|<span data-ttu-id="a6cb2-123">字段名</span><span class="sxs-lookup"><span data-stu-id="a6cb2-123">Field name</span></span>|<span data-ttu-id="a6cb2-124">数据类型</span><span class="sxs-lookup"><span data-stu-id="a6cb2-124">Data type</span></span>|<span data-ttu-id="a6cb2-125">描述</span><span class="sxs-lookup"><span data-stu-id="a6cb2-125">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="a6cb2-126">ThreadID</span><span class="sxs-lookup"><span data-stu-id="a6cb2-126">ThreadID</span></span>|<span data-ttu-id="a6cb2-127">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a6cb2-127">win:UInt64</span></span>|<span data-ttu-id="a6cb2-128">已创建的线程 ID。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-128">ID of the thread that was created.</span></span>|
|<span data-ttu-id="a6cb2-129">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="a6cb2-129">AppDomainID</span></span>|<span data-ttu-id="a6cb2-130">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a6cb2-130">win:UInt64</span></span>|<span data-ttu-id="a6cb2-131">正在报告其线程活动的应用程序域的标识符。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-131">Identifier of the application domain for which thread activity is being reported.</span></span>|
|<span data-ttu-id="a6cb2-132">Flags</span><span class="sxs-lookup"><span data-stu-id="a6cb2-132">Flags</span></span>|<span data-ttu-id="a6cb2-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a6cb2-133">win:UInt32</span></span>|<span data-ttu-id="a6cb2-134">线程创建标志。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-134">Thread creation flags.</span></span>|
|<span data-ttu-id="a6cb2-135">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="a6cb2-135">ManagedThreadIndex</span></span>|<span data-ttu-id="a6cb2-136">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a6cb2-136">win:UInt32</span></span>|<span data-ttu-id="a6cb2-137">已创建线程的托管索引。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-137">Managed index of the thread that was created.</span></span>|
|<span data-ttu-id="a6cb2-138">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="a6cb2-138">OSThreadID</span></span>|<span data-ttu-id="a6cb2-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a6cb2-139">win:UInt32</span></span>|<span data-ttu-id="a6cb2-140">已创建线程的操作系统 ID。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-140">Operating system ID of the thread that was created.</span></span>|
|<span data-ttu-id="a6cb2-141">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a6cb2-141">ClrInstanceID</span></span>|<span data-ttu-id="a6cb2-142">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a6cb2-142">win:UInt16</span></span>|<span data-ttu-id="a6cb2-143">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-143">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemallocated-event"></a><span data-ttu-id="a6cb2-144">AppDomainMemAllocated 事件</span><span class="sxs-lookup"><span data-stu-id="a6cb2-144">AppDomainMemAllocated Event</span></span>

<span data-ttu-id="a6cb2-145">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="a6cb2-145">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="a6cb2-146">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a6cb2-146">Keyword for raising the event</span></span>|<span data-ttu-id="a6cb2-147">Level</span><span class="sxs-lookup"><span data-stu-id="a6cb2-147">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="a6cb2-148">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="a6cb2-148">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="a6cb2-149">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a6cb2-149">Informational(4)</span></span>|

<span data-ttu-id="a6cb2-150">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="a6cb2-150">The following table shows the event information:</span></span>

|<span data-ttu-id="a6cb2-151">Event</span><span class="sxs-lookup"><span data-stu-id="a6cb2-151">Event</span></span>|<span data-ttu-id="a6cb2-152">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a6cb2-152">Event ID</span></span>|<span data-ttu-id="a6cb2-153">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a6cb2-153">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemAllocated`|<span data-ttu-id="a6cb2-154">83</span><span class="sxs-lookup"><span data-stu-id="a6cb2-154">83</span></span>|<span data-ttu-id="a6cb2-155">应用程序域中分配每 4 MB 的内存（大约）。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-155">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|

<span data-ttu-id="a6cb2-156">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="a6cb2-156">The following table shows the event data:</span></span>

|<span data-ttu-id="a6cb2-157">字段名</span><span class="sxs-lookup"><span data-stu-id="a6cb2-157">Field name</span></span>|<span data-ttu-id="a6cb2-158">数据类型</span><span class="sxs-lookup"><span data-stu-id="a6cb2-158">Data type</span></span>|<span data-ttu-id="a6cb2-159">描述</span><span class="sxs-lookup"><span data-stu-id="a6cb2-159">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="a6cb2-160">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="a6cb2-160">AppDomainID</span></span>|<span data-ttu-id="a6cb2-161">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a6cb2-161">win:UInt64</span></span>|<span data-ttu-id="a6cb2-162">正在报告其资源使用情况的应用程序域的标识符。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-162">Identifier of the application domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="a6cb2-163">已分配</span><span class="sxs-lookup"><span data-stu-id="a6cb2-163">Allocated</span></span>|<span data-ttu-id="a6cb2-164">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a6cb2-164">win:UInt64</span></span>|<span data-ttu-id="a6cb2-165">自应用程序域创建以来在此应用程序域中分配的字节总数（不减去已释放的内存量）。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-165">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|
|<span data-ttu-id="a6cb2-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a6cb2-166">ClrInstanceID</span></span>|<span data-ttu-id="a6cb2-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a6cb2-167">win:UInt16</span></span>|<span data-ttu-id="a6cb2-168">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="a6cb2-169">AppDomainMemSurvived 事件</span><span class="sxs-lookup"><span data-stu-id="a6cb2-169">AppDomainMemSurvived Event</span></span>

<span data-ttu-id="a6cb2-170">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="a6cb2-170">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="a6cb2-171">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a6cb2-171">Keyword for raising the event</span></span>|<span data-ttu-id="a6cb2-172">Level</span><span class="sxs-lookup"><span data-stu-id="a6cb2-172">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="a6cb2-173">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="a6cb2-173">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="a6cb2-174">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a6cb2-174">Informational(4)</span></span>|

<span data-ttu-id="a6cb2-175">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="a6cb2-175">The following table shows the event information:</span></span>

|<span data-ttu-id="a6cb2-176">Event</span><span class="sxs-lookup"><span data-stu-id="a6cb2-176">Event</span></span>|<span data-ttu-id="a6cb2-177">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a6cb2-177">Event ID</span></span>|<span data-ttu-id="a6cb2-178">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a6cb2-178">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemSurvived`|<span data-ttu-id="a6cb2-179">84</span><span class="sxs-lookup"><span data-stu-id="a6cb2-179">84</span></span>|<span data-ttu-id="a6cb2-180">每个垃圾回收已结束。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-180">Each garbage collection has ended.</span></span>|

<span data-ttu-id="a6cb2-181">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="a6cb2-181">The following table shows the event data:</span></span>

|<span data-ttu-id="a6cb2-182">字段名</span><span class="sxs-lookup"><span data-stu-id="a6cb2-182">Field name</span></span>|<span data-ttu-id="a6cb2-183">数据类型</span><span class="sxs-lookup"><span data-stu-id="a6cb2-183">Data type</span></span>|<span data-ttu-id="a6cb2-184">描述</span><span class="sxs-lookup"><span data-stu-id="a6cb2-184">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="a6cb2-185">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="a6cb2-185">AppDomainID</span></span>|<span data-ttu-id="a6cb2-186">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a6cb2-186">win:UInt64</span></span>|<span data-ttu-id="a6cb2-187">正在报告其资源使用情况的域的标识符。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-187">Identifier of the domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="a6cb2-188">已保留</span><span class="sxs-lookup"><span data-stu-id="a6cb2-188">Survived</span></span>|<span data-ttu-id="a6cb2-189">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a6cb2-189">win:UInt64</span></span>|<span data-ttu-id="a6cb2-190">上次回收后保留下来的、已知由此应用程序域保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-190">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="a6cb2-191">此数字在完整回收之后准确且完整，但在暂时的回收之后可能不完整。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-191">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|
|<span data-ttu-id="a6cb2-192">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="a6cb2-192">ProcessSurvived</span></span>|<span data-ttu-id="a6cb2-193">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a6cb2-193">win:UInt64</span></span>|<span data-ttu-id="a6cb2-194">从上一次回收中保留的总字节数。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-194">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="a6cb2-195">完整回收之后，该数字表示托管堆中实时保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-195">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="a6cb2-196">暂时回收之后，该数字表示暂时生成中实时保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-196">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|
|<span data-ttu-id="a6cb2-197">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a6cb2-197">ClrInstanceID</span></span>|<span data-ttu-id="a6cb2-198">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a6cb2-198">win:UInt16</span></span>|<span data-ttu-id="a6cb2-199">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-199">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadappdomainenter-event"></a><span data-ttu-id="a6cb2-200">ThreadAppDomainEnter 事件</span><span class="sxs-lookup"><span data-stu-id="a6cb2-200">ThreadAppDomainEnter Event</span></span>

<span data-ttu-id="a6cb2-201">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="a6cb2-201">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="a6cb2-202">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a6cb2-202">Keyword for raising the event</span></span>|<span data-ttu-id="a6cb2-203">Level</span><span class="sxs-lookup"><span data-stu-id="a6cb2-203">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="a6cb2-204">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="a6cb2-204">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="a6cb2-205">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a6cb2-205">Informational(4)</span></span>|
|<span data-ttu-id="a6cb2-206">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="a6cb2-206">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a6cb2-207">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a6cb2-207">Informational(4)</span></span>|

<span data-ttu-id="a6cb2-208">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="a6cb2-208">The following table shows the event information:</span></span>

|<span data-ttu-id="a6cb2-209">Event</span><span class="sxs-lookup"><span data-stu-id="a6cb2-209">Event</span></span>|<span data-ttu-id="a6cb2-210">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a6cb2-210">Event ID</span></span>|<span data-ttu-id="a6cb2-211">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a6cb2-211">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadAppDomainEnter`|<span data-ttu-id="a6cb2-212">87</span><span class="sxs-lookup"><span data-stu-id="a6cb2-212">87</span></span>|<span data-ttu-id="a6cb2-213">线程进入应用程序域。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-213">A thread enters an application domain.</span></span>|

<span data-ttu-id="a6cb2-214">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="a6cb2-214">The following table shows the event data:</span></span>

|<span data-ttu-id="a6cb2-215">字段名</span><span class="sxs-lookup"><span data-stu-id="a6cb2-215">Field name</span></span>|<span data-ttu-id="a6cb2-216">数据类型</span><span class="sxs-lookup"><span data-stu-id="a6cb2-216">Data type</span></span>|<span data-ttu-id="a6cb2-217">描述</span><span class="sxs-lookup"><span data-stu-id="a6cb2-217">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="a6cb2-218">ThreadID</span><span class="sxs-lookup"><span data-stu-id="a6cb2-218">ThreadID</span></span>|<span data-ttu-id="a6cb2-219">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a6cb2-219">win:UInt64</span></span>|<span data-ttu-id="a6cb2-220">线程标识符。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-220">The thread identifier.</span></span>|
|<span data-ttu-id="a6cb2-221">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="a6cb2-221">AppDomainID</span></span>|<span data-ttu-id="a6cb2-222">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a6cb2-222">win:UInt64</span></span>|<span data-ttu-id="a6cb2-223">应用程序域标识符。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-223">The application domain identifier.</span></span>|
|<span data-ttu-id="a6cb2-224">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a6cb2-224">ClrInstanceID</span></span>|<span data-ttu-id="a6cb2-225">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a6cb2-225">win:UInt16</span></span>|<span data-ttu-id="a6cb2-226">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-226">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadterminated-event"></a><span data-ttu-id="a6cb2-227">ThreadTerminated 事件</span><span class="sxs-lookup"><span data-stu-id="a6cb2-227">ThreadTerminated Event</span></span>

<span data-ttu-id="a6cb2-228">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="a6cb2-228">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="a6cb2-229">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a6cb2-229">Keyword for raising the event</span></span>|<span data-ttu-id="a6cb2-230">Level</span><span class="sxs-lookup"><span data-stu-id="a6cb2-230">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="a6cb2-231">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="a6cb2-231">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="a6cb2-232">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a6cb2-232">Informational(4)</span></span>|
|<span data-ttu-id="a6cb2-233">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="a6cb2-233">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a6cb2-234">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a6cb2-234">Informational(4)</span></span>|

<span data-ttu-id="a6cb2-235">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="a6cb2-235">The following table shows the event information:</span></span>

|<span data-ttu-id="a6cb2-236">Event</span><span class="sxs-lookup"><span data-stu-id="a6cb2-236">Event</span></span>|<span data-ttu-id="a6cb2-237">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a6cb2-237">Event ID</span></span>|<span data-ttu-id="a6cb2-238">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a6cb2-238">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadTerminated`|<span data-ttu-id="a6cb2-239">86</span><span class="sxs-lookup"><span data-stu-id="a6cb2-239">86</span></span>|<span data-ttu-id="a6cb2-240">线程终止。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-240">A thread terminates.</span></span>|

<span data-ttu-id="a6cb2-241">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="a6cb2-241">The following table shows the event data:</span></span>

|<span data-ttu-id="a6cb2-242">字段名</span><span class="sxs-lookup"><span data-stu-id="a6cb2-242">Field name</span></span>|<span data-ttu-id="a6cb2-243">数据类型</span><span class="sxs-lookup"><span data-stu-id="a6cb2-243">Data type</span></span>|<span data-ttu-id="a6cb2-244">描述</span><span class="sxs-lookup"><span data-stu-id="a6cb2-244">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="a6cb2-245">ThreadID</span><span class="sxs-lookup"><span data-stu-id="a6cb2-245">ThreadID</span></span>|<span data-ttu-id="a6cb2-246">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a6cb2-246">win:UInt64</span></span>|<span data-ttu-id="a6cb2-247">线程标识符。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-247">The thread identifier.</span></span>|
|<span data-ttu-id="a6cb2-248">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="a6cb2-248">AppDomainID</span></span>|<span data-ttu-id="a6cb2-249">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a6cb2-249">win:UInt64</span></span>|<span data-ttu-id="a6cb2-250">应用程序域标识符。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-250">The application domain identifier.</span></span>|
|<span data-ttu-id="a6cb2-251">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a6cb2-251">ClrInstanceID</span></span>|<span data-ttu-id="a6cb2-252">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a6cb2-252">win:UInt16</span></span>|<span data-ttu-id="a6cb2-253">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a6cb2-253">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="a6cb2-254">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6cb2-254">See also</span></span>

- [<span data-ttu-id="a6cb2-255">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="a6cb2-255">CLR ETW Events</span></span>](clr-etw-events.md)
