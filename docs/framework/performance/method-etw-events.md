---
title: 方法 ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, method events (CLR)
- method events [.NET Framework]
ms.assetid: 167a4459-bb6e-476c-9046-7920880f2bb5
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c7969c0a3f5f828f1a1c0d4f33b82881130c6e15
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949248"
---
# <a name="method-etw-events"></a><span data-ttu-id="e4dbf-102">方法 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="e4dbf-102">Method ETW Events</span></span>

<a name="top"></a> <span data-ttu-id="e4dbf-103">这些事件收集特定于方法的信息。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-103">These events collect information that is specific to methods.</span></span> <span data-ttu-id="e4dbf-104">符号解析需要这些事件的负载。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-104">The payload of these events is required for symbol resolution.</span></span> <span data-ttu-id="e4dbf-105">此外，这些事件还提供如调用方法的次数等有用信息。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-105">In addition, these events provide helpful information such as the number of times a method was called.</span></span>

<span data-ttu-id="e4dbf-106">所有方法事件都具有“信息性 (4)”级别。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-106">All method events have a level of "Informational (4)".</span></span> <span data-ttu-id="e4dbf-107">所有方法的详细事件都具有“详细级别 (5)”级别。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-107">All method verbose events have a level of "Verbose (5)".</span></span>

<span data-ttu-id="e4dbf-108">所有方法事件都是由运行时提供程序下的 `JITKeyword` (0x10) 关键字或 `NGenKeyword` (0x20) 关键字引发的，或是由断开提供程序下的 `JitRundownKeyword` (0x10) 或 `NGENRundownKeyword` (0x20) 引发的。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-108">All method events are raised by the `JITKeyword` (0x10) keyword or the `NGenKeyword` (0x20) keyword under the runtime provider, or `JitRundownKeyword` (0x10) or `NGENRundownKeyword` (0x20) under the rundown provider.</span></span>

<span data-ttu-id="e4dbf-109">CLR 方法事件进一步细分为以下几类：</span><span class="sxs-lookup"><span data-stu-id="e4dbf-109">CLR method events are further subdivided into the following:</span></span>

