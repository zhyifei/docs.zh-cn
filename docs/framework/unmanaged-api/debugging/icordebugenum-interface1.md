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
ms.openlocfilehash: b25c47e101ad0fb8e8cbdbb2718a41c9be6c0c22
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931987"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="e6273-102">ICorDebugEnum 接口</span><span class="sxs-lookup"><span data-stu-id="e6273-102">ICorDebugEnum Interface</span></span>

<span data-ttu-id="e6273-103">用作调试应用程序所使用的枚举器的抽象基接口。</span><span class="sxs-lookup"><span data-stu-id="e6273-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e6273-104">方法</span><span class="sxs-lookup"><span data-stu-id="e6273-104">Methods</span></span>  
  
|<span data-ttu-id="e6273-105">方法</span><span class="sxs-lookup"><span data-stu-id="e6273-105">Method</span></span>|<span data-ttu-id="e6273-106">描述</span><span class="sxs-lookup"><span data-stu-id="e6273-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e6273-107">Clone 方法</span><span class="sxs-lookup"><span data-stu-id="e6273-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="e6273-108">创建此`ICorDebugEnum`对象的副本。</span><span class="sxs-lookup"><span data-stu-id="e6273-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="e6273-109">GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="e6273-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="e6273-110">获取枚举中的项数。</span><span class="sxs-lookup"><span data-stu-id="e6273-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="e6273-111">Reset 方法</span><span class="sxs-lookup"><span data-stu-id="e6273-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="e6273-112">将光标移到枚举的开头。</span><span class="sxs-lookup"><span data-stu-id="e6273-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="e6273-113">Skip 方法</span><span class="sxs-lookup"><span data-stu-id="e6273-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="e6273-114">按指定的项数在枚举中向前移动光标。</span><span class="sxs-lookup"><span data-stu-id="e6273-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6273-115">备注</span><span class="sxs-lookup"><span data-stu-id="e6273-115">Remarks</span></span>  
 <span data-ttu-id="e6273-116">以下枚举器派生自`ICorDebugEnum`:</span><span class="sxs-lookup"><span data-stu-id="e6273-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
- <span data-ttu-id="e6273-117">ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="e6273-117">"ICorDebugAppDomainEnum"</span></span>  
  
- <span data-ttu-id="e6273-118">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="e6273-118">"ICorDebugAssemblyEnum"</span></span>  
  
- [<span data-ttu-id="e6273-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="e6273-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
- <span data-ttu-id="e6273-120">ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="e6273-120">"ICorDebugBreakpointEnum"</span></span>  
  
- <span data-ttu-id="e6273-121">ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="e6273-121">"ICorDebugChainEnum"</span></span>  
  
- <span data-ttu-id="e6273-122">ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="e6273-122">"ICorDebugCodeEnum"</span></span>  
  
- <span data-ttu-id="e6273-123">ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="e6273-123">"ICorDebugErrorInfoEnum"</span></span>  
  
- [<span data-ttu-id="e6273-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="e6273-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
- <span data-ttu-id="e6273-125">ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="e6273-125">"ICorDebugFrameEnum"</span></span>  
  
- [<span data-ttu-id="e6273-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="e6273-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
- [<span data-ttu-id="e6273-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="e6273-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
- [<span data-ttu-id="e6273-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="e6273-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
- [<span data-ttu-id="e6273-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="e6273-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
- <span data-ttu-id="e6273-130">ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="e6273-130">"ICorDebugModuleEnum"</span></span>  
  
- <span data-ttu-id="e6273-131">ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="e6273-131">"ICorDebugObjectEnum"</span></span>  
  
- <span data-ttu-id="e6273-132">ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="e6273-132">"ICorDebugProcessEnum"</span></span>  
  
- <span data-ttu-id="e6273-133">ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="e6273-133">"ICorDebugStepperEnum"</span></span>  
  
- <span data-ttu-id="e6273-134">ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="e6273-134">"ICorDebugThreadEnum"</span></span>  
  
- <span data-ttu-id="e6273-135">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="e6273-135">"ICorDebugTypeEnum"</span></span>  
  
- <span data-ttu-id="e6273-136">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="e6273-136">"ICorDebugValueEnum"</span></span>  
  
- [<span data-ttu-id="e6273-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="e6273-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="e6273-138">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="e6273-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6273-139">要求</span><span class="sxs-lookup"><span data-stu-id="e6273-139">Requirements</span></span>  
 <span data-ttu-id="e6273-140">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e6273-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6273-141">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="e6273-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6273-142">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6273-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6273-143">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6273-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6273-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6273-144">See also</span></span>

- [<span data-ttu-id="e6273-145">调试接口</span><span class="sxs-lookup"><span data-stu-id="e6273-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
