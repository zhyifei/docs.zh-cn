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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f663f5134cf34bf9beb66da20bbb5886baff5415
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987423"
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="9b8fa-102">ICorDebugStepper::StepOut 方法</span><span class="sxs-lookup"><span data-stu-id="9b8fa-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="9b8fa-103">导致此 ICorDebugStepper 单步执行其包含的线程，并完成时的当前帧将控制权返回给调用的帧。</span><span class="sxs-lookup"><span data-stu-id="9b8fa-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b8fa-104">语法</span><span class="sxs-lookup"><span data-stu-id="9b8fa-104">Syntax</span></span>  
  
```  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="9b8fa-105">备注</span><span class="sxs-lookup"><span data-stu-id="9b8fa-105">Remarks</span></span>  
 <span data-ttu-id="9b8fa-106">一个`StepOut`操作将正常返回从当前帧的调用的帧后完成。</span><span class="sxs-lookup"><span data-stu-id="9b8fa-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="9b8fa-107">如果`StepOut`时，将调用在非托管代码中，该步骤完成后，将当前帧返回到调用它的托管代码。</span><span class="sxs-lookup"><span data-stu-id="9b8fa-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="9b8fa-108">在.NET Framework 2.0 版中，不要使用`StepOut`STOP_UNMANAGED 标志集因为这将会失败。</span><span class="sxs-lookup"><span data-stu-id="9b8fa-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="9b8fa-109">(使用[icordebugstepper:: Setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)来设置标志的单步执行。)互操作调试程序必须跳出为本机代码本身。</span><span class="sxs-lookup"><span data-stu-id="9b8fa-109">(Use [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b8fa-110">要求</span><span class="sxs-lookup"><span data-stu-id="9b8fa-110">Requirements</span></span>  
 <span data-ttu-id="9b8fa-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9b8fa-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b8fa-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b8fa-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b8fa-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b8fa-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b8fa-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b8fa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
