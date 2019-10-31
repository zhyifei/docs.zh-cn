---
title: ICorDebugController::HasQueuedCallbacks 方法
ms.date: 03/30/2017
api_name:
- ICorDebugController.HasQueuedCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::HasQueuedCallbacks
helpviewer_keywords:
- HasQueuedCallbacks method [.NET Framework debugging]
- ICorDebugController::HasQueuedCallbacks method [.NET Framework debugging]
ms.assetid: 0d6a1cd9-370b-4462-adbf-e3980e897ea7
topic_type:
- apiref
ms.openlocfilehash: 51ee8b3631bffe9fd7fef4351e0aa67d1cbbe2c9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125389"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a><span data-ttu-id="b6391-102">ICorDebugController::HasQueuedCallbacks 方法</span><span class="sxs-lookup"><span data-stu-id="b6391-102">ICorDebugController::HasQueuedCallbacks Method</span></span>
<span data-ttu-id="b6391-103">获取一个值，该值指示当前是否为指定线程排队任何托管回调。</span><span class="sxs-lookup"><span data-stu-id="b6391-103">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6391-104">语法</span><span class="sxs-lookup"><span data-stu-id="b6391-104">Syntax</span></span>  
  
```cpp  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6391-105">参数</span><span class="sxs-lookup"><span data-stu-id="b6391-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="b6391-106">中指向表示线程的 "ICorDebugThread" 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="b6391-106">[in] A pointer to an "ICorDebugThread" object that represents the thread.</span></span>  
  
 `pbQueued`  
 <span data-ttu-id="b6391-107">弄指向一个值的指针，该值在当前为指定线程排队时 `true` 的值;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="b6391-107">[out] A pointer to a value that is `true` if any managed callbacks are currently queued for the specified thread; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="b6391-108">如果为 `pThread` 参数指定了 null，则如果当前存在托管的回调，则 `HasQueuedCallbacks` 会返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="b6391-108">If null is specified for the `pThread` parameter, `HasQueuedCallbacks` will return `true` if there are currently managed callbacks queued for any thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6391-109">备注</span><span class="sxs-lookup"><span data-stu-id="b6391-109">Remarks</span></span>  
 <span data-ttu-id="b6391-110">每次都将调度一个回调，每次调用[ICorDebugController：： Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) 。</span><span class="sxs-lookup"><span data-stu-id="b6391-110">Callbacks will be dispatched one at a time, each time [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called.</span></span> <span data-ttu-id="b6391-111">如果要报告同时发生的多个调试事件，则调试器可以检查此标志。</span><span class="sxs-lookup"><span data-stu-id="b6391-111">The debugger can check this flag if it wants to report multiple debugging events that occur simultaneously.</span></span>  
  
 <span data-ttu-id="b6391-112">调试事件排队后，它们已发生，因此调试器必须释放整个队列，才能确保调试对象的状态。</span><span class="sxs-lookup"><span data-stu-id="b6391-112">When debugging events are queued, they have already occurred, so the debugger must drain the entire queue to be sure of the state of the debuggee.</span></span> <span data-ttu-id="b6391-113">（调用 `ICorDebugController::Continue` 以排出队列。）例如，如果队列在线程*x*上包含两个调试事件，并且调试器在第一个调试事件之后挂起线程*x* ，然后调用 `ICorDebugController::Continue`，则将调度线程*x*的第二个调试事件，但线程已暂停。</span><span class="sxs-lookup"><span data-stu-id="b6391-113">(Call `ICorDebugController::Continue` to drain the queue.) For example, if the queue contains two debugging events on thread *X*, and the debugger suspends thread *X* after the first debugging event and then calls `ICorDebugController::Continue`, the second debugging event for thread *X* will be dispatched although the thread has been suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6391-114">要求</span><span class="sxs-lookup"><span data-stu-id="b6391-114">Requirements</span></span>  
 <span data-ttu-id="b6391-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b6391-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6391-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6391-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6391-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6391-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6391-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6391-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6391-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="b6391-119">See also</span></span>
