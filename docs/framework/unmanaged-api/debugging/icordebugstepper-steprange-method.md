---
title: "ICorDebugStepper::StepRange 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.StepRange
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::StepRange
helpviewer_keywords:
- StepRange method [.NET Framework debugging]
- ICorDebugStepper::StepRange method [.NET Framework debugging]
ms.assetid: b9776112-6e6d-4708-892a-8873db02e16f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a02efe1b701506cc3de695c5b79d5e9c84b25b8f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsteppersteprange-method"></a><span data-ttu-id="94fb6-102">ICorDebugStepper::StepRange 方法</span><span class="sxs-lookup"><span data-stu-id="94fb6-102">ICorDebugStepper::StepRange Method</span></span>
<span data-ttu-id="94fb6-103">导致此 ICorDebugStepper 到单步执行其包含的线程，并返回在到达超出指定范围的最后一个代码时。</span><span class="sxs-lookup"><span data-stu-id="94fb6-103">Causes this ICorDebugStepper to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94fb6-104">语法</span><span class="sxs-lookup"><span data-stu-id="94fb6-104">Syntax</span></span>  
  
```  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="94fb6-105">参数</span><span class="sxs-lookup"><span data-stu-id="94fb6-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="94fb6-106">[in]设置为`true`以单步执行线程中调用的函数。</span><span class="sxs-lookup"><span data-stu-id="94fb6-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="94fb6-107">设置为`false`以单步执行函数。</span><span class="sxs-lookup"><span data-stu-id="94fb6-107">Set to `false` to step over the function.</span></span>  
  
 `ranges`  
 <span data-ttu-id="94fb6-108">[in]COR_DEBUG_STEP_RANGE 结构数组，其中每个指定的范围。</span><span class="sxs-lookup"><span data-stu-id="94fb6-108">[in] An array of COR_DEBUG_STEP_RANGE structures, each of which specifies a range.</span></span>  
  
 `cRangeCount`  
 <span data-ttu-id="94fb6-109">[in] `ranges` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="94fb6-109">[in] The size of the `ranges` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94fb6-110">备注</span><span class="sxs-lookup"><span data-stu-id="94fb6-110">Remarks</span></span>  
 <span data-ttu-id="94fb6-111">`StepRange`方法的工作原理类似[icordebugstepper:: Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)达到方法，只不过它给定范围之外的代码之前，无法完成。</span><span class="sxs-lookup"><span data-stu-id="94fb6-111">The `StepRange` method works like the [ICorDebugStepper::Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) method, except that it does not complete until code outside the given range is reached.</span></span>  
  
 <span data-ttu-id="94fb6-112">这可能比单步执行一次一条指令更高效。</span><span class="sxs-lookup"><span data-stu-id="94fb6-112">This can be more efficient than stepping one instruction at a time.</span></span> <span data-ttu-id="94fb6-113">范围被指定为从单步调试器的帧的开头的偏移量对的列表。</span><span class="sxs-lookup"><span data-stu-id="94fb6-113">Ranges are specified as a list of offset pairs from the start of the stepper's frame.</span></span>  
  
 <span data-ttu-id="94fb6-114">范围都是方法的相对于 Microsoft 中间语言 (MSIL) 代码。</span><span class="sxs-lookup"><span data-stu-id="94fb6-114">Ranges are relative to the Microsoft intermediate language (MSIL) code of a method.</span></span> <span data-ttu-id="94fb6-115">调用[icordebugstepper:: Setrangeil](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)与`false`以便相对于本机代码的方法的范围。</span><span class="sxs-lookup"><span data-stu-id="94fb6-115">Call [ICorDebugStepper::SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) with `false` to make the ranges relative to the native code of a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94fb6-116">惠?</span><span class="sxs-lookup"><span data-stu-id="94fb6-116">Requirements</span></span>  
 <span data-ttu-id="94fb6-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="94fb6-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94fb6-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94fb6-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94fb6-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94fb6-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94fb6-120">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94fb6-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
