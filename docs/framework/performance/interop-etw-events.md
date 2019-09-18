---
title: 互操作 ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 787c6221b651a53dbb932a5a9d0edea123e1d97d
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046440"
---
# <a name="interop-etw-events"></a><span data-ttu-id="8e0ea-102">互操作 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="8e0ea-102">Interop ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="8e0ea-103">互操作事件捕获有关 Microsoft 中间语言 (MSIL) 存根生成和缓存的信息。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-103">Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 <span data-ttu-id="8e0ea-104">此类别包含以下事件：</span><span class="sxs-lookup"><span data-stu-id="8e0ea-104">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="8e0ea-105">ILStubGenerated 事件</span><span class="sxs-lookup"><span data-stu-id="8e0ea-105">ILStubGenerated Event</span></span>](#ilstubgenerated_event)  
  
- [<span data-ttu-id="8e0ea-106">ILStubCacheHit 事件</span><span class="sxs-lookup"><span data-stu-id="8e0ea-106">ILStubCacheHit Event</span></span>](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## <a name="ilstubgenerated-event"></a><span data-ttu-id="8e0ea-107">ILStubGenerated 事件</span><span class="sxs-lookup"><span data-stu-id="8e0ea-107">ILStubGenerated Event</span></span>  
 <span data-ttu-id="8e0ea-108">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="8e0ea-109">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="8e0ea-109">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="8e0ea-110">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="8e0ea-110">Keyword for raising the event</span></span>|<span data-ttu-id="8e0ea-111">Level</span><span class="sxs-lookup"><span data-stu-id="8e0ea-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="8e0ea-112">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="8e0ea-112">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="8e0ea-113">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="8e0ea-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="8e0ea-114">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="8e0ea-115">Event</span><span class="sxs-lookup"><span data-stu-id="8e0ea-115">Event</span></span>|<span data-ttu-id="8e0ea-116">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8e0ea-116">Event ID</span></span>|<span data-ttu-id="8e0ea-117">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="8e0ea-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="8e0ea-118">88</span><span class="sxs-lookup"><span data-stu-id="8e0ea-118">88</span></span>|<span data-ttu-id="8e0ea-119">已生成 MSIL 存根。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-119">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="8e0ea-120">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="8e0ea-121">字段名</span><span class="sxs-lookup"><span data-stu-id="8e0ea-121">Field name</span></span>|<span data-ttu-id="8e0ea-122">数据类型</span><span class="sxs-lookup"><span data-stu-id="8e0ea-122">Data type</span></span>|<span data-ttu-id="8e0ea-123">描述</span><span class="sxs-lookup"><span data-stu-id="8e0ea-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="8e0ea-124">ModuleID</span><span class="sxs-lookup"><span data-stu-id="8e0ea-124">ModuleID</span></span>|<span data-ttu-id="8e0ea-125">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="8e0ea-125">win:UInt16</span></span>|<span data-ttu-id="8e0ea-126">模块标识符。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-126">The module identifier.</span></span>|  
|<span data-ttu-id="8e0ea-127">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="8e0ea-127">StubMethodID</span></span>|<span data-ttu-id="8e0ea-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8e0ea-128">win:UInt64</span></span>|<span data-ttu-id="8e0ea-129">存根方法标识符。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-129">The stub method identifier.</span></span>|  
|<span data-ttu-id="8e0ea-130">StubFlags</span><span class="sxs-lookup"><span data-stu-id="8e0ea-130">StubFlags</span></span>|<span data-ttu-id="8e0ea-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8e0ea-131">win:UInt64</span></span>|<span data-ttu-id="8e0ea-132">存根标志：</span><span class="sxs-lookup"><span data-stu-id="8e0ea-132">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="8e0ea-133">0x1 - 反向互操作。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-133">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="8e0ea-134">0x2 - COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-134">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="8e0ea-135">0x4 - 由 NGen.exe 生成的存根。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-135">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="8e0ea-136">0x8 - 委托。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-136">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="8e0ea-137">0x10-可变参数。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-137">0x10 - Variable argument.</span></span><br /><br /> <span data-ttu-id="8e0ea-138">0x20 - 非托管被调用方。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-138">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="8e0ea-139">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="8e0ea-139">ManagedInteropMethodToken</span></span>|<span data-ttu-id="8e0ea-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="8e0ea-140">win:UInt32</span></span>|<span data-ttu-id="8e0ea-141">托管互操作方法的标记。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-141">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="8e0ea-142">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="8e0ea-142">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="8e0ea-143">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="8e0ea-143">win:UnicodeString</span></span>|<span data-ttu-id="8e0ea-144">托管互操作方法的命名空间。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-144">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="8e0ea-145">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="8e0ea-145">ManagedInteropMethodName</span></span>|<span data-ttu-id="8e0ea-146">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="8e0ea-146">win:UnicodeString</span></span>|<span data-ttu-id="8e0ea-147">托管互操作方法的名称。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-147">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="8e0ea-148">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="8e0ea-148">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="8e0ea-149">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="8e0ea-149">win:UnicodeString</span></span>|<span data-ttu-id="8e0ea-150">托管互操作方法的签名。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-150">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="8e0ea-151">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="8e0ea-151">NativeMethodSignature</span></span>|<span data-ttu-id="8e0ea-152">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="8e0ea-152">win:UnicodeString</span></span>|<span data-ttu-id="8e0ea-153">本机方法签名。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-153">The native method signature.</span></span>|  
|<span data-ttu-id="8e0ea-154">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="8e0ea-154">StubMethodSignature</span></span>|<span data-ttu-id="8e0ea-155">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="8e0ea-155">win:UnicodeString</span></span>|<span data-ttu-id="8e0ea-156">存根方法签名。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-156">The stub method signature.</span></span>|  
|<span data-ttu-id="8e0ea-157">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="8e0ea-157">StubMethodILCode</span></span>|<span data-ttu-id="8e0ea-158">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="8e0ea-158">win:UnicodeString</span></span>|<span data-ttu-id="8e0ea-159">存根方法的 MSIL 代码。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-159">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="8e0ea-160">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="8e0ea-160">ClrInstanceID</span></span>|<span data-ttu-id="8e0ea-161">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="8e0ea-161">win:UInt16</span></span>|<span data-ttu-id="8e0ea-162">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-162">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="8e0ea-163">返回页首</span><span class="sxs-lookup"><span data-stu-id="8e0ea-163">Back to top</span></span>](#top)  
  
<a name="ilstubcachehit_event"></a>   
## <a name="ilstubcachehit-event"></a><span data-ttu-id="8e0ea-164">ILStubCacheHit 事件</span><span class="sxs-lookup"><span data-stu-id="8e0ea-164">ILStubCacheHit Event</span></span>  
 <span data-ttu-id="8e0ea-165">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-165">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="8e0ea-166">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="8e0ea-166">Keyword for raising the event</span></span>|<span data-ttu-id="8e0ea-167">Level</span><span class="sxs-lookup"><span data-stu-id="8e0ea-167">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="8e0ea-168">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="8e0ea-168">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="8e0ea-169">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="8e0ea-169">Informational(4)</span></span>|  
  
 <span data-ttu-id="8e0ea-170">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-170">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="8e0ea-171">Event</span><span class="sxs-lookup"><span data-stu-id="8e0ea-171">Event</span></span>|<span data-ttu-id="8e0ea-172">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8e0ea-172">Event ID</span></span>|<span data-ttu-id="8e0ea-173">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="8e0ea-173">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="8e0ea-174">89</span><span class="sxs-lookup"><span data-stu-id="8e0ea-174">89</span></span>|<span data-ttu-id="8e0ea-175">已访问 MSIL 缓存。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-175">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="8e0ea-176">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-176">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="8e0ea-177">字段名</span><span class="sxs-lookup"><span data-stu-id="8e0ea-177">Field name</span></span>|<span data-ttu-id="8e0ea-178">数据类型</span><span class="sxs-lookup"><span data-stu-id="8e0ea-178">Data type</span></span>|<span data-ttu-id="8e0ea-179">描述</span><span class="sxs-lookup"><span data-stu-id="8e0ea-179">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="8e0ea-180">ModuleID</span><span class="sxs-lookup"><span data-stu-id="8e0ea-180">ModuleID</span></span>|<span data-ttu-id="8e0ea-181">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="8e0ea-181">win:UInt16</span></span>|<span data-ttu-id="8e0ea-182">模块标识符。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-182">The module identifier.</span></span>|  
|<span data-ttu-id="8e0ea-183">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="8e0ea-183">StubMethodID</span></span>|<span data-ttu-id="8e0ea-184">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8e0ea-184">win:UInt64</span></span>|<span data-ttu-id="8e0ea-185">存根方法标识符。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-185">The stub method identifier.</span></span>|  
|<span data-ttu-id="8e0ea-186">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="8e0ea-186">ManagedInteropMethodToken</span></span>|<span data-ttu-id="8e0ea-187">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="8e0ea-187">win:UInt32</span></span>|<span data-ttu-id="8e0ea-188">托管互操作方法的标记。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-188">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="8e0ea-189">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="8e0ea-189">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="8e0ea-190">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="8e0ea-190">win:UnicodeString</span></span>|<span data-ttu-id="8e0ea-191">托管互操作方法的命名空间。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-191">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="8e0ea-192">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="8e0ea-192">ManagedInteropMethodName</span></span>|<span data-ttu-id="8e0ea-193">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="8e0ea-193">win:UnicodeString</span></span>|<span data-ttu-id="8e0ea-194">托管互操作方法的名称。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-194">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="8e0ea-195">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="8e0ea-195">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="8e0ea-196">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="8e0ea-196">win:UnicodeString</span></span>|<span data-ttu-id="8e0ea-197">托管互操作方法的签名。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-197">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="8e0ea-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="8e0ea-198">ClrInstanceID</span></span>|<span data-ttu-id="8e0ea-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="8e0ea-199">win:UInt16</span></span>|<span data-ttu-id="8e0ea-200">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="8e0ea-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="8e0ea-201">返回页首</span><span class="sxs-lookup"><span data-stu-id="8e0ea-201">Back to top</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="8e0ea-202">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e0ea-202">See also</span></span>

- [<span data-ttu-id="8e0ea-203">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="8e0ea-203">CLR ETW Events</span></span>](clr-etw-events.md)
