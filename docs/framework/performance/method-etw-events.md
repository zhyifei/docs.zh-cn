---
title: 方法 ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, method events (CLR)
- method events [.NET Framework]
ms.assetid: 167a4459-bb6e-476c-9046-7920880f2bb5
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 48e1c2271d6d011296d347e7d74fb363cc4d8527
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834554"
---
# <a name="method-etw-events"></a><span data-ttu-id="af3bf-102">方法 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="af3bf-102">Method ETW Events</span></span>

<a name="top"></a> <span data-ttu-id="af3bf-103">这些事件收集特定于方法的信息。</span><span class="sxs-lookup"><span data-stu-id="af3bf-103">These events collect information that is specific to methods.</span></span> <span data-ttu-id="af3bf-104">符号解析需要这些事件的负载。</span><span class="sxs-lookup"><span data-stu-id="af3bf-104">The payload of these events is required for symbol resolution.</span></span> <span data-ttu-id="af3bf-105">此外，这些事件还提供如调用方法的次数等有用信息。</span><span class="sxs-lookup"><span data-stu-id="af3bf-105">In addition, these events provide helpful information such as the number of times a method was called.</span></span>

<span data-ttu-id="af3bf-106">所有方法事件都具有“信息性 (4)”级别。</span><span class="sxs-lookup"><span data-stu-id="af3bf-106">All method events have a level of "Informational (4)".</span></span> <span data-ttu-id="af3bf-107">所有方法的详细事件都具有“详细级别 (5)”级别。</span><span class="sxs-lookup"><span data-stu-id="af3bf-107">All method verbose events have a level of "Verbose (5)".</span></span>

<span data-ttu-id="af3bf-108">所有方法事件都是由运行时提供程序下的 `JITKeyword` (0x10) 关键字或 `NGenKeyword` (0x20) 关键字引发的，或是由断开提供程序下的 `JitRundownKeyword` (0x10) 或 `NGENRundownKeyword` (0x20) 引发的。</span><span class="sxs-lookup"><span data-stu-id="af3bf-108">All method events are raised by the `JITKeyword` (0x10) keyword or the `NGenKeyword` (0x20) keyword under the runtime provider, or `JitRundownKeyword` (0x10) or `NGENRundownKeyword` (0x20) under the rundown provider.</span></span>

<span data-ttu-id="af3bf-109">CLR 方法事件进一步细分为以下几类：</span><span class="sxs-lookup"><span data-stu-id="af3bf-109">CLR method events are further subdivided into the following:</span></span>

