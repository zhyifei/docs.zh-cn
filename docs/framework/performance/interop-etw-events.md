---
title: "互操作 ETW 事件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 55097e38161ea5c76f4e46584241344ec5a52cb9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="interop-etw-events"></a><span data-ttu-id="18acd-102">互操作 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="18acd-102">Interop ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="18acd-103">互操作事件捕获有关 Microsoft 中间语言 (MSIL) 存根生成和缓存的信息。</span><span class="sxs-lookup"><span data-stu-id="18acd-103">Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 <span data-ttu-id="18acd-104">此类别包含以下事件：</span><span class="sxs-lookup"><span data-stu-id="18acd-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="18acd-105">ILStubGenerated 事件</span><span class="sxs-lookup"><span data-stu-id="18acd-105">ILStubGenerated Event</span></span>](#ilstubgenerated_event)  
  
-   [<span data-ttu-id="18acd-106">ILStubCacheHit 事件</span><span class="sxs-lookup"><span data-stu-id="18acd-106">ILStubCacheHit Event</span></span>](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## <a name="ilstubgenerated-event"></a><span data-ttu-id="18acd-107">ILStubGenerated 事件</span><span class="sxs-lookup"><span data-stu-id="18acd-107">ILStubGenerated Event</span></span>  
 <span data-ttu-id="18acd-108">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="18acd-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="18acd-109">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="18acd-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="18acd-110">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="18acd-110">Keyword for raising the event</span></span>|<span data-ttu-id="18acd-111">级别</span><span class="sxs-lookup"><span data-stu-id="18acd-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="18acd-112">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="18acd-112">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="18acd-113">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="18acd-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="18acd-114">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="18acd-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="18acd-115">Event</span><span class="sxs-lookup"><span data-stu-id="18acd-115">Event</span></span>|<span data-ttu-id="18acd-116">事件 ID</span><span class="sxs-lookup"><span data-stu-id="18acd-116">Event ID</span></span>|<span data-ttu-id="18acd-117">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="18acd-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="18acd-118">88</span><span class="sxs-lookup"><span data-stu-id="18acd-118">88</span></span>|<span data-ttu-id="18acd-119">已生成 MSIL 存根。</span><span class="sxs-lookup"><span data-stu-id="18acd-119">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="18acd-120">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="18acd-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="18acd-121">字段名</span><span class="sxs-lookup"><span data-stu-id="18acd-121">Field name</span></span>|<span data-ttu-id="18acd-122">数据类型</span><span class="sxs-lookup"><span data-stu-id="18acd-122">Data type</span></span>|<span data-ttu-id="18acd-123">说明</span><span class="sxs-lookup"><span data-stu-id="18acd-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="18acd-124">ModuleID</span><span class="sxs-lookup"><span data-stu-id="18acd-124">ModuleID</span></span>|<span data-ttu-id="18acd-125">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="18acd-125">win:UInt16</span></span>|<span data-ttu-id="18acd-126">模块标识符。</span><span class="sxs-lookup"><span data-stu-id="18acd-126">The module identifier.</span></span>|  
|<span data-ttu-id="18acd-127">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="18acd-127">StubMethodID</span></span>|<span data-ttu-id="18acd-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="18acd-128">win:UInt64</span></span>|<span data-ttu-id="18acd-129">存根方法标识符。</span><span class="sxs-lookup"><span data-stu-id="18acd-129">The stub method identifier.</span></span>|  
|<span data-ttu-id="18acd-130">StubFlags</span><span class="sxs-lookup"><span data-stu-id="18acd-130">StubFlags</span></span>|<span data-ttu-id="18acd-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="18acd-131">win:UInt64</span></span>|<span data-ttu-id="18acd-132">存根标志：</span><span class="sxs-lookup"><span data-stu-id="18acd-132">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="18acd-133">0x1 - 反向互操作。</span><span class="sxs-lookup"><span data-stu-id="18acd-133">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="18acd-134">0x2 - COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="18acd-134">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="18acd-135">0x4 - 由 NGen.exe 生成的存根。</span><span class="sxs-lookup"><span data-stu-id="18acd-135">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="18acd-136">0x8 - 委托。</span><span class="sxs-lookup"><span data-stu-id="18acd-136">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="18acd-137">0x10 - 可变参数。</span><span class="sxs-lookup"><span data-stu-id="18acd-137">0x10 - Variable arrgument.</span></span><br /><br /> <span data-ttu-id="18acd-138">0x20 - 非托管被调用方。</span><span class="sxs-lookup"><span data-stu-id="18acd-138">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="18acd-139">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="18acd-139">ManagedInteropMethodToken</span></span>|<span data-ttu-id="18acd-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="18acd-140">win:UInt32</span></span>|<span data-ttu-id="18acd-141">托管互操作方法的标记。</span><span class="sxs-lookup"><span data-stu-id="18acd-141">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="18acd-142">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="18acd-142">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="18acd-143">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="18acd-143">win:UnicodeString</span></span>|<span data-ttu-id="18acd-144">托管互操作方法的命名空间。</span><span class="sxs-lookup"><span data-stu-id="18acd-144">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="18acd-145">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="18acd-145">ManagedInteropMethodName</span></span>|<span data-ttu-id="18acd-146">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="18acd-146">win:UnicodeString</span></span>|<span data-ttu-id="18acd-147">托管互操作方法的名称。</span><span class="sxs-lookup"><span data-stu-id="18acd-147">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="18acd-148">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="18acd-148">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="18acd-149">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="18acd-149">win:UnicodeString</span></span>|<span data-ttu-id="18acd-150">托管互操作方法的签名。</span><span class="sxs-lookup"><span data-stu-id="18acd-150">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="18acd-151">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="18acd-151">NativeMethodSignature</span></span>|<span data-ttu-id="18acd-152">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="18acd-152">win:UnicodeString</span></span>|<span data-ttu-id="18acd-153">本机方法签名。</span><span class="sxs-lookup"><span data-stu-id="18acd-153">The native method signature.</span></span>|  
|<span data-ttu-id="18acd-154">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="18acd-154">StubMethodSignature</span></span>|<span data-ttu-id="18acd-155">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="18acd-155">win:UnicodeString</span></span>|<span data-ttu-id="18acd-156">存根方法签名。</span><span class="sxs-lookup"><span data-stu-id="18acd-156">The stub method signature.</span></span>|  
|<span data-ttu-id="18acd-157">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="18acd-157">StubMethodILCode</span></span>|<span data-ttu-id="18acd-158">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="18acd-158">win:UnicodeString</span></span>|<span data-ttu-id="18acd-159">存根方法的 MSIL 代码。</span><span class="sxs-lookup"><span data-stu-id="18acd-159">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="18acd-160">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="18acd-160">ClrInstanceID</span></span>|<span data-ttu-id="18acd-161">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="18acd-161">win:UInt16</span></span>|<span data-ttu-id="18acd-162">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="18acd-162">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="18acd-163">返回页首</span><span class="sxs-lookup"><span data-stu-id="18acd-163">Back to top</span></span>](#top)  
  
<a name="ilstubcachehit_event"></a>   
## <a name="ilstubcachehit-event"></a><span data-ttu-id="18acd-164">ILStubCacheHit 事件</span><span class="sxs-lookup"><span data-stu-id="18acd-164">ILStubCacheHit Event</span></span>  
 <span data-ttu-id="18acd-165">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="18acd-165">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="18acd-166">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="18acd-166">Keyword for raising the event</span></span>|<span data-ttu-id="18acd-167">级别</span><span class="sxs-lookup"><span data-stu-id="18acd-167">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="18acd-168">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="18acd-168">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="18acd-169">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="18acd-169">Informational(4)</span></span>|  
  
 <span data-ttu-id="18acd-170">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="18acd-170">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="18acd-171">Event</span><span class="sxs-lookup"><span data-stu-id="18acd-171">Event</span></span>|<span data-ttu-id="18acd-172">事件 ID</span><span class="sxs-lookup"><span data-stu-id="18acd-172">Event ID</span></span>|<span data-ttu-id="18acd-173">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="18acd-173">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="18acd-174">89</span><span class="sxs-lookup"><span data-stu-id="18acd-174">89</span></span>|<span data-ttu-id="18acd-175">已访问 MSIL 缓存。</span><span class="sxs-lookup"><span data-stu-id="18acd-175">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="18acd-176">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="18acd-176">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="18acd-177">字段名</span><span class="sxs-lookup"><span data-stu-id="18acd-177">Field name</span></span>|<span data-ttu-id="18acd-178">数据类型</span><span class="sxs-lookup"><span data-stu-id="18acd-178">Data type</span></span>|<span data-ttu-id="18acd-179">说明</span><span class="sxs-lookup"><span data-stu-id="18acd-179">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="18acd-180">ModuleID</span><span class="sxs-lookup"><span data-stu-id="18acd-180">ModuleID</span></span>|<span data-ttu-id="18acd-181">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="18acd-181">win:UInt16</span></span>|<span data-ttu-id="18acd-182">模块标识符。</span><span class="sxs-lookup"><span data-stu-id="18acd-182">The module identifier.</span></span>|  
|<span data-ttu-id="18acd-183">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="18acd-183">StubMethodID</span></span>|<span data-ttu-id="18acd-184">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="18acd-184">win:UInt64</span></span>|<span data-ttu-id="18acd-185">存根方法标识符。</span><span class="sxs-lookup"><span data-stu-id="18acd-185">The stub method identifier.</span></span>|  
|<span data-ttu-id="18acd-186">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="18acd-186">ManagedInteropMethodToken</span></span>|<span data-ttu-id="18acd-187">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="18acd-187">win:UInt32</span></span>|<span data-ttu-id="18acd-188">托管互操作方法的标记。</span><span class="sxs-lookup"><span data-stu-id="18acd-188">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="18acd-189">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="18acd-189">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="18acd-190">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="18acd-190">win:UnicodeString</span></span>|<span data-ttu-id="18acd-191">托管互操作方法的命名空间。</span><span class="sxs-lookup"><span data-stu-id="18acd-191">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="18acd-192">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="18acd-192">ManagedInteropMethodName</span></span>|<span data-ttu-id="18acd-193">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="18acd-193">win:UnicodeString</span></span>|<span data-ttu-id="18acd-194">托管互操作方法的名称。</span><span class="sxs-lookup"><span data-stu-id="18acd-194">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="18acd-195">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="18acd-195">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="18acd-196">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="18acd-196">win:UnicodeString</span></span>|<span data-ttu-id="18acd-197">托管互操作方法的签名。</span><span class="sxs-lookup"><span data-stu-id="18acd-197">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="18acd-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="18acd-198">ClrInstanceID</span></span>|<span data-ttu-id="18acd-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="18acd-199">win:UInt16</span></span>|<span data-ttu-id="18acd-200">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="18acd-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="18acd-201">返回页首</span><span class="sxs-lookup"><span data-stu-id="18acd-201">Back to top</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="18acd-202">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18acd-202">See Also</span></span>  
 [<span data-ttu-id="18acd-203">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="18acd-203">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
