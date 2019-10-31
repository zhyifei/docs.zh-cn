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
ms.openlocfilehash: 59dcb7ae6f27f8d049cd4dc2d313f7f1130fc503
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085267"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="19cb6-102">ICorDebugEnum 接口</span><span class="sxs-lookup"><span data-stu-id="19cb6-102">ICorDebugEnum Interface</span></span>

<span data-ttu-id="19cb6-103">用作调试应用程序所使用的枚举器的抽象基接口。</span><span class="sxs-lookup"><span data-stu-id="19cb6-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="19cb6-104">方法</span><span class="sxs-lookup"><span data-stu-id="19cb6-104">Methods</span></span>  
  
|<span data-ttu-id="19cb6-105">方法</span><span class="sxs-lookup"><span data-stu-id="19cb6-105">Method</span></span>|<span data-ttu-id="19cb6-106">描述</span><span class="sxs-lookup"><span data-stu-id="19cb6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="19cb6-107">Clone 方法</span><span class="sxs-lookup"><span data-stu-id="19cb6-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="19cb6-108">创建此 `ICorDebugEnum` 对象的副本。</span><span class="sxs-lookup"><span data-stu-id="19cb6-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="19cb6-109">GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="19cb6-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="19cb6-110">获取枚举中的项数。</span><span class="sxs-lookup"><span data-stu-id="19cb6-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="19cb6-111">Reset 方法</span><span class="sxs-lookup"><span data-stu-id="19cb6-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="19cb6-112">将光标移到枚举的开头。</span><span class="sxs-lookup"><span data-stu-id="19cb6-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="19cb6-113">Skip 方法</span><span class="sxs-lookup"><span data-stu-id="19cb6-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="19cb6-114">按指定的项数在枚举中向前移动光标。</span><span class="sxs-lookup"><span data-stu-id="19cb6-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19cb6-115">备注</span><span class="sxs-lookup"><span data-stu-id="19cb6-115">Remarks</span></span>  
 <span data-ttu-id="19cb6-116">以下枚举器派生自 `ICorDebugEnum`：</span><span class="sxs-lookup"><span data-stu-id="19cb6-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
- <span data-ttu-id="19cb6-117">ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="19cb6-117">"ICorDebugAppDomainEnum"</span></span>  
  
- <span data-ttu-id="19cb6-118">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="19cb6-118">"ICorDebugAssemblyEnum"</span></span>  
  
- [<span data-ttu-id="19cb6-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="19cb6-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
- <span data-ttu-id="19cb6-120">ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="19cb6-120">"ICorDebugBreakpointEnum"</span></span>  
  
- <span data-ttu-id="19cb6-121">ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="19cb6-121">"ICorDebugChainEnum"</span></span>  
  
- <span data-ttu-id="19cb6-122">ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="19cb6-122">"ICorDebugCodeEnum"</span></span>  
  
- <span data-ttu-id="19cb6-123">ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="19cb6-123">"ICorDebugErrorInfoEnum"</span></span>  
  
- [<span data-ttu-id="19cb6-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="19cb6-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
- <span data-ttu-id="19cb6-125">ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="19cb6-125">"ICorDebugFrameEnum"</span></span>  
  
- [<span data-ttu-id="19cb6-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="19cb6-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
- [<span data-ttu-id="19cb6-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="19cb6-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
- [<span data-ttu-id="19cb6-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="19cb6-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
- [<span data-ttu-id="19cb6-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="19cb6-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
- <span data-ttu-id="19cb6-130">ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="19cb6-130">"ICorDebugModuleEnum"</span></span>  
  
- <span data-ttu-id="19cb6-131">ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="19cb6-131">"ICorDebugObjectEnum"</span></span>  
  
- <span data-ttu-id="19cb6-132">ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="19cb6-132">"ICorDebugProcessEnum"</span></span>  
  
- <span data-ttu-id="19cb6-133">ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="19cb6-133">"ICorDebugStepperEnum"</span></span>  
  
- <span data-ttu-id="19cb6-134">ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="19cb6-134">"ICorDebugThreadEnum"</span></span>  
  
- <span data-ttu-id="19cb6-135">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="19cb6-135">"ICorDebugTypeEnum"</span></span>  
  
- <span data-ttu-id="19cb6-136">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="19cb6-136">"ICorDebugValueEnum"</span></span>  
  
- [<span data-ttu-id="19cb6-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="19cb6-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="19cb6-138">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="19cb6-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19cb6-139">要求</span><span class="sxs-lookup"><span data-stu-id="19cb6-139">Requirements</span></span>  
 <span data-ttu-id="19cb6-140">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="19cb6-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19cb6-141">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19cb6-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19cb6-142">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19cb6-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19cb6-143">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19cb6-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19cb6-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="19cb6-144">See also</span></span>

- [<span data-ttu-id="19cb6-145">调试接口</span><span class="sxs-lookup"><span data-stu-id="19cb6-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
