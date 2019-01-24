---
title: 互操作 ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fb458958f55a3f9fb2b79d87f0ee32d4a028e457
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611769"
---
# <a name="interop-etw-events"></a><span data-ttu-id="a261b-102">互操作 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="a261b-102">Interop ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="a261b-103">互操作事件捕获有关 Microsoft 中间语言 (MSIL) 存根生成和缓存的信息。</span><span class="sxs-lookup"><span data-stu-id="a261b-103">Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 <span data-ttu-id="a261b-104">此类别包含以下事件：</span><span class="sxs-lookup"><span data-stu-id="a261b-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="a261b-105">ILStubGenerated 事件</span><span class="sxs-lookup"><span data-stu-id="a261b-105">ILStubGenerated Event</span></span>](#ilstubgenerated_event)  
  
-   [<span data-ttu-id="a261b-106">ILStubCacheHit 事件</span><span class="sxs-lookup"><span data-stu-id="a261b-106">ILStubCacheHit Event</span></span>](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## <a name="ilstubgenerated-event"></a><span data-ttu-id="a261b-107">ILStubGenerated 事件</span><span class="sxs-lookup"><span data-stu-id="a261b-107">ILStubGenerated Event</span></span>  
 <span data-ttu-id="a261b-108">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a261b-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="a261b-109">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="a261b-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="a261b-110">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a261b-110">Keyword for raising the event</span></span>|<span data-ttu-id="a261b-111">级别</span><span class="sxs-lookup"><span data-stu-id="a261b-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a261b-112">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="a261b-112">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="a261b-113">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a261b-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="a261b-114">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a261b-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a261b-115">Event</span><span class="sxs-lookup"><span data-stu-id="a261b-115">Event</span></span>|<span data-ttu-id="a261b-116">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a261b-116">Event ID</span></span>|<span data-ttu-id="a261b-117">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a261b-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="a261b-118">88</span><span class="sxs-lookup"><span data-stu-id="a261b-118">88</span></span>|<span data-ttu-id="a261b-119">已生成 MSIL 存根。</span><span class="sxs-lookup"><span data-stu-id="a261b-119">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="a261b-120">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="a261b-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a261b-121">字段名</span><span class="sxs-lookup"><span data-stu-id="a261b-121">Field name</span></span>|<span data-ttu-id="a261b-122">数据类型</span><span class="sxs-lookup"><span data-stu-id="a261b-122">Data type</span></span>|<span data-ttu-id="a261b-123">描述</span><span class="sxs-lookup"><span data-stu-id="a261b-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a261b-124">ModuleID</span><span class="sxs-lookup"><span data-stu-id="a261b-124">ModuleID</span></span>|<span data-ttu-id="a261b-125">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a261b-125">win:UInt16</span></span>|<span data-ttu-id="a261b-126">模块标识符。</span><span class="sxs-lookup"><span data-stu-id="a261b-126">The module identifier.</span></span>|  
|<span data-ttu-id="a261b-127">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="a261b-127">StubMethodID</span></span>|<span data-ttu-id="a261b-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a261b-128">win:UInt64</span></span>|<span data-ttu-id="a261b-129">存根方法标识符。</span><span class="sxs-lookup"><span data-stu-id="a261b-129">The stub method identifier.</span></span>|  
|<span data-ttu-id="a261b-130">StubFlags</span><span class="sxs-lookup"><span data-stu-id="a261b-130">StubFlags</span></span>|<span data-ttu-id="a261b-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a261b-131">win:UInt64</span></span>|<span data-ttu-id="a261b-132">存根标志：</span><span class="sxs-lookup"><span data-stu-id="a261b-132">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="a261b-133">0x1 - 反向互操作。</span><span class="sxs-lookup"><span data-stu-id="a261b-133">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="a261b-134">0x2 - COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="a261b-134">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="a261b-135">0x4 - 由 NGen.exe 生成的存根。</span><span class="sxs-lookup"><span data-stu-id="a261b-135">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="a261b-136">0x8 - 委托。</span><span class="sxs-lookup"><span data-stu-id="a261b-136">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="a261b-137">0x10 - 可变参数。</span><span class="sxs-lookup"><span data-stu-id="a261b-137">0x10 - Variable arrgument.</span></span><br /><br /> <span data-ttu-id="a261b-138">0x20 - 非托管被调用方。</span><span class="sxs-lookup"><span data-stu-id="a261b-138">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="a261b-139">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="a261b-139">ManagedInteropMethodToken</span></span>|<span data-ttu-id="a261b-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a261b-140">win:UInt32</span></span>|<span data-ttu-id="a261b-141">托管互操作方法的标记。</span><span class="sxs-lookup"><span data-stu-id="a261b-141">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="a261b-142">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="a261b-142">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="a261b-143">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a261b-143">win:UnicodeString</span></span>|<span data-ttu-id="a261b-144">托管互操作方法的命名空间。</span><span class="sxs-lookup"><span data-stu-id="a261b-144">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="a261b-145">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="a261b-145">ManagedInteropMethodName</span></span>|<span data-ttu-id="a261b-146">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a261b-146">win:UnicodeString</span></span>|<span data-ttu-id="a261b-147">托管互操作方法的名称。</span><span class="sxs-lookup"><span data-stu-id="a261b-147">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="a261b-148">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="a261b-148">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="a261b-149">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a261b-149">win:UnicodeString</span></span>|<span data-ttu-id="a261b-150">托管互操作方法的签名。</span><span class="sxs-lookup"><span data-stu-id="a261b-150">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="a261b-151">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="a261b-151">NativeMethodSignature</span></span>|<span data-ttu-id="a261b-152">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a261b-152">win:UnicodeString</span></span>|<span data-ttu-id="a261b-153">本机方法签名。</span><span class="sxs-lookup"><span data-stu-id="a261b-153">The native method signature.</span></span>|  
|<span data-ttu-id="a261b-154">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="a261b-154">StubMethodSignature</span></span>|<span data-ttu-id="a261b-155">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a261b-155">win:UnicodeString</span></span>|<span data-ttu-id="a261b-156">存根方法签名。</span><span class="sxs-lookup"><span data-stu-id="a261b-156">The stub method signature.</span></span>|  
|<span data-ttu-id="a261b-157">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="a261b-157">StubMethodILCode</span></span>|<span data-ttu-id="a261b-158">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a261b-158">win:UnicodeString</span></span>|<span data-ttu-id="a261b-159">存根方法的 MSIL 代码。</span><span class="sxs-lookup"><span data-stu-id="a261b-159">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="a261b-160">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a261b-160">ClrInstanceID</span></span>|<span data-ttu-id="a261b-161">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a261b-161">win:UInt16</span></span>|<span data-ttu-id="a261b-162">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a261b-162">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a261b-163">返回页首</span><span class="sxs-lookup"><span data-stu-id="a261b-163">Back to top</span></span>](#top)  
  
<a name="ilstubcachehit_event"></a>   
## <a name="ilstubcachehit-event"></a><span data-ttu-id="a261b-164">ILStubCacheHit 事件</span><span class="sxs-lookup"><span data-stu-id="a261b-164">ILStubCacheHit Event</span></span>  
 <span data-ttu-id="a261b-165">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a261b-165">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a261b-166">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a261b-166">Keyword for raising the event</span></span>|<span data-ttu-id="a261b-167">级别</span><span class="sxs-lookup"><span data-stu-id="a261b-167">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a261b-168">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="a261b-168">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="a261b-169">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a261b-169">Informational(4)</span></span>|  
  
 <span data-ttu-id="a261b-170">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a261b-170">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a261b-171">Event</span><span class="sxs-lookup"><span data-stu-id="a261b-171">Event</span></span>|<span data-ttu-id="a261b-172">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a261b-172">Event ID</span></span>|<span data-ttu-id="a261b-173">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a261b-173">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="a261b-174">89</span><span class="sxs-lookup"><span data-stu-id="a261b-174">89</span></span>|<span data-ttu-id="a261b-175">已访问 MSIL 缓存。</span><span class="sxs-lookup"><span data-stu-id="a261b-175">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="a261b-176">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="a261b-176">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a261b-177">字段名</span><span class="sxs-lookup"><span data-stu-id="a261b-177">Field name</span></span>|<span data-ttu-id="a261b-178">数据类型</span><span class="sxs-lookup"><span data-stu-id="a261b-178">Data type</span></span>|<span data-ttu-id="a261b-179">描述</span><span class="sxs-lookup"><span data-stu-id="a261b-179">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a261b-180">ModuleID</span><span class="sxs-lookup"><span data-stu-id="a261b-180">ModuleID</span></span>|<span data-ttu-id="a261b-181">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a261b-181">win:UInt16</span></span>|<span data-ttu-id="a261b-182">模块标识符。</span><span class="sxs-lookup"><span data-stu-id="a261b-182">The module identifier.</span></span>|  
|<span data-ttu-id="a261b-183">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="a261b-183">StubMethodID</span></span>|<span data-ttu-id="a261b-184">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a261b-184">win:UInt64</span></span>|<span data-ttu-id="a261b-185">存根方法标识符。</span><span class="sxs-lookup"><span data-stu-id="a261b-185">The stub method identifier.</span></span>|  
|<span data-ttu-id="a261b-186">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="a261b-186">ManagedInteropMethodToken</span></span>|<span data-ttu-id="a261b-187">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a261b-187">win:UInt32</span></span>|<span data-ttu-id="a261b-188">托管互操作方法的标记。</span><span class="sxs-lookup"><span data-stu-id="a261b-188">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="a261b-189">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="a261b-189">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="a261b-190">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a261b-190">win:UnicodeString</span></span>|<span data-ttu-id="a261b-191">托管互操作方法的命名空间。</span><span class="sxs-lookup"><span data-stu-id="a261b-191">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="a261b-192">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="a261b-192">ManagedInteropMethodName</span></span>|<span data-ttu-id="a261b-193">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a261b-193">win:UnicodeString</span></span>|<span data-ttu-id="a261b-194">托管互操作方法的名称。</span><span class="sxs-lookup"><span data-stu-id="a261b-194">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="a261b-195">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="a261b-195">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="a261b-196">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a261b-196">win:UnicodeString</span></span>|<span data-ttu-id="a261b-197">托管互操作方法的签名。</span><span class="sxs-lookup"><span data-stu-id="a261b-197">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="a261b-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a261b-198">ClrInstanceID</span></span>|<span data-ttu-id="a261b-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a261b-199">win:UInt16</span></span>|<span data-ttu-id="a261b-200">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a261b-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a261b-201">返回页首</span><span class="sxs-lookup"><span data-stu-id="a261b-201">Back to top</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="a261b-202">请参阅</span><span class="sxs-lookup"><span data-stu-id="a261b-202">See also</span></span>
- [<span data-ttu-id="a261b-203">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="a261b-203">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
