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
ms.openlocfilehash: 70d9ee06d64cc80306a1988aa6e28859cadb9ecf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778408"
---
# <a name="cordebuginterfaceversion-enumeration"></a><span data-ttu-id="dc181-102">CorDebugInterfaceVersion 枚举</span><span class="sxs-lookup"><span data-stu-id="dc181-102">CorDebugInterfaceVersion Enumeration</span></span>
<span data-ttu-id="dc181-103">指定接口，.NET Framework 的版本，或在其中引入了接口的 .NET Framework 的版本。</span><span class="sxs-lookup"><span data-stu-id="dc181-103">Specifies an interface, a version of the .NET Framework, or a version of the .NET Framework in which an interface was introduced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc181-104">语法</span><span class="sxs-lookup"><span data-stu-id="dc181-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="dc181-105">Members</span><span class="sxs-lookup"><span data-stu-id="dc181-105">Members</span></span>  
 <span data-ttu-id="dc181-106">下表提供了从每个枚举值到相应的接口的链接。</span><span class="sxs-lookup"><span data-stu-id="dc181-106">The following table provides links from each enumeration value to the corresponding interface.</span></span> <span data-ttu-id="dc181-107">此外，该表还指示了支持该接口的第一版 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="dc181-107">In addition, the table indicates the first version of the .NET Framework that the interface was supported in.</span></span>  
  
