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
ms.openlocfilehash: 21b8bf618e197372e301d5f56e7592c20710014d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791712"
---
# <a name="icordebugsteppersteprange-method"></a><span data-ttu-id="22a5c-102">ICorDebugStepper::StepRange 方法</span><span class="sxs-lookup"><span data-stu-id="22a5c-102">ICorDebugStepper::StepRange Method</span></span>
<span data-ttu-id="22a5c-103">使此 ICorDebugStepper 单步执行其包含线程，并在到达指定范围内的最后一个代码时返回。</span><span class="sxs-lookup"><span data-stu-id="22a5c-103">Causes this ICorDebugStepper to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22a5c-104">语法</span><span class="sxs-lookup"><span data-stu-id="22a5c-104">Syntax</span></span>  
  
```cpp  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22a5c-105">参数</span><span class="sxs-lookup"><span data-stu-id="22a5c-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="22a5c-106">中设置为单步执行在线程中调用的函数的 `true`。</span><span class="sxs-lookup"><span data-stu-id="22a5c-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="22a5c-107">设置为 `false` 以逐过程执行函数。</span><span class="sxs-lookup"><span data-stu-id="22a5c-107">Set to `false` to step over the function.</span></span>  
  
 `ranges`  
 <span data-ttu-id="22a5c-108">中COR_DEBUG_STEP_RANGE 结构的数组，其中每个结构都指定一个范围。</span><span class="sxs-lookup"><span data-stu-id="22a5c-108">[in] An array of COR_DEBUG_STEP_RANGE structures, each of which specifies a range.</span></span>  
  
 `cRangeCount`  
 <span data-ttu-id="22a5c-109">[in] `ranges` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="22a5c-109">[in] The size of the `ranges` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22a5c-110">备注</span><span class="sxs-lookup"><span data-stu-id="22a5c-110">Remarks</span></span>  
 <span data-ttu-id="22a5c-111">`StepRange` 方法的工作方式类似于[ICorDebugStepper：： Step](icordebugstepper-step-method.md)方法，但直到到达给定范围之外的代码时才会完成。</span><span class="sxs-lookup"><span data-stu-id="22a5c-111">The `StepRange` method works like the [ICorDebugStepper::Step](icordebugstepper-step-method.md) method, except that it does not complete until code outside the given range is reached.</span></span>  
  
 <span data-ttu-id="22a5c-112">这比单步执行一次指令更有效。</span><span class="sxs-lookup"><span data-stu-id="22a5c-112">This can be more efficient than stepping one instruction at a time.</span></span> <span data-ttu-id="22a5c-113">范围指定为自分档器帧开头的偏移量对的列表。</span><span class="sxs-lookup"><span data-stu-id="22a5c-113">Ranges are specified as a list of offset pairs from the start of the stepper's frame.</span></span>  
  
 <span data-ttu-id="22a5c-114">范围相对于方法的 Microsoft 中间语言（MSIL）代码。</span><span class="sxs-lookup"><span data-stu-id="22a5c-114">Ranges are relative to the Microsoft intermediate language (MSIL) code of a method.</span></span> <span data-ttu-id="22a5c-115">调用[ICorDebugStepper：： SetRangeIL](icordebugstepper-setrangeil-method.md)与 `false` 以使范围相对于方法的本机代码。</span><span class="sxs-lookup"><span data-stu-id="22a5c-115">Call [ICorDebugStepper::SetRangeIL](icordebugstepper-setrangeil-method.md) with `false` to make the ranges relative to the native code of a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22a5c-116">需求</span><span class="sxs-lookup"><span data-stu-id="22a5c-116">Requirements</span></span>  
 <span data-ttu-id="22a5c-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="22a5c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22a5c-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22a5c-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22a5c-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22a5c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22a5c-120">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22a5c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
