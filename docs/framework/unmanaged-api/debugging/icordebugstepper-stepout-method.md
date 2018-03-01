---
title: "ICorDebugStepper::StepOut 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1d6462f166e9c734dacc7ebee13cb82e3b12158b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="28d42-102">ICorDebugStepper::StepOut 方法</span><span class="sxs-lookup"><span data-stu-id="28d42-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="28d42-103">导致此 ICorDebugStepper 到单步通过其包含线程，而若要完成在当前帧将控制权返回给调用的帧。</span><span class="sxs-lookup"><span data-stu-id="28d42-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28d42-104">语法</span><span class="sxs-lookup"><span data-stu-id="28d42-104">Syntax</span></span>  
  
```  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="28d42-105">备注</span><span class="sxs-lookup"><span data-stu-id="28d42-105">Remarks</span></span>  
 <span data-ttu-id="28d42-106">A`StepOut`操作将在正常情况下从返回当前帧到调用的帧后完成。</span><span class="sxs-lookup"><span data-stu-id="28d42-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="28d42-107">如果`StepOut`时，将调用在非托管代码中，该步骤将完成当前帧返回到调用它的托管代码时。</span><span class="sxs-lookup"><span data-stu-id="28d42-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="28d42-108">在.NET Framework 2.0 版中，请勿使用`StepOut`与 STOP_UNMANAGED 标志设置因为它将失败。</span><span class="sxs-lookup"><span data-stu-id="28d42-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="28d42-109">(使用[icordebugstepper:: Setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)设置为单步执行的标志。)互操作调试程序必须单步执行到本机代码本身。</span><span class="sxs-lookup"><span data-stu-id="28d42-109">(Use [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28d42-110">惠?</span><span class="sxs-lookup"><span data-stu-id="28d42-110">Requirements</span></span>  
 <span data-ttu-id="28d42-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="28d42-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28d42-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28d42-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28d42-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28d42-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28d42-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28d42-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