- [<span data-ttu-id="af3bf-110">CLR 方法事件</span><span class="sxs-lookup"><span data-stu-id="af3bf-110">CLR Method Events</span></span>](#clr_method_events)

- [<span data-ttu-id="af3bf-111">CLR 方法标记事件</span><span class="sxs-lookup"><span data-stu-id="af3bf-111">CLR Method Marker Events</span></span>](#clr_method_marker_events)

- [<span data-ttu-id="af3bf-112">CLR 方法详细事件</span><span class="sxs-lookup"><span data-stu-id="af3bf-112">CLR Method Verbose Events</span></span>](#clr_method_verbose_events)

- [<span data-ttu-id="af3bf-113">MethodJittingStarted 事件</span><span class="sxs-lookup"><span data-stu-id="af3bf-113">MethodJittingStarted Event</span></span>](#methodjittingstarted_event)

<a name="clr_method_events"></a>

## <a name="clr-method-events"></a><span data-ttu-id="af3bf-114">CLR 方法事件</span><span class="sxs-lookup"><span data-stu-id="af3bf-114">CLR Method Events</span></span>

<span data-ttu-id="af3bf-115">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="af3bf-115">The following table shows the keyword and level.</span></span> <span data-ttu-id="af3bf-116">有关详细信息，请参阅[CLR ETW 关键字和级别](clr-etw-keywords-and-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="af3bf-116">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="af3bf-117">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="af3bf-117">Keyword for raising the event</span></span>|<span data-ttu-id="af3bf-118">Level</span><span class="sxs-lookup"><span data-stu-id="af3bf-118">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="af3bf-119">`JITKeyword` (0x10) 运行时提供程序</span><span class="sxs-lookup"><span data-stu-id="af3bf-119">`JITKeyword` (0x10) runtime provider</span></span>|<span data-ttu-id="af3bf-120">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="af3bf-120">Informational (4)</span></span>|
|<span data-ttu-id="af3bf-121">`NGenKeyword` (0x20) 运行时提供程序</span><span class="sxs-lookup"><span data-stu-id="af3bf-121">`NGenKeyword` (0x20) runtime provider</span></span>|<span data-ttu-id="af3bf-122">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="af3bf-122">Informational (4)</span></span>|
|<span data-ttu-id="af3bf-123">`JitRundownKeyword` (0x10) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="af3bf-123">`JitRundownKeyword` (0x10) rundown provider</span></span>|<span data-ttu-id="af3bf-124">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="af3bf-124">Informational (4)</span></span>|
|<span data-ttu-id="af3bf-125">`NGENRundownKeyword` (0x20) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="af3bf-125">`NGENRundownKeyword` (0x20) rundown provider</span></span>|<span data-ttu-id="af3bf-126">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="af3bf-126">Informational (4)</span></span>|

<span data-ttu-id="af3bf-127">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="af3bf-127">The following table shows the event information:</span></span>

|<span data-ttu-id="af3bf-128">Event</span><span class="sxs-lookup"><span data-stu-id="af3bf-128">Event</span></span>|<span data-ttu-id="af3bf-129">事件 ID</span><span class="sxs-lookup"><span data-stu-id="af3bf-129">Event ID</span></span>|<span data-ttu-id="af3bf-130">描述</span><span class="sxs-lookup"><span data-stu-id="af3bf-130">Description</span></span>|
|-----------|--------------|-----------------|
|`MethodLoad_V1`|<span data-ttu-id="af3bf-131">136</span><span class="sxs-lookup"><span data-stu-id="af3bf-131">136</span></span>|<span data-ttu-id="af3bf-132">在实时加载（JIT 加载）方法或者加载 NGEN 映像时引发。</span><span class="sxs-lookup"><span data-stu-id="af3bf-132">Raised when a method is just-in-time loaded (JIT-loaded) or an NGEN image is loaded.</span></span> <span data-ttu-id="af3bf-133">动态和泛型方法不使用此版本进行方法加载。</span><span class="sxs-lookup"><span data-stu-id="af3bf-133">Dynamic and generic methods do not use this version for method loads.</span></span> <span data-ttu-id="af3bf-134">JIT 帮助器从不使用此版本。</span><span class="sxs-lookup"><span data-stu-id="af3bf-134">JIT helpers never use this version.</span></span>|
|`MethodUnLoad_V1`|<span data-ttu-id="af3bf-135">137</span><span class="sxs-lookup"><span data-stu-id="af3bf-135">137</span></span>|<span data-ttu-id="af3bf-136">在卸载模块或销毁应用程序域时引发。</span><span class="sxs-lookup"><span data-stu-id="af3bf-136">Raised when a module is unloaded, or an application domain is destroyed.</span></span> <span data-ttu-id="af3bf-137">动态方法从不使用此版本进行方法卸载。</span><span class="sxs-lookup"><span data-stu-id="af3bf-137">Dynamic methods never use this version for method unloads.</span></span>|
|`MethodDCStart_V1`|<span data-ttu-id="af3bf-138">137</span><span class="sxs-lookup"><span data-stu-id="af3bf-138">137</span></span>|<span data-ttu-id="af3bf-139">启动断开期间的枚举方法。</span><span class="sxs-lookup"><span data-stu-id="af3bf-139">Enumerates methods during a start rundown.</span></span>|
|`MethodDCEnd_V1`|<span data-ttu-id="af3bf-140">138</span><span class="sxs-lookup"><span data-stu-id="af3bf-140">138</span></span>|<span data-ttu-id="af3bf-141">结束断开期间的枚举方法。</span><span class="sxs-lookup"><span data-stu-id="af3bf-141">Enumerates methods during an end rundown.</span></span>|

<span data-ttu-id="af3bf-142">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="af3bf-142">The following table shows the event data:</span></span>

|<span data-ttu-id="af3bf-143">字段名</span><span class="sxs-lookup"><span data-stu-id="af3bf-143">Field name</span></span>|<span data-ttu-id="af3bf-144">数据类型</span><span class="sxs-lookup"><span data-stu-id="af3bf-144">Data type</span></span>|<span data-ttu-id="af3bf-145">描述</span><span class="sxs-lookup"><span data-stu-id="af3bf-145">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="af3bf-146">MethodID</span><span class="sxs-lookup"><span data-stu-id="af3bf-146">MethodID</span></span>|<span data-ttu-id="af3bf-147">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="af3bf-147">win:UInt64</span></span>|<span data-ttu-id="af3bf-148">方法的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="af3bf-148">Unique identifier of a method.</span></span> <span data-ttu-id="af3bf-149">对于 JIT 帮助器方法，将设置为该方法的起始地址。</span><span class="sxs-lookup"><span data-stu-id="af3bf-149">For JIT helper methods, this is set to the start address of the method.</span></span>|
|<span data-ttu-id="af3bf-150">ModuleID</span><span class="sxs-lookup"><span data-stu-id="af3bf-150">ModuleID</span></span>|<span data-ttu-id="af3bf-151">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="af3bf-151">win:UInt64</span></span>|<span data-ttu-id="af3bf-152">此方法所属的模块标识符（0 表示 JIT 帮助器）。</span><span class="sxs-lookup"><span data-stu-id="af3bf-152">Identifier of the module to which this method belongs (0 for JIT helpers).</span></span>|
|<span data-ttu-id="af3bf-153">MethodStartAddress</span><span class="sxs-lookup"><span data-stu-id="af3bf-153">MethodStartAddress</span></span>|<span data-ttu-id="af3bf-154">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="af3bf-154">win:UInt64</span></span>|<span data-ttu-id="af3bf-155">方法的起始地址。</span><span class="sxs-lookup"><span data-stu-id="af3bf-155">Start address of the method.</span></span>|
|<span data-ttu-id="af3bf-156">MethodSize</span><span class="sxs-lookup"><span data-stu-id="af3bf-156">MethodSize</span></span>|<span data-ttu-id="af3bf-157">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="af3bf-157">win:UInt32</span></span>|<span data-ttu-id="af3bf-158">方法的大小。</span><span class="sxs-lookup"><span data-stu-id="af3bf-158">Size of the method.</span></span>|
|<span data-ttu-id="af3bf-159">MethodToken</span><span class="sxs-lookup"><span data-stu-id="af3bf-159">MethodToken</span></span>|<span data-ttu-id="af3bf-160">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="af3bf-160">win:UInt32</span></span>|<span data-ttu-id="af3bf-161">0 代表动态方法和 JIT 帮助器。</span><span class="sxs-lookup"><span data-stu-id="af3bf-161">0 for dynamic methods and JIT helpers.</span></span>|
|<span data-ttu-id="af3bf-162">MethodFlags</span><span class="sxs-lookup"><span data-stu-id="af3bf-162">MethodFlags</span></span>|<span data-ttu-id="af3bf-163">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="af3bf-163">win:UInt32</span></span>|<span data-ttu-id="af3bf-164">0x1动态方法。</span><span class="sxs-lookup"><span data-stu-id="af3bf-164">0x1: Dynamic method.</span></span><br /><br /> <span data-ttu-id="af3bf-165">0x2泛型方法。</span><span class="sxs-lookup"><span data-stu-id="af3bf-165">0x2: Generic method.</span></span><br /><br /> <span data-ttu-id="af3bf-166">0x4JIT 编译的代码方法（否则为 NGEN 本机映像代码）。</span><span class="sxs-lookup"><span data-stu-id="af3bf-166">0x4: JIT-compiled code method (otherwise NGEN native image code).</span></span><br /><br /> <span data-ttu-id="af3bf-167">0x8Helper 方法。</span><span class="sxs-lookup"><span data-stu-id="af3bf-167">0x8: Helper method.</span></span>|
|<span data-ttu-id="af3bf-168">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="af3bf-168">ClrInstanceID</span></span>|<span data-ttu-id="af3bf-169">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="af3bf-169">win:UInt16</span></span>|<span data-ttu-id="af3bf-170">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="af3bf-170">Unique ID for the instance of CLR or CoreCLR.</span></span>|

[<span data-ttu-id="af3bf-171">返回页首</span><span class="sxs-lookup"><span data-stu-id="af3bf-171">Back to top</span></span>](#top)

<a name="clr_method_marker_events"></a>

## <a name="clr-method-marker-events"></a><span data-ttu-id="af3bf-172">CLR 方法标记事件</span><span class="sxs-lookup"><span data-stu-id="af3bf-172">CLR Method Marker Events</span></span>

<span data-ttu-id="af3bf-173">仅在断开提供程序中会引发这些事件。</span><span class="sxs-lookup"><span data-stu-id="af3bf-173">These events are raised only under the rundown provider.</span></span> <span data-ttu-id="af3bf-174">它们表示在启动或结束断开期间方法枚举的结束。</span><span class="sxs-lookup"><span data-stu-id="af3bf-174">They signify the end of method enumeration during a start or end rundown.</span></span> <span data-ttu-id="af3bf-175">（即，启用 `NGENRundownKeyword`、 `JitRundownKeyword`、 `LoaderRundownKeyword`或 `AppDomainResourceManagementRundownKeyword` 关键字时引发。）</span><span class="sxs-lookup"><span data-stu-id="af3bf-175">(That is, they are raised when the `NGENRundownKeyword`, `JitRundownKeyword`, `LoaderRundownKeyword`, or `AppDomainResourceManagementRundownKeyword` keyword is enabled.)</span></span>

<span data-ttu-id="af3bf-176">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="af3bf-176">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="af3bf-177">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="af3bf-177">Keyword for raising the event</span></span>|<span data-ttu-id="af3bf-178">Level</span><span class="sxs-lookup"><span data-stu-id="af3bf-178">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="af3bf-179">`AppDomainResourceManagementRundownKeyword` (0x800) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="af3bf-179">`AppDomainResourceManagementRundownKeyword` (0x800) rundown provider</span></span>|<span data-ttu-id="af3bf-180">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="af3bf-180">Informational (4)</span></span>|
|<span data-ttu-id="af3bf-181">`JitRundownKeyword` (0x10) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="af3bf-181">`JitRundownKeyword` (0x10) rundown provider</span></span>|<span data-ttu-id="af3bf-182">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="af3bf-182">Informational (4)</span></span>|
|<span data-ttu-id="af3bf-183">`NGENRundownKeyword` (0x20) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="af3bf-183">`NGENRundownKeyword` (0x20) rundown provider</span></span>|<span data-ttu-id="af3bf-184">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="af3bf-184">Informational (4)</span></span>|

<span data-ttu-id="af3bf-185">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="af3bf-185">The following table shows the event information:</span></span>

|<span data-ttu-id="af3bf-186">Event</span><span class="sxs-lookup"><span data-stu-id="af3bf-186">Event</span></span>|<span data-ttu-id="af3bf-187">事件 ID</span><span class="sxs-lookup"><span data-stu-id="af3bf-187">Event ID</span></span>|<span data-ttu-id="af3bf-188">描述</span><span class="sxs-lookup"><span data-stu-id="af3bf-188">Description</span></span>|
|-----------|--------------|----------------|
|`DCStartInit_V1`|<span data-ttu-id="af3bf-189">147</span><span class="sxs-lookup"><span data-stu-id="af3bf-189">147</span></span>|<span data-ttu-id="af3bf-190">启动断开期间枚举开始之前发送。</span><span class="sxs-lookup"><span data-stu-id="af3bf-190">Sent before the start of the enumeration during a start rundown.</span></span>|
|`DCStartComplete_V1`|<span data-ttu-id="af3bf-191">145</span><span class="sxs-lookup"><span data-stu-id="af3bf-191">145</span></span>|<span data-ttu-id="af3bf-192">启动断开期间枚举结束时发送。</span><span class="sxs-lookup"><span data-stu-id="af3bf-192">Sent at the end of the enumeration during a start rundown.</span></span>|
|`DCEndInit_V1`|<span data-ttu-id="af3bf-193">148</span><span class="sxs-lookup"><span data-stu-id="af3bf-193">148</span></span>|<span data-ttu-id="af3bf-194">结束断开期间枚举开始之前发送。</span><span class="sxs-lookup"><span data-stu-id="af3bf-194">Sent before the start of the enumeration during an end rundown.</span></span>|
|`DCEndComplete_V1`|<span data-ttu-id="af3bf-195">146</span><span class="sxs-lookup"><span data-stu-id="af3bf-195">146</span></span>|<span data-ttu-id="af3bf-196">结束断开期间枚举结束时发送。</span><span class="sxs-lookup"><span data-stu-id="af3bf-196">Sent at the end of the enumeration during an end rundown.</span></span>|

<span data-ttu-id="af3bf-197">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="af3bf-197">The following table shows the event data:</span></span>

|<span data-ttu-id="af3bf-198">字段名</span><span class="sxs-lookup"><span data-stu-id="af3bf-198">Field name</span></span>|<span data-ttu-id="af3bf-199">数据类型</span><span class="sxs-lookup"><span data-stu-id="af3bf-199">Data type</span></span>|<span data-ttu-id="af3bf-200">描述</span><span class="sxs-lookup"><span data-stu-id="af3bf-200">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="af3bf-201">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="af3bf-201">ClrInstanceID</span></span>|<span data-ttu-id="af3bf-202">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="af3bf-202">win:UInt16</span></span>|<span data-ttu-id="af3bf-203">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="af3bf-203">Unique ID for the instance of CLR or CoreCLR.</span></span>|

[<span data-ttu-id="af3bf-204">返回页首</span><span class="sxs-lookup"><span data-stu-id="af3bf-204">Back to top</span></span>](#top)

<a name="clr_method_verbose_events"></a>

## <a name="clr-method-verbose-events"></a><span data-ttu-id="af3bf-205">CLR 方法详细事件</span><span class="sxs-lookup"><span data-stu-id="af3bf-205">CLR Method Verbose Events</span></span>

<span data-ttu-id="af3bf-206">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="af3bf-206">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="af3bf-207">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="af3bf-207">Keyword for raising the event</span></span>|<span data-ttu-id="af3bf-208">Level</span><span class="sxs-lookup"><span data-stu-id="af3bf-208">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="af3bf-209">`JITKeyword` (0x10) 运行时提供程序</span><span class="sxs-lookup"><span data-stu-id="af3bf-209">`JITKeyword` (0x10) runtime provider</span></span>|<span data-ttu-id="af3bf-210">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="af3bf-210">Verbose (5)</span></span>|
|<span data-ttu-id="af3bf-211">`NGenKeyword` (0x20) 运行时提供程序</span><span class="sxs-lookup"><span data-stu-id="af3bf-211">`NGenKeyword` (0x20) runtime provider</span></span>|<span data-ttu-id="af3bf-212">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="af3bf-212">Verbose (5)</span></span>|
|<span data-ttu-id="af3bf-213">`JitRundownKeyword` (0x10) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="af3bf-213">`JitRundownKeyword` (0x10) rundown provider</span></span>|<span data-ttu-id="af3bf-214">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="af3bf-214">Verbose (5)</span></span>|
|<span data-ttu-id="af3bf-215">`NGENRundownKeyword` (0x20) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="af3bf-215">`NGENRundownKeyword` (0x20) rundown provider</span></span>|<span data-ttu-id="af3bf-216">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="af3bf-216">Verbose (5)</span></span>|

<span data-ttu-id="af3bf-217">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="af3bf-217">The following table shows the event information:</span></span>

|<span data-ttu-id="af3bf-218">Event</span><span class="sxs-lookup"><span data-stu-id="af3bf-218">Event</span></span>|<span data-ttu-id="af3bf-219">事件 ID</span><span class="sxs-lookup"><span data-stu-id="af3bf-219">Event ID</span></span>|<span data-ttu-id="af3bf-220">描述</span><span class="sxs-lookup"><span data-stu-id="af3bf-220">Description</span></span>|
|-----------|--------------|-----------------|
|`MethodLoadVerbose_V1`|<span data-ttu-id="af3bf-221">143</span><span class="sxs-lookup"><span data-stu-id="af3bf-221">143</span></span>|<span data-ttu-id="af3bf-222">当方法为 JIT 加载的或加载 NGEN 映像时引发。</span><span class="sxs-lookup"><span data-stu-id="af3bf-222">Raised when a method is JIT-loaded or an NGEN image is loaded.</span></span> <span data-ttu-id="af3bf-223">动态和泛型方法始终使用此版本进行方法加载。</span><span class="sxs-lookup"><span data-stu-id="af3bf-223">Dynamic and generic methods always use this version for method loads.</span></span> <span data-ttu-id="af3bf-224">JIT 帮助器始终使用此版本。</span><span class="sxs-lookup"><span data-stu-id="af3bf-224">JIT helpers always use this version.</span></span>|
|`MethodUnLoadVerbose_V1`|<span data-ttu-id="af3bf-225">144</span><span class="sxs-lookup"><span data-stu-id="af3bf-225">144</span></span>|<span data-ttu-id="af3bf-226">在销毁动态方法、卸载模块或销毁应用程序域时引发。</span><span class="sxs-lookup"><span data-stu-id="af3bf-226">Raised when a dynamic method is destroyed, a module is unloaded, or an application domain is destroyed.</span></span> <span data-ttu-id="af3bf-227">动态方法始终使用此版本进行方法卸载。</span><span class="sxs-lookup"><span data-stu-id="af3bf-227">Dynamic methods always use this version for method unloads.</span></span>|
|`MethodDCStartVerbose_V1`|<span data-ttu-id="af3bf-228">141</span><span class="sxs-lookup"><span data-stu-id="af3bf-228">141</span></span>|<span data-ttu-id="af3bf-229">启动断开期间的枚举方法。</span><span class="sxs-lookup"><span data-stu-id="af3bf-229">Enumerates methods during a start rundown.</span></span>|
|`MethodDCEndVerbose_V1`|<span data-ttu-id="af3bf-230">142</span><span class="sxs-lookup"><span data-stu-id="af3bf-230">142</span></span>|<span data-ttu-id="af3bf-231">结束断开期间的枚举方法。</span><span class="sxs-lookup"><span data-stu-id="af3bf-231">Enumerates methods during an end rundown.</span></span>|

<span data-ttu-id="af3bf-232">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="af3bf-232">The following table shows the event data:</span></span>

|<span data-ttu-id="af3bf-233">字段名</span><span class="sxs-lookup"><span data-stu-id="af3bf-233">Field name</span></span>|<span data-ttu-id="af3bf-234">数据类型</span><span class="sxs-lookup"><span data-stu-id="af3bf-234">Data type</span></span>|<span data-ttu-id="af3bf-235">描述</span><span class="sxs-lookup"><span data-stu-id="af3bf-235">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="af3bf-236">MethodID</span><span class="sxs-lookup"><span data-stu-id="af3bf-236">MethodID</span></span>|<span data-ttu-id="af3bf-237">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="af3bf-237">win:UInt64</span></span>|<span data-ttu-id="af3bf-238">方法的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="af3bf-238">Unique identifier of the method.</span></span> <span data-ttu-id="af3bf-239">对于 JIT 帮助器方法，将设置为该方法的起始地址。</span><span class="sxs-lookup"><span data-stu-id="af3bf-239">For JIT helper methods, set to the start address of the method.</span></span>|
|<span data-ttu-id="af3bf-240">ModuleID</span><span class="sxs-lookup"><span data-stu-id="af3bf-240">ModuleID</span></span>|<span data-ttu-id="af3bf-241">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="af3bf-241">win:UInt64</span></span>|<span data-ttu-id="af3bf-242">此方法所属的模块标识符（0 表示 JIT 帮助器）。</span><span class="sxs-lookup"><span data-stu-id="af3bf-242">Identifier of the module to which this method belongs (0 for JIT helpers).</span></span>|
|<span data-ttu-id="af3bf-243">MethodStartAddress</span><span class="sxs-lookup"><span data-stu-id="af3bf-243">MethodStartAddress</span></span>|<span data-ttu-id="af3bf-244">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="af3bf-244">win:UInt64</span></span>|<span data-ttu-id="af3bf-245">起始地址。</span><span class="sxs-lookup"><span data-stu-id="af3bf-245">Start address.</span></span>|
|<span data-ttu-id="af3bf-246">MethodSize</span><span class="sxs-lookup"><span data-stu-id="af3bf-246">MethodSize</span></span>|<span data-ttu-id="af3bf-247">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="af3bf-247">win:UInt32</span></span>|<span data-ttu-id="af3bf-248">方法长度。</span><span class="sxs-lookup"><span data-stu-id="af3bf-248">Method length.</span></span>|
|<span data-ttu-id="af3bf-249">MethodToken</span><span class="sxs-lookup"><span data-stu-id="af3bf-249">MethodToken</span></span>|<span data-ttu-id="af3bf-250">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="af3bf-250">win:UInt32</span></span>|<span data-ttu-id="af3bf-251">0 代表动态方法和 JIT 帮助器。</span><span class="sxs-lookup"><span data-stu-id="af3bf-251">0 for dynamic methods and JIT helpers.</span></span>|
|<span data-ttu-id="af3bf-252">MethodFlags</span><span class="sxs-lookup"><span data-stu-id="af3bf-252">MethodFlags</span></span>|<span data-ttu-id="af3bf-253">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="af3bf-253">win:UInt32</span></span>|<span data-ttu-id="af3bf-254">0x1动态方法。</span><span class="sxs-lookup"><span data-stu-id="af3bf-254">0x1: Dynamic method.</span></span><br /><br /> <span data-ttu-id="af3bf-255">0x2泛型方法。</span><span class="sxs-lookup"><span data-stu-id="af3bf-255">0x2: Generic method.</span></span><br /><br /> <span data-ttu-id="af3bf-256">0x4JIT 编译的方法（否则由 Ngen.exe 生成）</span><span class="sxs-lookup"><span data-stu-id="af3bf-256">0x4: JIT-compiled method (otherwise, generated by NGen.exe)</span></span><br /><br /> <span data-ttu-id="af3bf-257">0x8Helper 方法。</span><span class="sxs-lookup"><span data-stu-id="af3bf-257">0x8: Helper method.</span></span>|
|<span data-ttu-id="af3bf-258">MethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="af3bf-258">MethodNameSpace</span></span>|<span data-ttu-id="af3bf-259">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="af3bf-259">win:UnicodeString</span></span>|<span data-ttu-id="af3bf-260">与该方法关联的完整命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="af3bf-260">Full namespace name associated with the method.</span></span>|
|<span data-ttu-id="af3bf-261">MethodName</span><span class="sxs-lookup"><span data-stu-id="af3bf-261">MethodName</span></span>|<span data-ttu-id="af3bf-262">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="af3bf-262">win:UnicodeString</span></span>|<span data-ttu-id="af3bf-263">与该方法关联的完整类名称。</span><span class="sxs-lookup"><span data-stu-id="af3bf-263">Full class name associated with the method.</span></span>|
|<span data-ttu-id="af3bf-264">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="af3bf-264">MethodSignature</span></span>|<span data-ttu-id="af3bf-265">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="af3bf-265">win:UnicodeString</span></span>|<span data-ttu-id="af3bf-266">方法的签名（以逗号分隔的类型名称列表）。</span><span class="sxs-lookup"><span data-stu-id="af3bf-266">Signature of the method (comma-separated list of type names).</span></span>|
|<span data-ttu-id="af3bf-267">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="af3bf-267">ClrInstanceID</span></span>|<span data-ttu-id="af3bf-268">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="af3bf-268">win:UInt16</span></span>|<span data-ttu-id="af3bf-269">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="af3bf-269">Unique ID for the instance of CLR or CoreCLR.</span></span>|

[<span data-ttu-id="af3bf-270">返回页首</span><span class="sxs-lookup"><span data-stu-id="af3bf-270">Back to top</span></span>](#top)

<a name="methodjittingstarted_event"></a>

## <a name="methodjittingstarted-event"></a><span data-ttu-id="af3bf-271">MethodJittingStarted 事件</span><span class="sxs-lookup"><span data-stu-id="af3bf-271">MethodJittingStarted Event</span></span>

<span data-ttu-id="af3bf-272">下表显示了关键字和级别：</span><span class="sxs-lookup"><span data-stu-id="af3bf-272">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="af3bf-273">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="af3bf-273">Keyword for raising the event</span></span>|<span data-ttu-id="af3bf-274">Level</span><span class="sxs-lookup"><span data-stu-id="af3bf-274">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="af3bf-275">`JITKeyword` (0x10) 运行时提供程序</span><span class="sxs-lookup"><span data-stu-id="af3bf-275">`JITKeyword` (0x10) runtime provider</span></span>|<span data-ttu-id="af3bf-276">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="af3bf-276">Verbose (5)</span></span>|
|<span data-ttu-id="af3bf-277">`NGenKeyword` (0x20) 运行时提供程序</span><span class="sxs-lookup"><span data-stu-id="af3bf-277">`NGenKeyword` (0x20) runtime provider</span></span>|<span data-ttu-id="af3bf-278">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="af3bf-278">Verbose (5)</span></span>|
|<span data-ttu-id="af3bf-279">`JitRundownKeyword` (0x10) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="af3bf-279">`JitRundownKeyword` (0x10) rundown provider</span></span>|<span data-ttu-id="af3bf-280">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="af3bf-280">Verbose (5)</span></span>|
|<span data-ttu-id="af3bf-281">`NGENRundownKeyword` (0x20) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="af3bf-281">`NGENRundownKeyword` (0x20) rundown provider</span></span>|<span data-ttu-id="af3bf-282">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="af3bf-282">Verbose (5)</span></span>|

<span data-ttu-id="af3bf-283">下表显示了事件信息：</span><span class="sxs-lookup"><span data-stu-id="af3bf-283">The following table shows the event information:</span></span>

|<span data-ttu-id="af3bf-284">Event</span><span class="sxs-lookup"><span data-stu-id="af3bf-284">Event</span></span>|<span data-ttu-id="af3bf-285">事件 ID</span><span class="sxs-lookup"><span data-stu-id="af3bf-285">Event ID</span></span>|<span data-ttu-id="af3bf-286">描述</span><span class="sxs-lookup"><span data-stu-id="af3bf-286">Description</span></span>|
|-----------|--------------|-----------------|
|`MethodJittingStarted`|<span data-ttu-id="af3bf-287">145</span><span class="sxs-lookup"><span data-stu-id="af3bf-287">145</span></span>|<span data-ttu-id="af3bf-288">在方法由 JIT 编译时引发。</span><span class="sxs-lookup"><span data-stu-id="af3bf-288">Raised when a method is being JIT-compiled.</span></span>|

<span data-ttu-id="af3bf-289">下表显示了事件数据：</span><span class="sxs-lookup"><span data-stu-id="af3bf-289">The following table shows the event data:</span></span>

|<span data-ttu-id="af3bf-290">字段名</span><span class="sxs-lookup"><span data-stu-id="af3bf-290">Field name</span></span>|<span data-ttu-id="af3bf-291">数据类型</span><span class="sxs-lookup"><span data-stu-id="af3bf-291">Data type</span></span>|<span data-ttu-id="af3bf-292">描述</span><span class="sxs-lookup"><span data-stu-id="af3bf-292">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="af3bf-293">MethodID</span><span class="sxs-lookup"><span data-stu-id="af3bf-293">MethodID</span></span>|<span data-ttu-id="af3bf-294">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="af3bf-294">win:UInt64</span></span>|<span data-ttu-id="af3bf-295">方法的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="af3bf-295">Unique identifier of the method.</span></span>|
|<span data-ttu-id="af3bf-296">ModuleID</span><span class="sxs-lookup"><span data-stu-id="af3bf-296">ModuleID</span></span>|<span data-ttu-id="af3bf-297">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="af3bf-297">win:UInt64</span></span>|<span data-ttu-id="af3bf-298">此方法所属的模块标识符。</span><span class="sxs-lookup"><span data-stu-id="af3bf-298">Identifier of the module to which this method belongs.</span></span>|
|<span data-ttu-id="af3bf-299">MethodToken</span><span class="sxs-lookup"><span data-stu-id="af3bf-299">MethodToken</span></span>|<span data-ttu-id="af3bf-300">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="af3bf-300">win:UInt32</span></span>|<span data-ttu-id="af3bf-301">0 代表动态方法和 JIT 帮助器。</span><span class="sxs-lookup"><span data-stu-id="af3bf-301">0 for dynamic methods and JIT helpers.</span></span>|
|<span data-ttu-id="af3bf-302">MethodILSize</span><span class="sxs-lookup"><span data-stu-id="af3bf-302">MethodILSize</span></span>|<span data-ttu-id="af3bf-303">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="af3bf-303">win:UInt32</span></span>|<span data-ttu-id="af3bf-304">JIT 编译的方法的 Microsoft 中间语言 (MSIL) 的大小。</span><span class="sxs-lookup"><span data-stu-id="af3bf-304">The size of the Microsoft intermediate language (MSIL) for the method that is being JIT-compiled.</span></span>|
|<span data-ttu-id="af3bf-305">MethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="af3bf-305">MethodNameSpace</span></span>|<span data-ttu-id="af3bf-306">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="af3bf-306">win:UnicodeString</span></span>|<span data-ttu-id="af3bf-307">与该方法关联的完整类名称。</span><span class="sxs-lookup"><span data-stu-id="af3bf-307">Full class name associated with the method.</span></span>|
|<span data-ttu-id="af3bf-308">MethodName</span><span class="sxs-lookup"><span data-stu-id="af3bf-308">MethodName</span></span>|<span data-ttu-id="af3bf-309">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="af3bf-309">win:UnicodeString</span></span>|<span data-ttu-id="af3bf-310">方法的名称。</span><span class="sxs-lookup"><span data-stu-id="af3bf-310">Name of the method.</span></span>|
|<span data-ttu-id="af3bf-311">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="af3bf-311">MethodSignature</span></span>|<span data-ttu-id="af3bf-312">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="af3bf-312">win:UnicodeString</span></span>|<span data-ttu-id="af3bf-313">方法的签名（以逗号分隔的类型名称列表）。</span><span class="sxs-lookup"><span data-stu-id="af3bf-313">Signature of the method (comma-separated list of type names).</span></span>|
|<span data-ttu-id="af3bf-314">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="af3bf-314">ClrInstanceID</span></span>|<span data-ttu-id="af3bf-315">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="af3bf-315">win:UInt16</span></span>|<span data-ttu-id="af3bf-316">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="af3bf-316">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="af3bf-317">请参阅</span><span class="sxs-lookup"><span data-stu-id="af3bf-317">See also</span></span>

- [<span data-ttu-id="af3bf-318">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="af3bf-318">CLR ETW Events</span></span>](clr-etw-events.md)