|<span data-ttu-id="dc181-108">成员</span><span class="sxs-lookup"><span data-stu-id="dc181-108">Member</span></span>|<span data-ttu-id="dc181-109">指定</span><span class="sxs-lookup"><span data-stu-id="dc181-109">Specifies</span></span>|<span data-ttu-id="dc181-110">.NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="dc181-110">.NET Framework version</span></span>|  
|------------|---------------|----------------------------|  
|`CorDebugInvalidVersion`|<span data-ttu-id="dc181-111">.NET Framework 的版本无效。</span><span class="sxs-lookup"><span data-stu-id="dc181-111">The version of the .NET Framework is invalid.</span></span>|-|  
|`CorDebugVersion_1_0`|<span data-ttu-id="dc181-112">.NET Framework（包括其所有 Service Pack）的版本为 1.0。</span><span class="sxs-lookup"><span data-stu-id="dc181-112">The version of the .NET Framework, including all its service packs, is 1.0.</span></span>|<span data-ttu-id="dc181-113">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-113">1.0</span></span>|  
|`CorDebugVersion_1_1`|<span data-ttu-id="dc181-114">.NET Framework（包括所有 Service Pack）的版本为 1.1。</span><span class="sxs-lookup"><span data-stu-id="dc181-114">The version of the .NET Framework, including all service packs, is 1.1.</span></span>|<span data-ttu-id="dc181-115">1.1</span><span class="sxs-lookup"><span data-stu-id="dc181-115">1.1</span></span>|  
|`CorDebugVersion_2_0`|<span data-ttu-id="dc181-116">.NET Framework（包括所有 Service Pack）的版本为 2.0。</span><span class="sxs-lookup"><span data-stu-id="dc181-116">The version of the .NET Framework, including all service packs, is 2.0.</span></span>|<span data-ttu-id="dc181-117">2.0</span><span class="sxs-lookup"><span data-stu-id="dc181-117">2.0</span></span>|  
|`CorDebugVersion_4_0`|<span data-ttu-id="dc181-118">.NET Framework（包括所有 Service Pack）的版本为 4。</span><span class="sxs-lookup"><span data-stu-id="dc181-118">The version of the .NET Framework, including all service packs, is 4.</span></span>|<span data-ttu-id="dc181-119">4</span><span class="sxs-lookup"><span data-stu-id="dc181-119">4</span></span>|  
|`CorDebugVersion_4_5`|<span data-ttu-id="dc181-120">.NET Framework（包括所有 Service Pack）的版本为 4.5。</span><span class="sxs-lookup"><span data-stu-id="dc181-120">The version of the .NET Framework, including all service packs, is 4.5.</span></span>|<span data-ttu-id="dc181-121">4.5</span><span class="sxs-lookup"><span data-stu-id="dc181-121">4.5</span></span>|  
|`ver_ICorDebugManagedCallback`|[<span data-ttu-id="dc181-122">ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="dc181-122">ICorDebugManagedCallback</span></span>](icordebugmanagedcallback-interface.md)|<span data-ttu-id="dc181-123">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-123">1.0</span></span>|  
|`ver_ICorDebugUnmanagedCallback`|[<span data-ttu-id="dc181-124">ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="dc181-124">ICorDebugUnmanagedCallback</span></span>](icordebugunmanagedcallback-interface.md)|<span data-ttu-id="dc181-125">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-125">1.0</span></span>|  
|`ver_ICorDebug`|[<span data-ttu-id="dc181-126">ICorDebug</span><span class="sxs-lookup"><span data-stu-id="dc181-126">ICorDebug</span></span>](icordebug-interface.md)|<span data-ttu-id="dc181-127">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-127">1.0</span></span>|  
|`ver_ICorDebugController`|[<span data-ttu-id="dc181-128">ICorDebugController</span><span class="sxs-lookup"><span data-stu-id="dc181-128">ICorDebugController</span></span>](icordebugcontroller-interface.md)|<span data-ttu-id="dc181-129">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-129">1.0</span></span>|  
|`ver_ICorDebugAppDomain`|[<span data-ttu-id="dc181-130">ICorDebugAppDomain</span><span class="sxs-lookup"><span data-stu-id="dc181-130">ICorDebugAppDomain</span></span>](icordebugappdomain-interface.md)|<span data-ttu-id="dc181-131">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-131">1.0</span></span>|  
|`ver_ICorDebugAssembly`|[<span data-ttu-id="dc181-132">ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="dc181-132">ICorDebugAssembly</span></span>](icordebugassembly-interface.md)|<span data-ttu-id="dc181-133">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-133">1.0</span></span>|  
|`ver_ICorDebugProcess`|[<span data-ttu-id="dc181-134">ICorDebugProcess</span><span class="sxs-lookup"><span data-stu-id="dc181-134">ICorDebugProcess</span></span>](icordebugprocess-interface.md)|<span data-ttu-id="dc181-135">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-135">1.0</span></span>|  
|`ver_ICorDebugBreakpoint`|[<span data-ttu-id="dc181-136">ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="dc181-136">ICorDebugBreakpoint</span></span>](icordebugbreakpoint-interface.md)|<span data-ttu-id="dc181-137">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-137">1.0</span></span>|  
|`ver_ICorDebugFunctionBreakpoint`|[<span data-ttu-id="dc181-138">ICorDebugFunctionBreakpoint</span><span class="sxs-lookup"><span data-stu-id="dc181-138">ICorDebugFunctionBreakpoint</span></span>](icordebugfunctionbreakpoint-interface.md)|<span data-ttu-id="dc181-139">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-139">1.0</span></span>|  
|`ver_ICorDebugModuleBreakpoint`|[<span data-ttu-id="dc181-140">ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="dc181-140">ICorDebugModuleBreakpoint</span></span>](icordebugmodulebreakpoint-interface.md)|<span data-ttu-id="dc181-141">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-141">1.0</span></span>|  
|`ver_ICorDebugValueBreakpoint`|[<span data-ttu-id="dc181-142">ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="dc181-142">ICorDebugValueBreakpoint</span></span>](icordebugvaluebreakpoint-interface.md)|<span data-ttu-id="dc181-143">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-143">1.0</span></span>|  
|`ver_ICorDebugStepper`|[<span data-ttu-id="dc181-144">ICorDebugStepper</span><span class="sxs-lookup"><span data-stu-id="dc181-144">ICorDebugStepper</span></span>](icordebugstepper-interface.md)|<span data-ttu-id="dc181-145">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-145">1.0</span></span>|  
|`ver_ICorDebugRegisterSet`|[<span data-ttu-id="dc181-146">ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="dc181-146">ICorDebugRegisterSet</span></span>](icordebugregisterset-interface.md)|<span data-ttu-id="dc181-147">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-147">1.0</span></span>|  
|`ver_ICorDebugThread`|[<span data-ttu-id="dc181-148">ICorDebugThread</span><span class="sxs-lookup"><span data-stu-id="dc181-148">ICorDebugThread</span></span>](icordebugthread-interface.md)|<span data-ttu-id="dc181-149">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-149">1.0</span></span>|  
|`ver_ICorDebugChain`|[<span data-ttu-id="dc181-150">ICorDebugChain</span><span class="sxs-lookup"><span data-stu-id="dc181-150">ICorDebugChain</span></span>](icordebugchain-interface.md)|<span data-ttu-id="dc181-151">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-151">1.0</span></span>|  
|`ver_ICorDebugFrame`|[<span data-ttu-id="dc181-152">ICorDebugFrame</span><span class="sxs-lookup"><span data-stu-id="dc181-152">ICorDebugFrame</span></span>](icordebugframe-interface.md)|<span data-ttu-id="dc181-153">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-153">1.0</span></span>|  
|`ver_ICorDebugILFrame`|[<span data-ttu-id="dc181-154">ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="dc181-154">ICorDebugILFrame</span></span>](icordebugilframe-interface.md)|<span data-ttu-id="dc181-155">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-155">1.0</span></span>|  
|`ver_ICorDebugNativeFrame`|[<span data-ttu-id="dc181-156">ICorDebugNativeFrame</span><span class="sxs-lookup"><span data-stu-id="dc181-156">ICorDebugNativeFrame</span></span>](icordebugnativeframe-interface.md)|<span data-ttu-id="dc181-157">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-157">1.0</span></span>|  
|`ver_ICorDebugModule`|[<span data-ttu-id="dc181-158">ICorDebugModule</span><span class="sxs-lookup"><span data-stu-id="dc181-158">ICorDebugModule</span></span>](icordebugmodule-interface.md)|<span data-ttu-id="dc181-159">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-159">1.0</span></span>|  
|`ver_ICorDebugFunction`|[<span data-ttu-id="dc181-160">ICorDebugFunction</span><span class="sxs-lookup"><span data-stu-id="dc181-160">ICorDebugFunction</span></span>](icordebugfunction-interface1.md)|<span data-ttu-id="dc181-161">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-161">1.0</span></span>|  
|`ver_ICorDebugCode`|[<span data-ttu-id="dc181-162">ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="dc181-162">ICorDebugCode</span></span>](icordebugcode-interface1.md)|<span data-ttu-id="dc181-163">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-163">1.0</span></span>|  
|`ver_ICorDebugClass`|[<span data-ttu-id="dc181-164">ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="dc181-164">ICorDebugClass</span></span>](icordebugclass-interface.md)|<span data-ttu-id="dc181-165">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-165">1.0</span></span>|  
|`ver_ICorDebugEval`|[<span data-ttu-id="dc181-166">ICorDebugEval</span><span class="sxs-lookup"><span data-stu-id="dc181-166">ICorDebugEval</span></span>](icordebugeval-interface.md)|<span data-ttu-id="dc181-167">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-167">1.0</span></span>|  
|`ver_ICorDebugValue`|[<span data-ttu-id="dc181-168">ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="dc181-168">ICorDebugValue</span></span>](icordebugvalue-interface.md)|<span data-ttu-id="dc181-169">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-169">1.0</span></span>|  
|`ver_ICorDebugGenericValue`|[<span data-ttu-id="dc181-170">ICorDebugGenericValue</span><span class="sxs-lookup"><span data-stu-id="dc181-170">ICorDebugGenericValue</span></span>](icordebuggenericvalue-interface.md)|<span data-ttu-id="dc181-171">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-171">1.0</span></span>|  
|`ver_ICorDebugReferenceValue`|[<span data-ttu-id="dc181-172">ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="dc181-172">ICorDebugReferenceValue</span></span>](icordebugreferencevalue-interface.md)|<span data-ttu-id="dc181-173">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-173">1.0</span></span>|  
|`ver_ICorDebugHeapValue`|[<span data-ttu-id="dc181-174">ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="dc181-174">ICorDebugHeapValue</span></span>](icordebugheapvalue-interface.md)|<span data-ttu-id="dc181-175">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-175">1.0</span></span>|  
|`ver_ICorDebugObjectValue`|[<span data-ttu-id="dc181-176">ICorDebugObjectValue</span><span class="sxs-lookup"><span data-stu-id="dc181-176">ICorDebugObjectValue</span></span>](icordebugobjectvalue-interface.md)|<span data-ttu-id="dc181-177">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-177">1.0</span></span>|  
|`ver_ICorDebugBoxValue`|[<span data-ttu-id="dc181-178">ICorDebugBoxValue</span><span class="sxs-lookup"><span data-stu-id="dc181-178">ICorDebugBoxValue</span></span>](icordebugboxvalue-interface.md)|<span data-ttu-id="dc181-179">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-179">1.0</span></span>|  
|`ver_ICorDebugStringValue`|[<span data-ttu-id="dc181-180">ICorDebugStringValue</span><span class="sxs-lookup"><span data-stu-id="dc181-180">ICorDebugStringValue</span></span>](icordebugstringvalue-interface.md)|<span data-ttu-id="dc181-181">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-181">1.0</span></span>|  
|`ver_ICorDebugArrayValue`|[<span data-ttu-id="dc181-182">ICorDebugArrayValue</span><span class="sxs-lookup"><span data-stu-id="dc181-182">ICorDebugArrayValue</span></span>](icordebugarrayvalue-interface.md)|<span data-ttu-id="dc181-183">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-183">1.0</span></span>|  
|`ver_ICorDebugContext`|[<span data-ttu-id="dc181-184">ICorDebugContext</span><span class="sxs-lookup"><span data-stu-id="dc181-184">ICorDebugContext</span></span>](icordebugcontext-interface.md)|<span data-ttu-id="dc181-185">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-185">1.0</span></span>|  
|`ver_ICorDebugEnum`|[<span data-ttu-id="dc181-186">ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="dc181-186">ICorDebugEnum</span></span>](icordebugenum-interface1.md)|<span data-ttu-id="dc181-187">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-187">1.0</span></span>|  
|`ver_ICorDebugObjectEnum`|[<span data-ttu-id="dc181-188">ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="dc181-188">ICorDebugObjectEnum</span></span>](icordebugobjectenum-interface.md)|<span data-ttu-id="dc181-189">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-189">1.0</span></span>|  
|`ver_ICorDebugBreakpointEnum`|[<span data-ttu-id="dc181-190">ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="dc181-190">ICorDebugBreakpointEnum</span></span>](icordebugbreakpointenum-interface.md)|<span data-ttu-id="dc181-191">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-191">1.0</span></span>|  
|`ver_ICorDebugStepperEnum`|[<span data-ttu-id="dc181-192">ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="dc181-192">ICorDebugStepperEnum</span></span>](icordebugstepperenum-interface.md)|<span data-ttu-id="dc181-193">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-193">1.0</span></span>|  
|`ver_ICorDebugProcessEnum`|[<span data-ttu-id="dc181-194">ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="dc181-194">ICorDebugProcessEnum</span></span>](icordebugprocessenum-interface.md)|<span data-ttu-id="dc181-195">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-195">1.0</span></span>|  
|`ver_ICorDebugThreadEnum`|[<span data-ttu-id="dc181-196">ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="dc181-196">ICorDebugThreadEnum</span></span>](icordebugthreadenum-interface1.md)|<span data-ttu-id="dc181-197">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-197">1.0</span></span>|  
|`ver_ICorDebugFrameEnum`|[<span data-ttu-id="dc181-198">ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="dc181-198">ICorDebugFrameEnum</span></span>](icordebugframeenum-interface.md)|<span data-ttu-id="dc181-199">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-199">1.0</span></span>|  
|`ver_ICorDebugChainEnum`|[<span data-ttu-id="dc181-200">ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="dc181-200">ICorDebugChainEnum</span></span>](icordebugchainenum-interface.md)|<span data-ttu-id="dc181-201">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-201">1.0</span></span>|  
|`ver_ICorDebugModuleEnum`|[<span data-ttu-id="dc181-202">ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="dc181-202">ICorDebugModuleEnum</span></span>](icordebugmoduleenum-interface.md)|<span data-ttu-id="dc181-203">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-203">1.0</span></span>|  
|`ver_ICorDebugValueEnum`|[<span data-ttu-id="dc181-204">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="dc181-204">ICorDebugValueEnum</span></span>](icordebugvalueenum-interface.md)|<span data-ttu-id="dc181-205">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-205">1.0</span></span>|  
|`ver_ICorDebugCodeEnum`|[<span data-ttu-id="dc181-206">ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="dc181-206">ICorDebugCodeEnum</span></span>](icordebugcodeenum-interface.md)|<span data-ttu-id="dc181-207">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-207">1.0</span></span>|  
|`ver_ICorDebugTypeEnum`|[<span data-ttu-id="dc181-208">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="dc181-208">ICorDebugTypeEnum</span></span>](icordebugtypeenum-interface.md)|<span data-ttu-id="dc181-209">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-209">1.0</span></span>|  
|`ver_ICorDebugErrorInfoEnum`|[<span data-ttu-id="dc181-210">ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="dc181-210">ICorDebugErrorInfoEnum</span></span>](icordebugerrorinfoenum-interface.md)|<span data-ttu-id="dc181-211">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-211">1.0</span></span>|  
|`ver_ICorDebugAppDomainEnum`|[<span data-ttu-id="dc181-212">ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="dc181-212">ICorDebugAppDomainEnum</span></span>](icordebugappdomainenum-interface.md)|<span data-ttu-id="dc181-213">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-213">1.0</span></span>|  
|`ver_ICorDebugAssemblyEnum`|[<span data-ttu-id="dc181-214">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="dc181-214">ICorDebugAssemblyEnum</span></span>](icordebugassemblyenum-interface.md)|<span data-ttu-id="dc181-215">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-215">1.0</span></span>|  
|`ver_ICorDebugEditAndContinueErrorInfo`|[<span data-ttu-id="dc181-216">ICorDebugEditAndContinueErrorInfo</span><span class="sxs-lookup"><span data-stu-id="dc181-216">ICorDebugEditAndContinueErrorInfo</span></span>](icordebugeditandcontinueerrorinfo-interface.md)|<span data-ttu-id="dc181-217">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-217">1.0</span></span>|  
|`ver_ICorDebugEditAndContinueSnapshot`|[<span data-ttu-id="dc181-218">ICorDebugEditAndContinueSnapshot</span><span class="sxs-lookup"><span data-stu-id="dc181-218">ICorDebugEditAndContinueSnapshot</span></span>](icordebugeditandcontinuesnapshot-interface.md)|<span data-ttu-id="dc181-219">1.0</span><span class="sxs-lookup"><span data-stu-id="dc181-219">1.0</span></span>|  
|`ver_ICorDebugManagedCallback2`|[<span data-ttu-id="dc181-220">ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="dc181-220">ICorDebugManagedCallback2</span></span>](icordebugmanagedcallback2-interface.md)|<span data-ttu-id="dc181-221">2.0</span><span class="sxs-lookup"><span data-stu-id="dc181-221">2.0</span></span>|  
|`ver_ICorDebugAppDomain2`|[<span data-ttu-id="dc181-222">ICorDebugAppDomain2</span><span class="sxs-lookup"><span data-stu-id="dc181-222">ICorDebugAppDomain2</span></span>](icordebugappdomain2-interface.md)|<span data-ttu-id="dc181-223">2.0</span><span class="sxs-lookup"><span data-stu-id="dc181-223">2.0</span></span>|  
|`ver_ICorDebugProcess2`|[<span data-ttu-id="dc181-224">ICorDebugProcess2</span><span class="sxs-lookup"><span data-stu-id="dc181-224">ICorDebugProcess2</span></span>](icordebugprocess2-interface1.md)|<span data-ttu-id="dc181-225">2.0</span><span class="sxs-lookup"><span data-stu-id="dc181-225">2.0</span></span>|  
|`ver_ICorDebugStepper2`|[<span data-ttu-id="dc181-226">ICorDebugStepper2</span><span class="sxs-lookup"><span data-stu-id="dc181-226">ICorDebugStepper2</span></span>](icordebugstepper2-interface1.md)|<span data-ttu-id="dc181-227">2.0</span><span class="sxs-lookup"><span data-stu-id="dc181-227">2.0</span></span>|  
|`ver_ICorDebugRegisterSet2`|[<span data-ttu-id="dc181-228">ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="dc181-228">ICorDebugRegisterSet2</span></span>](icordebugregisterset2-interface.md)|<span data-ttu-id="dc181-229">2.0</span><span class="sxs-lookup"><span data-stu-id="dc181-229">2.0</span></span>|  
|`ver_ICorDebugThread2`|[<span data-ttu-id="dc181-230">ICorDebugThread2</span><span class="sxs-lookup"><span data-stu-id="dc181-230">ICorDebugThread2</span></span>](icordebugthread2-interface.md)|<span data-ttu-id="dc181-231">2.0</span><span class="sxs-lookup"><span data-stu-id="dc181-231">2.0</span></span>|  
|`ver_ICorDebugILFrame2`|[<span data-ttu-id="dc181-232">ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="dc181-232">ICorDebugILFrame2</span></span>](icordebugilframe2-interface.md)|<span data-ttu-id="dc181-233">2.0</span><span class="sxs-lookup"><span data-stu-id="dc181-233">2.0</span></span>|  
|`ver_ICorDebugModule2`|[<span data-ttu-id="dc181-234">ICorDebugModule2</span><span class="sxs-lookup"><span data-stu-id="dc181-234">ICorDebugModule2</span></span>](icordebugmodule2-interface.md)|<span data-ttu-id="dc181-235">2.0</span><span class="sxs-lookup"><span data-stu-id="dc181-235">2.0</span></span>|  
|`ver_ICorDebugFunction2`|[<span data-ttu-id="dc181-236">ICorDebugFunction2</span><span class="sxs-lookup"><span data-stu-id="dc181-236">ICorDebugFunction2</span></span>](icordebugfunction2-interface.md)|<span data-ttu-id="dc181-237">2.0</span><span class="sxs-lookup"><span data-stu-id="dc181-237">2.0</span></span>|  
|`ver_ICorDebugCode2`|[<span data-ttu-id="dc181-238">ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="dc181-238">ICorDebugCode2</span></span>](icordebugcode2-interface.md)|<span data-ttu-id="dc181-239">2.0</span><span class="sxs-lookup"><span data-stu-id="dc181-239">2.0</span></span>|  
|`ver_ICorDebugClass2`|<span data-ttu-id="dc181-240">ICorDebugClass2</span><span class="sxs-lookup"><span data-stu-id="dc181-240">"ICorDebugClass2"</span></span>|<span data-ttu-id="dc181-241">2.0</span><span class="sxs-lookup"><span data-stu-id="dc181-241">2.0</span></span>|  
|`ver_ICorDebugValue2`|<span data-ttu-id="dc181-242">ICorDebugValue2</span><span class="sxs-lookup"><span data-stu-id="dc181-242">"ICorDebugValue2"</span></span>|<span data-ttu-id="dc181-243">2.0</span><span class="sxs-lookup"><span data-stu-id="dc181-243">2.0</span></span>|  
|`ver_ICorDebugEval2`|<span data-ttu-id="dc181-244">"ICorDebugEval2"。</span><span class="sxs-lookup"><span data-stu-id="dc181-244">The "ICorDebugEval2".</span></span>|<span data-ttu-id="dc181-245">2.0</span><span class="sxs-lookup"><span data-stu-id="dc181-245">2.0</span></span>|  
|`ver_ICorDebugObjectValue2`|<span data-ttu-id="dc181-246">"ICorDebugObjectValue2"</span><span class="sxs-lookup"><span data-stu-id="dc181-246">"ICorDebugObjectValue2"</span></span>|<span data-ttu-id="dc181-247">2.0</span><span class="sxs-lookup"><span data-stu-id="dc181-247">2.0</span></span>|  
|`ver_ICorDebugThread3`|[<span data-ttu-id="dc181-248">ICorDebugThread3</span><span class="sxs-lookup"><span data-stu-id="dc181-248">ICorDebugThread3</span></span>](icordebugthread3-interface.md)|<span data-ttu-id="dc181-249">4</span><span class="sxs-lookup"><span data-stu-id="dc181-249">4</span></span>|  
|`ver_ICorDebugThread4`|[<span data-ttu-id="dc181-250">ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="dc181-250">ICorDebugThread4</span></span>](icordebugthread4-interface.md)|<span data-ttu-id="dc181-251">4</span><span class="sxs-lookup"><span data-stu-id="dc181-251">4</span></span>|  
|`ver_ICorDebugStackWalk`|[<span data-ttu-id="dc181-252">ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="dc181-252">ICorDebugStackWalk</span></span>](icordebugstackwalk-interface.md)|<span data-ttu-id="dc181-253">4</span><span class="sxs-lookup"><span data-stu-id="dc181-253">4</span></span>|  
|`ver_ICorDebugNativeFrame2`|[<span data-ttu-id="dc181-254">ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="dc181-254">ICorDebugNativeFrame2</span></span>](icordebugnativeframe2-interface.md)|<span data-ttu-id="dc181-255">4</span><span class="sxs-lookup"><span data-stu-id="dc181-255">4</span></span>|  
|`ver_ICorDebugInternalFrame2`|[<span data-ttu-id="dc181-256">ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="dc181-256">ICorDebugInternalFrame2</span></span>](icordebuginternalframe2-interface.md)|<span data-ttu-id="dc181-257">4</span><span class="sxs-lookup"><span data-stu-id="dc181-257">4</span></span>|  
|`ver_ICorDebugRuntimeUnwindableFrame`|[<span data-ttu-id="dc181-258">ICorDebugRuntimeUnwindableFrame</span><span class="sxs-lookup"><span data-stu-id="dc181-258">ICorDebugRuntimeUnwindableFrame</span></span>](icordebugruntimeunwindableframe-interface.md)|<span data-ttu-id="dc181-259">4</span><span class="sxs-lookup"><span data-stu-id="dc181-259">4</span></span>|  
|`ver_ICorDebugHeapValue3`|[<span data-ttu-id="dc181-260">ICorDebugHeapValue3 接口</span><span class="sxs-lookup"><span data-stu-id="dc181-260">ICorDebugHeapValue3 Interface</span></span>](icordebugheapvalue3-interface.md)|<span data-ttu-id="dc181-261">4</span><span class="sxs-lookup"><span data-stu-id="dc181-261">4</span></span>|  
|`ver_ICorDebugBlockingObjectEnum`|[<span data-ttu-id="dc181-262">ICorDebugBlockingObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="dc181-262">ICorDebugBlockingObjectEnum Interface</span></span>](icordebugblockingobjectenum-interface.md)|<span data-ttu-id="dc181-263">4</span><span class="sxs-lookup"><span data-stu-id="dc181-263">4</span></span>|  
|`ver_ICorDebugValue3`|[<span data-ttu-id="dc181-264">ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="dc181-264">ICorDebugValue3</span></span>](icordebugvalue3-interface.md)|<span data-ttu-id="dc181-265">4</span><span class="sxs-lookup"><span data-stu-id="dc181-265">4</span></span>|  
|`ver_ICorDebugComObjectValue`|[<span data-ttu-id="dc181-266">ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="dc181-266">ICorDebugComObjectValue</span></span>](icordebugcomobjectvalue-interface.md)|<span data-ttu-id="dc181-267">4.5</span><span class="sxs-lookup"><span data-stu-id="dc181-267">4.5</span></span>|  
|`ver_ICorDebugAppDomain3`|[<span data-ttu-id="dc181-268">ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="dc181-268">ICorDebugAppDomain3</span></span>](icordebugappdomain3-interface.md)|<span data-ttu-id="dc181-269">4.5</span><span class="sxs-lookup"><span data-stu-id="dc181-269">4.5</span></span>|  
|`ver_ICorDebugCode3`|[<span data-ttu-id="dc181-270">ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="dc181-270">ICorDebugCode3</span></span>](icordebugcode3-interface.md)|<span data-ttu-id="dc181-271">4.5</span><span class="sxs-lookup"><span data-stu-id="dc181-271">4.5</span></span>|  
|`ver_ICorDebugILFrame3`|[<span data-ttu-id="dc181-272">ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="dc181-272">ICorDebugILFrame3</span></span>](icordebugilframe3-interface.md)|<span data-ttu-id="dc181-273">4.5</span><span class="sxs-lookup"><span data-stu-id="dc181-273">4.5</span></span>|  
|`CorDebugLatestVersion`|<span data-ttu-id="dc181-274">.NET Framework（包括其所有 Service Pack）的版本为最新版本。</span><span class="sxs-lookup"><span data-stu-id="dc181-274">The version of the .NET Framework, including all of its service packs, is the latest version.</span></span>|-|  
  
