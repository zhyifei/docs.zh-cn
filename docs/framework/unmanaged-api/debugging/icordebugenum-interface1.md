---
title: "ICorDebugEnum 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum
helpviewer_keywords:
- ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 80be7efe-2c32-4b9f-8c52-40c6f6268219
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 751cca87962473501ef29a4deb99d9d24be33396
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugenum-interface1"></a><span data-ttu-id="96f67-102">ICorDebugEnum 接口 1</span><span class="sxs-lookup"><span data-stu-id="96f67-102">ICorDebugEnum Interface1</span></span>
<span data-ttu-id="96f67-103">调试应用程序使用的枚举数作为抽象的基接口。</span><span class="sxs-lookup"><span data-stu-id="96f67-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="96f67-104">方法</span><span class="sxs-lookup"><span data-stu-id="96f67-104">Methods</span></span>  
  
|<span data-ttu-id="96f67-105">方法</span><span class="sxs-lookup"><span data-stu-id="96f67-105">Method</span></span>|<span data-ttu-id="96f67-106">描述</span><span class="sxs-lookup"><span data-stu-id="96f67-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="96f67-107">Clone 方法</span><span class="sxs-lookup"><span data-stu-id="96f67-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="96f67-108">创建一份`ICorDebugEnum`对象。</span><span class="sxs-lookup"><span data-stu-id="96f67-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="96f67-109">GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="96f67-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="96f67-110">枚举中获取项的数目。</span><span class="sxs-lookup"><span data-stu-id="96f67-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="96f67-111">Reset 方法</span><span class="sxs-lookup"><span data-stu-id="96f67-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="96f67-112">将光标移到枚举的开头。</span><span class="sxs-lookup"><span data-stu-id="96f67-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="96f67-113">Skip 方法</span><span class="sxs-lookup"><span data-stu-id="96f67-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="96f67-114">将光标向前移动在枚举中指定数目的项。</span><span class="sxs-lookup"><span data-stu-id="96f67-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96f67-115">备注</span><span class="sxs-lookup"><span data-stu-id="96f67-115">Remarks</span></span>  
 <span data-ttu-id="96f67-116">以下枚举器派生自`ICorDebugEnum`:</span><span class="sxs-lookup"><span data-stu-id="96f67-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
-   <span data-ttu-id="96f67-117">"ICorDebugAppDomainEnum"</span><span class="sxs-lookup"><span data-stu-id="96f67-117">"ICorDebugAppDomainEnum"</span></span>  
  
-   <span data-ttu-id="96f67-118">"ICorDebugAssemblyEnum"</span><span class="sxs-lookup"><span data-stu-id="96f67-118">"ICorDebugAssemblyEnum"</span></span>  
  
-   [<span data-ttu-id="96f67-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="96f67-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
-   <span data-ttu-id="96f67-120">"ICorDebugBreakpointEnum"</span><span class="sxs-lookup"><span data-stu-id="96f67-120">"ICorDebugBreakpointEnum"</span></span>  
  
-   <span data-ttu-id="96f67-121">"ICorDebugChainEnum"</span><span class="sxs-lookup"><span data-stu-id="96f67-121">"ICorDebugChainEnum"</span></span>  
  
-   <span data-ttu-id="96f67-122">"ICorDebugCodeEnum"</span><span class="sxs-lookup"><span data-stu-id="96f67-122">"ICorDebugCodeEnum"</span></span>  
  
-   <span data-ttu-id="96f67-123">"ICorDebugErrorInfoEnum"</span><span class="sxs-lookup"><span data-stu-id="96f67-123">"ICorDebugErrorInfoEnum"</span></span>  
  
-   [<span data-ttu-id="96f67-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="96f67-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
-   <span data-ttu-id="96f67-125">"ICorDebugFrameEnum"</span><span class="sxs-lookup"><span data-stu-id="96f67-125">"ICorDebugFrameEnum"</span></span>  
  
-   [<span data-ttu-id="96f67-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="96f67-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
-   [<span data-ttu-id="96f67-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="96f67-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
-   [<span data-ttu-id="96f67-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="96f67-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
-   [<span data-ttu-id="96f67-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="96f67-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
-   <span data-ttu-id="96f67-130">"ICorDebugModuleEnum"</span><span class="sxs-lookup"><span data-stu-id="96f67-130">"ICorDebugModuleEnum"</span></span>  
  
-   <span data-ttu-id="96f67-131">"ICorDebugObjectEnum"</span><span class="sxs-lookup"><span data-stu-id="96f67-131">"ICorDebugObjectEnum"</span></span>  
  
-   <span data-ttu-id="96f67-132">"ICorDebugProcessEnum"</span><span class="sxs-lookup"><span data-stu-id="96f67-132">"ICorDebugProcessEnum"</span></span>  
  
-   <span data-ttu-id="96f67-133">"ICorDebugStepperEnum"</span><span class="sxs-lookup"><span data-stu-id="96f67-133">"ICorDebugStepperEnum"</span></span>  
  
-   <span data-ttu-id="96f67-134">"ICorDebugThreadEnum"</span><span class="sxs-lookup"><span data-stu-id="96f67-134">"ICorDebugThreadEnum"</span></span>  
  
-   <span data-ttu-id="96f67-135">"ICorDebugTypeEnum"</span><span class="sxs-lookup"><span data-stu-id="96f67-135">"ICorDebugTypeEnum"</span></span>  
  
-   <span data-ttu-id="96f67-136">"ICorDebugValueEnum"</span><span class="sxs-lookup"><span data-stu-id="96f67-136">"ICorDebugValueEnum"</span></span>  
  
-   [<span data-ttu-id="96f67-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="96f67-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="96f67-138">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="96f67-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96f67-139">惠?</span><span class="sxs-lookup"><span data-stu-id="96f67-139">Requirements</span></span>  
 <span data-ttu-id="96f67-140">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="96f67-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96f67-141">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96f67-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96f67-142">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96f67-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96f67-143">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96f67-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96f67-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="96f67-144">See Also</span></span>  
 [<span data-ttu-id="96f67-145">调试接口</span><span class="sxs-lookup"><span data-stu-id="96f67-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
