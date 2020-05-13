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
ms.openlocfilehash: aaba751a58e5b23b98b1d0629ea3cc9e1e7a83a9
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379010"
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="dc11b-102">ICorDebugStepper::SetInterceptMask 方法</span><span class="sxs-lookup"><span data-stu-id="dc11b-102">ICorDebugStepper::SetInterceptMask Method</span></span>
<span data-ttu-id="dc11b-103">设置一个值，该值指定要单步执行的代码的类型。</span><span class="sxs-lookup"><span data-stu-id="dc11b-103">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc11b-104">语法</span><span class="sxs-lookup"><span data-stu-id="dc11b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc11b-105">参数</span><span class="sxs-lookup"><span data-stu-id="dc11b-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="dc11b-106">中CorDebugIntercept 枚举的值的组合，用于指定代码的类型。</span><span class="sxs-lookup"><span data-stu-id="dc11b-106">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc11b-107">备注</span><span class="sxs-lookup"><span data-stu-id="dc11b-107">Remarks</span></span>  
 <span data-ttu-id="dc11b-108">如果设置了侦听器的位，则遇到给定类型的截取代码时，分档器将完成。</span><span class="sxs-lookup"><span data-stu-id="dc11b-108">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="dc11b-109">如果清除该位，则将跳过拦截代码。</span><span class="sxs-lookup"><span data-stu-id="dc11b-109">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="dc11b-110">此 `SetInterceptMask` 方法可能与[ICorDebugStepper：： SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) （来自用户的观点）的交互无法预料。</span><span class="sxs-lookup"><span data-stu-id="dc11b-110">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="dc11b-111">例如，如果类初始化代码的唯一可见部分（即非内部）缺少映射信息，并且未设置 STOP_NO_MAPPING_INFO （请参阅[ICorDebugStepper：： SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md)方法和 CorDebugUnmappedStop 枚举），则分档器将逐过程执行类初始化。</span><span class="sxs-lookup"><span data-stu-id="dc11b-111">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="dc11b-112">默认情况下，将只使用枚举的 INTERCEPT_NONE 值 `CorDebugIntercept` 。</span><span class="sxs-lookup"><span data-stu-id="dc11b-112">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc11b-113">要求</span><span class="sxs-lookup"><span data-stu-id="dc11b-113">Requirements</span></span>  
 <span data-ttu-id="dc11b-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dc11b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc11b-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc11b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc11b-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc11b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc11b-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc11b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
