---
title: "方法 ETW 事件"
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
- ETW, method events (CLR)
- method events [.NET Framework]
ms.assetid: 167a4459-bb6e-476c-9046-7920880f2bb5
caps.latest.revision: 9
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 353ae034381ab29787aba1c1c362f4c6fc57da7e
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="method-etw-events"></a><span data-ttu-id="8b3cf-102">方法 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="8b3cf-102">Method ETW Events</span></span>
<span data-ttu-id="8b3cf-103"><a name="top"></a> 这些事件收集特定于方法的信息。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-103"><a name="top"></a> These events collect information that is specific to methods.</span></span> <span data-ttu-id="8b3cf-104">符号解析需要这些事件的负载。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-104">The payload of these events is required for symbol resolution.</span></span> <span data-ttu-id="8b3cf-105">此外，这些事件还提供如调用方法的次数等有用信息。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-105">In addition, these events provide helpful information such as the number of times a method was called.</span></span>  
  
 <span data-ttu-id="8b3cf-106">所有方法事件都具有“信息性 (4)”级别。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-106">All method events have a level of "Informational (4)".</span></span> <span data-ttu-id="8b3cf-107">所有方法的详细事件都具有“详细级别 (5)”级别。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-107">All method verbose events have a level of "Verbose (5)".</span></span>  
  
 <span data-ttu-id="8b3cf-108">所有方法事件都是由运行时提供程序下的 `JITKeyword` (0x10) 关键字或 `NGenKeyword` (0x20) 关键字引发的，或是由断开提供程序下的 `JitRundownKeyword` (0x10) 或 `NGENRundownKeyword` (0x20) 引发的。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-108">All method events are raised by the `JITKeyword` (0x10) keyword or the `NGenKeyword` (0x20) keyword under the runtime provider, or `JitRundownKeyword` (0x10) or `NGENRundownKeyword` (0x20) under the rundown provider.</span></span>  
  
 <span data-ttu-id="8b3cf-109">CLR 方法事件进一步细分为以下几类：</span><span class="sxs-lookup"><span data-stu-id="8b3cf-109">CLR method events are further subdivided into the following:</span></span>  
  
