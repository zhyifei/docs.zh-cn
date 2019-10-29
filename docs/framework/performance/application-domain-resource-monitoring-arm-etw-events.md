---
title: 应用程序域资源监视 (ARM) ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6e1c2a38be6f2c15a118b35925570119b474f096
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040569"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="30325-102">应用程序域资源监视 (ARM) ETW 事件</span><span class="sxs-lookup"><span data-stu-id="30325-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>

<span data-ttu-id="30325-103">这些事件提供有关应用程序域的状态的详细诊断信息。</span><span class="sxs-lookup"><span data-stu-id="30325-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="30325-104">你可以使用这些事件，或使用应用程序域资源监视 (ARM) 功能来获取相同的信息。</span><span class="sxs-lookup"><span data-stu-id="30325-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>

## <a name="threadcreated-event"></a><span data-ttu-id="30325-105">ThreadCreated 事件</span><span class="sxs-lookup"><span data-stu-id="30325-105">ThreadCreated Event</span></span>

<span data-ttu-id="30325-106">在断开的提供程序下此事件也会作为 `ThreadDC` 引发（在 `AppDomainResourceManagementRundownKeyword` 关键字下）。</span><span class="sxs-lookup"><span data-stu-id="30325-106">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="30325-107">这是此类别的断开提供程序下引发的唯一事件。</span><span class="sxs-lookup"><span data-stu-id="30325-107">This is the only event that is raised under the rundown provider in this category.</span></span>

<span data-ttu-id="30325-108">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="30325-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="30325-109">有关详细信息，请参阅[CLR ETW 关键字和级别](clr-etw-keywords-and-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="30325-109">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="30325-110">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="30325-110">Keyword for raising the event</span></span>|<span data-ttu-id="30325-111">层次</span><span class="sxs-lookup"><span data-stu-id="30325-111">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="30325-112">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="30325-112">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="30325-113">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="30325-113">Informational(4)</span></span>|
|<span data-ttu-id="30325-114">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="30325-114">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="30325-115">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="30325-115">Informational(4)</span></span>|

<span data-ttu-id="30325-116">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="30325-116">The following table shows the event information:</span></span>

