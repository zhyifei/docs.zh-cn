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
ms.openlocfilehash: c2e8aaa2774e3e2699a73c40804391ca245047b1
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976585"
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a><span data-ttu-id="9ef65-102">ICorDebugController::SetAllThreadsDebugState 方法</span><span class="sxs-lookup"><span data-stu-id="9ef65-102">ICorDebugController::SetAllThreadsDebugState Method</span></span>
<span data-ttu-id="9ef65-103">设置进程中所有托管线程的调试状态。</span><span class="sxs-lookup"><span data-stu-id="9ef65-103">Sets the debug state of all managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ef65-104">语法</span><span class="sxs-lookup"><span data-stu-id="9ef65-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ef65-105">参数</span><span class="sxs-lookup"><span data-stu-id="9ef65-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="9ef65-106">中一个 "CorDebugThreadState" 枚举的值，该值指定线程的状态以进行调试。</span><span class="sxs-lookup"><span data-stu-id="9ef65-106">[in] A value of the "CorDebugThreadState" enumeration that specifies the state of the thread for debugging.</span></span>  
  
 `pExceptThisThread`  
 <span data-ttu-id="9ef65-107">中一个指向 "ICorDebugThread" 对象的指针，该对象表示要从调试状态设置中免除的线程。</span><span class="sxs-lookup"><span data-stu-id="9ef65-107">[in] A pointer to an "ICorDebugThread" object that represents a thread to be exempted from the debug state setting.</span></span> <span data-ttu-id="9ef65-108">如果此值为 null，则不免除任何线程。</span><span class="sxs-lookup"><span data-stu-id="9ef65-108">If this value is null, no thread is exempted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ef65-109">备注</span><span class="sxs-lookup"><span data-stu-id="9ef65-109">Remarks</span></span>  
 <span data-ttu-id="9ef65-110">此`SetAllThreadsDebugState`方法可能会影响通过[EnumerateThreads 方法](icordebugcontroller-enumeratethreads-method.md)不可见的线程，因此，通过`SetAllThreadsDebugState`方法挂起的线程需要通过`SetAllThreadsDebugState`方法恢复。</span><span class="sxs-lookup"><span data-stu-id="9ef65-110">The `SetAllThreadsDebugState` method may affect threads that are not visible via [EnumerateThreads Method](icordebugcontroller-enumeratethreads-method.md), so threads that were suspended with the `SetAllThreadsDebugState` method will need to be resumed with the `SetAllThreadsDebugState` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ef65-111">要求</span><span class="sxs-lookup"><span data-stu-id="9ef65-111">Requirements</span></span>  
 <span data-ttu-id="9ef65-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9ef65-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ef65-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ef65-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ef65-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ef65-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ef65-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ef65-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ef65-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ef65-116">See also</span></span>
