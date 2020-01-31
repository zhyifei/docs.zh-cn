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
ms.openlocfilehash: 9792abb4ee38a45aae59eaf79f1f0499539bd2ae
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791770"
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="950d2-102">ICorDebugStepper::SetInterceptMask 方法</span><span class="sxs-lookup"><span data-stu-id="950d2-102">ICorDebugStepper::SetInterceptMask Method</span></span>
<span data-ttu-id="950d2-103">设置一个值，该值指定要单步执行的代码的类型。</span><span class="sxs-lookup"><span data-stu-id="950d2-103">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="950d2-104">语法</span><span class="sxs-lookup"><span data-stu-id="950d2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="950d2-105">参数</span><span class="sxs-lookup"><span data-stu-id="950d2-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="950d2-106">中CorDebugIntercept 枚举的值的组合，用于指定代码的类型。</span><span class="sxs-lookup"><span data-stu-id="950d2-106">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="950d2-107">备注</span><span class="sxs-lookup"><span data-stu-id="950d2-107">Remarks</span></span>  
 <span data-ttu-id="950d2-108">如果设置了侦听器的位，则遇到给定类型的截取代码时，分档器将完成。</span><span class="sxs-lookup"><span data-stu-id="950d2-108">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="950d2-109">如果清除该位，则将跳过拦截代码。</span><span class="sxs-lookup"><span data-stu-id="950d2-109">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="950d2-110">`SetInterceptMask` 方法与[ICorDebugStepper：： SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) （来自用户的观点）之间可能存在不可预见的交互。</span><span class="sxs-lookup"><span data-stu-id="950d2-110">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="950d2-111">例如，如果类初始化代码的唯一可见部分（即非内部）缺少映射信息，并且未设置 STOP_NO_MAPPING_INFO （请参阅[ICorDebugStepper：： SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md)方法和 CorDebugUnmappedStop 枚举），则分档器将逐过程执行类初始化。</span><span class="sxs-lookup"><span data-stu-id="950d2-111">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="950d2-112">默认情况下，只会使用 `CorDebugIntercept` 枚举的 INTERCEPT_NONE 值。</span><span class="sxs-lookup"><span data-stu-id="950d2-112">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="950d2-113">需求</span><span class="sxs-lookup"><span data-stu-id="950d2-113">Requirements</span></span>  
 <span data-ttu-id="950d2-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="950d2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="950d2-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="950d2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="950d2-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="950d2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="950d2-117">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="950d2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
