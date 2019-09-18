---
title: 方法 ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, method events (CLR)
- method events [.NET Framework]
ms.assetid: 167a4459-bb6e-476c-9046-7920880f2bb5
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 58249a0e080e045223bdaf170f2eaedb67fc0dea
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046376"
---
# <a name="method-etw-events"></a><span data-ttu-id="22df3-102">方法 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="22df3-102">Method ETW Events</span></span>

<a name="top"></a> <span data-ttu-id="22df3-103">这些事件收集特定于方法的信息。</span><span class="sxs-lookup"><span data-stu-id="22df3-103">These events collect information that is specific to methods.</span></span> <span data-ttu-id="22df3-104">符号解析需要这些事件的负载。</span><span class="sxs-lookup"><span data-stu-id="22df3-104">The payload of these events is required for symbol resolution.</span></span> <span data-ttu-id="22df3-105">此外，这些事件还提供如调用方法的次数等有用信息。</span><span class="sxs-lookup"><span data-stu-id="22df3-105">In addition, these events provide helpful information such as the number of times a method was called.</span></span>

<span data-ttu-id="22df3-106">所有方法事件都具有“信息性 (4)”级别。</span><span class="sxs-lookup"><span data-stu-id="22df3-106">All method events have a level of "Informational (4)".</span></span> <span data-ttu-id="22df3-107">所有方法的详细事件都具有“详细级别 (5)”级别。</span><span class="sxs-lookup"><span data-stu-id="22df3-107">All method verbose events have a level of "Verbose (5)".</span></span>

<span data-ttu-id="22df3-108">所有方法事件都是由运行时提供程序下的 `JITKeyword` (0x10) 关键字或 `NGenKeyword` (0x20) 关键字引发的，或是由断开提供程序下的 `JitRundownKeyword` (0x10) 或 `NGENRundownKeyword` (0x20) 引发的。</span><span class="sxs-lookup"><span data-stu-id="22df3-108">All method events are raised by the `JITKeyword` (0x10) keyword or the `NGenKeyword` (0x20) keyword under the runtime provider, or `JitRundownKeyword` (0x10) or `NGENRundownKeyword` (0x20) under the rundown provider.</span></span>

<span data-ttu-id="22df3-109">CLR 方法事件进一步细分为以下几类：</span><span class="sxs-lookup"><span data-stu-id="22df3-109">CLR method events are further subdivided into the following:</span></span>

