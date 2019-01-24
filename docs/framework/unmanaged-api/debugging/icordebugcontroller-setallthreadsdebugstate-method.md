---
title: ICorDebugController::SetAllThreadsDebugState 方法
ms.date: 03/30/2017
api_name:
- ICorDebugController.SetAllThreadsDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::SetAllThreadsDebugState
helpviewer_keywords:
- SetAllThreadsDebugState method [.NET Framework debugging]
- ICorDebugController::SetAllThreadsDebugState method [.NET Framework debugging]
ms.assetid: bdda4bd7-4743-4d58-a22b-8067e967db95
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8d14deae1923e2904818fc01ffa3665fdf5ea6c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710568"
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a><span data-ttu-id="9d5e8-102">ICorDebugController::SetAllThreadsDebugState 方法</span><span class="sxs-lookup"><span data-stu-id="9d5e8-102">ICorDebugController::SetAllThreadsDebugState Method</span></span>
<span data-ttu-id="9d5e8-103">设置过程中的所有托管线程的调试状态。</span><span class="sxs-lookup"><span data-stu-id="9d5e8-103">Sets the debug state of all managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d5e8-104">语法</span><span class="sxs-lookup"><span data-stu-id="9d5e8-104">Syntax</span></span>  
  
```  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9d5e8-105">参数</span><span class="sxs-lookup"><span data-stu-id="9d5e8-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="9d5e8-106">[in]指定用于调试线程的状态为"CorDebugThreadState"枚举的值。</span><span class="sxs-lookup"><span data-stu-id="9d5e8-106">[in] A value of the "CorDebugThreadState" enumeration that specifies the state of the thread for debugging.</span></span>  
  
 `pExceptThisThread`  
 <span data-ttu-id="9d5e8-107">[in]一个指向一个"ICorDebugThread"对象，表示线程调试状态设置也如此。</span><span class="sxs-lookup"><span data-stu-id="9d5e8-107">[in] A pointer to an "ICorDebugThread" object that represents a thread to be exempted from the debug state setting.</span></span> <span data-ttu-id="9d5e8-108">如果此值为 null，不受任何线程。</span><span class="sxs-lookup"><span data-stu-id="9d5e8-108">If this value is null, no thread is exempted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d5e8-109">备注</span><span class="sxs-lookup"><span data-stu-id="9d5e8-109">Remarks</span></span>  
 <span data-ttu-id="9d5e8-110">`SetAllThreadsDebugState`方法可能会影响线程不可见通过[EnumerateThreads 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)，因此与挂起的线程`SetAllThreadsDebugState`方法将需要使用恢复`SetAllThreadsDebugState`方法。</span><span class="sxs-lookup"><span data-stu-id="9d5e8-110">The `SetAllThreadsDebugState` method may affect threads that are not visible via [EnumerateThreads Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), so threads that were suspended with the `SetAllThreadsDebugState` method will need to be resumed with the `SetAllThreadsDebugState` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d5e8-111">要求</span><span class="sxs-lookup"><span data-stu-id="9d5e8-111">Requirements</span></span>  
 <span data-ttu-id="9d5e8-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9d5e8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d5e8-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d5e8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d5e8-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d5e8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d5e8-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d5e8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d5e8-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d5e8-116">See also</span></span>

