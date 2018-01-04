---
title: "ICorDebugStepper::SetInterceptMask 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.SetInterceptMask
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::SetInterceptMask
helpviewer_keywords:
- SetInterceptMask method [.NET Framework debugging]
- ICorDebugStepper::SetInterceptMask method [.NET Framework debugging]
ms.assetid: 6245e2ae-5cc2-43ff-8cc1-71953d12113a
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3ef03b63c4af79c01ba9962fcc6f106b3141b576
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="90246-102">ICorDebugStepper::SetInterceptMask 方法</span><span class="sxs-lookup"><span data-stu-id="90246-102">ICorDebugStepper::SetInterceptMask Method</span></span>
<span data-ttu-id="90246-103">设置一个值，指定的单步执行代码的类型。</span><span class="sxs-lookup"><span data-stu-id="90246-103">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90246-104">语法</span><span class="sxs-lookup"><span data-stu-id="90246-104">Syntax</span></span>  
  
```  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="90246-105">参数</span><span class="sxs-lookup"><span data-stu-id="90246-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="90246-106">[in]指定的代码类型 CorDebugIntercept 枚举的值的组合。</span><span class="sxs-lookup"><span data-stu-id="90246-106">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90246-107">备注</span><span class="sxs-lookup"><span data-stu-id="90246-107">Remarks</span></span>  
 <span data-ttu-id="90246-108">如果设置了拦截器位，遇到给定的类型的截获代码时，将完成分档器。</span><span class="sxs-lookup"><span data-stu-id="90246-108">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="90246-109">如果位将被清除，则将跳过截获的代码。</span><span class="sxs-lookup"><span data-stu-id="90246-109">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="90246-110">`SetInterceptMask`方法可能具有与出现未预见的交互[icordebugstepper:: Setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) （从用户的角度来看）。</span><span class="sxs-lookup"><span data-stu-id="90246-110">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="90246-111">例如，如果仅可见 (即非内部) 类初始化代码部分中的缺少映射信息，因而 STOP_NO_MAPPING_INFO 未设置 (请参阅[icordebugstepper:: Setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)方法和CorDebugUnmappedStop 枚举） 分档器将逐过程执行类初始化。</span><span class="sxs-lookup"><span data-stu-id="90246-111">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="90246-112">默认情况下，只对 INTERCEPT_NONE 数值`CorDebugIntercept`将使用枚举。</span><span class="sxs-lookup"><span data-stu-id="90246-112">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90246-113">惠?</span><span class="sxs-lookup"><span data-stu-id="90246-113">Requirements</span></span>  
 <span data-ttu-id="90246-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="90246-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90246-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90246-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90246-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90246-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90246-117">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90246-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
