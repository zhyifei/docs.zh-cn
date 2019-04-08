---
title: 互操作 ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 09b2848619256a255cc27f0268d46e5e6db8cbe4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083603"
---
# <a name="interop-etw-events"></a><span data-ttu-id="4ae41-102">互操作 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="4ae41-102">Interop ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="4ae41-103">互操作事件捕获有关 Microsoft 中间语言 (MSIL) 存根生成和缓存的信息。</span><span class="sxs-lookup"><span data-stu-id="4ae41-103">Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 <span data-ttu-id="4ae41-104">此类别包含以下事件：</span><span class="sxs-lookup"><span data-stu-id="4ae41-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="4ae41-105">ILStubGenerated 事件</span><span class="sxs-lookup"><span data-stu-id="4ae41-105">ILStubGenerated Event</span></span>](#ilstubgenerated_event)  
  
-   [<span data-ttu-id="4ae41-106">ILStubCacheHit 事件</span><span class="sxs-lookup"><span data-stu-id="4ae41-106">ILStubCacheHit Event</span></span>](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## <a name="ilstubgenerated-event"></a><span data-ttu-id="4ae41-107">ILStubGenerated 事件</span><span class="sxs-lookup"><span data-stu-id="4ae41-107">ILStubGenerated Event</span></span>  
 <span data-ttu-id="4ae41-108">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="4ae41-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="4ae41-109">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="4ae41-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="4ae41-110">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="4ae41-110">Keyword for raising the event</span></span>|<span data-ttu-id="4ae41-111">级别</span><span class="sxs-lookup"><span data-stu-id="4ae41-111">Level</span></span>|  
|-----------------------------------|-----------|  
|`InteropKeyword` <span data-ttu-id="4ae41-112">(0x2000)</span><span class="sxs-lookup"><span data-stu-id="4ae41-112">(0x2000)</span></span>|<span data-ttu-id="4ae41-113">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="4ae41-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="4ae41-114">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="4ae41-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="4ae41-115">Event</span><span class="sxs-lookup"><span data-stu-id="4ae41-115">Event</span></span>|<span data-ttu-id="4ae41-116">事件 ID</span><span class="sxs-lookup"><span data-stu-id="4ae41-116">Event ID</span></span>|<span data-ttu-id="4ae41-117">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="4ae41-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="4ae41-118">88</span><span class="sxs-lookup"><span data-stu-id="4ae41-118">88</span></span>|<span data-ttu-id="4ae41-119">已生成 MSIL 存根。</span><span class="sxs-lookup"><span data-stu-id="4ae41-119">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="4ae41-120">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="4ae41-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="4ae41-121">字段名</span><span class="sxs-lookup"><span data-stu-id="4ae41-121">Field name</span></span>|<span data-ttu-id="4ae41-122">数据类型</span><span class="sxs-lookup"><span data-stu-id="4ae41-122">Data type</span></span>|<span data-ttu-id="4ae41-123">描述</span><span class="sxs-lookup"><span data-stu-id="4ae41-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="4ae41-124">ModuleID</span><span class="sxs-lookup"><span data-stu-id="4ae41-124">ModuleID</span></span>|<span data-ttu-id="4ae41-125">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4ae41-125">win:UInt16</span></span>|<span data-ttu-id="4ae41-126">模块标识符。</span><span class="sxs-lookup"><span data-stu-id="4ae41-126">The module identifier.</span></span>|  
|<span data-ttu-id="4ae41-127">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="4ae41-127">StubMethodID</span></span>|<span data-ttu-id="4ae41-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4ae41-128">win:UInt64</span></span>|<span data-ttu-id="4ae41-129">存根方法标识符。</span><span class="sxs-lookup"><span data-stu-id="4ae41-129">The stub method identifier.</span></span>|  
|<span data-ttu-id="4ae41-130">StubFlags</span><span class="sxs-lookup"><span data-stu-id="4ae41-130">StubFlags</span></span>|<span data-ttu-id="4ae41-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4ae41-131">win:UInt64</span></span>|<span data-ttu-id="4ae41-132">存根标志：</span><span class="sxs-lookup"><span data-stu-id="4ae41-132">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="4ae41-133">0x1 - 反向互操作。</span><span class="sxs-lookup"><span data-stu-id="4ae41-133">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="4ae41-134">0x2 - COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="4ae41-134">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="4ae41-135">0x4 - 由 NGen.exe 生成的存根。</span><span class="sxs-lookup"><span data-stu-id="4ae41-135">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="4ae41-136">0x8 - 委托。</span><span class="sxs-lookup"><span data-stu-id="4ae41-136">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="4ae41-137">0x10 - 可变参数。</span><span class="sxs-lookup"><span data-stu-id="4ae41-137">0x10 - Variable arrgument.</span></span><br /><br /> <span data-ttu-id="4ae41-138">0x20 - 非托管被调用方。</span><span class="sxs-lookup"><span data-stu-id="4ae41-138">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="4ae41-139">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="4ae41-139">ManagedInteropMethodToken</span></span>|<span data-ttu-id="4ae41-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4ae41-140">win:UInt32</span></span>|<span data-ttu-id="4ae41-141">托管互操作方法的标记。</span><span class="sxs-lookup"><span data-stu-id="4ae41-141">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="4ae41-142">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="4ae41-142">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="4ae41-143">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="4ae41-143">win:UnicodeString</span></span>|<span data-ttu-id="4ae41-144">托管互操作方法的命名空间。</span><span class="sxs-lookup"><span data-stu-id="4ae41-144">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="4ae41-145">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="4ae41-145">ManagedInteropMethodName</span></span>|<span data-ttu-id="4ae41-146">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="4ae41-146">win:UnicodeString</span></span>|<span data-ttu-id="4ae41-147">托管互操作方法的名称。</span><span class="sxs-lookup"><span data-stu-id="4ae41-147">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="4ae41-148">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="4ae41-148">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="4ae41-149">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="4ae41-149">win:UnicodeString</span></span>|<span data-ttu-id="4ae41-150">托管互操作方法的签名。</span><span class="sxs-lookup"><span data-stu-id="4ae41-150">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="4ae41-151">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="4ae41-151">NativeMethodSignature</span></span>|<span data-ttu-id="4ae41-152">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="4ae41-152">win:UnicodeString</span></span>|<span data-ttu-id="4ae41-153">本机方法签名。</span><span class="sxs-lookup"><span data-stu-id="4ae41-153">The native method signature.</span></span>|  
|<span data-ttu-id="4ae41-154">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="4ae41-154">StubMethodSignature</span></span>|<span data-ttu-id="4ae41-155">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="4ae41-155">win:UnicodeString</span></span>|<span data-ttu-id="4ae41-156">存根方法签名。</span><span class="sxs-lookup"><span data-stu-id="4ae41-156">The stub method signature.</span></span>|  
|<span data-ttu-id="4ae41-157">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="4ae41-157">StubMethodILCode</span></span>|<span data-ttu-id="4ae41-158">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="4ae41-158">win:UnicodeString</span></span>|<span data-ttu-id="4ae41-159">存根方法的 MSIL 代码。</span><span class="sxs-lookup"><span data-stu-id="4ae41-159">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="4ae41-160">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4ae41-160">ClrInstanceID</span></span>|<span data-ttu-id="4ae41-161">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4ae41-161">win:UInt16</span></span>|<span data-ttu-id="4ae41-162">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="4ae41-162">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="4ae41-163">返回页首</span><span class="sxs-lookup"><span data-stu-id="4ae41-163">Back to top</span></span>](#top)  
  
<a name="ilstubcachehit_event"></a>   
## <a name="ilstubcachehit-event"></a><span data-ttu-id="4ae41-164">ILStubCacheHit 事件</span><span class="sxs-lookup"><span data-stu-id="4ae41-164">ILStubCacheHit Event</span></span>  
 <span data-ttu-id="4ae41-165">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="4ae41-165">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="4ae41-166">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="4ae41-166">Keyword for raising the event</span></span>|<span data-ttu-id="4ae41-167">级别</span><span class="sxs-lookup"><span data-stu-id="4ae41-167">Level</span></span>|  
|-----------------------------------|-----------|  
|`InteropKeyword` <span data-ttu-id="4ae41-168">(0x2000)</span><span class="sxs-lookup"><span data-stu-id="4ae41-168">(0x2000)</span></span>|<span data-ttu-id="4ae41-169">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="4ae41-169">Informational(4)</span></span>|  
  
 <span data-ttu-id="4ae41-170">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="4ae41-170">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="4ae41-171">Event</span><span class="sxs-lookup"><span data-stu-id="4ae41-171">Event</span></span>|<span data-ttu-id="4ae41-172">事件 ID</span><span class="sxs-lookup"><span data-stu-id="4ae41-172">Event ID</span></span>|<span data-ttu-id="4ae41-173">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="4ae41-173">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="4ae41-174">89</span><span class="sxs-lookup"><span data-stu-id="4ae41-174">89</span></span>|<span data-ttu-id="4ae41-175">已访问 MSIL 缓存。</span><span class="sxs-lookup"><span data-stu-id="4ae41-175">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="4ae41-176">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="4ae41-176">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="4ae41-177">字段名</span><span class="sxs-lookup"><span data-stu-id="4ae41-177">Field name</span></span>|<span data-ttu-id="4ae41-178">数据类型</span><span class="sxs-lookup"><span data-stu-id="4ae41-178">Data type</span></span>|<span data-ttu-id="4ae41-179">描述</span><span class="sxs-lookup"><span data-stu-id="4ae41-179">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="4ae41-180">ModuleID</span><span class="sxs-lookup"><span data-stu-id="4ae41-180">ModuleID</span></span>|<span data-ttu-id="4ae41-181">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4ae41-181">win:UInt16</span></span>|<span data-ttu-id="4ae41-182">模块标识符。</span><span class="sxs-lookup"><span data-stu-id="4ae41-182">The module identifier.</span></span>|  
|<span data-ttu-id="4ae41-183">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="4ae41-183">StubMethodID</span></span>|<span data-ttu-id="4ae41-184">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4ae41-184">win:UInt64</span></span>|<span data-ttu-id="4ae41-185">存根方法标识符。</span><span class="sxs-lookup"><span data-stu-id="4ae41-185">The stub method identifier.</span></span>|  
|<span data-ttu-id="4ae41-186">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="4ae41-186">ManagedInteropMethodToken</span></span>|<span data-ttu-id="4ae41-187">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4ae41-187">win:UInt32</span></span>|<span data-ttu-id="4ae41-188">托管互操作方法的标记。</span><span class="sxs-lookup"><span data-stu-id="4ae41-188">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="4ae41-189">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="4ae41-189">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="4ae41-190">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="4ae41-190">win:UnicodeString</span></span>|<span data-ttu-id="4ae41-191">托管互操作方法的命名空间。</span><span class="sxs-lookup"><span data-stu-id="4ae41-191">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="4ae41-192">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="4ae41-192">ManagedInteropMethodName</span></span>|<span data-ttu-id="4ae41-193">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="4ae41-193">win:UnicodeString</span></span>|<span data-ttu-id="4ae41-194">托管互操作方法的名称。</span><span class="sxs-lookup"><span data-stu-id="4ae41-194">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="4ae41-195">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="4ae41-195">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="4ae41-196">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="4ae41-196">win:UnicodeString</span></span>|<span data-ttu-id="4ae41-197">托管互操作方法的签名。</span><span class="sxs-lookup"><span data-stu-id="4ae41-197">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="4ae41-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4ae41-198">ClrInstanceID</span></span>|<span data-ttu-id="4ae41-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4ae41-199">win:UInt16</span></span>|<span data-ttu-id="4ae41-200">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="4ae41-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="4ae41-201">返回页首</span><span class="sxs-lookup"><span data-stu-id="4ae41-201">Back to top</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="4ae41-202">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ae41-202">See also</span></span>

- [<span data-ttu-id="4ae41-203">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="4ae41-203">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
