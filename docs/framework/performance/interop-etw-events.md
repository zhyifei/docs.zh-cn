---
title: 互操作 ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5db68cdce0db4f8f4d85e9d1dd03720bf235d865
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974931"
---
# <a name="interop-etw-events"></a><span data-ttu-id="f4c52-102">互操作 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="f4c52-102">Interop ETW Events</span></span>
<span data-ttu-id="f4c52-103">互操作事件捕获有关 Microsoft 中间语言 (MSIL) 存根生成和缓存的信息。</span><span class="sxs-lookup"><span data-stu-id="f4c52-103">Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  

## <a name="ilstubgenerated-event"></a><span data-ttu-id="f4c52-104">ILStubGenerated 事件</span><span class="sxs-lookup"><span data-stu-id="f4c52-104">ILStubGenerated Event</span></span>

<span data-ttu-id="f4c52-105">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="f4c52-105">The following table shows the keyword and level.</span></span> <span data-ttu-id="f4c52-106">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="f4c52-106">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="f4c52-107">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="f4c52-107">Keyword for raising the event</span></span>|<span data-ttu-id="f4c52-108">层次</span><span class="sxs-lookup"><span data-stu-id="f4c52-108">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f4c52-109">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="f4c52-109">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="f4c52-110">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="f4c52-110">Informational(4)</span></span>|  
  
 <span data-ttu-id="f4c52-111">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="f4c52-111">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f4c52-112">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="f4c52-112">Event</span></span>|<span data-ttu-id="f4c52-113">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f4c52-113">Event ID</span></span>|<span data-ttu-id="f4c52-114">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="f4c52-114">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="f4c52-115">88</span><span class="sxs-lookup"><span data-stu-id="f4c52-115">88</span></span>|<span data-ttu-id="f4c52-116">已生成 MSIL 存根。</span><span class="sxs-lookup"><span data-stu-id="f4c52-116">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="f4c52-117">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="f4c52-117">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f4c52-118">字段名</span><span class="sxs-lookup"><span data-stu-id="f4c52-118">Field name</span></span>|<span data-ttu-id="f4c52-119">数据类型</span><span class="sxs-lookup"><span data-stu-id="f4c52-119">Data type</span></span>|<span data-ttu-id="f4c52-120">描述</span><span class="sxs-lookup"><span data-stu-id="f4c52-120">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f4c52-121">ModuleID</span><span class="sxs-lookup"><span data-stu-id="f4c52-121">ModuleID</span></span>|<span data-ttu-id="f4c52-122">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f4c52-122">win:UInt16</span></span>|<span data-ttu-id="f4c52-123">模块标识符。</span><span class="sxs-lookup"><span data-stu-id="f4c52-123">The module identifier.</span></span>|  
|<span data-ttu-id="f4c52-124">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="f4c52-124">StubMethodID</span></span>|<span data-ttu-id="f4c52-125">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f4c52-125">win:UInt64</span></span>|<span data-ttu-id="f4c52-126">存根方法标识符。</span><span class="sxs-lookup"><span data-stu-id="f4c52-126">The stub method identifier.</span></span>|  
|<span data-ttu-id="f4c52-127">StubFlags</span><span class="sxs-lookup"><span data-stu-id="f4c52-127">StubFlags</span></span>|<span data-ttu-id="f4c52-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f4c52-128">win:UInt64</span></span>|<span data-ttu-id="f4c52-129">存根标志：</span><span class="sxs-lookup"><span data-stu-id="f4c52-129">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="f4c52-130">0x1 - 反向互操作。</span><span class="sxs-lookup"><span data-stu-id="f4c52-130">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="f4c52-131">0x2 - COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="f4c52-131">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="f4c52-132">0x4 - 由 NGen.exe 生成的存根。</span><span class="sxs-lookup"><span data-stu-id="f4c52-132">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="f4c52-133">0x8 - 委托。</span><span class="sxs-lookup"><span data-stu-id="f4c52-133">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="f4c52-134">0x10-可变参数。</span><span class="sxs-lookup"><span data-stu-id="f4c52-134">0x10 - Variable argument.</span></span><br /><br /> <span data-ttu-id="f4c52-135">0x20 - 非托管被调用方。</span><span class="sxs-lookup"><span data-stu-id="f4c52-135">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="f4c52-136">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="f4c52-136">ManagedInteropMethodToken</span></span>|<span data-ttu-id="f4c52-137">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f4c52-137">win:UInt32</span></span>|<span data-ttu-id="f4c52-138">托管互操作方法的标记。</span><span class="sxs-lookup"><span data-stu-id="f4c52-138">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="f4c52-139">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="f4c52-139">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="f4c52-140">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f4c52-140">win:UnicodeString</span></span>|<span data-ttu-id="f4c52-141">托管互操作方法的命名空间。</span><span class="sxs-lookup"><span data-stu-id="f4c52-141">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="f4c52-142">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="f4c52-142">ManagedInteropMethodName</span></span>|<span data-ttu-id="f4c52-143">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f4c52-143">win:UnicodeString</span></span>|<span data-ttu-id="f4c52-144">托管互操作方法的名称。</span><span class="sxs-lookup"><span data-stu-id="f4c52-144">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="f4c52-145">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="f4c52-145">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="f4c52-146">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f4c52-146">win:UnicodeString</span></span>|<span data-ttu-id="f4c52-147">托管互操作方法的签名。</span><span class="sxs-lookup"><span data-stu-id="f4c52-147">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="f4c52-148">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="f4c52-148">NativeMethodSignature</span></span>|<span data-ttu-id="f4c52-149">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f4c52-149">win:UnicodeString</span></span>|<span data-ttu-id="f4c52-150">本机方法签名。</span><span class="sxs-lookup"><span data-stu-id="f4c52-150">The native method signature.</span></span>|  
|<span data-ttu-id="f4c52-151">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="f4c52-151">StubMethodSignature</span></span>|<span data-ttu-id="f4c52-152">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f4c52-152">win:UnicodeString</span></span>|<span data-ttu-id="f4c52-153">存根方法签名。</span><span class="sxs-lookup"><span data-stu-id="f4c52-153">The stub method signature.</span></span>|  
|<span data-ttu-id="f4c52-154">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="f4c52-154">StubMethodILCode</span></span>|<span data-ttu-id="f4c52-155">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f4c52-155">win:UnicodeString</span></span>|<span data-ttu-id="f4c52-156">存根方法的 MSIL 代码。</span><span class="sxs-lookup"><span data-stu-id="f4c52-156">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="f4c52-157">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f4c52-157">ClrInstanceID</span></span>|<span data-ttu-id="f4c52-158">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f4c52-158">win:UInt16</span></span>|<span data-ttu-id="f4c52-159">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="f4c52-159">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="ilstubcachehit-event"></a><span data-ttu-id="f4c52-160">ILStubCacheHit 事件</span><span class="sxs-lookup"><span data-stu-id="f4c52-160">ILStubCacheHit Event</span></span>  

