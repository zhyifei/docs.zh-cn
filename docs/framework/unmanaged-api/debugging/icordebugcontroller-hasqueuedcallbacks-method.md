---
title: "ICorDebugController::HasQueuedCallbacks 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.HasQueuedCallbacks
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::HasQueuedCallbacks
helpviewer_keywords:
- HasQueuedCallbacks method [.NET Framework debugging]
- ICorDebugController::HasQueuedCallbacks method [.NET Framework debugging]
ms.assetid: 0d6a1cd9-370b-4462-adbf-e3980e897ea7
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 81830cbadcf9fb359b8e1a74cd47f9d18543c29c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a><span data-ttu-id="210a9-102">ICorDebugController::HasQueuedCallbacks 方法</span><span class="sxs-lookup"><span data-stu-id="210a9-102">ICorDebugController::HasQueuedCallbacks Method</span></span>
<span data-ttu-id="210a9-103">获取一个值，该值指示是否任何托管的回调当前正在排队等待指定的线程。</span><span class="sxs-lookup"><span data-stu-id="210a9-103">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="210a9-104">语法</span><span class="sxs-lookup"><span data-stu-id="210a9-104">Syntax</span></span>  
  
```  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="210a9-105">参数</span><span class="sxs-lookup"><span data-stu-id="210a9-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="210a9-106">[in]指向一个表示线程的"ICorDebugThread"对象的指针。</span><span class="sxs-lookup"><span data-stu-id="210a9-106">[in] A pointer to an "ICorDebugThread" object that represents the thread.</span></span>  
  
 `pbQueued`  
 <span data-ttu-id="210a9-107">[out]指向一个值，是`true`如果任何托管的回调目前排队指定线程; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="210a9-107">[out] A pointer to a value that is `true` if any managed callbacks are currently queued for the specified thread; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="210a9-108">如果为指定 null`pThread`参数，`HasQueuedCallbacks`将返回`true`托管的回调如果当前正在排队等待任何线程。</span><span class="sxs-lookup"><span data-stu-id="210a9-108">If null is specified for the `pThread` parameter, `HasQueuedCallbacks` will return `true` if there are currently managed callbacks queued for any thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="210a9-109">备注</span><span class="sxs-lookup"><span data-stu-id="210a9-109">Remarks</span></span>  
 <span data-ttu-id="210a9-110">回调将调度一次一个地，每次[icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)调用。</span><span class="sxs-lookup"><span data-stu-id="210a9-110">Callbacks will be dispatched one at a time, each time [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called.</span></span> <span data-ttu-id="210a9-111">如果想要报告同时发生的多个调试事件，则调试器可以检查此标志。</span><span class="sxs-lookup"><span data-stu-id="210a9-111">The debugger can check this flag if it wants to report multiple debugging events that occur simultaneously.</span></span>  
  
 <span data-ttu-id="210a9-112">调试事件排队时，它们已经发生，因此调试器必须耗尽整个队列，以确保的调试对象的状态。</span><span class="sxs-lookup"><span data-stu-id="210a9-112">When debugging events are queued, they have already occurred, so the debugger must drain the entire queue to be sure of the state of the debuggee.</span></span> <span data-ttu-id="210a9-113">(调用`ICorDebugController::Continue`清空队列。)例如，如果队列中包含两个线程上的调试事件*X*，调试器将暂停线程*X*后第一个调试事件，然后调用`ICorDebugController::Continue`，第二个调试事件线程*X*将进行调度，尽管线程已挂起。</span><span class="sxs-lookup"><span data-stu-id="210a9-113">(Call `ICorDebugController::Continue` to drain the queue.) For example, if the queue contains two debugging events on thread *X*, and the debugger suspends thread *X* after the first debugging event and then calls `ICorDebugController::Continue`, the second debugging event for thread *X* will be dispatched although the thread has been suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="210a9-114">要求</span><span class="sxs-lookup"><span data-stu-id="210a9-114">Requirements</span></span>  
 <span data-ttu-id="210a9-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="210a9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="210a9-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="210a9-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="210a9-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="210a9-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="210a9-118">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="210a9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="210a9-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="210a9-119">See Also</span></span>  
 