|<span data-ttu-id="30325-117">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="30325-117">Event</span></span>|<span data-ttu-id="30325-118">事件 ID</span><span class="sxs-lookup"><span data-stu-id="30325-118">Event ID</span></span>|<span data-ttu-id="30325-119">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="30325-119">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadCreated`|<span data-ttu-id="30325-120">85</span><span class="sxs-lookup"><span data-stu-id="30325-120">85</span></span>|<span data-ttu-id="30325-121">已为应用程序域创建了一个线程。</span><span class="sxs-lookup"><span data-stu-id="30325-121">A thread was created for the application domain.</span></span>|

<span data-ttu-id="30325-122">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="30325-122">The following table shows the event data:</span></span>

|<span data-ttu-id="30325-123">字段名</span><span class="sxs-lookup"><span data-stu-id="30325-123">Field name</span></span>|<span data-ttu-id="30325-124">数据类型</span><span class="sxs-lookup"><span data-stu-id="30325-124">Data type</span></span>|<span data-ttu-id="30325-125">描述</span><span class="sxs-lookup"><span data-stu-id="30325-125">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="30325-126">ThreadID</span><span class="sxs-lookup"><span data-stu-id="30325-126">ThreadID</span></span>|<span data-ttu-id="30325-127">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30325-127">win:UInt64</span></span>|<span data-ttu-id="30325-128">已创建的线程 ID。</span><span class="sxs-lookup"><span data-stu-id="30325-128">ID of the thread that was created.</span></span>|
|<span data-ttu-id="30325-129">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="30325-129">AppDomainID</span></span>|<span data-ttu-id="30325-130">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30325-130">win:UInt64</span></span>|<span data-ttu-id="30325-131">正在报告其线程活动的应用程序域的标识符。</span><span class="sxs-lookup"><span data-stu-id="30325-131">Identifier of the application domain for which thread activity is being reported.</span></span>|
|<span data-ttu-id="30325-132">Flags</span><span class="sxs-lookup"><span data-stu-id="30325-132">Flags</span></span>|<span data-ttu-id="30325-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="30325-133">win:UInt32</span></span>|<span data-ttu-id="30325-134">线程创建标志。</span><span class="sxs-lookup"><span data-stu-id="30325-134">Thread creation flags.</span></span>|
|<span data-ttu-id="30325-135">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="30325-135">ManagedThreadIndex</span></span>|<span data-ttu-id="30325-136">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="30325-136">win:UInt32</span></span>|<span data-ttu-id="30325-137">已创建线程的托管索引。</span><span class="sxs-lookup"><span data-stu-id="30325-137">Managed index of the thread that was created.</span></span>|
|<span data-ttu-id="30325-138">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="30325-138">OSThreadID</span></span>|<span data-ttu-id="30325-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="30325-139">win:UInt32</span></span>|<span data-ttu-id="30325-140">已创建线程的操作系统 ID。</span><span class="sxs-lookup"><span data-stu-id="30325-140">Operating system ID of the thread that was created.</span></span>|
|<span data-ttu-id="30325-141">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="30325-141">ClrInstanceID</span></span>|<span data-ttu-id="30325-142">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="30325-142">win:UInt16</span></span>|<span data-ttu-id="30325-143">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="30325-143">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemallocated-event"></a><span data-ttu-id="30325-144">AppDomainMemAllocated 事件</span><span class="sxs-lookup"><span data-stu-id="30325-144">AppDomainMemAllocated Event</span></span>

<span data-ttu-id="30325-145">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="30325-145">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="30325-146">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="30325-146">Keyword for raising the event</span></span>|<span data-ttu-id="30325-147">层次</span><span class="sxs-lookup"><span data-stu-id="30325-147">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="30325-148">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="30325-148">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="30325-149">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="30325-149">Informational(4)</span></span>|

<span data-ttu-id="30325-150">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="30325-150">The following table shows the event information:</span></span>

|<span data-ttu-id="30325-151">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="30325-151">Event</span></span>|<span data-ttu-id="30325-152">事件 ID</span><span class="sxs-lookup"><span data-stu-id="30325-152">Event ID</span></span>|<span data-ttu-id="30325-153">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="30325-153">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemAllocated`|<span data-ttu-id="30325-154">83</span><span class="sxs-lookup"><span data-stu-id="30325-154">83</span></span>|<span data-ttu-id="30325-155">应用程序域中分配每 4 MB 的内存（大约）。</span><span class="sxs-lookup"><span data-stu-id="30325-155">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|

<span data-ttu-id="30325-156">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="30325-156">The following table shows the event data:</span></span>

|<span data-ttu-id="30325-157">字段名</span><span class="sxs-lookup"><span data-stu-id="30325-157">Field name</span></span>|<span data-ttu-id="30325-158">数据类型</span><span class="sxs-lookup"><span data-stu-id="30325-158">Data type</span></span>|<span data-ttu-id="30325-159">描述</span><span class="sxs-lookup"><span data-stu-id="30325-159">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="30325-160">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="30325-160">AppDomainID</span></span>|<span data-ttu-id="30325-161">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30325-161">win:UInt64</span></span>|<span data-ttu-id="30325-162">正在报告其资源使用情况的应用程序域的标识符。</span><span class="sxs-lookup"><span data-stu-id="30325-162">Identifier of the application domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="30325-163">已分配</span><span class="sxs-lookup"><span data-stu-id="30325-163">Allocated</span></span>|<span data-ttu-id="30325-164">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30325-164">win:UInt64</span></span>|<span data-ttu-id="30325-165">自应用程序域创建以来在此应用程序域中分配的字节总数（不减去已释放的内存量）。</span><span class="sxs-lookup"><span data-stu-id="30325-165">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|
|<span data-ttu-id="30325-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="30325-166">ClrInstanceID</span></span>|<span data-ttu-id="30325-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="30325-167">win:UInt16</span></span>|<span data-ttu-id="30325-168">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="30325-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="30325-169">AppDomainMemSurvived 事件</span><span class="sxs-lookup"><span data-stu-id="30325-169">AppDomainMemSurvived Event</span></span>

<span data-ttu-id="30325-170">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="30325-170">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="30325-171">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="30325-171">Keyword for raising the event</span></span>|<span data-ttu-id="30325-172">层次</span><span class="sxs-lookup"><span data-stu-id="30325-172">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="30325-173">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="30325-173">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="30325-174">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="30325-174">Informational(4)</span></span>|

