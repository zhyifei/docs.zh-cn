---
title: "ICorDebugController::SetAllThreadsDebugState 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.SetAllThreadsDebugState
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::SetAllThreadsDebugState
helpviewer_keywords:
- SetAllThreadsDebugState method [.NET Framework debugging]
- ICorDebugController::SetAllThreadsDebugState method [.NET Framework debugging]
ms.assetid: bdda4bd7-4743-4d58-a22b-8067e967db95
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d5a033ef2efd8fa5e3b519e19b62ce2dfb84a5e2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a><span data-ttu-id="c0799-102">ICorDebugController::SetAllThreadsDebugState 方法</span><span class="sxs-lookup"><span data-stu-id="c0799-102">ICorDebugController::SetAllThreadsDebugState Method</span></span>
<span data-ttu-id="c0799-103">设置进程中的所有托管线程调试状态。</span><span class="sxs-lookup"><span data-stu-id="c0799-103">Sets the debug state of all managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0799-104">语法</span><span class="sxs-lookup"><span data-stu-id="c0799-104">Syntax</span></span>  
  
```  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c0799-105">参数</span><span class="sxs-lookup"><span data-stu-id="c0799-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="c0799-106">[in]指定用于调试线程的状态"CorDebugThreadState"枚举的值。</span><span class="sxs-lookup"><span data-stu-id="c0799-106">[in] A value of the "CorDebugThreadState" enumeration that specifies the state of the thread for debugging.</span></span>  
  
 `pExceptThisThread`  
 <span data-ttu-id="c0799-107">[in]指向一个表示线程调试状态设置从免除"ICorDebugThread"对象的指针。</span><span class="sxs-lookup"><span data-stu-id="c0799-107">[in] A pointer to an "ICorDebugThread" object that represents a thread to be exempted from the debug state setting.</span></span> <span data-ttu-id="c0799-108">如果此值为 null，则无需对线程被免除。</span><span class="sxs-lookup"><span data-stu-id="c0799-108">If this value is null, no thread is exempted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0799-109">备注</span><span class="sxs-lookup"><span data-stu-id="c0799-109">Remarks</span></span>  
 <span data-ttu-id="c0799-110">`SetAllThreadsDebugState`方法可能会影响不能通过显示的线程[EnumerateThreads 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)，因此与挂起的线程`SetAllThreadsDebugState`方法需要继续执行，但是`SetAllThreadsDebugState`方法。</span><span class="sxs-lookup"><span data-stu-id="c0799-110">The `SetAllThreadsDebugState` method may affect threads that are not visible via [EnumerateThreads Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), so threads that were suspended with the `SetAllThreadsDebugState` method will need to be resumed with the `SetAllThreadsDebugState` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0799-111">要求</span><span class="sxs-lookup"><span data-stu-id="c0799-111">Requirements</span></span>  
 <span data-ttu-id="c0799-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c0799-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0799-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0799-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0799-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0799-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0799-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0799-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0799-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c0799-116">See Also</span></span>  
 