<span data-ttu-id="f4c52-161">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="f4c52-161">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="f4c52-162">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="f4c52-162">Keyword for raising the event</span></span>|<span data-ttu-id="f4c52-163">层次</span><span class="sxs-lookup"><span data-stu-id="f4c52-163">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f4c52-164">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="f4c52-164">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="f4c52-165">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="f4c52-165">Informational(4)</span></span>|  
  
 <span data-ttu-id="f4c52-166">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="f4c52-166">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f4c52-167">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="f4c52-167">Event</span></span>|<span data-ttu-id="f4c52-168">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f4c52-168">Event ID</span></span>|<span data-ttu-id="f4c52-169">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="f4c52-169">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="f4c52-170">89</span><span class="sxs-lookup"><span data-stu-id="f4c52-170">89</span></span>|<span data-ttu-id="f4c52-171">已访问 MSIL 缓存。</span><span class="sxs-lookup"><span data-stu-id="f4c52-171">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="f4c52-172">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="f4c52-172">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f4c52-173">字段名</span><span class="sxs-lookup"><span data-stu-id="f4c52-173">Field name</span></span>|<span data-ttu-id="f4c52-174">数据类型</span><span class="sxs-lookup"><span data-stu-id="f4c52-174">Data type</span></span>|<span data-ttu-id="f4c52-175">描述</span><span class="sxs-lookup"><span data-stu-id="f4c52-175">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f4c52-176">ModuleID</span><span class="sxs-lookup"><span data-stu-id="f4c52-176">ModuleID</span></span>|<span data-ttu-id="f4c52-177">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f4c52-177">win:UInt16</span></span>|<span data-ttu-id="f4c52-178">模块标识符。</span><span class="sxs-lookup"><span data-stu-id="f4c52-178">The module identifier.</span></span>|  
|<span data-ttu-id="f4c52-179">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="f4c52-179">StubMethodID</span></span>|<span data-ttu-id="f4c52-180">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f4c52-180">win:UInt64</span></span>|<span data-ttu-id="f4c52-181">存根方法标识符。</span><span class="sxs-lookup"><span data-stu-id="f4c52-181">The stub method identifier.</span></span>|  
|<span data-ttu-id="f4c52-182">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="f4c52-182">ManagedInteropMethodToken</span></span>|<span data-ttu-id="f4c52-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f4c52-183">win:UInt32</span></span>|<span data-ttu-id="f4c52-184">托管互操作方法的标记。</span><span class="sxs-lookup"><span data-stu-id="f4c52-184">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="f4c52-185">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="f4c52-185">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="f4c52-186">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f4c52-186">win:UnicodeString</span></span>|<span data-ttu-id="f4c52-187">托管互操作方法的命名空间。</span><span class="sxs-lookup"><span data-stu-id="f4c52-187">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="f4c52-188">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="f4c52-188">ManagedInteropMethodName</span></span>|<span data-ttu-id="f4c52-189">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f4c52-189">win:UnicodeString</span></span>|<span data-ttu-id="f4c52-190">托管互操作方法的名称。</span><span class="sxs-lookup"><span data-stu-id="f4c52-190">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="f4c52-191">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="f4c52-191">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="f4c52-192">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f4c52-192">win:UnicodeString</span></span>|<span data-ttu-id="f4c52-193">托管互操作方法的签名。</span><span class="sxs-lookup"><span data-stu-id="f4c52-193">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="f4c52-194">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f4c52-194">ClrInstanceID</span></span>|<span data-ttu-id="f4c52-195">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f4c52-195">win:UInt16</span></span>|<span data-ttu-id="f4c52-196">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="f4c52-196">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f4c52-197">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4c52-197">See also</span></span>

- [<span data-ttu-id="f4c52-198">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="f4c52-198">CLR ETW Events</span></span>](clr-etw-events.md)
