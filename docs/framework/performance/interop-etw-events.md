---
title: 互操作 ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
ms.openlocfilehash: 80fd1f7487dbe3925b875e728eaeddac86927ad4
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716021"
---
# <a name="interop-etw-events"></a><span data-ttu-id="114c9-102">互操作 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="114c9-102">Interop ETW Events</span></span>
<span data-ttu-id="114c9-103">互操作事件捕获有关 Microsoft 中间语言 (MSIL) 存根生成和缓存的信息。</span><span class="sxs-lookup"><span data-stu-id="114c9-103">Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  

## <a name="ilstubgenerated-event"></a><span data-ttu-id="114c9-104">ILStubGenerated 事件</span><span class="sxs-lookup"><span data-stu-id="114c9-104">ILStubGenerated Event</span></span>

<span data-ttu-id="114c9-105">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="114c9-105">The following table shows the keyword and level.</span></span> <span data-ttu-id="114c9-106">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="114c9-106">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="114c9-107">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="114c9-107">Keyword for raising the event</span></span>|<span data-ttu-id="114c9-108">Level</span><span class="sxs-lookup"><span data-stu-id="114c9-108">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="114c9-109">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="114c9-109">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="114c9-110">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="114c9-110">Informational(4)</span></span>|  
  
 <span data-ttu-id="114c9-111">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="114c9-111">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="114c9-112">Event</span><span class="sxs-lookup"><span data-stu-id="114c9-112">Event</span></span>|<span data-ttu-id="114c9-113">事件 ID</span><span class="sxs-lookup"><span data-stu-id="114c9-113">Event ID</span></span>|<span data-ttu-id="114c9-114">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="114c9-114">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="114c9-115">88</span><span class="sxs-lookup"><span data-stu-id="114c9-115">88</span></span>|<span data-ttu-id="114c9-116">已生成 MSIL 存根。</span><span class="sxs-lookup"><span data-stu-id="114c9-116">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="114c9-117">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="114c9-117">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="114c9-118">字段名</span><span class="sxs-lookup"><span data-stu-id="114c9-118">Field name</span></span>|<span data-ttu-id="114c9-119">数据类型</span><span class="sxs-lookup"><span data-stu-id="114c9-119">Data type</span></span>|<span data-ttu-id="114c9-120">描述</span><span class="sxs-lookup"><span data-stu-id="114c9-120">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="114c9-121">ModuleID</span><span class="sxs-lookup"><span data-stu-id="114c9-121">ModuleID</span></span>|<span data-ttu-id="114c9-122">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="114c9-122">win:UInt16</span></span>|<span data-ttu-id="114c9-123">模块标识符。</span><span class="sxs-lookup"><span data-stu-id="114c9-123">The module identifier.</span></span>|  
|<span data-ttu-id="114c9-124">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="114c9-124">StubMethodID</span></span>|<span data-ttu-id="114c9-125">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="114c9-125">win:UInt64</span></span>|<span data-ttu-id="114c9-126">存根方法标识符。</span><span class="sxs-lookup"><span data-stu-id="114c9-126">The stub method identifier.</span></span>|  
|<span data-ttu-id="114c9-127">StubFlags</span><span class="sxs-lookup"><span data-stu-id="114c9-127">StubFlags</span></span>|<span data-ttu-id="114c9-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="114c9-128">win:UInt64</span></span>|<span data-ttu-id="114c9-129">存根标志：</span><span class="sxs-lookup"><span data-stu-id="114c9-129">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="114c9-130">0x1 - 反向互操作。</span><span class="sxs-lookup"><span data-stu-id="114c9-130">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="114c9-131">0x2 - COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="114c9-131">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="114c9-132">0x4 - 由 NGen.exe 生成的存根。</span><span class="sxs-lookup"><span data-stu-id="114c9-132">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="114c9-133">0x8 - 委托。</span><span class="sxs-lookup"><span data-stu-id="114c9-133">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="114c9-134">0x10-可变参数。</span><span class="sxs-lookup"><span data-stu-id="114c9-134">0x10 - Variable argument.</span></span><br /><br /> <span data-ttu-id="114c9-135">0x20 - 非托管被调用方。</span><span class="sxs-lookup"><span data-stu-id="114c9-135">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="114c9-136">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="114c9-136">ManagedInteropMethodToken</span></span>|<span data-ttu-id="114c9-137">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="114c9-137">win:UInt32</span></span>|<span data-ttu-id="114c9-138">托管互操作方法的标记。</span><span class="sxs-lookup"><span data-stu-id="114c9-138">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="114c9-139">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="114c9-139">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="114c9-140">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="114c9-140">win:UnicodeString</span></span>|<span data-ttu-id="114c9-141">托管互操作方法的命名空间。</span><span class="sxs-lookup"><span data-stu-id="114c9-141">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="114c9-142">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="114c9-142">ManagedInteropMethodName</span></span>|<span data-ttu-id="114c9-143">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="114c9-143">win:UnicodeString</span></span>|<span data-ttu-id="114c9-144">托管互操作方法的名称。</span><span class="sxs-lookup"><span data-stu-id="114c9-144">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="114c9-145">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="114c9-145">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="114c9-146">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="114c9-146">win:UnicodeString</span></span>|<span data-ttu-id="114c9-147">托管互操作方法的签名。</span><span class="sxs-lookup"><span data-stu-id="114c9-147">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="114c9-148">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="114c9-148">NativeMethodSignature</span></span>|<span data-ttu-id="114c9-149">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="114c9-149">win:UnicodeString</span></span>|<span data-ttu-id="114c9-150">本机方法签名。</span><span class="sxs-lookup"><span data-stu-id="114c9-150">The native method signature.</span></span>|  
|<span data-ttu-id="114c9-151">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="114c9-151">StubMethodSignature</span></span>|<span data-ttu-id="114c9-152">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="114c9-152">win:UnicodeString</span></span>|<span data-ttu-id="114c9-153">存根方法签名。</span><span class="sxs-lookup"><span data-stu-id="114c9-153">The stub method signature.</span></span>|  
|<span data-ttu-id="114c9-154">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="114c9-154">StubMethodILCode</span></span>|<span data-ttu-id="114c9-155">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="114c9-155">win:UnicodeString</span></span>|<span data-ttu-id="114c9-156">存根方法的 MSIL 代码。</span><span class="sxs-lookup"><span data-stu-id="114c9-156">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="114c9-157">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="114c9-157">ClrInstanceID</span></span>|<span data-ttu-id="114c9-158">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="114c9-158">win:UInt16</span></span>|<span data-ttu-id="114c9-159">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="114c9-159">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="ilstubcachehit-event"></a><span data-ttu-id="114c9-160">ILStubCacheHit 事件</span><span class="sxs-lookup"><span data-stu-id="114c9-160">ILStubCacheHit Event</span></span>  