- [<span data-ttu-id="22df3-110">CLR 方法事件</span><span class="sxs-lookup"><span data-stu-id="22df3-110">CLR Method Events</span></span>](#clr_method_events)

- [<span data-ttu-id="22df3-111">CLR 方法标记事件</span><span class="sxs-lookup"><span data-stu-id="22df3-111">CLR Method Marker Events</span></span>](#clr_method_marker_events)

- [<span data-ttu-id="22df3-112">CLR 方法详细事件</span><span class="sxs-lookup"><span data-stu-id="22df3-112">CLR Method Verbose Events</span></span>](#clr_method_verbose_events)

- [<span data-ttu-id="22df3-113">MethodJittingStarted 事件</span><span class="sxs-lookup"><span data-stu-id="22df3-113">MethodJittingStarted Event</span></span>](#methodjittingstarted_event)

<a name="clr_method_events"></a>

## <a name="clr-method-events"></a><span data-ttu-id="22df3-114">CLR 方法事件</span><span class="sxs-lookup"><span data-stu-id="22df3-114">CLR Method Events</span></span>

<span data-ttu-id="22df3-115">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="22df3-115">The following table shows the keyword and level.</span></span> <span data-ttu-id="22df3-116">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="22df3-116">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>

|<span data-ttu-id="22df3-117">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="22df3-117">Keyword for raising the event</span></span>|<span data-ttu-id="22df3-118">Level</span><span class="sxs-lookup"><span data-stu-id="22df3-118">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="22df3-119">`JITKeyword` (0x10) 运行时提供程序</span><span class="sxs-lookup"><span data-stu-id="22df3-119">`JITKeyword` (0x10) runtime provider</span></span>|<span data-ttu-id="22df3-120">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="22df3-120">Informational (4)</span></span>|
|<span data-ttu-id="22df3-121">`NGenKeyword` (0x20) 运行时提供程序</span><span class="sxs-lookup"><span data-stu-id="22df3-121">`NGenKeyword` (0x20) runtime provider</span></span>|<span data-ttu-id="22df3-122">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="22df3-122">Informational (4)</span></span>|
|<span data-ttu-id="22df3-123">`JitRundownKeyword` (0x10) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="22df3-123">`JitRundownKeyword` (0x10) rundown provider</span></span>|<span data-ttu-id="22df3-124">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="22df3-124">Informational (4)</span></span>|
|<span data-ttu-id="22df3-125">`NGENRundownKeyword` (0x20) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="22df3-125">`NGENRundownKeyword` (0x20) rundown provider</span></span>|<span data-ttu-id="22df3-126">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="22df3-126">Informational (4)</span></span>|

<span data-ttu-id="22df3-127">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="22df3-127">The following table shows the event information.</span></span>

|<span data-ttu-id="22df3-128">Event</span><span class="sxs-lookup"><span data-stu-id="22df3-128">Event</span></span>|<span data-ttu-id="22df3-129">事件 ID</span><span class="sxs-lookup"><span data-stu-id="22df3-129">Event ID</span></span>|<span data-ttu-id="22df3-130">描述</span><span class="sxs-lookup"><span data-stu-id="22df3-130">Description</span></span>|
|-----------|--------------|-----------------|
|`MethodLoad_V1`|<span data-ttu-id="22df3-131">136</span><span class="sxs-lookup"><span data-stu-id="22df3-131">136</span></span>|<span data-ttu-id="22df3-132">在实时加载（JIT 加载）方法或者加载 NGEN 映像时引发。</span><span class="sxs-lookup"><span data-stu-id="22df3-132">Raised when a method is just-in-time loaded (JIT-loaded) or an NGEN image is loaded.</span></span> <span data-ttu-id="22df3-133">动态和泛型方法不使用此版本进行方法加载。</span><span class="sxs-lookup"><span data-stu-id="22df3-133">Dynamic and generic methods do not use this version for method loads.</span></span> <span data-ttu-id="22df3-134">JIT 帮助器从不使用此版本。</span><span class="sxs-lookup"><span data-stu-id="22df3-134">JIT helpers never use this version.</span></span>|
|`MethodUnLoad_V1`|<span data-ttu-id="22df3-135">137</span><span class="sxs-lookup"><span data-stu-id="22df3-135">137</span></span>|<span data-ttu-id="22df3-136">在卸载模块或销毁应用程序域时引发。</span><span class="sxs-lookup"><span data-stu-id="22df3-136">Raised when a module is unloaded, or an application domain is destroyed.</span></span> <span data-ttu-id="22df3-137">动态方法从不使用此版本进行方法卸载。</span><span class="sxs-lookup"><span data-stu-id="22df3-137">Dynamic methods never use this version for method unloads.</span></span>|
|`MethodDCStart_V1`|<span data-ttu-id="22df3-138">137</span><span class="sxs-lookup"><span data-stu-id="22df3-138">137</span></span>|<span data-ttu-id="22df3-139">启动断开期间的枚举方法。</span><span class="sxs-lookup"><span data-stu-id="22df3-139">Enumerates methods during a start rundown.</span></span>|
|`MethodDCEnd_V1`|<span data-ttu-id="22df3-140">138</span><span class="sxs-lookup"><span data-stu-id="22df3-140">138</span></span>|<span data-ttu-id="22df3-141">结束断开期间的枚举方法。</span><span class="sxs-lookup"><span data-stu-id="22df3-141">Enumerates methods during an end rundown.</span></span>|

<span data-ttu-id="22df3-142">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="22df3-142">The following table shows the event data.</span></span>

|<span data-ttu-id="22df3-143">字段名</span><span class="sxs-lookup"><span data-stu-id="22df3-143">Field name</span></span>|<span data-ttu-id="22df3-144">数据类型</span><span class="sxs-lookup"><span data-stu-id="22df3-144">Data type</span></span>|<span data-ttu-id="22df3-145">描述</span><span class="sxs-lookup"><span data-stu-id="22df3-145">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="22df3-146">MethodID</span><span class="sxs-lookup"><span data-stu-id="22df3-146">MethodID</span></span>|<span data-ttu-id="22df3-147">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="22df3-147">win:UInt64</span></span>|<span data-ttu-id="22df3-148">方法的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="22df3-148">Unique identifier of a method.</span></span> <span data-ttu-id="22df3-149">对于 JIT 帮助器方法，将设置为该方法的起始地址。</span><span class="sxs-lookup"><span data-stu-id="22df3-149">For JIT helper methods, this is set to the start address of the method.</span></span>|
|<span data-ttu-id="22df3-150">ModuleID</span><span class="sxs-lookup"><span data-stu-id="22df3-150">ModuleID</span></span>|<span data-ttu-id="22df3-151">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="22df3-151">win:UInt64</span></span>|<span data-ttu-id="22df3-152">此方法所属的模块标识符（0 表示 JIT 帮助器）。</span><span class="sxs-lookup"><span data-stu-id="22df3-152">Identifier of the module to which this method belongs (0 for JIT helpers).</span></span>|
|<span data-ttu-id="22df3-153">MethodStartAddress</span><span class="sxs-lookup"><span data-stu-id="22df3-153">MethodStartAddress</span></span>|<span data-ttu-id="22df3-154">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="22df3-154">win:UInt64</span></span>|<span data-ttu-id="22df3-155">方法的起始地址。</span><span class="sxs-lookup"><span data-stu-id="22df3-155">Start address of the method.</span></span>|
|<span data-ttu-id="22df3-156">MethodSize</span><span class="sxs-lookup"><span data-stu-id="22df3-156">MethodSize</span></span>|<span data-ttu-id="22df3-157">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="22df3-157">win:UInt32</span></span>|<span data-ttu-id="22df3-158">方法的大小。</span><span class="sxs-lookup"><span data-stu-id="22df3-158">Size of the method.</span></span>|
|<span data-ttu-id="22df3-159">MethodToken</span><span class="sxs-lookup"><span data-stu-id="22df3-159">MethodToken</span></span>|<span data-ttu-id="22df3-160">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="22df3-160">win:UInt32</span></span>|<span data-ttu-id="22df3-161">0 代表动态方法和 JIT 帮助器。</span><span class="sxs-lookup"><span data-stu-id="22df3-161">0 for dynamic methods and JIT helpers.</span></span>|
|<span data-ttu-id="22df3-162">MethodFlags</span><span class="sxs-lookup"><span data-stu-id="22df3-162">MethodFlags</span></span>|<span data-ttu-id="22df3-163">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="22df3-163">win:UInt32</span></span>|<span data-ttu-id="22df3-164">0x1动态方法。</span><span class="sxs-lookup"><span data-stu-id="22df3-164">0x1: Dynamic method.</span></span><br /><br /> <span data-ttu-id="22df3-165">0x2泛型方法。</span><span class="sxs-lookup"><span data-stu-id="22df3-165">0x2: Generic method.</span></span><br /><br /> <span data-ttu-id="22df3-166">0x4JIT 编译的代码方法（否则为 NGEN 本机映像代码）。</span><span class="sxs-lookup"><span data-stu-id="22df3-166">0x4: JIT-compiled code method (otherwise NGEN native image code).</span></span><br /><br /> <span data-ttu-id="22df3-167">0x8Helper 方法。</span><span class="sxs-lookup"><span data-stu-id="22df3-167">0x8: Helper method.</span></span>|
|<span data-ttu-id="22df3-168">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="22df3-168">ClrInstanceID</span></span>|<span data-ttu-id="22df3-169">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="22df3-169">win:UInt16</span></span>|<span data-ttu-id="22df3-170">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="22df3-170">Unique ID for the instance of CLR or CoreCLR.</span></span>|

[<span data-ttu-id="22df3-171">返回页首</span><span class="sxs-lookup"><span data-stu-id="22df3-171">Back to top</span></span>](#top)

<a name="clr_method_marker_events"></a>

## <a name="clr-method-marker-events"></a><span data-ttu-id="22df3-172">CLR 方法标记事件</span><span class="sxs-lookup"><span data-stu-id="22df3-172">CLR Method Marker Events</span></span>

<span data-ttu-id="22df3-173">仅在断开提供程序中会引发这些事件。</span><span class="sxs-lookup"><span data-stu-id="22df3-173">These events are raised only under the rundown provider.</span></span> <span data-ttu-id="22df3-174">它们表示在启动或结束断开期间方法枚举的结束。</span><span class="sxs-lookup"><span data-stu-id="22df3-174">They signify the end of method enumeration during a start or end rundown.</span></span> <span data-ttu-id="22df3-175">（即，启用 `NGENRundownKeyword`、 `JitRundownKeyword`、 `LoaderRundownKeyword`或 `AppDomainResourceManagementRundownKeyword` 关键字时引发。）</span><span class="sxs-lookup"><span data-stu-id="22df3-175">(That is, they are raised when the `NGENRundownKeyword`, `JitRundownKeyword`, `LoaderRundownKeyword`, or `AppDomainResourceManagementRundownKeyword` keyword is enabled.)</span></span>

<span data-ttu-id="22df3-176">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="22df3-176">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="22df3-177">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="22df3-177">Keyword for raising the event</span></span>|<span data-ttu-id="22df3-178">Level</span><span class="sxs-lookup"><span data-stu-id="22df3-178">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="22df3-179">`AppDomainResourceManagementRundownKeyword` (0x800) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="22df3-179">`AppDomainResourceManagementRundownKeyword` (0x800) rundown provider</span></span>|<span data-ttu-id="22df3-180">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="22df3-180">Informational (4)</span></span>|
|<span data-ttu-id="22df3-181">`JitRundownKeyword` (0x10) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="22df3-181">`JitRundownKeyword` (0x10) rundown provider</span></span>|<span data-ttu-id="22df3-182">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="22df3-182">Informational (4)</span></span>|
|<span data-ttu-id="22df3-183">`NGENRundownKeyword` (0x20) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="22df3-183">`NGENRundownKeyword` (0x20) rundown provider</span></span>|<span data-ttu-id="22df3-184">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="22df3-184">Informational (4)</span></span>|

<span data-ttu-id="22df3-185">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="22df3-185">The following table shows the event information.</span></span>

|<span data-ttu-id="22df3-186">Event</span><span class="sxs-lookup"><span data-stu-id="22df3-186">Event</span></span>|<span data-ttu-id="22df3-187">事件 ID</span><span class="sxs-lookup"><span data-stu-id="22df3-187">Event ID</span></span>|<span data-ttu-id="22df3-188">描述</span><span class="sxs-lookup"><span data-stu-id="22df3-188">Description</span></span>|
|-----------|--------------|----------------|
|`DCStartInit_V1`|<span data-ttu-id="22df3-189">147</span><span class="sxs-lookup"><span data-stu-id="22df3-189">147</span></span>|<span data-ttu-id="22df3-190">启动断开期间枚举开始之前发送。</span><span class="sxs-lookup"><span data-stu-id="22df3-190">Sent before the start of the enumeration during a start rundown.</span></span>|
|`DCStartComplete_V1`|<span data-ttu-id="22df3-191">145</span><span class="sxs-lookup"><span data-stu-id="22df3-191">145</span></span>|<span data-ttu-id="22df3-192">启动断开期间枚举结束时发送。</span><span class="sxs-lookup"><span data-stu-id="22df3-192">Sent at the end of the enumeration during a start rundown.</span></span>|
|`DCEndInit_V1`|<span data-ttu-id="22df3-193">148</span><span class="sxs-lookup"><span data-stu-id="22df3-193">148</span></span>|<span data-ttu-id="22df3-194">结束断开期间枚举开始之前发送。</span><span class="sxs-lookup"><span data-stu-id="22df3-194">Sent before the start of the enumeration during an end rundown.</span></span>|
|`DCEndComplete_V1`|<span data-ttu-id="22df3-195">146</span><span class="sxs-lookup"><span data-stu-id="22df3-195">146</span></span>|<span data-ttu-id="22df3-196">结束断开期间枚举结束时发送。</span><span class="sxs-lookup"><span data-stu-id="22df3-196">Sent at the end of the enumeration during an end rundown.</span></span>|

<span data-ttu-id="22df3-197">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="22df3-197">The following table shows the event data.</span></span>

|<span data-ttu-id="22df3-198">字段名</span><span class="sxs-lookup"><span data-stu-id="22df3-198">Field name</span></span>|<span data-ttu-id="22df3-199">数据类型</span><span class="sxs-lookup"><span data-stu-id="22df3-199">Data type</span></span>|<span data-ttu-id="22df3-200">描述</span><span class="sxs-lookup"><span data-stu-id="22df3-200">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="22df3-201">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="22df3-201">ClrInstanceID</span></span>|<span data-ttu-id="22df3-202">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="22df3-202">win:UInt16</span></span>|<span data-ttu-id="22df3-203">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="22df3-203">Unique ID for the instance of CLR or CoreCLR.</span></span>|

[<span data-ttu-id="22df3-204">返回页首</span><span class="sxs-lookup"><span data-stu-id="22df3-204">Back to top</span></span>](#top)

<a name="clr_method_verbose_events"></a>

## <a name="clr-method-verbose-events"></a><span data-ttu-id="22df3-205">CLR 方法详细事件</span><span class="sxs-lookup"><span data-stu-id="22df3-205">CLR Method Verbose Events</span></span>

<span data-ttu-id="22df3-206">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="22df3-206">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="22df3-207">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="22df3-207">Keyword for raising the event</span></span>|<span data-ttu-id="22df3-208">Level</span><span class="sxs-lookup"><span data-stu-id="22df3-208">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="22df3-209">`JITKeyword` (0x10) 运行时提供程序</span><span class="sxs-lookup"><span data-stu-id="22df3-209">`JITKeyword` (0x10) runtime provider</span></span>|<span data-ttu-id="22df3-210">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="22df3-210">Verbose (5)</span></span>|
|<span data-ttu-id="22df3-211">`NGenKeyword` (0x20) 运行时提供程序</span><span class="sxs-lookup"><span data-stu-id="22df3-211">`NGenKeyword` (0x20) runtime provider</span></span>|<span data-ttu-id="22df3-212">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="22df3-212">Verbose (5)</span></span>|
|<span data-ttu-id="22df3-213">`JitRundownKeyword` (0x10) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="22df3-213">`JitRundownKeyword` (0x10) rundown provider</span></span>|<span data-ttu-id="22df3-214">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="22df3-214">Verbose (5)</span></span>|
|<span data-ttu-id="22df3-215">`NGENRundownKeyword` (0x20) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="22df3-215">`NGENRundownKeyword` (0x20) rundown provider</span></span>|<span data-ttu-id="22df3-216">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="22df3-216">Verbose (5)</span></span>|

<span data-ttu-id="22df3-217">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="22df3-217">The following table shows the event information.</span></span>

|<span data-ttu-id="22df3-218">Event</span><span class="sxs-lookup"><span data-stu-id="22df3-218">Event</span></span>|<span data-ttu-id="22df3-219">事件 ID</span><span class="sxs-lookup"><span data-stu-id="22df3-219">Event ID</span></span>|<span data-ttu-id="22df3-220">描述</span><span class="sxs-lookup"><span data-stu-id="22df3-220">Description</span></span>|
|-----------|--------------|-----------------|
|`MethodLoadVerbose_V1`|<span data-ttu-id="22df3-221">143</span><span class="sxs-lookup"><span data-stu-id="22df3-221">143</span></span>|<span data-ttu-id="22df3-222">当方法为 JIT 加载的或加载 NGEN 映像时引发。</span><span class="sxs-lookup"><span data-stu-id="22df3-222">Raised when a method is JIT-loaded or an NGEN image is loaded.</span></span> <span data-ttu-id="22df3-223">动态和泛型方法始终使用此版本进行方法加载。</span><span class="sxs-lookup"><span data-stu-id="22df3-223">Dynamic and generic methods always use this version for method loads.</span></span> <span data-ttu-id="22df3-224">JIT 帮助器始终使用此版本。</span><span class="sxs-lookup"><span data-stu-id="22df3-224">JIT helpers always use this version.</span></span>|
|`MethodUnLoadVerbose_V1`|<span data-ttu-id="22df3-225">144</span><span class="sxs-lookup"><span data-stu-id="22df3-225">144</span></span>|<span data-ttu-id="22df3-226">在销毁动态方法、卸载模块或销毁应用程序域时引发。</span><span class="sxs-lookup"><span data-stu-id="22df3-226">Raised when a dynamic method is destroyed, a module is unloaded, or an application domain is destroyed.</span></span> <span data-ttu-id="22df3-227">动态方法始终使用此版本进行方法卸载。</span><span class="sxs-lookup"><span data-stu-id="22df3-227">Dynamic methods always use this version for method unloads.</span></span>|
|`MethodDCStartVerbose_V1`|<span data-ttu-id="22df3-228">141</span><span class="sxs-lookup"><span data-stu-id="22df3-228">141</span></span>|<span data-ttu-id="22df3-229">启动断开期间的枚举方法。</span><span class="sxs-lookup"><span data-stu-id="22df3-229">Enumerates methods during a start rundown.</span></span>|
|`MethodDCEndVerbose_V1`|<span data-ttu-id="22df3-230">142</span><span class="sxs-lookup"><span data-stu-id="22df3-230">142</span></span>|<span data-ttu-id="22df3-231">结束断开期间的枚举方法。</span><span class="sxs-lookup"><span data-stu-id="22df3-231">Enumerates methods during an end rundown.</span></span>|

<span data-ttu-id="22df3-232">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="22df3-232">The following table shows the event data.</span></span>

|<span data-ttu-id="22df3-233">字段名</span><span class="sxs-lookup"><span data-stu-id="22df3-233">Field name</span></span>|<span data-ttu-id="22df3-234">数据类型</span><span class="sxs-lookup"><span data-stu-id="22df3-234">Data type</span></span>|<span data-ttu-id="22df3-235">描述</span><span class="sxs-lookup"><span data-stu-id="22df3-235">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="22df3-236">MethodID</span><span class="sxs-lookup"><span data-stu-id="22df3-236">MethodID</span></span>|<span data-ttu-id="22df3-237">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="22df3-237">win:UInt64</span></span>|<span data-ttu-id="22df3-238">方法的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="22df3-238">Unique identifier of the method.</span></span> <span data-ttu-id="22df3-239">对于 JIT 帮助器方法，将设置为该方法的起始地址。</span><span class="sxs-lookup"><span data-stu-id="22df3-239">For JIT helper methods, set to the start address of the method.</span></span>|
|<span data-ttu-id="22df3-240">ModuleID</span><span class="sxs-lookup"><span data-stu-id="22df3-240">ModuleID</span></span>|<span data-ttu-id="22df3-241">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="22df3-241">win:UInt64</span></span>|<span data-ttu-id="22df3-242">此方法所属的模块标识符（0 表示 JIT 帮助器）。</span><span class="sxs-lookup"><span data-stu-id="22df3-242">Identifier of the module to which this method belongs (0 for JIT helpers).</span></span>|
|<span data-ttu-id="22df3-243">MethodStartAddress</span><span class="sxs-lookup"><span data-stu-id="22df3-243">MethodStartAddress</span></span>|<span data-ttu-id="22df3-244">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="22df3-244">win:UInt64</span></span>|<span data-ttu-id="22df3-245">起始地址。</span><span class="sxs-lookup"><span data-stu-id="22df3-245">Start address.</span></span>|
|<span data-ttu-id="22df3-246">MethodSize</span><span class="sxs-lookup"><span data-stu-id="22df3-246">MethodSize</span></span>|<span data-ttu-id="22df3-247">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="22df3-247">win:UInt32</span></span>|<span data-ttu-id="22df3-248">方法长度。</span><span class="sxs-lookup"><span data-stu-id="22df3-248">Method length.</span></span>|
|<span data-ttu-id="22df3-249">MethodToken</span><span class="sxs-lookup"><span data-stu-id="22df3-249">MethodToken</span></span>|<span data-ttu-id="22df3-250">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="22df3-250">win:UInt32</span></span>|<span data-ttu-id="22df3-251">0 代表动态方法和 JIT 帮助器。</span><span class="sxs-lookup"><span data-stu-id="22df3-251">0 for dynamic methods and JIT helpers.</span></span>|
|<span data-ttu-id="22df3-252">MethodFlags</span><span class="sxs-lookup"><span data-stu-id="22df3-252">MethodFlags</span></span>|<span data-ttu-id="22df3-253">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="22df3-253">win:UInt32</span></span>|<span data-ttu-id="22df3-254">0x1动态方法。</span><span class="sxs-lookup"><span data-stu-id="22df3-254">0x1: Dynamic method.</span></span><br /><br /> <span data-ttu-id="22df3-255">0x2泛型方法。</span><span class="sxs-lookup"><span data-stu-id="22df3-255">0x2: Generic method.</span></span><br /><br /> <span data-ttu-id="22df3-256">0x4JIT 编译的方法（否则由 Ngen.exe 生成）</span><span class="sxs-lookup"><span data-stu-id="22df3-256">0x4: JIT-compiled method (otherwise, generated by NGen.exe)</span></span><br /><br /> <span data-ttu-id="22df3-257">0x8Helper 方法。</span><span class="sxs-lookup"><span data-stu-id="22df3-257">0x8: Helper method.</span></span>|
|<span data-ttu-id="22df3-258">MethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="22df3-258">MethodNameSpace</span></span>|<span data-ttu-id="22df3-259">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="22df3-259">win:UnicodeString</span></span>|<span data-ttu-id="22df3-260">与该方法关联的完整命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="22df3-260">Full namespace name associated with the method.</span></span>|
|<span data-ttu-id="22df3-261">MethodName</span><span class="sxs-lookup"><span data-stu-id="22df3-261">MethodName</span></span>|<span data-ttu-id="22df3-262">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="22df3-262">win:UnicodeString</span></span>|<span data-ttu-id="22df3-263">与该方法关联的完整类名称。</span><span class="sxs-lookup"><span data-stu-id="22df3-263">Full class name associated with the method.</span></span>|
|<span data-ttu-id="22df3-264">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="22df3-264">MethodSignature</span></span>|<span data-ttu-id="22df3-265">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="22df3-265">win:UnicodeString</span></span>|<span data-ttu-id="22df3-266">方法的签名（以逗号分隔的类型名称列表）。</span><span class="sxs-lookup"><span data-stu-id="22df3-266">Signature of the method (comma-separated list of type names).</span></span>|
|<span data-ttu-id="22df3-267">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="22df3-267">ClrInstanceID</span></span>|<span data-ttu-id="22df3-268">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="22df3-268">win:UInt16</span></span>|<span data-ttu-id="22df3-269">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="22df3-269">Unique ID for the instance of CLR or CoreCLR.</span></span>|

[<span data-ttu-id="22df3-270">返回页首</span><span class="sxs-lookup"><span data-stu-id="22df3-270">Back to top</span></span>](#top)

<a name="methodjittingstarted_event"></a>

## <a name="methodjittingstarted-event"></a><span data-ttu-id="22df3-271">MethodJittingStarted 事件</span><span class="sxs-lookup"><span data-stu-id="22df3-271">MethodJittingStarted Event</span></span>

<span data-ttu-id="22df3-272">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="22df3-272">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="22df3-273">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="22df3-273">Keyword for raising the event</span></span>|<span data-ttu-id="22df3-274">Level</span><span class="sxs-lookup"><span data-stu-id="22df3-274">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="22df3-275">`JITKeyword` (0x10) 运行时提供程序</span><span class="sxs-lookup"><span data-stu-id="22df3-275">`JITKeyword` (0x10) runtime provider</span></span>|<span data-ttu-id="22df3-276">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="22df3-276">Verbose (5)</span></span>|
|<span data-ttu-id="22df3-277">`NGenKeyword` (0x20) 运行时提供程序</span><span class="sxs-lookup"><span data-stu-id="22df3-277">`NGenKeyword` (0x20) runtime provider</span></span>|<span data-ttu-id="22df3-278">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="22df3-278">Verbose (5)</span></span>|
|<span data-ttu-id="22df3-279">`JitRundownKeyword` (0x10) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="22df3-279">`JitRundownKeyword` (0x10) rundown provider</span></span>|<span data-ttu-id="22df3-280">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="22df3-280">Verbose (5)</span></span>|
|<span data-ttu-id="22df3-281">`NGENRundownKeyword` (0x20) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="22df3-281">`NGENRundownKeyword` (0x20) rundown provider</span></span>|<span data-ttu-id="22df3-282">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="22df3-282">Verbose (5)</span></span>|

<span data-ttu-id="22df3-283">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="22df3-283">The following table shows the event information.</span></span>

|<span data-ttu-id="22df3-284">Event</span><span class="sxs-lookup"><span data-stu-id="22df3-284">Event</span></span>|<span data-ttu-id="22df3-285">事件 ID</span><span class="sxs-lookup"><span data-stu-id="22df3-285">Event ID</span></span>|<span data-ttu-id="22df3-286">描述</span><span class="sxs-lookup"><span data-stu-id="22df3-286">Description</span></span>|
|-----------|--------------|-----------------|
|`MethodJittingStarted`|<span data-ttu-id="22df3-287">145</span><span class="sxs-lookup"><span data-stu-id="22df3-287">145</span></span>|<span data-ttu-id="22df3-288">在方法由 JIT 编译时引发。</span><span class="sxs-lookup"><span data-stu-id="22df3-288">Raised when a method is being JIT-compiled.</span></span>|

<span data-ttu-id="22df3-289">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="22df3-289">The following table shows the event data.</span></span>

|<span data-ttu-id="22df3-290">字段名</span><span class="sxs-lookup"><span data-stu-id="22df3-290">Field name</span></span>|<span data-ttu-id="22df3-291">数据类型</span><span class="sxs-lookup"><span data-stu-id="22df3-291">Data type</span></span>|<span data-ttu-id="22df3-292">描述</span><span class="sxs-lookup"><span data-stu-id="22df3-292">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="22df3-293">MethodID</span><span class="sxs-lookup"><span data-stu-id="22df3-293">MethodID</span></span>|<span data-ttu-id="22df3-294">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="22df3-294">win:UInt64</span></span>|<span data-ttu-id="22df3-295">方法的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="22df3-295">Unique identifier of the method.</span></span>|
|<span data-ttu-id="22df3-296">ModuleID</span><span class="sxs-lookup"><span data-stu-id="22df3-296">ModuleID</span></span>|<span data-ttu-id="22df3-297">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="22df3-297">win:UInt64</span></span>|<span data-ttu-id="22df3-298">此方法所属的模块标识符。</span><span class="sxs-lookup"><span data-stu-id="22df3-298">Identifier of the module to which this method belongs.</span></span>|
|<span data-ttu-id="22df3-299">MethodToken</span><span class="sxs-lookup"><span data-stu-id="22df3-299">MethodToken</span></span>|<span data-ttu-id="22df3-300">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="22df3-300">win:UInt32</span></span>|<span data-ttu-id="22df3-301">0 代表动态方法和 JIT 帮助器。</span><span class="sxs-lookup"><span data-stu-id="22df3-301">0 for dynamic methods and JIT helpers.</span></span>|
|<span data-ttu-id="22df3-302">MethodILSize</span><span class="sxs-lookup"><span data-stu-id="22df3-302">MethodILSize</span></span>|<span data-ttu-id="22df3-303">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="22df3-303">win:UInt32</span></span>|<span data-ttu-id="22df3-304">JIT 编译的方法的 Microsoft 中间语言 (MSIL) 的大小。</span><span class="sxs-lookup"><span data-stu-id="22df3-304">The size of the Microsoft intermediate language (MSIL) for the method that is being JIT-compiled.</span></span>|
|<span data-ttu-id="22df3-305">MethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="22df3-305">MethodNameSpace</span></span>|<span data-ttu-id="22df3-306">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="22df3-306">win:UnicodeString</span></span>|<span data-ttu-id="22df3-307">与该方法关联的完整类名称。</span><span class="sxs-lookup"><span data-stu-id="22df3-307">Full class name associated with the method.</span></span>|
|<span data-ttu-id="22df3-308">MethodName</span><span class="sxs-lookup"><span data-stu-id="22df3-308">MethodName</span></span>|<span data-ttu-id="22df3-309">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="22df3-309">win:UnicodeString</span></span>|<span data-ttu-id="22df3-310">方法的名称。</span><span class="sxs-lookup"><span data-stu-id="22df3-310">Name of the method.</span></span>|
|<span data-ttu-id="22df3-311">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="22df3-311">MethodSignature</span></span>|<span data-ttu-id="22df3-312">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="22df3-312">win:UnicodeString</span></span>|<span data-ttu-id="22df3-313">方法的签名（以逗号分隔的类型名称列表）。</span><span class="sxs-lookup"><span data-stu-id="22df3-313">Signature of the method (comma-separated list of type names).</span></span>|
|<span data-ttu-id="22df3-314">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="22df3-314">ClrInstanceID</span></span>|<span data-ttu-id="22df3-315">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="22df3-315">win:UInt16</span></span>|<span data-ttu-id="22df3-316">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="22df3-316">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="22df3-317">请参阅</span><span class="sxs-lookup"><span data-stu-id="22df3-317">See also</span></span>

- [<span data-ttu-id="22df3-318">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="22df3-318">CLR ETW Events</span></span>](clr-etw-events.md)