## <a name="remarks"></a><span data-ttu-id="dc181-275">备注</span><span class="sxs-lookup"><span data-stu-id="dc181-275">Remarks</span></span>  
 <span data-ttu-id="dc181-276">调试器可以使用[CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)函数中的 `CorDebugInterfaceVersion` 枚举来指定调试器支持 .NET Framework 的最高版本。</span><span class="sxs-lookup"><span data-stu-id="dc181-276">A debugger can use the `CorDebugInterfaceVersion` enumeration in the [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) function to specify the highest version of the .NET Framework that the debugger supports.</span></span>  
  
## <a name="interface-names"></a><span data-ttu-id="dc181-277">接口名称</span><span class="sxs-lookup"><span data-stu-id="dc181-277">Interface Names</span></span>  
 <span data-ttu-id="dc181-278">出现在调试 API 中接口名称的末尾的数字（例如 `ICorDebugThread3` 中的“3”）指定接口版本，而不是 .NET Framework 的版本。</span><span class="sxs-lookup"><span data-stu-id="dc181-278">The number that appears at the end of the interface names in the debugging API (for example, the "3" in `ICorDebugThread3`) specifies the version of the interface, not the version of the .NET Framework.</span></span> <span data-ttu-id="dc181-279">调试 API 中的所有接口名称包括除了 .NET Framework 版本 1 中引入的接口之外的版本号。</span><span class="sxs-lookup"><span data-stu-id="dc181-279">All interface names in the debugging API include version numbers except for interfaces that were introduced in the .NET Framework version 1.</span></span> <span data-ttu-id="dc181-280">接口版本号和 .NET Framework 版本号之间的任何对应关系都是巧合。</span><span class="sxs-lookup"><span data-stu-id="dc181-280">Any correspondence between interface version numbers and.NET Framework version numbers are coincidental.</span></span>  
  
