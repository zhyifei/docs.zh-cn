---
title: CorDebugInterfaceVersion 枚举
ms.date: 03/30/2017
api_name:
- CorDebugInterfaceVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInterfaceVersion
helpviewer_keywords:
- CorDebugInterfaceVersion enumeration [.NET Framework debugging]
ms.assetid: 7d1e6cd9-2a15-41c6-9b68-008705a4ed90
topic_type:
- apiref
ms.openlocfilehash: ae65c60440a90959006cd8db94dda479e80613d4
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795802"
---
# <a name="cordebuginterfaceversion-enumeration"></a><span data-ttu-id="c4e00-102">CorDebugInterfaceVersion 枚举</span><span class="sxs-lookup"><span data-stu-id="c4e00-102">CorDebugInterfaceVersion Enumeration</span></span>
<span data-ttu-id="c4e00-103">指定接口，.NET Framework 的版本，或在其中引入了接口的 .NET Framework 的版本。</span><span class="sxs-lookup"><span data-stu-id="c4e00-103">Specifies an interface, a version of the .NET Framework, or a version of the .NET Framework in which an interface was introduced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4e00-104">语法</span><span class="sxs-lookup"><span data-stu-id="c4e00-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugInterfaceVersion {  
  
    CorDebugInvalidVersion            = 0,  
    CorDebugVersion_1_0               = CorDebugInvalidVersion + 1,  
  
    ver_ICorDebugManagedCallback      = CorDebugVersion_1_0,  
    ver_ICorDebugUnmanagedCallback    = CorDebugVersion_1_0,  
    ver_ICorDebug                     = CorDebugVersion_1_0,  
    ver_ICorDebugController           = CorDebugVersion_1_0,  
    ver_ICorDebugAppDomain            = CorDebugVersion_1_0,  
    ver_ICorDebugAssembly             = CorDebugVersion_1_0,  
    ver_ICorDebugProcess              = CorDebugVersion_1_0,  
    ver_ICorDebugBreakpoint           = CorDebugVersion_1_0,  
    ver_ICorDebugFunctionBreakpoint   = CorDebugVersion_1_0,  
    ver_ICorDebugModuleBreakpoint     = CorDebugVersion_1_0,  
    ver_ICorDebugValueBreakpoint      = CorDebugVersion_1_0,  
    ver_ICorDebugStepper              = CorDebugVersion_1_0,  
    ver_ICorDebugRegisterSet          = CorDebugVersion_1_0,  
    ver_ICorDebugThread               = CorDebugVersion_1_0,  
    ver_ICorDebugChain                = CorDebugVersion_1_0,  
    ver_ICorDebugFrame                = CorDebugVersion_1_0,  
    ver_ICorDebugILFrame              = CorDebugVersion_1_0,  
    ver_ICorDebugNativeFrame          = CorDebugVersion_1_0,  
    ver_ICorDebugModule               = CorDebugVersion_1_0,  
    ver_ICorDebugFunction             = CorDebugVersion_1_0,  
    ver_ICorDebugCode                 = CorDebugVersion_1_0,  
    ver_ICorDebugClass                = CorDebugVersion_1_0,  
    ver_ICorDebugEval                 = CorDebugVersion_1_0,  
    ver_ICorDebugValue                = CorDebugVersion_1_0,  
    ver_ICorDebugGenericValue         = CorDebugVersion_1_0,  
    ver_ICorDebugReferenceValue       = CorDebugVersion_1_0,  
    ver_ICorDebugHeapValue            = CorDebugVersion_1_0,  
    ver_ICorDebugObjectValue          = CorDebugVersion_1_0,  
    ver_ICorDebugBoxValue             = CorDebugVersion_1_0,  
    ver_ICorDebugStringValue          = CorDebugVersion_1_0,  
    ver_ICorDebugArrayValue           = CorDebugVersion_1_0,  
    ver_ICorDebugContext              = CorDebugVersion_1_0,  
    ver_ICorDebugEnum                 = CorDebugVersion_1_0,  
    ver_ICorDebugObjectEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugBreakpointEnum       = CorDebugVersion_1_0,  
    ver_ICorDebugStepperEnum          = CorDebugVersion_1_0,  
    ver_ICorDebugProcessEnum          = CorDebugVersion_1_0,  
    ver_ICorDebugThreadEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugFrameEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugChainEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugModuleEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugValueEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugCodeEnum             = CorDebugVersion_1_0,  
    ver_ICorDebugTypeEnum             = CorDebugVersion_1_0,  
    ver_ICorDebugErrorInfoEnum        = CorDebugVersion_1_0,  
    ver_ICorDebugAppDomainEnum        = CorDebugVersion_1_0,  
    ver_ICorDebugAssemblyEnum         = CorDebugVersion_1_0,  
    ver_ICorDebugEditAndContinueErrorInfo
                                      = CorDebugVersion_1_0,  
    ver_ICorDebugEditAndContinueSnapshot
                                      = CorDebugVersion_1_0,  
  
    CorDebugVersion_1_1               = CorDebugVersion_1_0 + 1,  
    // No interface definitions in version 1.1.  
  
    CorDebugVersion_2_0 = CorDebugVersion_1_1 + 1,  
  
    ver_ICorDebugManagedCallback2    = CorDebugVersion_2_0,  
    ver_ICorDebugAppDomain2          = CorDebugVersion_2_0,  
    ver_ICorDebugProcess2            = CorDebugVersion_2_0,  
    ver_ICorDebugStepper2            = CorDebugVersion_2_0,  
    ver_ICorDebugRegisterSet2        = CorDebugVersion_2_0,  
    ver_ICorDebugThread2             = CorDebugVersion_2_0,  
    ver_ICorDebugILFrame2            = CorDebugVersion_2_0,  
    ver_ICorDebugModule2             = CorDebugVersion_2_0,  
    ver_ICorDebugFunction2           = CorDebugVersion_2_0,  
    ver_ICorDebugCode2               = CorDebugVersion_2_0,  
    ver_ICorDebugClass2              = CorDebugVersion_2_0,  
    ver_ICorDebugValue2              = CorDebugVersion_2_0,  
    ver_ICorDebugEval2               = CorDebugVersion_2_0,  
    ver_ICorDebugObjectValue2        = CorDebugVersion_2_0,  
  
    // CLR v4 - next major CLR version after CLR v2  
    // Includes Silverlight 4  
    CorDebugVersion_4_0 = CorDebugVersion_2_0 + 1,  
  
    ver_ICorDebugThread3             = CorDebugVersion_4_0,  
    ver_ICorDebugThread4             = CorDebugVersion_4_0,  
    ver_ICorDebugStackWalk           = CorDebugVersion_4_0,  
    ver_ICorDebugNativeFrame2        = CorDebugVersion_4_0,  
    ver_ICorDebugInternalFrame2      = CorDebugVersion_4_0,  
    ver_ICorDebugRuntimeUnwindableFrame = CorDebugVersion_4_0,  
    ver_ICorDebugHeapValue3          = CorDebugVersion_4_0,  
    ver_ICorDebugBlockingObjectEnum  = CorDebugVersion_4_0,  
    ver_ICorDebugValue3 = CorDebugVersion_4_0,  
  
    CorDebugVersion_4_5 = CorDebugVersion_4_0 + 1,  
  
    ver_ICorDebugComObjectValue = CorDebugVersion_4_5,  
    ver_ICorDebugAppDomain3 = CorDebugVersion_4_5,  
    ver_ICorDebugCode3 = CorDebugVersion_4_5,  
    ver_ICorDebugILFrame3 = CorDebugVersion_4_5,  
  
    CorDebugLatestVersion = CorDebugVersion_4_5  
  
} CorDebugInterfaceVersion;  
```  
  
## <a name="members"></a><span data-ttu-id="c4e00-105">成员</span><span class="sxs-lookup"><span data-stu-id="c4e00-105">Members</span></span>  
 <span data-ttu-id="c4e00-106">下表提供了从每个枚举值到相应的接口的链接。</span><span class="sxs-lookup"><span data-stu-id="c4e00-106">The following table provides links from each enumeration value to the corresponding interface.</span></span> <span data-ttu-id="c4e00-107">此外，该表还指示了支持该接口的第一版 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="c4e00-107">In addition, the table indicates the first version of the .NET Framework that the interface was supported in.</span></span>  
  
|<span data-ttu-id="c4e00-108">成员</span><span class="sxs-lookup"><span data-stu-id="c4e00-108">Member</span></span>|<span data-ttu-id="c4e00-109">指定</span><span class="sxs-lookup"><span data-stu-id="c4e00-109">Specifies</span></span>|<span data-ttu-id="c4e00-110">.NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="c4e00-110">.NET Framework version</span></span>|  
|------------|---------------|----------------------------|  
|`CorDebugInvalidVersion`|<span data-ttu-id="c4e00-111">.NET Framework 的版本无效。</span><span class="sxs-lookup"><span data-stu-id="c4e00-111">The version of the .NET Framework is invalid.</span></span>|-|  
|`CorDebugVersion_1_0`|<span data-ttu-id="c4e00-112">.NET Framework（包括其所有 Service Pack）的版本为 1.0。</span><span class="sxs-lookup"><span data-stu-id="c4e00-112">The version of the .NET Framework, including all its service packs, is 1.0.</span></span>|<span data-ttu-id="c4e00-113">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-113">1.0</span></span>|  
|`CorDebugVersion_1_1`|<span data-ttu-id="c4e00-114">.NET Framework（包括所有 Service Pack）的版本为 1.1。</span><span class="sxs-lookup"><span data-stu-id="c4e00-114">The version of the .NET Framework, including all service packs, is 1.1.</span></span>|<span data-ttu-id="c4e00-115">1.1</span><span class="sxs-lookup"><span data-stu-id="c4e00-115">1.1</span></span>|  
|`CorDebugVersion_2_0`|<span data-ttu-id="c4e00-116">.NET Framework（包括所有 Service Pack）的版本为 2.0。</span><span class="sxs-lookup"><span data-stu-id="c4e00-116">The version of the .NET Framework, including all service packs, is 2.0.</span></span>|<span data-ttu-id="c4e00-117">2.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-117">2.0</span></span>|  
|`CorDebugVersion_4_0`|<span data-ttu-id="c4e00-118">.NET Framework（包括所有 Service Pack）的版本为 4。</span><span class="sxs-lookup"><span data-stu-id="c4e00-118">The version of the .NET Framework, including all service packs, is 4.</span></span>|<span data-ttu-id="c4e00-119">4</span><span class="sxs-lookup"><span data-stu-id="c4e00-119">4</span></span>|  
|`CorDebugVersion_4_5`|<span data-ttu-id="c4e00-120">.NET Framework（包括所有 Service Pack）的版本为 4.5。</span><span class="sxs-lookup"><span data-stu-id="c4e00-120">The version of the .NET Framework, including all service packs, is 4.5.</span></span>|<span data-ttu-id="c4e00-121">4.5</span><span class="sxs-lookup"><span data-stu-id="c4e00-121">4.5</span></span>|  
|`ver_ICorDebugManagedCallback`|[<span data-ttu-id="c4e00-122">ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="c4e00-122">ICorDebugManagedCallback</span></span>](icordebugmanagedcallback-interface.md)|<span data-ttu-id="c4e00-123">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-123">1.0</span></span>|  
|`ver_ICorDebugUnmanagedCallback`|[<span data-ttu-id="c4e00-124">ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="c4e00-124">ICorDebugUnmanagedCallback</span></span>](icordebugunmanagedcallback-interface.md)|<span data-ttu-id="c4e00-125">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-125">1.0</span></span>|  
|`ver_ICorDebug`|[<span data-ttu-id="c4e00-126">ICorDebug</span><span class="sxs-lookup"><span data-stu-id="c4e00-126">ICorDebug</span></span>](icordebug-interface.md)|<span data-ttu-id="c4e00-127">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-127">1.0</span></span>|  
|`ver_ICorDebugController`|[<span data-ttu-id="c4e00-128">ICorDebugController</span><span class="sxs-lookup"><span data-stu-id="c4e00-128">ICorDebugController</span></span>](icordebugcontroller-interface.md)|<span data-ttu-id="c4e00-129">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-129">1.0</span></span>|  
|`ver_ICorDebugAppDomain`|[<span data-ttu-id="c4e00-130">ICorDebugAppDomain</span><span class="sxs-lookup"><span data-stu-id="c4e00-130">ICorDebugAppDomain</span></span>](icordebugappdomain-interface.md)|<span data-ttu-id="c4e00-131">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-131">1.0</span></span>|  
|`ver_ICorDebugAssembly`|[<span data-ttu-id="c4e00-132">ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="c4e00-132">ICorDebugAssembly</span></span>](icordebugassembly-interface.md)|<span data-ttu-id="c4e00-133">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-133">1.0</span></span>|  
|`ver_ICorDebugProcess`|[<span data-ttu-id="c4e00-134">ICorDebugProcess</span><span class="sxs-lookup"><span data-stu-id="c4e00-134">ICorDebugProcess</span></span>](icordebugprocess-interface.md)|<span data-ttu-id="c4e00-135">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-135">1.0</span></span>|  
|`ver_ICorDebugBreakpoint`|[<span data-ttu-id="c4e00-136">ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="c4e00-136">ICorDebugBreakpoint</span></span>](icordebugbreakpoint-interface.md)|<span data-ttu-id="c4e00-137">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-137">1.0</span></span>|  
|`ver_ICorDebugFunctionBreakpoint`|[<span data-ttu-id="c4e00-138">ICorDebugFunctionBreakpoint</span><span class="sxs-lookup"><span data-stu-id="c4e00-138">ICorDebugFunctionBreakpoint</span></span>](icordebugfunctionbreakpoint-interface.md)|<span data-ttu-id="c4e00-139">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-139">1.0</span></span>|  
|`ver_ICorDebugModuleBreakpoint`|[<span data-ttu-id="c4e00-140">ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="c4e00-140">ICorDebugModuleBreakpoint</span></span>](icordebugmodulebreakpoint-interface.md)|<span data-ttu-id="c4e00-141">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-141">1.0</span></span>|  
|`ver_ICorDebugValueBreakpoint`|[<span data-ttu-id="c4e00-142">ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="c4e00-142">ICorDebugValueBreakpoint</span></span>](icordebugvaluebreakpoint-interface.md)|<span data-ttu-id="c4e00-143">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-143">1.0</span></span>|  
|`ver_ICorDebugStepper`|[<span data-ttu-id="c4e00-144">ICorDebugStepper</span><span class="sxs-lookup"><span data-stu-id="c4e00-144">ICorDebugStepper</span></span>](icordebugstepper-interface.md)|<span data-ttu-id="c4e00-145">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-145">1.0</span></span>|  
|`ver_ICorDebugRegisterSet`|[<span data-ttu-id="c4e00-146">ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="c4e00-146">ICorDebugRegisterSet</span></span>](icordebugregisterset-interface.md)|<span data-ttu-id="c4e00-147">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-147">1.0</span></span>|  
|`ver_ICorDebugThread`|[<span data-ttu-id="c4e00-148">ICorDebugThread</span><span class="sxs-lookup"><span data-stu-id="c4e00-148">ICorDebugThread</span></span>](icordebugthread-interface.md)|<span data-ttu-id="c4e00-149">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-149">1.0</span></span>|  
|`ver_ICorDebugChain`|[<span data-ttu-id="c4e00-150">ICorDebugChain</span><span class="sxs-lookup"><span data-stu-id="c4e00-150">ICorDebugChain</span></span>](icordebugchain-interface.md)|<span data-ttu-id="c4e00-151">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-151">1.0</span></span>|  
|`ver_ICorDebugFrame`|[<span data-ttu-id="c4e00-152">ICorDebugFrame</span><span class="sxs-lookup"><span data-stu-id="c4e00-152">ICorDebugFrame</span></span>](icordebugframe-interface.md)|<span data-ttu-id="c4e00-153">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-153">1.0</span></span>|  
|`ver_ICorDebugILFrame`|[<span data-ttu-id="c4e00-154">ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="c4e00-154">ICorDebugILFrame</span></span>](icordebugilframe-interface.md)|<span data-ttu-id="c4e00-155">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-155">1.0</span></span>|  
|`ver_ICorDebugNativeFrame`|[<span data-ttu-id="c4e00-156">ICorDebugNativeFrame</span><span class="sxs-lookup"><span data-stu-id="c4e00-156">ICorDebugNativeFrame</span></span>](icordebugnativeframe-interface.md)|<span data-ttu-id="c4e00-157">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-157">1.0</span></span>|  
|`ver_ICorDebugModule`|[<span data-ttu-id="c4e00-158">ICorDebugModule</span><span class="sxs-lookup"><span data-stu-id="c4e00-158">ICorDebugModule</span></span>](icordebugmodule-interface.md)|<span data-ttu-id="c4e00-159">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-159">1.0</span></span>|  
|`ver_ICorDebugFunction`|[<span data-ttu-id="c4e00-160">ICorDebugFunction</span><span class="sxs-lookup"><span data-stu-id="c4e00-160">ICorDebugFunction</span></span>](icordebugfunction-interface1.md)|<span data-ttu-id="c4e00-161">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-161">1.0</span></span>|  
|`ver_ICorDebugCode`|[<span data-ttu-id="c4e00-162">ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="c4e00-162">ICorDebugCode</span></span>](icordebugcode-interface1.md)|<span data-ttu-id="c4e00-163">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-163">1.0</span></span>|  
|`ver_ICorDebugClass`|[<span data-ttu-id="c4e00-164">ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="c4e00-164">ICorDebugClass</span></span>](icordebugclass-interface.md)|<span data-ttu-id="c4e00-165">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-165">1.0</span></span>|  
|`ver_ICorDebugEval`|[<span data-ttu-id="c4e00-166">ICorDebugEval</span><span class="sxs-lookup"><span data-stu-id="c4e00-166">ICorDebugEval</span></span>](icordebugeval-interface.md)|<span data-ttu-id="c4e00-167">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-167">1.0</span></span>|  
|`ver_ICorDebugValue`|[<span data-ttu-id="c4e00-168">ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="c4e00-168">ICorDebugValue</span></span>](icordebugvalue-interface.md)|<span data-ttu-id="c4e00-169">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-169">1.0</span></span>|  
|`ver_ICorDebugGenericValue`|[<span data-ttu-id="c4e00-170">ICorDebugGenericValue</span><span class="sxs-lookup"><span data-stu-id="c4e00-170">ICorDebugGenericValue</span></span>](icordebuggenericvalue-interface.md)|<span data-ttu-id="c4e00-171">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-171">1.0</span></span>|  
|`ver_ICorDebugReferenceValue`|[<span data-ttu-id="c4e00-172">ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="c4e00-172">ICorDebugReferenceValue</span></span>](icordebugreferencevalue-interface.md)|<span data-ttu-id="c4e00-173">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-173">1.0</span></span>|  
|`ver_ICorDebugHeapValue`|[<span data-ttu-id="c4e00-174">ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="c4e00-174">ICorDebugHeapValue</span></span>](icordebugheapvalue-interface.md)|<span data-ttu-id="c4e00-175">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-175">1.0</span></span>|  
|`ver_ICorDebugObjectValue`|[<span data-ttu-id="c4e00-176">ICorDebugObjectValue</span><span class="sxs-lookup"><span data-stu-id="c4e00-176">ICorDebugObjectValue</span></span>](icordebugobjectvalue-interface.md)|<span data-ttu-id="c4e00-177">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-177">1.0</span></span>|  
|`ver_ICorDebugBoxValue`|[<span data-ttu-id="c4e00-178">ICorDebugBoxValue</span><span class="sxs-lookup"><span data-stu-id="c4e00-178">ICorDebugBoxValue</span></span>](icordebugboxvalue-interface.md)|<span data-ttu-id="c4e00-179">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-179">1.0</span></span>|  
|`ver_ICorDebugStringValue`|[<span data-ttu-id="c4e00-180">ICorDebugStringValue</span><span class="sxs-lookup"><span data-stu-id="c4e00-180">ICorDebugStringValue</span></span>](icordebugstringvalue-interface.md)|<span data-ttu-id="c4e00-181">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-181">1.0</span></span>|  
|`ver_ICorDebugArrayValue`|[<span data-ttu-id="c4e00-182">ICorDebugArrayValue</span><span class="sxs-lookup"><span data-stu-id="c4e00-182">ICorDebugArrayValue</span></span>](icordebugarrayvalue-interface.md)|<span data-ttu-id="c4e00-183">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-183">1.0</span></span>|  
|`ver_ICorDebugContext`|[<span data-ttu-id="c4e00-184">ICorDebugContext</span><span class="sxs-lookup"><span data-stu-id="c4e00-184">ICorDebugContext</span></span>](icordebugcontext-interface.md)|<span data-ttu-id="c4e00-185">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-185">1.0</span></span>|  
|`ver_ICorDebugEnum`|[<span data-ttu-id="c4e00-186">ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="c4e00-186">ICorDebugEnum</span></span>](icordebugenum-interface1.md)|<span data-ttu-id="c4e00-187">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-187">1.0</span></span>|  
|`ver_ICorDebugObjectEnum`|[<span data-ttu-id="c4e00-188">ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="c4e00-188">ICorDebugObjectEnum</span></span>](icordebugobjectenum-interface.md)|<span data-ttu-id="c4e00-189">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-189">1.0</span></span>|  
|`ver_ICorDebugBreakpointEnum`|[<span data-ttu-id="c4e00-190">ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="c4e00-190">ICorDebugBreakpointEnum</span></span>](icordebugbreakpointenum-interface.md)|<span data-ttu-id="c4e00-191">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-191">1.0</span></span>|  
|`ver_ICorDebugStepperEnum`|[<span data-ttu-id="c4e00-192">ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="c4e00-192">ICorDebugStepperEnum</span></span>](icordebugstepperenum-interface.md)|<span data-ttu-id="c4e00-193">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-193">1.0</span></span>|  
|`ver_ICorDebugProcessEnum`|[<span data-ttu-id="c4e00-194">ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="c4e00-194">ICorDebugProcessEnum</span></span>](icordebugprocessenum-interface.md)|<span data-ttu-id="c4e00-195">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-195">1.0</span></span>|  
|`ver_ICorDebugThreadEnum`|[<span data-ttu-id="c4e00-196">ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="c4e00-196">ICorDebugThreadEnum</span></span>](icordebugthreadenum-interface1.md)|<span data-ttu-id="c4e00-197">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-197">1.0</span></span>|  
|`ver_ICorDebugFrameEnum`|[<span data-ttu-id="c4e00-198">ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="c4e00-198">ICorDebugFrameEnum</span></span>](icordebugframeenum-interface.md)|<span data-ttu-id="c4e00-199">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-199">1.0</span></span>|  
|`ver_ICorDebugChainEnum`|[<span data-ttu-id="c4e00-200">ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="c4e00-200">ICorDebugChainEnum</span></span>](icordebugchainenum-interface.md)|<span data-ttu-id="c4e00-201">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-201">1.0</span></span>|  
|`ver_ICorDebugModuleEnum`|[<span data-ttu-id="c4e00-202">ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="c4e00-202">ICorDebugModuleEnum</span></span>](icordebugmoduleenum-interface.md)|<span data-ttu-id="c4e00-203">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-203">1.0</span></span>|  
|`ver_ICorDebugValueEnum`|[<span data-ttu-id="c4e00-204">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="c4e00-204">ICorDebugValueEnum</span></span>](icordebugvalueenum-interface.md)|<span data-ttu-id="c4e00-205">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-205">1.0</span></span>|  
|`ver_ICorDebugCodeEnum`|[<span data-ttu-id="c4e00-206">ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="c4e00-206">ICorDebugCodeEnum</span></span>](icordebugcodeenum-interface.md)|<span data-ttu-id="c4e00-207">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-207">1.0</span></span>|  
|`ver_ICorDebugTypeEnum`|[<span data-ttu-id="c4e00-208">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="c4e00-208">ICorDebugTypeEnum</span></span>](icordebugtypeenum-interface.md)|<span data-ttu-id="c4e00-209">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-209">1.0</span></span>|  
|`ver_ICorDebugErrorInfoEnum`|[<span data-ttu-id="c4e00-210">ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="c4e00-210">ICorDebugErrorInfoEnum</span></span>](icordebugerrorinfoenum-interface.md)|<span data-ttu-id="c4e00-211">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-211">1.0</span></span>|  
|`ver_ICorDebugAppDomainEnum`|[<span data-ttu-id="c4e00-212">ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="c4e00-212">ICorDebugAppDomainEnum</span></span>](icordebugappdomainenum-interface.md)|<span data-ttu-id="c4e00-213">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-213">1.0</span></span>|  
|`ver_ICorDebugAssemblyEnum`|[<span data-ttu-id="c4e00-214">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="c4e00-214">ICorDebugAssemblyEnum</span></span>](icordebugassemblyenum-interface.md)|<span data-ttu-id="c4e00-215">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-215">1.0</span></span>|  
|`ver_ICorDebugEditAndContinueErrorInfo`|[<span data-ttu-id="c4e00-216">ICorDebugEditAndContinueErrorInfo</span><span class="sxs-lookup"><span data-stu-id="c4e00-216">ICorDebugEditAndContinueErrorInfo</span></span>](icordebugeditandcontinueerrorinfo-interface.md)|<span data-ttu-id="c4e00-217">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-217">1.0</span></span>|  
|`ver_ICorDebugEditAndContinueSnapshot`|[<span data-ttu-id="c4e00-218">ICorDebugEditAndContinueSnapshot</span><span class="sxs-lookup"><span data-stu-id="c4e00-218">ICorDebugEditAndContinueSnapshot</span></span>](icordebugeditandcontinuesnapshot-interface.md)|<span data-ttu-id="c4e00-219">1.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-219">1.0</span></span>|  
|`ver_ICorDebugManagedCallback2`|[<span data-ttu-id="c4e00-220">ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="c4e00-220">ICorDebugManagedCallback2</span></span>](icordebugmanagedcallback2-interface.md)|<span data-ttu-id="c4e00-221">2.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-221">2.0</span></span>|  
|`ver_ICorDebugAppDomain2`|[<span data-ttu-id="c4e00-222">ICorDebugAppDomain2</span><span class="sxs-lookup"><span data-stu-id="c4e00-222">ICorDebugAppDomain2</span></span>](icordebugappdomain2-interface.md)|<span data-ttu-id="c4e00-223">2.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-223">2.0</span></span>|  
|`ver_ICorDebugProcess2`|[<span data-ttu-id="c4e00-224">ICorDebugProcess2</span><span class="sxs-lookup"><span data-stu-id="c4e00-224">ICorDebugProcess2</span></span>](icordebugprocess2-interface1.md)|<span data-ttu-id="c4e00-225">2.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-225">2.0</span></span>|  
|`ver_ICorDebugStepper2`|[<span data-ttu-id="c4e00-226">ICorDebugStepper2</span><span class="sxs-lookup"><span data-stu-id="c4e00-226">ICorDebugStepper2</span></span>](icordebugstepper2-interface1.md)|<span data-ttu-id="c4e00-227">2.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-227">2.0</span></span>|  
|`ver_ICorDebugRegisterSet2`|[<span data-ttu-id="c4e00-228">ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="c4e00-228">ICorDebugRegisterSet2</span></span>](icordebugregisterset2-interface.md)|<span data-ttu-id="c4e00-229">2.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-229">2.0</span></span>|  
|`ver_ICorDebugThread2`|[<span data-ttu-id="c4e00-230">ICorDebugThread2</span><span class="sxs-lookup"><span data-stu-id="c4e00-230">ICorDebugThread2</span></span>](icordebugthread2-interface.md)|<span data-ttu-id="c4e00-231">2.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-231">2.0</span></span>|  
|`ver_ICorDebugILFrame2`|[<span data-ttu-id="c4e00-232">ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="c4e00-232">ICorDebugILFrame2</span></span>](icordebugilframe2-interface.md)|<span data-ttu-id="c4e00-233">2.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-233">2.0</span></span>|  
|`ver_ICorDebugModule2`|[<span data-ttu-id="c4e00-234">ICorDebugModule2</span><span class="sxs-lookup"><span data-stu-id="c4e00-234">ICorDebugModule2</span></span>](icordebugmodule2-interface.md)|<span data-ttu-id="c4e00-235">2.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-235">2.0</span></span>|  
|`ver_ICorDebugFunction2`|[<span data-ttu-id="c4e00-236">ICorDebugFunction2</span><span class="sxs-lookup"><span data-stu-id="c4e00-236">ICorDebugFunction2</span></span>](icordebugfunction2-interface.md)|<span data-ttu-id="c4e00-237">2.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-237">2.0</span></span>|  
|`ver_ICorDebugCode2`|[<span data-ttu-id="c4e00-238">ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="c4e00-238">ICorDebugCode2</span></span>](icordebugcode2-interface.md)|<span data-ttu-id="c4e00-239">2.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-239">2.0</span></span>|  
|`ver_ICorDebugClass2`|<span data-ttu-id="c4e00-240">ICorDebugClass2</span><span class="sxs-lookup"><span data-stu-id="c4e00-240">"ICorDebugClass2"</span></span>|<span data-ttu-id="c4e00-241">2.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-241">2.0</span></span>|  
|`ver_ICorDebugValue2`|<span data-ttu-id="c4e00-242">ICorDebugValue2</span><span class="sxs-lookup"><span data-stu-id="c4e00-242">"ICorDebugValue2"</span></span>|<span data-ttu-id="c4e00-243">2.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-243">2.0</span></span>|  
|`ver_ICorDebugEval2`|<span data-ttu-id="c4e00-244">"ICorDebugEval2"。</span><span class="sxs-lookup"><span data-stu-id="c4e00-244">The "ICorDebugEval2".</span></span>|<span data-ttu-id="c4e00-245">2.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-245">2.0</span></span>|  
|`ver_ICorDebugObjectValue2`|<span data-ttu-id="c4e00-246">ICorDebugObjectValue2</span><span class="sxs-lookup"><span data-stu-id="c4e00-246">"ICorDebugObjectValue2"</span></span>|<span data-ttu-id="c4e00-247">2.0</span><span class="sxs-lookup"><span data-stu-id="c4e00-247">2.0</span></span>|  
|`ver_ICorDebugThread3`|[<span data-ttu-id="c4e00-248">ICorDebugThread3</span><span class="sxs-lookup"><span data-stu-id="c4e00-248">ICorDebugThread3</span></span>](icordebugthread3-interface.md)|<span data-ttu-id="c4e00-249">4</span><span class="sxs-lookup"><span data-stu-id="c4e00-249">4</span></span>|  
|`ver_ICorDebugThread4`|[<span data-ttu-id="c4e00-250">ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="c4e00-250">ICorDebugThread4</span></span>](icordebugthread4-interface.md)|<span data-ttu-id="c4e00-251">4</span><span class="sxs-lookup"><span data-stu-id="c4e00-251">4</span></span>|  
|`ver_ICorDebugStackWalk`|[<span data-ttu-id="c4e00-252">ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="c4e00-252">ICorDebugStackWalk</span></span>](icordebugstackwalk-interface.md)|<span data-ttu-id="c4e00-253">4</span><span class="sxs-lookup"><span data-stu-id="c4e00-253">4</span></span>|  
|`ver_ICorDebugNativeFrame2`|[<span data-ttu-id="c4e00-254">ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="c4e00-254">ICorDebugNativeFrame2</span></span>](icordebugnativeframe2-interface.md)|<span data-ttu-id="c4e00-255">4</span><span class="sxs-lookup"><span data-stu-id="c4e00-255">4</span></span>|  
|`ver_ICorDebugInternalFrame2`|[<span data-ttu-id="c4e00-256">ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="c4e00-256">ICorDebugInternalFrame2</span></span>](icordebuginternalframe2-interface.md)|<span data-ttu-id="c4e00-257">4</span><span class="sxs-lookup"><span data-stu-id="c4e00-257">4</span></span>|  
|`ver_ICorDebugRuntimeUnwindableFrame`|[<span data-ttu-id="c4e00-258">ICorDebugRuntimeUnwindableFrame</span><span class="sxs-lookup"><span data-stu-id="c4e00-258">ICorDebugRuntimeUnwindableFrame</span></span>](icordebugruntimeunwindableframe-interface.md)|<span data-ttu-id="c4e00-259">4</span><span class="sxs-lookup"><span data-stu-id="c4e00-259">4</span></span>|  
|`ver_ICorDebugHeapValue3`|[<span data-ttu-id="c4e00-260">ICorDebugHeapValue3 接口</span><span class="sxs-lookup"><span data-stu-id="c4e00-260">ICorDebugHeapValue3 Interface</span></span>](icordebugheapvalue3-interface.md)|<span data-ttu-id="c4e00-261">4</span><span class="sxs-lookup"><span data-stu-id="c4e00-261">4</span></span>|  
|`ver_ICorDebugBlockingObjectEnum`|[<span data-ttu-id="c4e00-262">ICorDebugBlockingObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="c4e00-262">ICorDebugBlockingObjectEnum Interface</span></span>](icordebugblockingobjectenum-interface.md)|<span data-ttu-id="c4e00-263">4</span><span class="sxs-lookup"><span data-stu-id="c4e00-263">4</span></span>|  
|`ver_ICorDebugValue3`|[<span data-ttu-id="c4e00-264">ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="c4e00-264">ICorDebugValue3</span></span>](icordebugvalue3-interface.md)|<span data-ttu-id="c4e00-265">4</span><span class="sxs-lookup"><span data-stu-id="c4e00-265">4</span></span>|  
|`ver_ICorDebugComObjectValue`|[<span data-ttu-id="c4e00-266">ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="c4e00-266">ICorDebugComObjectValue</span></span>](icordebugcomobjectvalue-interface.md)|<span data-ttu-id="c4e00-267">4.5</span><span class="sxs-lookup"><span data-stu-id="c4e00-267">4.5</span></span>|  
|`ver_ICorDebugAppDomain3`|[<span data-ttu-id="c4e00-268">ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="c4e00-268">ICorDebugAppDomain3</span></span>](icordebugappdomain3-interface.md)|<span data-ttu-id="c4e00-269">4.5</span><span class="sxs-lookup"><span data-stu-id="c4e00-269">4.5</span></span>|  
|`ver_ICorDebugCode3`|[<span data-ttu-id="c4e00-270">ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="c4e00-270">ICorDebugCode3</span></span>](icordebugcode3-interface.md)|<span data-ttu-id="c4e00-271">4.5</span><span class="sxs-lookup"><span data-stu-id="c4e00-271">4.5</span></span>|  
|`ver_ICorDebugILFrame3`|[<span data-ttu-id="c4e00-272">ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="c4e00-272">ICorDebugILFrame3</span></span>](icordebugilframe3-interface.md)|<span data-ttu-id="c4e00-273">4.5</span><span class="sxs-lookup"><span data-stu-id="c4e00-273">4.5</span></span>|  
|`CorDebugLatestVersion`|<span data-ttu-id="c4e00-274">.NET Framework（包括其所有 Service Pack）的版本为最新版本。</span><span class="sxs-lookup"><span data-stu-id="c4e00-274">The version of the .NET Framework, including all of its service packs, is the latest version.</span></span>|-|  
  
## <a name="remarks"></a><span data-ttu-id="c4e00-275">备注</span><span class="sxs-lookup"><span data-stu-id="c4e00-275">Remarks</span></span>  
 <span data-ttu-id="c4e00-276">调试器可以在[CreateDebuggingInterfaceFromVersion](../hosting/createdebugginginterfacefromversion-function.md)函数`CorDebugInterfaceVersion`中使用枚举来指定调试器支持的 .NET Framework 的最高版本。</span><span class="sxs-lookup"><span data-stu-id="c4e00-276">A debugger can use the `CorDebugInterfaceVersion` enumeration in the [CreateDebuggingInterfaceFromVersion](../hosting/createdebugginginterfacefromversion-function.md) function to specify the highest version of the .NET Framework that the debugger supports.</span></span>  
  
## <a name="interface-names"></a><span data-ttu-id="c4e00-277">接口名称</span><span class="sxs-lookup"><span data-stu-id="c4e00-277">Interface Names</span></span>  
 <span data-ttu-id="c4e00-278">出现在调试 API 中接口名称的末尾的数字（例如 `ICorDebugThread3` 中的“3”）指定接口版本，而不是 .NET Framework 的版本。</span><span class="sxs-lookup"><span data-stu-id="c4e00-278">The number that appears at the end of the interface names in the debugging API (for example, the "3" in `ICorDebugThread3`) specifies the version of the interface, not the version of the .NET Framework.</span></span> <span data-ttu-id="c4e00-279">调试 API 中的所有接口名称包括除了 .NET Framework 版本 1 中引入的接口之外的版本号。</span><span class="sxs-lookup"><span data-stu-id="c4e00-279">All interface names in the debugging API include version numbers except for interfaces that were introduced in the .NET Framework version 1.</span></span> <span data-ttu-id="c4e00-280">接口版本号和 .NET Framework 版本号之间的任何对应关系都是巧合。</span><span class="sxs-lookup"><span data-stu-id="c4e00-280">Any correspondence between interface version numbers and.NET Framework version numbers are coincidental.</span></span>  
  
- <span data-ttu-id="c4e00-281">在 .NET Framework 版本 1.0 中引入的接口不包括数字，因为它们都是隐式版本 1。</span><span class="sxs-lookup"><span data-stu-id="c4e00-281">Interfaces that were introduced in the .NET Framework version 1.0 do not include numbers, because they are all implicitly version 1.</span></span>  
  
- <span data-ttu-id="c4e00-282">.NET Framework 版本 1.1 使用版本 1.0 接口，并且并未引入任何新调试接口。</span><span class="sxs-lookup"><span data-stu-id="c4e00-282">The .NET Framework version 1.1 uses version 1.0 interfaces, and does not introduce any new debugging interfaces.</span></span>  
  
- <span data-ttu-id="c4e00-283">在 .NET Framework 版本 2.0 中引入的 14 调试接口是版本 1 对应部分的逻辑扩展，并在其名称中包含数字“2”。</span><span class="sxs-lookup"><span data-stu-id="c4e00-283">The 14 debugging interfaces introduced in the .NET Framework version 2.0 are logical extensions of their version 1 counterparts and include the number "2" in their names.</span></span>  
  
- <span data-ttu-id="c4e00-284">.NET Framework 版本 3.0 和 3.5 使用现有 .NET Framework 2.0 接口，并且并未引入任何新接口。</span><span class="sxs-lookup"><span data-stu-id="c4e00-284">The .NET Framework versions 3.0 and 3.5 use the existing .NET Framework 2.0 interfaces, and do not introduce any new interfaces.</span></span>  
  
- <span data-ttu-id="c4e00-285">.NET Framework 4 引入了接口版本的混合。</span><span class="sxs-lookup"><span data-stu-id="c4e00-285">The .NET Framework 4 introduces a mix of interface versions.</span></span> <span data-ttu-id="c4e00-286">例如，`ICorDebugThread3` 和 `ICorDebugThread4` 显示为 `ICorDebugThread` 接口的第三个和第四个版本。</span><span class="sxs-lookup"><span data-stu-id="c4e00-286">For example, both `ICorDebugThread3` and `ICorDebugThread4` appear as the third and fourth versions of the `ICorDebugThread` interface.</span></span> <span data-ttu-id="c4e00-287">.NET Framework 4 还引入了`ICorDebugStackWalk`接口的第一个版本和该`ICorDebugNativeFrame`接口的第二个版本（`ICorDebugNativeFrame2`）。</span><span class="sxs-lookup"><span data-stu-id="c4e00-287">The .NET Framework 4 also introduces the first version of the `ICorDebugStackWalk` interface and the second version of the `ICorDebugNativeFrame` interface (`ICorDebugNativeFrame2`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4e00-288">要求</span><span class="sxs-lookup"><span data-stu-id="c4e00-288">Requirements</span></span>  
 <span data-ttu-id="c4e00-289">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c4e00-289">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4e00-290">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4e00-290">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4e00-291">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4e00-291">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4e00-292">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4e00-292">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4e00-293">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4e00-293">See also</span></span>

- [<span data-ttu-id="c4e00-294">调试枚举</span><span class="sxs-lookup"><span data-stu-id="c4e00-294">Debugging Enumerations</span></span>](debugging-enumerations.md)
