---
title: ICorDebugStepper::SetInterceptMask 方法
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetInterceptMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetInterceptMask
helpviewer_keywords:
- SetInterceptMask method [.NET Framework debugging]
- ICorDebugStepper::SetInterceptMask method [.NET Framework debugging]
ms.assetid: 6245e2ae-5cc2-43ff-8cc1-71953d12113a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25a9d287e6520f1fc7826d85dfbcd8e9a6da22f7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481052"
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="f9483-102">ICorDebugStepper::SetInterceptMask 方法</span><span class="sxs-lookup"><span data-stu-id="f9483-102">ICorDebugStepper::SetInterceptMask Method</span></span>
<span data-ttu-id="f9483-103">设置一个值，指定的单步执行代码的类型。</span><span class="sxs-lookup"><span data-stu-id="f9483-103">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9483-104">语法</span><span class="sxs-lookup"><span data-stu-id="f9483-104">Syntax</span></span>  
  
```  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9483-105">参数</span><span class="sxs-lookup"><span data-stu-id="f9483-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="f9483-106">[in]CorDebugIntercept 枚举用于指定代码的类型的值的组合。</span><span class="sxs-lookup"><span data-stu-id="f9483-106">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9483-107">备注</span><span class="sxs-lookup"><span data-stu-id="f9483-107">Remarks</span></span>  
 <span data-ttu-id="f9483-108">如果设置了拦截器位，则遇到给定的类型的拦截代码时将完成分档器。</span><span class="sxs-lookup"><span data-stu-id="f9483-108">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="f9483-109">如果清除了位，则将跳过截取代码。</span><span class="sxs-lookup"><span data-stu-id="f9483-109">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="f9483-110">`SetInterceptMask`方法有与无法预见的交互[icordebugstepper:: Setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) （从用户的角度来看）。</span><span class="sxs-lookup"><span data-stu-id="f9483-110">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="f9483-111">例如，如果仅可见 (即，非内部) 类初始化代码部分中的缺少映射信息，STOP_NO_MAPPING_INFO 未设置 (请参阅[icordebugstepper:: Setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)方法和CorDebugUnmappedStop 枚举），分档器将逐过程类初始化。</span><span class="sxs-lookup"><span data-stu-id="f9483-111">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="f9483-112">默认情况下，仅的 INTERCEPT_NONE 值`CorDebugIntercept`将使用枚举。</span><span class="sxs-lookup"><span data-stu-id="f9483-112">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9483-113">要求</span><span class="sxs-lookup"><span data-stu-id="f9483-113">Requirements</span></span>  
 <span data-ttu-id="f9483-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f9483-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9483-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f9483-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f9483-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9483-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9483-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9483-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