- <span data-ttu-id="dc181-281">在 .NET Framework 版本 1.0 中引入的接口不包括数字，因为它们都是隐式版本 1。</span><span class="sxs-lookup"><span data-stu-id="dc181-281">Interfaces that were introduced in the .NET Framework version 1.0 do not include numbers, because they are all implicitly version 1.</span></span>  
  
- <span data-ttu-id="dc181-282">.NET Framework 版本 1.1 使用版本 1.0 接口，并且并未引入任何新调试接口。</span><span class="sxs-lookup"><span data-stu-id="dc181-282">The .NET Framework version 1.1 uses version 1.0 interfaces, and does not introduce any new debugging interfaces.</span></span>  
  
- <span data-ttu-id="dc181-283">在 .NET Framework 版本 2.0 中引入的 14 调试接口是版本 1 对应部分的逻辑扩展，并在其名称中包含数字“2”。</span><span class="sxs-lookup"><span data-stu-id="dc181-283">The 14 debugging interfaces introduced in the .NET Framework version 2.0 are logical extensions of their version 1 counterparts and include the number "2" in their names.</span></span>  
  
- <span data-ttu-id="dc181-284">.NET Framework 版本 3.0 和 3.5 使用现有 .NET Framework 2.0 接口，并且并未引入任何新接口。</span><span class="sxs-lookup"><span data-stu-id="dc181-284">The .NET Framework versions 3.0 and 3.5 use the existing .NET Framework 2.0 interfaces, and do not introduce any new interfaces.</span></span>  
  