<span data-ttu-id="114c9-161">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="114c9-161">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="114c9-162">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="114c9-162">Keyword for raising the event</span></span>|<span data-ttu-id="114c9-163">Level</span><span class="sxs-lookup"><span data-stu-id="114c9-163">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="114c9-164">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="114c9-164">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="114c9-165">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="114c9-165">Informational(4)</span></span>|  
  
 <span data-ttu-id="114c9-166">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="114c9-166">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="114c9-167">Event</span><span class="sxs-lookup"><span data-stu-id="114c9-167">Event</span></span>|<span data-ttu-id="114c9-168">事件 ID</span><span class="sxs-lookup"><span data-stu-id="114c9-168">Event ID</span></span>|<span data-ttu-id="114c9-169">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="114c9-169">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="114c9-170">89</span><span class="sxs-lookup"><span data-stu-id="114c9-170">89</span></span>|<span data-ttu-id="114c9-171">已访问 MSIL 缓存。</span><span class="sxs-lookup"><span data-stu-id="114c9-171">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="114c9-172">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="114c9-172">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="114c9-173">字段名</span><span class="sxs-lookup"><span data-stu-id="114c9-173">Field name</span></span>|<span data-ttu-id="114c9-174">数据类型</span><span class="sxs-lookup"><span data-stu-id="114c9-174">Data type</span></span>|<span data-ttu-id="114c9-175">描述</span><span class="sxs-lookup"><span data-stu-id="114c9-175">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="114c9-176">ModuleID</span><span class="sxs-lookup"><span data-stu-id="114c9-176">ModuleID</span></span>|<span data-ttu-id="114c9-177">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="114c9-177">win:UInt16</span></span>|<span data-ttu-id="114c9-178">模块标识符。</span><span class="sxs-lookup"><span data-stu-id="114c9-178">The module identifier.</span></span>|  
|<span data-ttu-id="114c9-179">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="114c9-179">StubMethodID</span></span>|<span data-ttu-id="114c9-180">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="114c9-180">win:UInt64</span></span>|<span data-ttu-id="114c9-181">存根方法标识符。</span><span class="sxs-lookup"><span data-stu-id="114c9-181">The stub method identifier.</span></span>|  
|<span data-ttu-id="114c9-182">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="114c9-182">ManagedInteropMethodToken</span></span>|<span data-ttu-id="114c9-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="114c9-183">win:UInt32</span></span>|<span data-ttu-id="114c9-184">托管互操作方法的标记。</span><span class="sxs-lookup"><span data-stu-id="114c9-184">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="114c9-185">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="114c9-185">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="114c9-186">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="114c9-186">win:UnicodeString</span></span>|<span data-ttu-id="114c9-187">托管互操作方法的命名空间。</span><span class="sxs-lookup"><span data-stu-id="114c9-187">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="114c9-188">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="114c9-188">ManagedInteropMethodName</span></span>|<span data-ttu-id="114c9-189">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="114c9-189">win:UnicodeString</span></span>|<span data-ttu-id="114c9-190">托管互操作方法的名称。</span><span class="sxs-lookup"><span data-stu-id="114c9-190">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="114c9-191">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="114c9-191">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="114c9-192">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="114c9-192">win:UnicodeString</span></span>|<span data-ttu-id="114c9-193">托管互操作方法的签名。</span><span class="sxs-lookup"><span data-stu-id="114c9-193">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="114c9-194">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="114c9-194">ClrInstanceID</span></span>|<span data-ttu-id="114c9-195">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="114c9-195">win:UInt16</span></span>|<span data-ttu-id="114c9-196">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="114c9-196">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="114c9-197">另请参阅</span><span class="sxs-lookup"><span data-stu-id="114c9-197">See also</span></span>

- [<span data-ttu-id="114c9-198">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="114c9-198">CLR ETW Events</span></span>](clr-etw-events.md)