- [<span data-ttu-id="e4dbf-110">CLR 方法事件</span><span class="sxs-lookup"><span data-stu-id="e4dbf-110">CLR Method Events</span></span>](#clr_method_events)

- [<span data-ttu-id="e4dbf-111">CLR 方法标记事件</span><span class="sxs-lookup"><span data-stu-id="e4dbf-111">CLR Method Marker Events</span></span>](#clr_method_marker_events)

- [<span data-ttu-id="e4dbf-112">CLR 方法详细事件</span><span class="sxs-lookup"><span data-stu-id="e4dbf-112">CLR Method Verbose Events</span></span>](#clr_method_verbose_events)

- [<span data-ttu-id="e4dbf-113">MethodJittingStarted 事件</span><span class="sxs-lookup"><span data-stu-id="e4dbf-113">MethodJittingStarted Event</span></span>](#methodjittingstarted_event)

<a name="clr_method_events"></a>

## <a name="clr-method-events"></a><span data-ttu-id="e4dbf-114">CLR 方法事件</span><span class="sxs-lookup"><span data-stu-id="e4dbf-114">CLR Method Events</span></span>

<span data-ttu-id="e4dbf-115">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-115">The following table shows the keyword and level.</span></span> <span data-ttu-id="e4dbf-116">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="e4dbf-116">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>

|<span data-ttu-id="e4dbf-117">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="e4dbf-117">Keyword for raising the event</span></span>|<span data-ttu-id="e4dbf-118">级别</span><span class="sxs-lookup"><span data-stu-id="e4dbf-118">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="e4dbf-119">`JITKeyword` (0x10) 运行时提供程序</span><span class="sxs-lookup"><span data-stu-id="e4dbf-119">`JITKeyword` (0x10) runtime provider</span></span>|<span data-ttu-id="e4dbf-120">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="e4dbf-120">Informational (4)</span></span>|
|<span data-ttu-id="e4dbf-121">`NGenKeyword` (0x20) 运行时提供程序</span><span class="sxs-lookup"><span data-stu-id="e4dbf-121">`NGenKeyword` (0x20) runtime provider</span></span>|<span data-ttu-id="e4dbf-122">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="e4dbf-122">Informational (4)</span></span>|
|<span data-ttu-id="e4dbf-123">`JitRundownKeyword` (0x10) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="e4dbf-123">`JitRundownKeyword` (0x10) rundown provider</span></span>|<span data-ttu-id="e4dbf-124">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="e4dbf-124">Informational (4)</span></span>|
|<span data-ttu-id="e4dbf-125">`NGENRundownKeyword` (0x20) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="e4dbf-125">`NGENRundownKeyword` (0x20) rundown provider</span></span>|<span data-ttu-id="e4dbf-126">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="e4dbf-126">Informational (4)</span></span>|

<span data-ttu-id="e4dbf-127">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-127">The following table shows the event information.</span></span>

|<span data-ttu-id="e4dbf-128">Event</span><span class="sxs-lookup"><span data-stu-id="e4dbf-128">Event</span></span>|<span data-ttu-id="e4dbf-129">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e4dbf-129">Event ID</span></span>|<span data-ttu-id="e4dbf-130">描述</span><span class="sxs-lookup"><span data-stu-id="e4dbf-130">Description</span></span>|
|-----------|--------------|-----------------|
|`MethodLoad_V1`|<span data-ttu-id="e4dbf-131">136</span><span class="sxs-lookup"><span data-stu-id="e4dbf-131">136</span></span>|<span data-ttu-id="e4dbf-132">在实时加载（JIT 加载）方法或者加载 NGEN 映像时引发。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-132">Raised when a method is just-in-time loaded (JIT-loaded) or an NGEN image is loaded.</span></span> <span data-ttu-id="e4dbf-133">动态和泛型方法不使用此版本进行方法加载。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-133">Dynamic and generic methods do not use this version for method loads.</span></span> <span data-ttu-id="e4dbf-134">JIT 帮助器从不使用此版本。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-134">JIT helpers never use this version.</span></span>|
|`MethodUnLoad_V1`|<span data-ttu-id="e4dbf-135">137</span><span class="sxs-lookup"><span data-stu-id="e4dbf-135">137</span></span>|<span data-ttu-id="e4dbf-136">在卸载模块或销毁应用程序域时引发。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-136">Raised when a module is unloaded, or an application domain is destroyed.</span></span> <span data-ttu-id="e4dbf-137">动态方法从不使用此版本进行方法卸载。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-137">Dynamic methods never use this version for method unloads.</span></span>|
|`MethodDCStart_V1`|<span data-ttu-id="e4dbf-138">137</span><span class="sxs-lookup"><span data-stu-id="e4dbf-138">137</span></span>|<span data-ttu-id="e4dbf-139">启动断开期间的枚举方法。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-139">Enumerates methods during a start rundown.</span></span>|
|`MethodDCEnd_V1`|<span data-ttu-id="e4dbf-140">138</span><span class="sxs-lookup"><span data-stu-id="e4dbf-140">138</span></span>|<span data-ttu-id="e4dbf-141">结束断开期间的枚举方法。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-141">Enumerates methods during an end rundown.</span></span>|

<span data-ttu-id="e4dbf-142">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-142">The following table shows the event data.</span></span>

|<span data-ttu-id="e4dbf-143">字段名</span><span class="sxs-lookup"><span data-stu-id="e4dbf-143">Field name</span></span>|<span data-ttu-id="e4dbf-144">数据类型</span><span class="sxs-lookup"><span data-stu-id="e4dbf-144">Data type</span></span>|<span data-ttu-id="e4dbf-145">描述</span><span class="sxs-lookup"><span data-stu-id="e4dbf-145">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="e4dbf-146">MethodID</span><span class="sxs-lookup"><span data-stu-id="e4dbf-146">MethodID</span></span>|<span data-ttu-id="e4dbf-147">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e4dbf-147">win:UInt64</span></span>|<span data-ttu-id="e4dbf-148">方法的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-148">Unique identifier of a method.</span></span> <span data-ttu-id="e4dbf-149">对于 JIT 帮助器方法，将设置为该方法的起始地址。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-149">For JIT helper methods, this is set to the start address of the method.</span></span>|
|<span data-ttu-id="e4dbf-150">ModuleID</span><span class="sxs-lookup"><span data-stu-id="e4dbf-150">ModuleID</span></span>|<span data-ttu-id="e4dbf-151">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e4dbf-151">win:UInt64</span></span>|<span data-ttu-id="e4dbf-152">此方法所属的模块标识符（0 表示 JIT 帮助器）。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-152">Identifier of the module to which this method belongs (0 for JIT helpers).</span></span>|
|<span data-ttu-id="e4dbf-153">MethodStartAddress</span><span class="sxs-lookup"><span data-stu-id="e4dbf-153">MethodStartAddress</span></span>|<span data-ttu-id="e4dbf-154">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e4dbf-154">win:UInt64</span></span>|<span data-ttu-id="e4dbf-155">方法的起始地址。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-155">Start address of the method.</span></span>|
|<span data-ttu-id="e4dbf-156">MethodSize</span><span class="sxs-lookup"><span data-stu-id="e4dbf-156">MethodSize</span></span>|<span data-ttu-id="e4dbf-157">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4dbf-157">win:UInt32</span></span>|<span data-ttu-id="e4dbf-158">方法的大小。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-158">Size of the method.</span></span>|
|<span data-ttu-id="e4dbf-159">MethodToken</span><span class="sxs-lookup"><span data-stu-id="e4dbf-159">MethodToken</span></span>|<span data-ttu-id="e4dbf-160">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4dbf-160">win:UInt32</span></span>|<span data-ttu-id="e4dbf-161">0 代表动态方法和 JIT 帮助器。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-161">0 for dynamic methods and JIT helpers.</span></span>|
|<span data-ttu-id="e4dbf-162">MethodFlags</span><span class="sxs-lookup"><span data-stu-id="e4dbf-162">MethodFlags</span></span>|<span data-ttu-id="e4dbf-163">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4dbf-163">win:UInt32</span></span>|<span data-ttu-id="e4dbf-164">0x1:动态方法。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-164">0x1: Dynamic method.</span></span><br /><br /> <span data-ttu-id="e4dbf-165">0x2:泛型方法。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-165">0x2: Generic method.</span></span><br /><br /> <span data-ttu-id="e4dbf-166">0x4:JIT 编译的代码方法 （否则为 NGEN 本机映像代码）。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-166">0x4: JIT-compiled code method (otherwise NGEN native image code).</span></span><br /><br /> <span data-ttu-id="e4dbf-167">0x8:帮助器方法。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-167">0x8: Helper method.</span></span>|
|<span data-ttu-id="e4dbf-168">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e4dbf-168">ClrInstanceID</span></span>|<span data-ttu-id="e4dbf-169">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e4dbf-169">win:UInt16</span></span>|<span data-ttu-id="e4dbf-170">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-170">Unique ID for the instance of CLR or CoreCLR.</span></span>|

[<span data-ttu-id="e4dbf-171">返回页首</span><span class="sxs-lookup"><span data-stu-id="e4dbf-171">Back to top</span></span>](#top)

<a name="clr_method_marker_events"></a>

## <a name="clr-method-marker-events"></a><span data-ttu-id="e4dbf-172">CLR 方法标记事件</span><span class="sxs-lookup"><span data-stu-id="e4dbf-172">CLR Method Marker Events</span></span>

<span data-ttu-id="e4dbf-173">仅在断开提供程序中会引发这些事件。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-173">These events are raised only under the rundown provider.</span></span> <span data-ttu-id="e4dbf-174">它们表示在启动或结束断开期间方法枚举的结束。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-174">They signify the end of method enumeration during a start or end rundown.</span></span> <span data-ttu-id="e4dbf-175">（即，启用 `NGENRundownKeyword`、 `JitRundownKeyword`、 `LoaderRundownKeyword`或 `AppDomainResourceManagementRundownKeyword` 关键字时引发。）</span><span class="sxs-lookup"><span data-stu-id="e4dbf-175">(That is, they are raised when the `NGENRundownKeyword`, `JitRundownKeyword`, `LoaderRundownKeyword`, or `AppDomainResourceManagementRundownKeyword` keyword is enabled.)</span></span>

<span data-ttu-id="e4dbf-176">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-176">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="e4dbf-177">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="e4dbf-177">Keyword for raising the event</span></span>|<span data-ttu-id="e4dbf-178">级别</span><span class="sxs-lookup"><span data-stu-id="e4dbf-178">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="e4dbf-179">`AppDomainResourceManagementRundownKeyword` (0x800) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="e4dbf-179">`AppDomainResourceManagementRundownKeyword` (0x800) rundown provider</span></span>|<span data-ttu-id="e4dbf-180">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="e4dbf-180">Informational (4)</span></span>|
|<span data-ttu-id="e4dbf-181">`JitRundownKeyword` (0x10) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="e4dbf-181">`JitRundownKeyword` (0x10) rundown provider</span></span>|<span data-ttu-id="e4dbf-182">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="e4dbf-182">Informational (4)</span></span>|
|<span data-ttu-id="e4dbf-183">`NGENRundownKeyword` (0x20) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="e4dbf-183">`NGENRundownKeyword` (0x20) rundown provider</span></span>|<span data-ttu-id="e4dbf-184">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="e4dbf-184">Informational (4)</span></span>|

<span data-ttu-id="e4dbf-185">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-185">The following table shows the event information.</span></span>

|<span data-ttu-id="e4dbf-186">Event</span><span class="sxs-lookup"><span data-stu-id="e4dbf-186">Event</span></span>|<span data-ttu-id="e4dbf-187">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e4dbf-187">Event ID</span></span>|<span data-ttu-id="e4dbf-188">描述</span><span class="sxs-lookup"><span data-stu-id="e4dbf-188">Description</span></span>|
|-----------|--------------|----------------|
|`DCStartInit_V1`|<span data-ttu-id="e4dbf-189">147</span><span class="sxs-lookup"><span data-stu-id="e4dbf-189">147</span></span>|<span data-ttu-id="e4dbf-190">启动断开期间枚举开始之前发送。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-190">Sent before the start of the enumeration during a start rundown.</span></span>|
|`DCStartComplete_V1`|<span data-ttu-id="e4dbf-191">145</span><span class="sxs-lookup"><span data-stu-id="e4dbf-191">145</span></span>|<span data-ttu-id="e4dbf-192">启动断开期间枚举结束时发送。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-192">Sent at the end of the enumeration during a start rundown.</span></span>|
|`DCEndInit_V1`|<span data-ttu-id="e4dbf-193">148</span><span class="sxs-lookup"><span data-stu-id="e4dbf-193">148</span></span>|<span data-ttu-id="e4dbf-194">结束断开期间枚举开始之前发送。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-194">Sent before the start of the enumeration during an end rundown.</span></span>|
|`DCEndComplete_V1`|<span data-ttu-id="e4dbf-195">146</span><span class="sxs-lookup"><span data-stu-id="e4dbf-195">146</span></span>|<span data-ttu-id="e4dbf-196">结束断开期间枚举结束时发送。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-196">Sent at the end of the enumeration during an end rundown.</span></span>|

<span data-ttu-id="e4dbf-197">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-197">The following table shows the event data.</span></span>

|<span data-ttu-id="e4dbf-198">字段名</span><span class="sxs-lookup"><span data-stu-id="e4dbf-198">Field name</span></span>|<span data-ttu-id="e4dbf-199">数据类型</span><span class="sxs-lookup"><span data-stu-id="e4dbf-199">Data type</span></span>|<span data-ttu-id="e4dbf-200">描述</span><span class="sxs-lookup"><span data-stu-id="e4dbf-200">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="e4dbf-201">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e4dbf-201">ClrInstanceID</span></span>|<span data-ttu-id="e4dbf-202">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e4dbf-202">win:UInt16</span></span>|<span data-ttu-id="e4dbf-203">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-203">Unique ID for the instance of CLR or CoreCLR.</span></span>|

[<span data-ttu-id="e4dbf-204">返回页首</span><span class="sxs-lookup"><span data-stu-id="e4dbf-204">Back to top</span></span>](#top)

<a name="clr_method_verbose_events"></a>

## <a name="clr-method-verbose-events"></a><span data-ttu-id="e4dbf-205">CLR 方法详细事件</span><span class="sxs-lookup"><span data-stu-id="e4dbf-205">CLR Method Verbose Events</span></span>

<span data-ttu-id="e4dbf-206">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-206">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="e4dbf-207">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="e4dbf-207">Keyword for raising the event</span></span>|<span data-ttu-id="e4dbf-208">级别</span><span class="sxs-lookup"><span data-stu-id="e4dbf-208">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="e4dbf-209">`JITKeyword` (0x10) 运行时提供程序</span><span class="sxs-lookup"><span data-stu-id="e4dbf-209">`JITKeyword` (0x10) runtime provider</span></span>|<span data-ttu-id="e4dbf-210">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="e4dbf-210">Verbose (5)</span></span>|
|<span data-ttu-id="e4dbf-211">`NGenKeyword` (0x20) 运行时提供程序</span><span class="sxs-lookup"><span data-stu-id="e4dbf-211">`NGenKeyword` (0x20) runtime provider</span></span>|<span data-ttu-id="e4dbf-212">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="e4dbf-212">Verbose (5)</span></span>|
|<span data-ttu-id="e4dbf-213">`JitRundownKeyword` (0x10) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="e4dbf-213">`JitRundownKeyword` (0x10) rundown provider</span></span>|<span data-ttu-id="e4dbf-214">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="e4dbf-214">Verbose (5)</span></span>|
|<span data-ttu-id="e4dbf-215">`NGENRundownKeyword` (0x20) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="e4dbf-215">`NGENRundownKeyword` (0x20) rundown provider</span></span>|<span data-ttu-id="e4dbf-216">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="e4dbf-216">Verbose (5)</span></span>|

<span data-ttu-id="e4dbf-217">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-217">The following table shows the event information.</span></span>

|<span data-ttu-id="e4dbf-218">Event</span><span class="sxs-lookup"><span data-stu-id="e4dbf-218">Event</span></span>|<span data-ttu-id="e4dbf-219">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e4dbf-219">Event ID</span></span>|<span data-ttu-id="e4dbf-220">描述</span><span class="sxs-lookup"><span data-stu-id="e4dbf-220">Description</span></span>|
|-----------|--------------|-----------------|
|`MethodLoadVerbose_V1`|<span data-ttu-id="e4dbf-221">143</span><span class="sxs-lookup"><span data-stu-id="e4dbf-221">143</span></span>|<span data-ttu-id="e4dbf-222">当方法为 JIT 加载的或加载 NGEN 映像时引发。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-222">Raised when a method is JIT-loaded or an NGEN image is loaded.</span></span> <span data-ttu-id="e4dbf-223">动态和泛型方法始终使用此版本进行方法加载。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-223">Dynamic and generic methods always use this version for method loads.</span></span> <span data-ttu-id="e4dbf-224">JIT 帮助器始终使用此版本。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-224">JIT helpers always use this version.</span></span>|
|`MethodUnLoadVerbose_V1`|<span data-ttu-id="e4dbf-225">144</span><span class="sxs-lookup"><span data-stu-id="e4dbf-225">144</span></span>|<span data-ttu-id="e4dbf-226">在销毁动态方法、卸载模块或销毁应用程序域时引发。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-226">Raised when a dynamic method is destroyed, a module is unloaded, or an application domain is destroyed.</span></span> <span data-ttu-id="e4dbf-227">动态方法始终使用此版本进行方法卸载。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-227">Dynamic methods always use this version for method unloads.</span></span>|
|`MethodDCStartVerbose_V1`|<span data-ttu-id="e4dbf-228">141</span><span class="sxs-lookup"><span data-stu-id="e4dbf-228">141</span></span>|<span data-ttu-id="e4dbf-229">启动断开期间的枚举方法。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-229">Enumerates methods during a start rundown.</span></span>|
|`MethodDCEndVerbose_V1`|<span data-ttu-id="e4dbf-230">142</span><span class="sxs-lookup"><span data-stu-id="e4dbf-230">142</span></span>|<span data-ttu-id="e4dbf-231">结束断开期间的枚举方法。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-231">Enumerates methods during an end rundown.</span></span>|

<span data-ttu-id="e4dbf-232">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-232">The following table shows the event data.</span></span>

|<span data-ttu-id="e4dbf-233">字段名</span><span class="sxs-lookup"><span data-stu-id="e4dbf-233">Field name</span></span>|<span data-ttu-id="e4dbf-234">数据类型</span><span class="sxs-lookup"><span data-stu-id="e4dbf-234">Data type</span></span>|<span data-ttu-id="e4dbf-235">描述</span><span class="sxs-lookup"><span data-stu-id="e4dbf-235">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="e4dbf-236">MethodID</span><span class="sxs-lookup"><span data-stu-id="e4dbf-236">MethodID</span></span>|<span data-ttu-id="e4dbf-237">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e4dbf-237">win:UInt64</span></span>|<span data-ttu-id="e4dbf-238">方法的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-238">Unique identifier of the method.</span></span> <span data-ttu-id="e4dbf-239">对于 JIT 帮助器方法，将设置为该方法的起始地址。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-239">For JIT helper methods, set to the start address of the method.</span></span>|
|<span data-ttu-id="e4dbf-240">ModuleID</span><span class="sxs-lookup"><span data-stu-id="e4dbf-240">ModuleID</span></span>|<span data-ttu-id="e4dbf-241">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e4dbf-241">win:UInt64</span></span>|<span data-ttu-id="e4dbf-242">此方法所属的模块标识符（0 表示 JIT 帮助器）。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-242">Identifier of the module to which this method belongs (0 for JIT helpers).</span></span>|
|<span data-ttu-id="e4dbf-243">MethodStartAddress</span><span class="sxs-lookup"><span data-stu-id="e4dbf-243">MethodStartAddress</span></span>|<span data-ttu-id="e4dbf-244">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e4dbf-244">win:UInt64</span></span>|<span data-ttu-id="e4dbf-245">起始地址。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-245">Start address.</span></span>|
|<span data-ttu-id="e4dbf-246">MethodSize</span><span class="sxs-lookup"><span data-stu-id="e4dbf-246">MethodSize</span></span>|<span data-ttu-id="e4dbf-247">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4dbf-247">win:UInt32</span></span>|<span data-ttu-id="e4dbf-248">方法长度。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-248">Method length.</span></span>|
|<span data-ttu-id="e4dbf-249">MethodToken</span><span class="sxs-lookup"><span data-stu-id="e4dbf-249">MethodToken</span></span>|<span data-ttu-id="e4dbf-250">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4dbf-250">win:UInt32</span></span>|<span data-ttu-id="e4dbf-251">0 代表动态方法和 JIT 帮助器。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-251">0 for dynamic methods and JIT helpers.</span></span>|
|<span data-ttu-id="e4dbf-252">MethodFlags</span><span class="sxs-lookup"><span data-stu-id="e4dbf-252">MethodFlags</span></span>|<span data-ttu-id="e4dbf-253">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4dbf-253">win:UInt32</span></span>|<span data-ttu-id="e4dbf-254">0x1:动态方法。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-254">0x1: Dynamic method.</span></span><br /><br /> <span data-ttu-id="e4dbf-255">0x2:泛型方法。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-255">0x2: Generic method.</span></span><br /><br /> <span data-ttu-id="e4dbf-256">0x4:JIT 编译的方法 （否则为由 NGen.exe 生成)</span><span class="sxs-lookup"><span data-stu-id="e4dbf-256">0x4: JIT-compiled method (otherwise, generated by NGen.exe)</span></span><br /><br /> <span data-ttu-id="e4dbf-257">0x8:帮助器方法。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-257">0x8: Helper method.</span></span>|
|<span data-ttu-id="e4dbf-258">MethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="e4dbf-258">MethodNameSpace</span></span>|<span data-ttu-id="e4dbf-259">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="e4dbf-259">win:UnicodeString</span></span>|<span data-ttu-id="e4dbf-260">与该方法关联的完整命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-260">Full namespace name associated with the method.</span></span>|
|<span data-ttu-id="e4dbf-261">MethodName</span><span class="sxs-lookup"><span data-stu-id="e4dbf-261">MethodName</span></span>|<span data-ttu-id="e4dbf-262">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="e4dbf-262">win:UnicodeString</span></span>|<span data-ttu-id="e4dbf-263">与该方法关联的完整类名称。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-263">Full class name associated with the method.</span></span>|
|<span data-ttu-id="e4dbf-264">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="e4dbf-264">MethodSignature</span></span>|<span data-ttu-id="e4dbf-265">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="e4dbf-265">win:UnicodeString</span></span>|<span data-ttu-id="e4dbf-266">方法的签名（以逗号分隔的类型名称列表）。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-266">Signature of the method (comma-separated list of type names).</span></span>|
|<span data-ttu-id="e4dbf-267">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e4dbf-267">ClrInstanceID</span></span>|<span data-ttu-id="e4dbf-268">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e4dbf-268">win:UInt16</span></span>|<span data-ttu-id="e4dbf-269">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-269">Unique ID for the instance of CLR or CoreCLR.</span></span>|

[<span data-ttu-id="e4dbf-270">返回页首</span><span class="sxs-lookup"><span data-stu-id="e4dbf-270">Back to top</span></span>](#top)

<a name="methodjittingstarted_event"></a>

## <a name="methodjittingstarted-event"></a><span data-ttu-id="e4dbf-271">MethodJittingStarted 事件</span><span class="sxs-lookup"><span data-stu-id="e4dbf-271">MethodJittingStarted Event</span></span>

<span data-ttu-id="e4dbf-272">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-272">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="e4dbf-273">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="e4dbf-273">Keyword for raising the event</span></span>|<span data-ttu-id="e4dbf-274">级别</span><span class="sxs-lookup"><span data-stu-id="e4dbf-274">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="e4dbf-275">`JITKeyword` (0x10) 运行时提供程序</span><span class="sxs-lookup"><span data-stu-id="e4dbf-275">`JITKeyword` (0x10) runtime provider</span></span>|<span data-ttu-id="e4dbf-276">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="e4dbf-276">Verbose (5)</span></span>|
|<span data-ttu-id="e4dbf-277">`NGenKeyword` (0x20) 运行时提供程序</span><span class="sxs-lookup"><span data-stu-id="e4dbf-277">`NGenKeyword` (0x20) runtime provider</span></span>|<span data-ttu-id="e4dbf-278">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="e4dbf-278">Verbose (5)</span></span>|
|<span data-ttu-id="e4dbf-279">`JitRundownKeyword` (0x10) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="e4dbf-279">`JitRundownKeyword` (0x10) rundown provider</span></span>|<span data-ttu-id="e4dbf-280">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="e4dbf-280">Verbose (5)</span></span>|
|<span data-ttu-id="e4dbf-281">`NGENRundownKeyword` (0x20) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="e4dbf-281">`NGENRundownKeyword` (0x20) rundown provider</span></span>|<span data-ttu-id="e4dbf-282">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="e4dbf-282">Verbose (5)</span></span>|

<span data-ttu-id="e4dbf-283">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-283">The following table shows the event information.</span></span>

|<span data-ttu-id="e4dbf-284">Event</span><span class="sxs-lookup"><span data-stu-id="e4dbf-284">Event</span></span>|<span data-ttu-id="e4dbf-285">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e4dbf-285">Event ID</span></span>|<span data-ttu-id="e4dbf-286">描述</span><span class="sxs-lookup"><span data-stu-id="e4dbf-286">Description</span></span>|
|-----------|--------------|-----------------|
|`MethodJittingStarted`|<span data-ttu-id="e4dbf-287">145</span><span class="sxs-lookup"><span data-stu-id="e4dbf-287">145</span></span>|<span data-ttu-id="e4dbf-288">在方法由 JIT 编译时引发。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-288">Raised when a method is being JIT-compiled.</span></span>|

<span data-ttu-id="e4dbf-289">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-289">The following table shows the event data.</span></span>

|<span data-ttu-id="e4dbf-290">字段名</span><span class="sxs-lookup"><span data-stu-id="e4dbf-290">Field name</span></span>|<span data-ttu-id="e4dbf-291">数据类型</span><span class="sxs-lookup"><span data-stu-id="e4dbf-291">Data type</span></span>|<span data-ttu-id="e4dbf-292">描述</span><span class="sxs-lookup"><span data-stu-id="e4dbf-292">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="e4dbf-293">MethodID</span><span class="sxs-lookup"><span data-stu-id="e4dbf-293">MethodID</span></span>|<span data-ttu-id="e4dbf-294">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e4dbf-294">win:UInt64</span></span>|<span data-ttu-id="e4dbf-295">方法的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-295">Unique identifier of the method.</span></span>|
|<span data-ttu-id="e4dbf-296">ModuleID</span><span class="sxs-lookup"><span data-stu-id="e4dbf-296">ModuleID</span></span>|<span data-ttu-id="e4dbf-297">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e4dbf-297">win:UInt64</span></span>|<span data-ttu-id="e4dbf-298">此方法所属的模块标识符。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-298">Identifier of the module to which this method belongs.</span></span>|
|<span data-ttu-id="e4dbf-299">MethodToken</span><span class="sxs-lookup"><span data-stu-id="e4dbf-299">MethodToken</span></span>|<span data-ttu-id="e4dbf-300">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4dbf-300">win:UInt32</span></span>|<span data-ttu-id="e4dbf-301">0 代表动态方法和 JIT 帮助器。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-301">0 for dynamic methods and JIT helpers.</span></span>|
|<span data-ttu-id="e4dbf-302">MethodILSize</span><span class="sxs-lookup"><span data-stu-id="e4dbf-302">MethodILSize</span></span>|<span data-ttu-id="e4dbf-303">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4dbf-303">win:UInt32</span></span>|<span data-ttu-id="e4dbf-304">JIT 编译的方法的 Microsoft 中间语言 (MSIL) 的大小。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-304">The size of the Microsoft intermediate language (MSIL) for the method that is being JIT-compiled.</span></span>|
|<span data-ttu-id="e4dbf-305">MethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="e4dbf-305">MethodNameSpace</span></span>|<span data-ttu-id="e4dbf-306">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="e4dbf-306">win:UnicodeString</span></span>|<span data-ttu-id="e4dbf-307">与该方法关联的完整类名称。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-307">Full class name associated with the method.</span></span>|
|<span data-ttu-id="e4dbf-308">MethodName</span><span class="sxs-lookup"><span data-stu-id="e4dbf-308">MethodName</span></span>|<span data-ttu-id="e4dbf-309">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="e4dbf-309">win:UnicodeString</span></span>|<span data-ttu-id="e4dbf-310">方法的名称。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-310">Name of the method.</span></span>|
|<span data-ttu-id="e4dbf-311">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="e4dbf-311">MethodSignature</span></span>|<span data-ttu-id="e4dbf-312">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="e4dbf-312">win:UnicodeString</span></span>|<span data-ttu-id="e4dbf-313">方法的签名（以逗号分隔的类型名称列表）。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-313">Signature of the method (comma-separated list of type names).</span></span>|
|<span data-ttu-id="e4dbf-314">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e4dbf-314">ClrInstanceID</span></span>|<span data-ttu-id="e4dbf-315">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e4dbf-315">win:UInt16</span></span>|<span data-ttu-id="e4dbf-316">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="e4dbf-316">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="e4dbf-317">请参阅</span><span class="sxs-lookup"><span data-stu-id="e4dbf-317">See also</span></span>

- [<span data-ttu-id="e4dbf-318">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="e4dbf-318">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