- <span data-ttu-id="dc181-285">.NET Framework 4 引入了接口版本的混合。</span><span class="sxs-lookup"><span data-stu-id="dc181-285">The .NET Framework 4 introduces a mix of interface versions.</span></span> <span data-ttu-id="dc181-286">例如，`ICorDebugThread3` 和 `ICorDebugThread4` 显示为 `ICorDebugThread` 接口的第三个和第四个版本。</span><span class="sxs-lookup"><span data-stu-id="dc181-286">For example, both `ICorDebugThread3` and `ICorDebugThread4` appear as the third and fourth versions of the `ICorDebugThread` interface.</span></span> <span data-ttu-id="dc181-287">.NET Framework 4 还引入了 `ICorDebugStackWalk` 接口的第一个版本和 `ICorDebugNativeFrame` 接口的第二个版本（`ICorDebugNativeFrame2`）。</span><span class="sxs-lookup"><span data-stu-id="dc181-287">The .NET Framework 4 also introduces the first version of the `ICorDebugStackWalk` interface and the second version of the `ICorDebugNativeFrame` interface (`ICorDebugNativeFrame2`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc181-288">需求</span><span class="sxs-lookup"><span data-stu-id="dc181-288">Requirements</span></span>  
 <span data-ttu-id="dc181-289">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dc181-289">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc181-290">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc181-290">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc181-291">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc181-291">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc181-292">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc181-292">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc181-293">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc181-293">See also</span></span>

- [<span data-ttu-id="dc181-294">调试枚举</span><span class="sxs-lookup"><span data-stu-id="dc181-294">Debugging Enumerations</span></span>](debugging-enumerations.md)
