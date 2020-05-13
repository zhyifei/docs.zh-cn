---
title: ICorDebugStepper::StepOut 方法
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepOut
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepOut
helpviewer_keywords:
- ICorDebugStepper::StepOut method [.NET Framework debugging]
- StepOut method [.NET Framework debugging]
ms.assetid: aae0f48c-4ede-4256-9251-a7fc85a229dc
topic_type:
- apiref
ms.openlocfilehash: 9f6962f987079da1ccb04ea368307d7c119910a6
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379506"
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="ee1d6-102">ICorDebugStepper::StepOut 方法</span><span class="sxs-lookup"><span data-stu-id="ee1d6-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="ee1d6-103">使此 ICorDebugStepper 单步执行其包含线程，并在当前帧将控件返回到调用帧时完成。</span><span class="sxs-lookup"><span data-stu-id="ee1d6-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee1d6-104">语法</span><span class="sxs-lookup"><span data-stu-id="ee1d6-104">Syntax</span></span>  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="ee1d6-105">备注</span><span class="sxs-lookup"><span data-stu-id="ee1d6-105">Remarks</span></span>  
 <span data-ttu-id="ee1d6-106">`StepOut`操作将在从当前帧正常返回到调用帧后完成。</span><span class="sxs-lookup"><span data-stu-id="ee1d6-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="ee1d6-107">如果 `StepOut` 在非托管代码中调用，则当当前帧返回到调用它的托管代码时，步骤将完成。</span><span class="sxs-lookup"><span data-stu-id="ee1d6-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="ee1d6-108">在 .NET Framework 版本2.0 中，不要将 `StepOut` 与 STOP_UNMANAGED 标志集一起使用，因为它将失败。</span><span class="sxs-lookup"><span data-stu-id="ee1d6-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="ee1d6-109">（使用[ICorDebugStepper：： SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md)设置用于单步执行的标志。）互操作调试器必须自行单步执行到本机代码。</span><span class="sxs-lookup"><span data-stu-id="ee1d6-109">(Use [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee1d6-110">要求</span><span class="sxs-lookup"><span data-stu-id="ee1d6-110">Requirements</span></span>  
 <span data-ttu-id="ee1d6-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ee1d6-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee1d6-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee1d6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee1d6-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee1d6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee1d6-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee1d6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
