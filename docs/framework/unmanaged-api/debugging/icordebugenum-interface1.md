---
title: ICorDebugEnum 接口
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9afaeebfdb98a404ea53b0b5ec147f8c8104e14d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148806"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="8f244-102">ICorDebugEnum 接口</span><span class="sxs-lookup"><span data-stu-id="8f244-102">ICorDebugEnum Interface</span></span>

<span data-ttu-id="8f244-103">调试应用程序所使用的枚举数作为抽象的基接口。</span><span class="sxs-lookup"><span data-stu-id="8f244-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8f244-104">方法</span><span class="sxs-lookup"><span data-stu-id="8f244-104">Methods</span></span>  
  
|<span data-ttu-id="8f244-105">方法</span><span class="sxs-lookup"><span data-stu-id="8f244-105">Method</span></span>|<span data-ttu-id="8f244-106">描述</span><span class="sxs-lookup"><span data-stu-id="8f244-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8f244-107">Clone 方法</span><span class="sxs-lookup"><span data-stu-id="8f244-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="8f244-108">创建一份`ICorDebugEnum`对象。</span><span class="sxs-lookup"><span data-stu-id="8f244-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="8f244-109">GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="8f244-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="8f244-110">枚举中获取项的数目。</span><span class="sxs-lookup"><span data-stu-id="8f244-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="8f244-111">Reset 方法</span><span class="sxs-lookup"><span data-stu-id="8f244-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="8f244-112">将光标移到枚举的开头。</span><span class="sxs-lookup"><span data-stu-id="8f244-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="8f244-113">Skip 方法</span><span class="sxs-lookup"><span data-stu-id="8f244-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="8f244-114">将光标向前移动在枚举中指定数目的项。</span><span class="sxs-lookup"><span data-stu-id="8f244-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f244-115">备注</span><span class="sxs-lookup"><span data-stu-id="8f244-115">Remarks</span></span>  
 <span data-ttu-id="8f244-116">派生自以下枚举器`ICorDebugEnum`:</span><span class="sxs-lookup"><span data-stu-id="8f244-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
-   <span data-ttu-id="8f244-117">"ICorDebugAppDomainEnum"</span><span class="sxs-lookup"><span data-stu-id="8f244-117">"ICorDebugAppDomainEnum"</span></span>  
  
-   <span data-ttu-id="8f244-118">"ICorDebugAssemblyEnum"</span><span class="sxs-lookup"><span data-stu-id="8f244-118">"ICorDebugAssemblyEnum"</span></span>  
  
-   [<span data-ttu-id="8f244-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="8f244-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
-   <span data-ttu-id="8f244-120">"ICorDebugBreakpointEnum"</span><span class="sxs-lookup"><span data-stu-id="8f244-120">"ICorDebugBreakpointEnum"</span></span>  
  
-   <span data-ttu-id="8f244-121">"ICorDebugChainEnum"</span><span class="sxs-lookup"><span data-stu-id="8f244-121">"ICorDebugChainEnum"</span></span>  
  
-   <span data-ttu-id="8f244-122">"ICorDebugCodeEnum"</span><span class="sxs-lookup"><span data-stu-id="8f244-122">"ICorDebugCodeEnum"</span></span>  
  
-   <span data-ttu-id="8f244-123">"ICorDebugErrorInfoEnum"</span><span class="sxs-lookup"><span data-stu-id="8f244-123">"ICorDebugErrorInfoEnum"</span></span>  
  
-   [<span data-ttu-id="8f244-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="8f244-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
-   <span data-ttu-id="8f244-125">"ICorDebugFrameEnum"</span><span class="sxs-lookup"><span data-stu-id="8f244-125">"ICorDebugFrameEnum"</span></span>  
  
-   [<span data-ttu-id="8f244-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="8f244-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
-   [<span data-ttu-id="8f244-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="8f244-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
-   [<span data-ttu-id="8f244-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="8f244-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
-   [<span data-ttu-id="8f244-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="8f244-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
-   <span data-ttu-id="8f244-130">"ICorDebugModuleEnum"</span><span class="sxs-lookup"><span data-stu-id="8f244-130">"ICorDebugModuleEnum"</span></span>  
  
-   <span data-ttu-id="8f244-131">"ICorDebugObjectEnum"</span><span class="sxs-lookup"><span data-stu-id="8f244-131">"ICorDebugObjectEnum"</span></span>  
  
-   <span data-ttu-id="8f244-132">"ICorDebugProcessEnum"</span><span class="sxs-lookup"><span data-stu-id="8f244-132">"ICorDebugProcessEnum"</span></span>  
  
-   <span data-ttu-id="8f244-133">"ICorDebugStepperEnum"</span><span class="sxs-lookup"><span data-stu-id="8f244-133">"ICorDebugStepperEnum"</span></span>  
  
-   <span data-ttu-id="8f244-134">"ICorDebugThreadEnum"</span><span class="sxs-lookup"><span data-stu-id="8f244-134">"ICorDebugThreadEnum"</span></span>  
  
-   <span data-ttu-id="8f244-135">"ICorDebugTypeEnum"</span><span class="sxs-lookup"><span data-stu-id="8f244-135">"ICorDebugTypeEnum"</span></span>  
  
-   <span data-ttu-id="8f244-136">"ICorDebugValueEnum"</span><span class="sxs-lookup"><span data-stu-id="8f244-136">"ICorDebugValueEnum"</span></span>  
  
-   [<span data-ttu-id="8f244-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="8f244-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="8f244-138">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="8f244-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f244-139">要求</span><span class="sxs-lookup"><span data-stu-id="8f244-139">Requirements</span></span>  
 <span data-ttu-id="8f244-140">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8f244-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f244-141">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f244-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f244-142">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f244-142">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8f244-143">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="8f244-143">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8f244-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f244-144">See also</span></span>

- [<span data-ttu-id="8f244-145">调试接口</span><span class="sxs-lookup"><span data-stu-id="8f244-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