-   [<span data-ttu-id="8b3cf-110">CLR 方法事件</span><span class="sxs-lookup"><span data-stu-id="8b3cf-110">CLR Method Events</span></span>](#clr_method_events)  
  
-   [<span data-ttu-id="8b3cf-111">CLR 方法标记事件</span><span class="sxs-lookup"><span data-stu-id="8b3cf-111">CLR Method Marker Events</span></span>](#clr_method_marker_events)  
  
-   [<span data-ttu-id="8b3cf-112">CLR 方法详细事件</span><span class="sxs-lookup"><span data-stu-id="8b3cf-112">CLR Method Verbose Events</span></span>](#clr_method_verbose_events)  
  
-   [<span data-ttu-id="8b3cf-113">MethodJittingStarted 事件</span><span class="sxs-lookup"><span data-stu-id="8b3cf-113">MethodJittingStarted Event</span></span>](#methodjittingstarted_event)  
  
<a name="clr_method_events"></a>   
## <a name="clr-method-events"></a><span data-ttu-id="8b3cf-114">CLR 方法事件</span><span class="sxs-lookup"><span data-stu-id="8b3cf-114">CLR Method Events</span></span>  
 <span data-ttu-id="8b3cf-115">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-115">The following table shows the keyword and level.</span></span> <span data-ttu-id="8b3cf-116">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="8b3cf-116">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="8b3cf-117">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="8b3cf-117">Keyword for raising the event</span></span>|<span data-ttu-id="8b3cf-118">级别</span><span class="sxs-lookup"><span data-stu-id="8b3cf-118">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="8b3cf-119">`JITKeyword` (0x10) 运行时提供程序</span><span class="sxs-lookup"><span data-stu-id="8b3cf-119">`JITKeyword` (0x10) runtime provider</span></span>|<span data-ttu-id="8b3cf-120">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="8b3cf-120">Informational (4)</span></span>|  
|<span data-ttu-id="8b3cf-121">`NGenKeyword` (0x20) 运行时提供程序</span><span class="sxs-lookup"><span data-stu-id="8b3cf-121">`NGenKeyword` (0x20) runtime provider</span></span>|<span data-ttu-id="8b3cf-122">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="8b3cf-122">Informational (4)</span></span>|  
|<span data-ttu-id="8b3cf-123">`JitRundownKeyword` (0x10) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="8b3cf-123">`JitRundownKeyword` (0x10) rundown provider</span></span>|<span data-ttu-id="8b3cf-124">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="8b3cf-124">Informational (4)</span></span>|  
|<span data-ttu-id="8b3cf-125">`NGENRundownKeyword` (0x20) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="8b3cf-125">`NGENRundownKeyword` (0x20) rundown provider</span></span>|<span data-ttu-id="8b3cf-126">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="8b3cf-126">Informational (4)</span></span>|  
  
 <span data-ttu-id="8b3cf-127">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-127">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="8b3cf-128">Event</span><span class="sxs-lookup"><span data-stu-id="8b3cf-128">Event</span></span>|<span data-ttu-id="8b3cf-129">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8b3cf-129">Event ID</span></span>|<span data-ttu-id="8b3cf-130">描述</span><span class="sxs-lookup"><span data-stu-id="8b3cf-130">Description</span></span>|  
|-----------|--------------|-----------------|  
|`MethodLoad_V1`|<span data-ttu-id="8b3cf-131">136</span><span class="sxs-lookup"><span data-stu-id="8b3cf-131">136</span></span>|<span data-ttu-id="8b3cf-132">在实时加载（JIT 加载）方法或者加载 NGEN 映像时引发。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-132">Raised when a method is just-in-time loaded (JIT-loaded) or an NGEN image is loaded.</span></span> <span data-ttu-id="8b3cf-133">动态和泛型方法不使用此版本进行方法加载。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-133">Dynamic and generic methods do not use this version for method loads.</span></span> <span data-ttu-id="8b3cf-134">JIT 帮助器从不使用此版本。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-134">JIT helpers never use this version.</span></span>|  
|`MethodUnLoad_V1`|<span data-ttu-id="8b3cf-135">137</span><span class="sxs-lookup"><span data-stu-id="8b3cf-135">137</span></span>|<span data-ttu-id="8b3cf-136">在卸载模块或销毁应用程序域时引发。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-136">Raised when a module is unloaded, or an application domain is destroyed.</span></span> <span data-ttu-id="8b3cf-137">动态方法从不使用此版本进行方法卸载。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-137">Dynamic methods never use this version for method unloads.</span></span>|  
|`MethodDCStart_V1`|<span data-ttu-id="8b3cf-138">137</span><span class="sxs-lookup"><span data-stu-id="8b3cf-138">137</span></span>|<span data-ttu-id="8b3cf-139">启动断开期间的枚举方法。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-139">Enumerates methods during a start rundown.</span></span>|  
|`MethodDCEnd_V1`|<span data-ttu-id="8b3cf-140">138</span><span class="sxs-lookup"><span data-stu-id="8b3cf-140">138</span></span>|<span data-ttu-id="8b3cf-141">结束断开期间的枚举方法。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-141">Enumerates methods during an end rundown.</span></span>|  
  
 <span data-ttu-id="8b3cf-142">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-142">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="8b3cf-143">字段名</span><span class="sxs-lookup"><span data-stu-id="8b3cf-143">Field name</span></span>|<span data-ttu-id="8b3cf-144">数据类型</span><span class="sxs-lookup"><span data-stu-id="8b3cf-144">Data type</span></span>|<span data-ttu-id="8b3cf-145">描述</span><span class="sxs-lookup"><span data-stu-id="8b3cf-145">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="8b3cf-146">MethodID</span><span class="sxs-lookup"><span data-stu-id="8b3cf-146">MethodID</span></span>|<span data-ttu-id="8b3cf-147">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8b3cf-147">win:UInt64</span></span>|<span data-ttu-id="8b3cf-148">方法的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-148">Unique identifier of a method.</span></span> <span data-ttu-id="8b3cf-149">对于 JIT 帮助器方法，将设置为该方法的起始地址。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-149">For JIT helper methods, this is set to the start address of the method.</span></span>|  
|<span data-ttu-id="8b3cf-150">ModuleID</span><span class="sxs-lookup"><span data-stu-id="8b3cf-150">ModuleID</span></span>|<span data-ttu-id="8b3cf-151">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8b3cf-151">win:UInt64</span></span>|<span data-ttu-id="8b3cf-152">此方法所属的模块标识符（0 表示 JIT 帮助器）。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-152">Identifier of the module to which this method belongs (0 for JIT helpers).</span></span>|  
|<span data-ttu-id="8b3cf-153">MethodStartAddress</span><span class="sxs-lookup"><span data-stu-id="8b3cf-153">MethodStartAddress</span></span>|<span data-ttu-id="8b3cf-154">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8b3cf-154">win:UInt64</span></span>|<span data-ttu-id="8b3cf-155">方法的起始地址。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-155">Start address of the method.</span></span>|  
|<span data-ttu-id="8b3cf-156">MethodSize</span><span class="sxs-lookup"><span data-stu-id="8b3cf-156">MethodSize</span></span>|<span data-ttu-id="8b3cf-157">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="8b3cf-157">win:UInt32</span></span>|<span data-ttu-id="8b3cf-158">方法的大小。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-158">Size of the method.</span></span>|  
|<span data-ttu-id="8b3cf-159">MethodToken</span><span class="sxs-lookup"><span data-stu-id="8b3cf-159">MethodToken</span></span>|<span data-ttu-id="8b3cf-160">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="8b3cf-160">win:UInt32</span></span>|<span data-ttu-id="8b3cf-161">0 代表动态方法和 JIT 帮助器。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-161">0 for dynamic methods and JIT helpers.</span></span>|  
|<span data-ttu-id="8b3cf-162">MethodFlags</span><span class="sxs-lookup"><span data-stu-id="8b3cf-162">MethodFlags</span></span>|<span data-ttu-id="8b3cf-163">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="8b3cf-163">win:UInt32</span></span>|<span data-ttu-id="8b3cf-164">0x1：动态方法。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-164">0x1: Dynamic method.</span></span><br /><br /> <span data-ttu-id="8b3cf-165">0x2：泛型方法。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-165">0x2: Generic method.</span></span><br /><br /> <span data-ttu-id="8b3cf-166">0x4：JIT 编译的代码方法（否则为 NGEN 本机映像代码）。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-166">0x4: JIT-compiled code method (otherwise NGEN native image code).</span></span><br /><br /> <span data-ttu-id="8b3cf-167">0x8：帮助器方法。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-167">0x8: Helper method.</span></span>|  
|<span data-ttu-id="8b3cf-168">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="8b3cf-168">ClrInstanceID</span></span>|<span data-ttu-id="8b3cf-169">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="8b3cf-169">win:UInt16</span></span>|<span data-ttu-id="8b3cf-170">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-170">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="8b3cf-171">返回页首</span><span class="sxs-lookup"><span data-stu-id="8b3cf-171">Back to top</span></span>](#top)  
  
<a name="clr_method_marker_events"></a>   
## <a name="clr-method-marker-events"></a><span data-ttu-id="8b3cf-172">CLR 方法标记事件</span><span class="sxs-lookup"><span data-stu-id="8b3cf-172">CLR Method Marker Events</span></span>  
 <span data-ttu-id="8b3cf-173">仅在断开提供程序中会引发这些事件。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-173">These events are raised only under the rundown provider.</span></span> <span data-ttu-id="8b3cf-174">它们表示在启动或结束断开期间方法枚举的结束。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-174">They signify the end of method enumeration during a start or end rundown.</span></span> <span data-ttu-id="8b3cf-175">（即，启用 `NGENRundownKeyword`、 `JitRundownKeyword`、 `LoaderRundownKeyword`或 `AppDomainResourceManagementRundownKeyword` 关键字时引发。）</span><span class="sxs-lookup"><span data-stu-id="8b3cf-175">(That is, they are raised when the `NGENRundownKeyword`, `JitRundownKeyword`, `LoaderRundownKeyword`, or `AppDomainResourceManagementRundownKeyword` keyword is enabled.)</span></span>  
  
 <span data-ttu-id="8b3cf-176">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-176">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="8b3cf-177">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="8b3cf-177">Keyword for raising the event</span></span>|<span data-ttu-id="8b3cf-178">级别</span><span class="sxs-lookup"><span data-stu-id="8b3cf-178">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="8b3cf-179">`AppDomainResourceManagementRundownKeyword` (0x800) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="8b3cf-179">`AppDomainResourceManagementRundownKeyword` (0x800) rundown provider</span></span>|<span data-ttu-id="8b3cf-180">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="8b3cf-180">Informational (4)</span></span>|  
|<span data-ttu-id="8b3cf-181">`JitRundownKeyword` (0x10) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="8b3cf-181">`JitRundownKeyword` (0x10) rundown provider</span></span>|<span data-ttu-id="8b3cf-182">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="8b3cf-182">Informational (4)</span></span>|  
|<span data-ttu-id="8b3cf-183">`NGENRundownKeyword` (0x20) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="8b3cf-183">`NGENRundownKeyword` (0x20) rundown provider</span></span>|<span data-ttu-id="8b3cf-184">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="8b3cf-184">Informational (4)</span></span>|  
  
 <span data-ttu-id="8b3cf-185">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-185">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="8b3cf-186">Event</span><span class="sxs-lookup"><span data-stu-id="8b3cf-186">Event</span></span>|<span data-ttu-id="8b3cf-187">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8b3cf-187">Event ID</span></span>|<span data-ttu-id="8b3cf-188">说明</span><span class="sxs-lookup"><span data-stu-id="8b3cf-188">Desciption</span></span>|  
|-----------|--------------|----------------|  
|`DCStartInit_V1`|<span data-ttu-id="8b3cf-189">147</span><span class="sxs-lookup"><span data-stu-id="8b3cf-189">147</span></span>|<span data-ttu-id="8b3cf-190">启动断开期间枚举开始之前发送。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-190">Sent before the start of the enumeration during a start rundown.</span></span>|  
|`DCStartComplete_V1`|<span data-ttu-id="8b3cf-191">145</span><span class="sxs-lookup"><span data-stu-id="8b3cf-191">145</span></span>|<span data-ttu-id="8b3cf-192">启动断开期间枚举结束时发送。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-192">Sent at the end of the enumeration during a start rundown.</span></span>|  
|`DCEndInit_V1`|<span data-ttu-id="8b3cf-193">148</span><span class="sxs-lookup"><span data-stu-id="8b3cf-193">148</span></span>|<span data-ttu-id="8b3cf-194">结束断开期间枚举开始之前发送。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-194">Sent before the start of the enumeration during an end rundown.</span></span>|  
|`DCEndComplete_V1`|<span data-ttu-id="8b3cf-195">146</span><span class="sxs-lookup"><span data-stu-id="8b3cf-195">146</span></span>|<span data-ttu-id="8b3cf-196">结束断开期间枚举结束时发送。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-196">Sent at the end of the enumeration during an end rundown.</span></span>|  
  
 <span data-ttu-id="8b3cf-197">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-197">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="8b3cf-198">字段名</span><span class="sxs-lookup"><span data-stu-id="8b3cf-198">Field name</span></span>|<span data-ttu-id="8b3cf-199">数据类型</span><span class="sxs-lookup"><span data-stu-id="8b3cf-199">Data type</span></span>|<span data-ttu-id="8b3cf-200">描述</span><span class="sxs-lookup"><span data-stu-id="8b3cf-200">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="8b3cf-201">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="8b3cf-201">ClrInstanceID</span></span>|<span data-ttu-id="8b3cf-202">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="8b3cf-202">win:UInt16</span></span>|<span data-ttu-id="8b3cf-203">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-203">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="8b3cf-204">返回页首</span><span class="sxs-lookup"><span data-stu-id="8b3cf-204">Back to top</span></span>](#top)  
  
<a name="clr_method_verbose_events"></a>   
## <a name="clr-method-verbose-events"></a><span data-ttu-id="8b3cf-205">CLR 方法详细事件</span><span class="sxs-lookup"><span data-stu-id="8b3cf-205">CLR Method Verbose Events</span></span>  
 <span data-ttu-id="8b3cf-206">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-206">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="8b3cf-207">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="8b3cf-207">Keyword for raising the event</span></span>|<span data-ttu-id="8b3cf-208">级别</span><span class="sxs-lookup"><span data-stu-id="8b3cf-208">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="8b3cf-209">`JITKeyword` (0x10) 运行时提供程序</span><span class="sxs-lookup"><span data-stu-id="8b3cf-209">`JITKeyword` (0x10) runtime provider</span></span>|<span data-ttu-id="8b3cf-210">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="8b3cf-210">Verbose (5)</span></span>|  
|<span data-ttu-id="8b3cf-211">`NGenKeyword` (0x20) 运行时提供程序</span><span class="sxs-lookup"><span data-stu-id="8b3cf-211">`NGenKeyword` (0x20) runtime provider</span></span>|<span data-ttu-id="8b3cf-212">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="8b3cf-212">Verbose (5)</span></span>|  
|<span data-ttu-id="8b3cf-213">`JitRundownKeyword` (0x10) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="8b3cf-213">`JitRundownKeyword` (0x10) rundown provider</span></span>|<span data-ttu-id="8b3cf-214">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="8b3cf-214">Verbose (5)</span></span>|  
|<span data-ttu-id="8b3cf-215">`NGENRundownKeyword` (0x20) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="8b3cf-215">`NGENRundownKeyword` (0x20) rundown provider</span></span>|<span data-ttu-id="8b3cf-216">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="8b3cf-216">Verbose (5)</span></span>|  
  
 <span data-ttu-id="8b3cf-217">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="8b3cf-218">Event</span><span class="sxs-lookup"><span data-stu-id="8b3cf-218">Event</span></span>|<span data-ttu-id="8b3cf-219">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8b3cf-219">Event ID</span></span>|<span data-ttu-id="8b3cf-220">描述</span><span class="sxs-lookup"><span data-stu-id="8b3cf-220">Description</span></span>|  
|-----------|--------------|-----------------|  
|`MethodLoadVerbose_V1`|<span data-ttu-id="8b3cf-221">143</span><span class="sxs-lookup"><span data-stu-id="8b3cf-221">143</span></span>|<span data-ttu-id="8b3cf-222">当方法为 JIT 加载的或加载 NGEN 映像时引发。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-222">Raised when a method is JIT-loaded or an NGEN image is loaded.</span></span> <span data-ttu-id="8b3cf-223">动态和泛型方法始终使用此版本进行方法加载。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-223">Dynamic and generic methods always use this version for method loads.</span></span> <span data-ttu-id="8b3cf-224">JIT 帮助器始终使用此版本。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-224">JIT helpers always use this version.</span></span>|  
|`MethodUnLoadVerbose_V1`|<span data-ttu-id="8b3cf-225">144</span><span class="sxs-lookup"><span data-stu-id="8b3cf-225">144</span></span>|<span data-ttu-id="8b3cf-226">在销毁动态方法、卸载模块或销毁应用程序域时引发。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-226">Raised when a dynamic method is destroyed, a module is unloaded, or an application domain is destroyed.</span></span> <span data-ttu-id="8b3cf-227">动态方法始终使用此版本进行方法卸载。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-227">Dynamic methods always use this version for method unloads.</span></span>|  
|`MethodDCStartVerbose_V1`|<span data-ttu-id="8b3cf-228">141</span><span class="sxs-lookup"><span data-stu-id="8b3cf-228">141</span></span>|<span data-ttu-id="8b3cf-229">启动断开期间的枚举方法。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-229">Enumerates methods during a start rundown.</span></span>|  
|`MethodDCEndVerbose_V1`|<span data-ttu-id="8b3cf-230">142</span><span class="sxs-lookup"><span data-stu-id="8b3cf-230">142</span></span>|<span data-ttu-id="8b3cf-231">结束断开期间的枚举方法。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-231">Enumerates methods during an end rundown.</span></span>|  
  
 <span data-ttu-id="8b3cf-232">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-232">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="8b3cf-233">字段名</span><span class="sxs-lookup"><span data-stu-id="8b3cf-233">Field name</span></span>|<span data-ttu-id="8b3cf-234">数据类型</span><span class="sxs-lookup"><span data-stu-id="8b3cf-234">Data type</span></span>|<span data-ttu-id="8b3cf-235">描述</span><span class="sxs-lookup"><span data-stu-id="8b3cf-235">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="8b3cf-236">MethodID</span><span class="sxs-lookup"><span data-stu-id="8b3cf-236">MethodID</span></span>|<span data-ttu-id="8b3cf-237">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8b3cf-237">win:UInt64</span></span>|<span data-ttu-id="8b3cf-238">方法的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-238">Unique identifier of the method.</span></span> <span data-ttu-id="8b3cf-239">对于 JIT 帮助器方法，将设置为该方法的起始地址。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-239">For JIT helper methods, set to the start address of the method.</span></span>|  
|<span data-ttu-id="8b3cf-240">ModuleID</span><span class="sxs-lookup"><span data-stu-id="8b3cf-240">ModuleID</span></span>|<span data-ttu-id="8b3cf-241">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8b3cf-241">win:UInt64</span></span>|<span data-ttu-id="8b3cf-242">此方法所属的模块标识符（0 表示 JIT 帮助器）。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-242">Identifier of the module to which this method belongs (0 for JIT helpers).</span></span>|  
|<span data-ttu-id="8b3cf-243">MethodStartAddress</span><span class="sxs-lookup"><span data-stu-id="8b3cf-243">MethodStartAddress</span></span>|<span data-ttu-id="8b3cf-244">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8b3cf-244">win:UInt64</span></span>|<span data-ttu-id="8b3cf-245">起始地址。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-245">Start address.</span></span>|  
|<span data-ttu-id="8b3cf-246">MethodSize</span><span class="sxs-lookup"><span data-stu-id="8b3cf-246">MethodSize</span></span>|<span data-ttu-id="8b3cf-247">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="8b3cf-247">win:UInt32</span></span>|<span data-ttu-id="8b3cf-248">方法长度。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-248">Method length.</span></span>|  
|<span data-ttu-id="8b3cf-249">MethodToken</span><span class="sxs-lookup"><span data-stu-id="8b3cf-249">MethodToken</span></span>|<span data-ttu-id="8b3cf-250">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="8b3cf-250">win:UInt32</span></span>|<span data-ttu-id="8b3cf-251">0 代表动态方法和 JIT 帮助器。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-251">0 for dynamic methods and JIT helpers.</span></span>|  
|<span data-ttu-id="8b3cf-252">MethodFlags</span><span class="sxs-lookup"><span data-stu-id="8b3cf-252">MethodFlags</span></span>|<span data-ttu-id="8b3cf-253">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="8b3cf-253">win:UInt32</span></span>|<span data-ttu-id="8b3cf-254">0x1：动态方法。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-254">0x1: Dynamic method.</span></span><br /><br /> <span data-ttu-id="8b3cf-255">0x2：泛型方法。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-255">0x2: Generic method.</span></span><br /><br /> <span data-ttu-id="8b3cf-256">0x4：JIT 编译的方法（否则由 NGen.exe 生成）</span><span class="sxs-lookup"><span data-stu-id="8b3cf-256">0x4: JIT-compiled method (otherwise, generated by NGen.exe)</span></span><br /><br /> <span data-ttu-id="8b3cf-257">0x8：帮助器方法。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-257">0x8: Helper method.</span></span>|  
|<span data-ttu-id="8b3cf-258">MethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="8b3cf-258">MethodNameSpace</span></span>|<span data-ttu-id="8b3cf-259">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="8b3cf-259">win:UnicodeString</span></span>|<span data-ttu-id="8b3cf-260">与该方法关联的完整命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-260">Full namespace name associated with the method.</span></span>|  
|<span data-ttu-id="8b3cf-261">MethodName</span><span class="sxs-lookup"><span data-stu-id="8b3cf-261">MethodName</span></span>|<span data-ttu-id="8b3cf-262">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="8b3cf-262">win:UnicodeString</span></span>|<span data-ttu-id="8b3cf-263">与该方法关联的完整类名称。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-263">Full class name associated with the method.</span></span>|  
|<span data-ttu-id="8b3cf-264">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="8b3cf-264">MethodSignature</span></span>|<span data-ttu-id="8b3cf-265">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="8b3cf-265">win:UnicodeString</span></span>|<span data-ttu-id="8b3cf-266">方法的签名（以逗号分隔的类型名称列表）。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-266">Signature of the method (comma-separated list of type names).</span></span>|  
|<span data-ttu-id="8b3cf-267">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="8b3cf-267">ClrInstanceID</span></span>|<span data-ttu-id="8b3cf-268">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="8b3cf-268">win:UInt16</span></span>|<span data-ttu-id="8b3cf-269">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-269">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="8b3cf-270">返回页首</span><span class="sxs-lookup"><span data-stu-id="8b3cf-270">Back to top</span></span>](#top)  
  
<a name="methodjittingstarted_event"></a>   
## <a name="methodjittingstarted-event"></a><span data-ttu-id="8b3cf-271">MethodJittingStarted 事件</span><span class="sxs-lookup"><span data-stu-id="8b3cf-271">MethodJittingStarted Event</span></span>  
 <span data-ttu-id="8b3cf-272">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-272">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="8b3cf-273">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="8b3cf-273">Keyword for raising the event</span></span>|<span data-ttu-id="8b3cf-274">级别</span><span class="sxs-lookup"><span data-stu-id="8b3cf-274">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="8b3cf-275">`JITKeyword` (0x10) 运行时提供程序</span><span class="sxs-lookup"><span data-stu-id="8b3cf-275">`JITKeyword` (0x10) runtime provider</span></span>|<span data-ttu-id="8b3cf-276">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="8b3cf-276">Verbose (5)</span></span>|  
|<span data-ttu-id="8b3cf-277">`NGenKeyword` (0x20) 运行时提供程序</span><span class="sxs-lookup"><span data-stu-id="8b3cf-277">`NGenKeyword` (0x20) runtime provider</span></span>|<span data-ttu-id="8b3cf-278">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="8b3cf-278">Verbose (5)</span></span>|  
|<span data-ttu-id="8b3cf-279">`JitRundownKeyword` (0x10) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="8b3cf-279">`JitRundownKeyword` (0x10) rundown provider</span></span>|<span data-ttu-id="8b3cf-280">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="8b3cf-280">Verbose (5)</span></span>|  
|<span data-ttu-id="8b3cf-281">`NGENRundownKeyword` (0x20) 断开提供程序</span><span class="sxs-lookup"><span data-stu-id="8b3cf-281">`NGENRundownKeyword` (0x20) rundown provider</span></span>|<span data-ttu-id="8b3cf-282">详细级别 (5)</span><span class="sxs-lookup"><span data-stu-id="8b3cf-282">Verbose (5)</span></span>|  
  
 <span data-ttu-id="8b3cf-283">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-283">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="8b3cf-284">Event</span><span class="sxs-lookup"><span data-stu-id="8b3cf-284">Event</span></span>|<span data-ttu-id="8b3cf-285">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8b3cf-285">Event ID</span></span>|<span data-ttu-id="8b3cf-286">描述</span><span class="sxs-lookup"><span data-stu-id="8b3cf-286">Description</span></span>|  
|-----------|--------------|-----------------|  
|`MethodJittingStarted`|<span data-ttu-id="8b3cf-287">145</span><span class="sxs-lookup"><span data-stu-id="8b3cf-287">145</span></span>|<span data-ttu-id="8b3cf-288">在方法由 JIT 编译时引发。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-288">Raised when a method is being JIT-compiled.</span></span>|  
  
 <span data-ttu-id="8b3cf-289">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-289">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="8b3cf-290">字段名</span><span class="sxs-lookup"><span data-stu-id="8b3cf-290">Field name</span></span>|<span data-ttu-id="8b3cf-291">数据类型</span><span class="sxs-lookup"><span data-stu-id="8b3cf-291">Data type</span></span>|<span data-ttu-id="8b3cf-292">描述</span><span class="sxs-lookup"><span data-stu-id="8b3cf-292">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="8b3cf-293">MethodID</span><span class="sxs-lookup"><span data-stu-id="8b3cf-293">MethodID</span></span>|<span data-ttu-id="8b3cf-294">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8b3cf-294">win:UInt64</span></span>|<span data-ttu-id="8b3cf-295">方法的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-295">Unique identifier of the method.</span></span>|  
|<span data-ttu-id="8b3cf-296">ModuleID</span><span class="sxs-lookup"><span data-stu-id="8b3cf-296">ModuleID</span></span>|<span data-ttu-id="8b3cf-297">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8b3cf-297">win:UInt64</span></span>|<span data-ttu-id="8b3cf-298">此方法所属的模块标识符。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-298">Identifier of the module to which this method belongs.</span></span>|  
|<span data-ttu-id="8b3cf-299">MethodToken</span><span class="sxs-lookup"><span data-stu-id="8b3cf-299">MethodToken</span></span>|<span data-ttu-id="8b3cf-300">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="8b3cf-300">win:UInt32</span></span>|<span data-ttu-id="8b3cf-301">0 代表动态方法和 JIT 帮助器。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-301">0 for dynamic methods and JIT helpers.</span></span>|  
|<span data-ttu-id="8b3cf-302">MethodILSize</span><span class="sxs-lookup"><span data-stu-id="8b3cf-302">MethodILSize</span></span>|<span data-ttu-id="8b3cf-303">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="8b3cf-303">win:UInt32</span></span>|<span data-ttu-id="8b3cf-304">JIT 编译的方法的 Microsoft 中间语言 (MSIL) 的大小。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-304">The size of the Microsoft intermediate language (MSIL) for the method that is being JIT-compiled.</span></span>|  
|<span data-ttu-id="8b3cf-305">MethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="8b3cf-305">MethodNameSpace</span></span>|<span data-ttu-id="8b3cf-306">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="8b3cf-306">win:UnicodeString</span></span>|<span data-ttu-id="8b3cf-307">与该方法关联的完整类名称。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-307">Full class name associated with the method.</span></span>|  
|<span data-ttu-id="8b3cf-308">MethodName</span><span class="sxs-lookup"><span data-stu-id="8b3cf-308">MethodName</span></span>|<span data-ttu-id="8b3cf-309">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="8b3cf-309">win:UnicodeString</span></span>|<span data-ttu-id="8b3cf-310">方法的名称。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-310">Name of the method.</span></span>|  
|<span data-ttu-id="8b3cf-311">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="8b3cf-311">MethodSignature</span></span>|<span data-ttu-id="8b3cf-312">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="8b3cf-312">win:UnicodeString</span></span>|<span data-ttu-id="8b3cf-313">方法的签名（以逗号分隔的类型名称列表）。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-313">Signature of the method (comma-separated list of type names).</span></span>|  
|<span data-ttu-id="8b3cf-314">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="8b3cf-314">ClrInstanceID</span></span>|<span data-ttu-id="8b3cf-315">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="8b3cf-315">win:UInt16</span></span>|<span data-ttu-id="8b3cf-316">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="8b3cf-316">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8b3cf-317">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b3cf-317">See Also</span></span>  
 [<span data-ttu-id="8b3cf-318">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="8b3cf-318">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)

