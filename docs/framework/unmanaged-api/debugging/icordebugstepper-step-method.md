---
title: ICorDebugStepper::Step 方法
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Step
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Step
helpviewer_keywords:
- Step method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::Step method [.NET Framework debugging]
ms.assetid: 38c1940b-ada1-40ba-8295-4c0833744e1e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2d282e27ec5068fa6fe7f58ba95458fdc219972
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugstepperstep-method"></a><span data-ttu-id="e87df-102">ICorDebugStepper::Step 方法</span><span class="sxs-lookup"><span data-stu-id="e87df-102">ICorDebugStepper::Step Method</span></span>
<span data-ttu-id="e87df-103">导致到单步执行其包含的线程，以及 （可选） 为此 ICorDebugStepper 继续单步执行通过该线程中调用的函数。</span><span class="sxs-lookup"><span data-stu-id="e87df-103">Causes this ICorDebugStepper to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e87df-104">语法</span><span class="sxs-lookup"><span data-stu-id="e87df-104">Syntax</span></span>  
  
```  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e87df-105">参数</span><span class="sxs-lookup"><span data-stu-id="e87df-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="e87df-106">[in]设置为`true`以单步执行线程中调用的函数。</span><span class="sxs-lookup"><span data-stu-id="e87df-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="e87df-107">设置为`false`以单步执行函数。</span><span class="sxs-lookup"><span data-stu-id="e87df-107">Set to `false` to step over the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e87df-108">备注</span><span class="sxs-lookup"><span data-stu-id="e87df-108">Remarks</span></span>  
 <span data-ttu-id="e87df-109">步骤完成时公共语言运行时执行此分档帧中的下一步的托管的指令。</span><span class="sxs-lookup"><span data-stu-id="e87df-109">The step completes when the common language runtime performs the next managed instruction in this stepper's frame.</span></span> <span data-ttu-id="e87df-110">如果`Step`是在分档器上调用，这不是在托管代码中，该步骤将完成时由线程执行的下一个托管的代码指令。</span><span class="sxs-lookup"><span data-stu-id="e87df-110">If `Step` is called on a stepper, which is not in managed code, the step will complete when the next managed code instruction is executed by the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e87df-111">要求</span><span class="sxs-lookup"><span data-stu-id="e87df-111">Requirements</span></span>  
 <span data-ttu-id="e87df-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e87df-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e87df-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e87df-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e87df-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e87df-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e87df-115">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e87df-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