<span data-ttu-id="30325-175">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="30325-175">The following table shows the event information:</span></span>

|<span data-ttu-id="30325-176">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="30325-176">Event</span></span>|<span data-ttu-id="30325-177">事件 ID</span><span class="sxs-lookup"><span data-stu-id="30325-177">Event ID</span></span>|<span data-ttu-id="30325-178">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="30325-178">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemSurvived`|<span data-ttu-id="30325-179">84</span><span class="sxs-lookup"><span data-stu-id="30325-179">84</span></span>|<span data-ttu-id="30325-180">每个垃圾回收已结束。</span><span class="sxs-lookup"><span data-stu-id="30325-180">Each garbage collection has ended.</span></span>|

<span data-ttu-id="30325-181">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="30325-181">The following table shows the event data:</span></span>

|<span data-ttu-id="30325-182">字段名</span><span class="sxs-lookup"><span data-stu-id="30325-182">Field name</span></span>|<span data-ttu-id="30325-183">数据类型</span><span class="sxs-lookup"><span data-stu-id="30325-183">Data type</span></span>|<span data-ttu-id="30325-184">描述</span><span class="sxs-lookup"><span data-stu-id="30325-184">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="30325-185">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="30325-185">AppDomainID</span></span>|<span data-ttu-id="30325-186">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30325-186">win:UInt64</span></span>|<span data-ttu-id="30325-187">正在报告其资源使用情况的域的标识符。</span><span class="sxs-lookup"><span data-stu-id="30325-187">Identifier of the domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="30325-188">已保留</span><span class="sxs-lookup"><span data-stu-id="30325-188">Survived</span></span>|<span data-ttu-id="30325-189">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30325-189">win:UInt64</span></span>|<span data-ttu-id="30325-190">上次回收后保留下来的、已知由此应用程序域保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="30325-190">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="30325-191">此数字在完整回收之后准确且完整，但在暂时的回收之后可能不完整。</span><span class="sxs-lookup"><span data-stu-id="30325-191">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|
|<span data-ttu-id="30325-192">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="30325-192">ProcessSurvived</span></span>|<span data-ttu-id="30325-193">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30325-193">win:UInt64</span></span>|<span data-ttu-id="30325-194">从上一次回收中保留的总字节数。</span><span class="sxs-lookup"><span data-stu-id="30325-194">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="30325-195">完整回收之后，该数字表示托管堆中实时保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="30325-195">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="30325-196">暂时回收之后，该数字表示暂时生成中实时保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="30325-196">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|
|<span data-ttu-id="30325-197">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="30325-197">ClrInstanceID</span></span>|<span data-ttu-id="30325-198">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="30325-198">win:UInt16</span></span>|<span data-ttu-id="30325-199">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="30325-199">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadappdomainenter-event"></a><span data-ttu-id="30325-200">ThreadAppDomainEnter 事件</span><span class="sxs-lookup"><span data-stu-id="30325-200">ThreadAppDomainEnter Event</span></span>

<span data-ttu-id="30325-201">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="30325-201">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="30325-202">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="30325-202">Keyword for raising the event</span></span>|<span data-ttu-id="30325-203">层次</span><span class="sxs-lookup"><span data-stu-id="30325-203">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="30325-204">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="30325-204">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="30325-205">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="30325-205">Informational(4)</span></span>|
|<span data-ttu-id="30325-206">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="30325-206">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="30325-207">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="30325-207">Informational(4)</span></span>|

<span data-ttu-id="30325-208">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="30325-208">The following table shows the event information:</span></span>

|<span data-ttu-id="30325-209">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="30325-209">Event</span></span>|<span data-ttu-id="30325-210">事件 ID</span><span class="sxs-lookup"><span data-stu-id="30325-210">Event ID</span></span>|<span data-ttu-id="30325-211">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="30325-211">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadAppDomainEnter`|<span data-ttu-id="30325-212">87</span><span class="sxs-lookup"><span data-stu-id="30325-212">87</span></span>|<span data-ttu-id="30325-213">线程进入应用程序域。</span><span class="sxs-lookup"><span data-stu-id="30325-213">A thread enters an application domain.</span></span>|

<span data-ttu-id="30325-214">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="30325-214">The following table shows the event data:</span></span>

