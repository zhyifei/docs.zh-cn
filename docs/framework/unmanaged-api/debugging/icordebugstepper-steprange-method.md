---
title: ICorDebugStepper::StepRange 方法
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepRange
helpviewer_keywords:
- StepRange method [.NET Framework debugging]
- ICorDebugStepper::StepRange method [.NET Framework debugging]
ms.assetid: b9776112-6e6d-4708-892a-8873db02e16f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b18474aeaa79224de5371df3ff0cac5ed9bf4ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994275"
---
# <a name="icordebugsteppersteprange-method"></a><span data-ttu-id="dbb9d-102">ICorDebugStepper::StepRange 方法</span><span class="sxs-lookup"><span data-stu-id="dbb9d-102">ICorDebugStepper::StepRange Method</span></span>
<span data-ttu-id="dbb9d-103">导致此 ICorDebugStepper 单步执行其包含的线程，并返回到达超出指定范围的最后一个代码时。</span><span class="sxs-lookup"><span data-stu-id="dbb9d-103">Causes this ICorDebugStepper to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbb9d-104">语法</span><span class="sxs-lookup"><span data-stu-id="dbb9d-104">Syntax</span></span>  
  
```  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbb9d-105">参数</span><span class="sxs-lookup"><span data-stu-id="dbb9d-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="dbb9d-106">[in]设置为`true`来单步执行的线程内调用的函数。</span><span class="sxs-lookup"><span data-stu-id="dbb9d-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="dbb9d-107">设置为`false`到逐过程执行函数。</span><span class="sxs-lookup"><span data-stu-id="dbb9d-107">Set to `false` to step over the function.</span></span>  
  
 `ranges`  
 <span data-ttu-id="dbb9d-108">[in]COR_DEBUG_STEP_RANGE 结构数组，其中每个指定的范围。</span><span class="sxs-lookup"><span data-stu-id="dbb9d-108">[in] An array of COR_DEBUG_STEP_RANGE structures, each of which specifies a range.</span></span>  
  
 `cRangeCount`  
 <span data-ttu-id="dbb9d-109">[in] `ranges` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="dbb9d-109">[in] The size of the `ranges` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbb9d-110">备注</span><span class="sxs-lookup"><span data-stu-id="dbb9d-110">Remarks</span></span>  
 <span data-ttu-id="dbb9d-111">`StepRange`方法的工作方式类似于[icordebugstepper:: Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)达到方法，只不过它给定范围之外的代码之前，无法完成。</span><span class="sxs-lookup"><span data-stu-id="dbb9d-111">The `StepRange` method works like the [ICorDebugStepper::Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) method, except that it does not complete until code outside the given range is reached.</span></span>  
  
 <span data-ttu-id="dbb9d-112">这可以是单步执行一次一条指令比效率更高。</span><span class="sxs-lookup"><span data-stu-id="dbb9d-112">This can be more efficient than stepping one instruction at a time.</span></span> <span data-ttu-id="dbb9d-113">范围被指定为从一开始单步调试器的帧的偏移量对的列表。</span><span class="sxs-lookup"><span data-stu-id="dbb9d-113">Ranges are specified as a list of offset pairs from the start of the stepper's frame.</span></span>  
  
 <span data-ttu-id="dbb9d-114">范围是相对于一种方法的 Microsoft 中间语言 (MSIL) 代码。</span><span class="sxs-lookup"><span data-stu-id="dbb9d-114">Ranges are relative to the Microsoft intermediate language (MSIL) code of a method.</span></span> <span data-ttu-id="dbb9d-115">调用[icordebugstepper:: Setrangeil](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)与`false`以便相对于一种方法的本机代码的范围。</span><span class="sxs-lookup"><span data-stu-id="dbb9d-115">Call [ICorDebugStepper::SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) with `false` to make the ranges relative to the native code of a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbb9d-116">要求</span><span class="sxs-lookup"><span data-stu-id="dbb9d-116">Requirements</span></span>  
 <span data-ttu-id="dbb9d-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dbb9d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbb9d-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dbb9d-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dbb9d-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbb9d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbb9d-120">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbb9d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
