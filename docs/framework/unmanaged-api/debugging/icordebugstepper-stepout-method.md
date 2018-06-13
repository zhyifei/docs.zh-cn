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
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419161"
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="700ff-102">ICorDebugStepper::StepOut 方法</span><span class="sxs-lookup"><span data-stu-id="700ff-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="700ff-103">导致此 ICorDebugStepper 到单步通过其包含线程，而若要完成在当前帧将控制权返回给调用的帧。</span><span class="sxs-lookup"><span data-stu-id="700ff-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="700ff-104">语法</span><span class="sxs-lookup"><span data-stu-id="700ff-104">Syntax</span></span>  
  
```  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="700ff-105">备注</span><span class="sxs-lookup"><span data-stu-id="700ff-105">Remarks</span></span>  
 <span data-ttu-id="700ff-106">A`StepOut`操作将在正常情况下从返回当前帧到调用的帧后完成。</span><span class="sxs-lookup"><span data-stu-id="700ff-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="700ff-107">如果`StepOut`时，将调用在非托管代码中，该步骤将完成当前帧返回到调用它的托管代码时。</span><span class="sxs-lookup"><span data-stu-id="700ff-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="700ff-108">在.NET Framework 2.0 版中，请勿使用`StepOut`与 STOP_UNMANAGED 标志设置因为它将失败。</span><span class="sxs-lookup"><span data-stu-id="700ff-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="700ff-109">(使用[icordebugstepper:: Setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)设置为单步执行的标志。)互操作调试程序必须单步执行到本机代码本身。</span><span class="sxs-lookup"><span data-stu-id="700ff-109">(Use [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="700ff-110">要求</span><span class="sxs-lookup"><span data-stu-id="700ff-110">Requirements</span></span>  
 <span data-ttu-id="700ff-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="700ff-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="700ff-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="700ff-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="700ff-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="700ff-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="700ff-114">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="700ff-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