|<span data-ttu-id="30325-215">字段名</span><span class="sxs-lookup"><span data-stu-id="30325-215">Field name</span></span>|<span data-ttu-id="30325-216">数据类型</span><span class="sxs-lookup"><span data-stu-id="30325-216">Data type</span></span>|<span data-ttu-id="30325-217">描述</span><span class="sxs-lookup"><span data-stu-id="30325-217">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="30325-218">ThreadID</span><span class="sxs-lookup"><span data-stu-id="30325-218">ThreadID</span></span>|<span data-ttu-id="30325-219">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30325-219">win:UInt64</span></span>|<span data-ttu-id="30325-220">线程标识符。</span><span class="sxs-lookup"><span data-stu-id="30325-220">The thread identifier.</span></span>|
|<span data-ttu-id="30325-221">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="30325-221">AppDomainID</span></span>|<span data-ttu-id="30325-222">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30325-222">win:UInt64</span></span>|<span data-ttu-id="30325-223">应用程序域标识符。</span><span class="sxs-lookup"><span data-stu-id="30325-223">The application domain identifier.</span></span>|
|<span data-ttu-id="30325-224">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="30325-224">ClrInstanceID</span></span>|<span data-ttu-id="30325-225">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="30325-225">win:UInt16</span></span>|<span data-ttu-id="30325-226">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="30325-226">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadterminated-event"></a><span data-ttu-id="30325-227">ThreadTerminated 事件</span><span class="sxs-lookup"><span data-stu-id="30325-227">ThreadTerminated Event</span></span>

<span data-ttu-id="30325-228">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="30325-228">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="30325-229">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="30325-229">Keyword for raising the event</span></span>|<span data-ttu-id="30325-230">层次</span><span class="sxs-lookup"><span data-stu-id="30325-230">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="30325-231">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="30325-231">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="30325-232">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="30325-232">Informational(4)</span></span>|
|<span data-ttu-id="30325-233">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="30325-233">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="30325-234">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="30325-234">Informational(4)</span></span>|

<span data-ttu-id="30325-235">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="30325-235">The following table shows the event information:</span></span>

|<span data-ttu-id="30325-236">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="30325-236">Event</span></span>|<span data-ttu-id="30325-237">事件 ID</span><span class="sxs-lookup"><span data-stu-id="30325-237">Event ID</span></span>|<span data-ttu-id="30325-238">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="30325-238">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadTerminated`|<span data-ttu-id="30325-239">86</span><span class="sxs-lookup"><span data-stu-id="30325-239">86</span></span>|<span data-ttu-id="30325-240">线程终止。</span><span class="sxs-lookup"><span data-stu-id="30325-240">A thread terminates.</span></span>|

<span data-ttu-id="30325-241">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="30325-241">The following table shows the event data:</span></span>

|<span data-ttu-id="30325-242">字段名</span><span class="sxs-lookup"><span data-stu-id="30325-242">Field name</span></span>|<span data-ttu-id="30325-243">数据类型</span><span class="sxs-lookup"><span data-stu-id="30325-243">Data type</span></span>|<span data-ttu-id="30325-244">描述</span><span class="sxs-lookup"><span data-stu-id="30325-244">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="30325-245">ThreadID</span><span class="sxs-lookup"><span data-stu-id="30325-245">ThreadID</span></span>|<span data-ttu-id="30325-246">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30325-246">win:UInt64</span></span>|<span data-ttu-id="30325-247">线程标识符。</span><span class="sxs-lookup"><span data-stu-id="30325-247">The thread identifier.</span></span>|
|<span data-ttu-id="30325-248">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="30325-248">AppDomainID</span></span>|<span data-ttu-id="30325-249">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30325-249">win:UInt64</span></span>|<span data-ttu-id="30325-250">应用程序域标识符。</span><span class="sxs-lookup"><span data-stu-id="30325-250">The application domain identifier.</span></span>|
|<span data-ttu-id="30325-251">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="30325-251">ClrInstanceID</span></span>|<span data-ttu-id="30325-252">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="30325-252">win:UInt16</span></span>|<span data-ttu-id="30325-253">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="30325-253">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="30325-254">请参阅</span><span class="sxs-lookup"><span data-stu-id="30325-254">See also</span></span>

- [<span data-ttu-id="30325-255">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="30325-255">CLR ETW Events</span></span>](clr-etw-events.md)
