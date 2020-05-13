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
ms.openlocfilehash: b040d9454a5a3a0d550bb645953c783357419f73
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379496"
---
# <a name="icordebugsteppersteprange-method"></a><span data-ttu-id="fe568-102">ICorDebugStepper::StepRange 方法</span><span class="sxs-lookup"><span data-stu-id="fe568-102">ICorDebugStepper::StepRange Method</span></span>
<span data-ttu-id="fe568-103">使此 ICorDebugStepper 单步执行其包含线程，并在到达指定范围内的最后一个代码时返回。</span><span class="sxs-lookup"><span data-stu-id="fe568-103">Causes this ICorDebugStepper to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe568-104">语法</span><span class="sxs-lookup"><span data-stu-id="fe568-104">Syntax</span></span>  
  
```cpp  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe568-105">参数</span><span class="sxs-lookup"><span data-stu-id="fe568-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="fe568-106">中设置为 `true` 可单步执行在线程中调用的函数。</span><span class="sxs-lookup"><span data-stu-id="fe568-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="fe568-107">设置为 `false` 以逐过程执行函数。</span><span class="sxs-lookup"><span data-stu-id="fe568-107">Set to `false` to step over the function.</span></span>  
  
 `ranges`  
 <span data-ttu-id="fe568-108">中COR_DEBUG_STEP_RANGE 结构的数组，其中每个结构都指定一个范围。</span><span class="sxs-lookup"><span data-stu-id="fe568-108">[in] An array of COR_DEBUG_STEP_RANGE structures, each of which specifies a range.</span></span>  
  
 `cRangeCount`  
 <span data-ttu-id="fe568-109">[in] `ranges` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="fe568-109">[in] The size of the `ranges` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe568-110">备注</span><span class="sxs-lookup"><span data-stu-id="fe568-110">Remarks</span></span>  
 <span data-ttu-id="fe568-111">`StepRange`方法的工作方式类似于[ICorDebugStepper：： Step](icordebugstepper-step-method.md)方法，但直到到达给定范围之外的代码时才会完成。</span><span class="sxs-lookup"><span data-stu-id="fe568-111">The `StepRange` method works like the [ICorDebugStepper::Step](icordebugstepper-step-method.md) method, except that it does not complete until code outside the given range is reached.</span></span>  
  
 <span data-ttu-id="fe568-112">这比单步执行一次指令更有效。</span><span class="sxs-lookup"><span data-stu-id="fe568-112">This can be more efficient than stepping one instruction at a time.</span></span> <span data-ttu-id="fe568-113">范围指定为自分档器帧开头的偏移量对的列表。</span><span class="sxs-lookup"><span data-stu-id="fe568-113">Ranges are specified as a list of offset pairs from the start of the stepper's frame.</span></span>  
  
 <span data-ttu-id="fe568-114">范围相对于方法的 Microsoft 中间语言（MSIL）代码。</span><span class="sxs-lookup"><span data-stu-id="fe568-114">Ranges are relative to the Microsoft intermediate language (MSIL) code of a method.</span></span> <span data-ttu-id="fe568-115">调用[ICorDebugStepper：： SetRangeIL](icordebugstepper-setrangeil-method.md)以 `false` 使范围相对于方法的本机代码。</span><span class="sxs-lookup"><span data-stu-id="fe568-115">Call [ICorDebugStepper::SetRangeIL](icordebugstepper-setrangeil-method.md) with `false` to make the ranges relative to the native code of a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe568-116">要求</span><span class="sxs-lookup"><span data-stu-id="fe568-116">Requirements</span></span>  
 <span data-ttu-id="fe568-117">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fe568-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe568-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe568-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe568-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe568-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe568-120">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe568-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
