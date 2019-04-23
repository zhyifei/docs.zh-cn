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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce6ad24e5e670db21d3a6942ab4650a68ae44568
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59102684"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a><span data-ttu-id="77a5e-102">ICorDebugController::HasQueuedCallbacks 方法</span><span class="sxs-lookup"><span data-stu-id="77a5e-102">ICorDebugController::HasQueuedCallbacks Method</span></span>
<span data-ttu-id="77a5e-103">获取一个值，该值指示是否为指定的线程当前正在排队任何托管的回调。</span><span class="sxs-lookup"><span data-stu-id="77a5e-103">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77a5e-104">语法</span><span class="sxs-lookup"><span data-stu-id="77a5e-104">Syntax</span></span>  
  
```  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77a5e-105">参数</span><span class="sxs-lookup"><span data-stu-id="77a5e-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="77a5e-106">[in]指向一个"ICorDebugThread"对象，表示在线程的指针。</span><span class="sxs-lookup"><span data-stu-id="77a5e-106">[in] A pointer to an "ICorDebugThread" object that represents the thread.</span></span>  
  
 `pbQueued`  
 <span data-ttu-id="77a5e-107">[out]指向一个值，则该值`true`如果任何托管的回调当前都是对指定线程排队; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="77a5e-107">[out] A pointer to a value that is `true` if any managed callbacks are currently queued for the specified thread; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="77a5e-108">如果为指定 null`pThread`参数，`HasQueuedCallbacks`将返回`true`托管的回调如果当前排队等待任何线程。</span><span class="sxs-lookup"><span data-stu-id="77a5e-108">If null is specified for the `pThread` parameter, `HasQueuedCallbacks` will return `true` if there are currently managed callbacks queued for any thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77a5e-109">备注</span><span class="sxs-lookup"><span data-stu-id="77a5e-109">Remarks</span></span>  
 <span data-ttu-id="77a5e-110">回调将是一次，每次执行一个调度[icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)调用。</span><span class="sxs-lookup"><span data-stu-id="77a5e-110">Callbacks will be dispatched one at a time, each time [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called.</span></span> <span data-ttu-id="77a5e-111">如果它想要报告同时发生的多个调试事件，则调试器可以检查此标志。</span><span class="sxs-lookup"><span data-stu-id="77a5e-111">The debugger can check this flag if it wants to report multiple debugging events that occur simultaneously.</span></span>  
  
 <span data-ttu-id="77a5e-112">调试事件排队时，它们已发生了，因此调试器必须清空的调试对象的状态以确保整个队列。</span><span class="sxs-lookup"><span data-stu-id="77a5e-112">When debugging events are queued, they have already occurred, so the debugger must drain the entire queue to be sure of the state of the debuggee.</span></span> <span data-ttu-id="77a5e-113">(调用`ICorDebugController::Continue`以清空队列。)例如，如果队列中包含两个线程上的调试事件*X*，调试器将暂停线程*X*后第一个调试事件，然后调用`ICorDebugController::Continue`，调试的第二个事件线程*X*将被调度，尽管线程被挂起。</span><span class="sxs-lookup"><span data-stu-id="77a5e-113">(Call `ICorDebugController::Continue` to drain the queue.) For example, if the queue contains two debugging events on thread *X*, and the debugger suspends thread *X* after the first debugging event and then calls `ICorDebugController::Continue`, the second debugging event for thread *X* will be dispatched although the thread has been suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77a5e-114">要求</span><span class="sxs-lookup"><span data-stu-id="77a5e-114">Requirements</span></span>  
 <span data-ttu-id="77a5e-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="77a5e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77a5e-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77a5e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77a5e-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77a5e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77a5e-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77a5e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77a5e-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="77a5e-119">See also</span></span>
