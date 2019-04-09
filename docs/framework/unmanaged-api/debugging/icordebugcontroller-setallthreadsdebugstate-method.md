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
ms.openlocfilehash: 280dc3f0271d7326fe4c22b813abebfd4d45c89e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138471"
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a><span data-ttu-id="9a43f-102">ICorDebugController::SetAllThreadsDebugState 方法</span><span class="sxs-lookup"><span data-stu-id="9a43f-102">ICorDebugController::SetAllThreadsDebugState Method</span></span>
<span data-ttu-id="9a43f-103">设置过程中的所有托管线程的调试状态。</span><span class="sxs-lookup"><span data-stu-id="9a43f-103">Sets the debug state of all managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a43f-104">语法</span><span class="sxs-lookup"><span data-stu-id="9a43f-104">Syntax</span></span>  
  
```  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a43f-105">参数</span><span class="sxs-lookup"><span data-stu-id="9a43f-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="9a43f-106">[in]指定用于调试线程的状态为"CorDebugThreadState"枚举的值。</span><span class="sxs-lookup"><span data-stu-id="9a43f-106">[in] A value of the "CorDebugThreadState" enumeration that specifies the state of the thread for debugging.</span></span>  
  
 `pExceptThisThread`  
 <span data-ttu-id="9a43f-107">[in]一个指向一个"ICorDebugThread"对象，表示线程调试状态设置也如此。</span><span class="sxs-lookup"><span data-stu-id="9a43f-107">[in] A pointer to an "ICorDebugThread" object that represents a thread to be exempted from the debug state setting.</span></span> <span data-ttu-id="9a43f-108">如果此值为 null，不受任何线程。</span><span class="sxs-lookup"><span data-stu-id="9a43f-108">If this value is null, no thread is exempted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a43f-109">备注</span><span class="sxs-lookup"><span data-stu-id="9a43f-109">Remarks</span></span>  
 <span data-ttu-id="9a43f-110">`SetAllThreadsDebugState`方法可能会影响线程不可见通过[EnumerateThreads 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)，因此与挂起的线程`SetAllThreadsDebugState`方法将需要使用恢复`SetAllThreadsDebugState`方法。</span><span class="sxs-lookup"><span data-stu-id="9a43f-110">The `SetAllThreadsDebugState` method may affect threads that are not visible via [EnumerateThreads Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), so threads that were suspended with the `SetAllThreadsDebugState` method will need to be resumed with the `SetAllThreadsDebugState` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a43f-111">要求</span><span class="sxs-lookup"><span data-stu-id="9a43f-111">Requirements</span></span>  
 <span data-ttu-id="9a43f-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9a43f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a43f-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a43f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a43f-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a43f-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="9a43f-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="9a43f-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9a43f-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a43f-116">See also</span></span>
