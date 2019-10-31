---
title: ICorDebugThread::SetDebugState 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread.SetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::SetDebugState
helpviewer_keywords:
- ICorDebugThread::SetDebugState method [.NET Framework debugging]
- SetDebugState method [.NET Framework debugging]
ms.assetid: 6382bdf6-d488-4952-b653-cb09b6e1c6c2
topic_type:
- apiref
ms.openlocfilehash: 1b2f3feca15bb8add17c9fe70805347b7c6a48ca
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133420"
---
# <a name="icordebugthreadsetdebugstate-method"></a><span data-ttu-id="4a7ea-102">ICorDebugThread::SetDebugState 方法</span><span class="sxs-lookup"><span data-stu-id="4a7ea-102">ICorDebugThread::SetDebugState Method</span></span>
<span data-ttu-id="4a7ea-103">设置描述此 ICorDebugThread 的调试状态的标志。</span><span class="sxs-lookup"><span data-stu-id="4a7ea-103">Sets flags that describe the debugging state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a7ea-104">语法</span><span class="sxs-lookup"><span data-stu-id="4a7ea-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a7ea-105">参数</span><span class="sxs-lookup"><span data-stu-id="4a7ea-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="4a7ea-106">中CorDebugThreadState 枚举值的按位组合，用于指定此线程的调试状态。</span><span class="sxs-lookup"><span data-stu-id="4a7ea-106">[in] A bitwise combination of CorDebugThreadState enumeration values that specify the debugging state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a7ea-107">备注</span><span class="sxs-lookup"><span data-stu-id="4a7ea-107">Remarks</span></span>  
 <span data-ttu-id="4a7ea-108">`SetDebugState` 设置线程的当前调试状态。</span><span class="sxs-lookup"><span data-stu-id="4a7ea-108">`SetDebugState` sets the current debug state of the thread.</span></span> <span data-ttu-id="4a7ea-109">（如果进程继续，则为 "当前调试状态"，而不是实际的当前状态。）此值的正常值为 THREAD_RUN。</span><span class="sxs-lookup"><span data-stu-id="4a7ea-109">(The "current debug state" represents the debug state if the process were to be continued, not the actual current state.) The normal value for this is THREAD_RUN.</span></span> <span data-ttu-id="4a7ea-110">只有调试器才能影响线程的调试状态。</span><span class="sxs-lookup"><span data-stu-id="4a7ea-110">Only the debugger can affect the debug state of a thread.</span></span> <span data-ttu-id="4a7ea-111">调试状态完成最后一步，因此，如果想要使线程 THREAD_SUSPENDed 在多个继续，则可以将其设置一次，此后不必担心。</span><span class="sxs-lookup"><span data-stu-id="4a7ea-111">Debug states do last across continues, so if you want to keep a thread THREAD_SUSPENDed over multiple continues, you can set it once and thereafter not have to worry about it.</span></span> <span data-ttu-id="4a7ea-112">挂起线程并恢复进程可能会导致死锁，但通常不太可能。</span><span class="sxs-lookup"><span data-stu-id="4a7ea-112">Suspending threads and resuming the process can cause deadlocks, though it's usually unlikely.</span></span> <span data-ttu-id="4a7ea-113">这是线程和进程的内部质量，并按设计进行。</span><span class="sxs-lookup"><span data-stu-id="4a7ea-113">This is an intrinsic quality of threads and processes and is by-design.</span></span> <span data-ttu-id="4a7ea-114">调试器可以异步中断和恢复线程以中断死锁。</span><span class="sxs-lookup"><span data-stu-id="4a7ea-114">A debugger can asynchronously break and resume the threads to break the deadlock.</span></span> <span data-ttu-id="4a7ea-115">如果线程的用户状态包括 USER_UNSAFE_POINT，则线程可能会阻止垃圾回收（GC）。</span><span class="sxs-lookup"><span data-stu-id="4a7ea-115">If the thread's user state includes USER_UNSAFE_POINT, then the thread may block a garbage collection (GC).</span></span> <span data-ttu-id="4a7ea-116">这意味着暂停的线程可能会导致死锁。</span><span class="sxs-lookup"><span data-stu-id="4a7ea-116">This means the suspended thread has a much higher chance of causing a deadlock.</span></span> <span data-ttu-id="4a7ea-117">这不会影响已排队的调试事件。</span><span class="sxs-lookup"><span data-stu-id="4a7ea-117">This may not affect debug events already queued.</span></span> <span data-ttu-id="4a7ea-118">因此，在挂起或恢复线程之前，调试程序应释放整个事件队列（通过调用[ICorDebugController：： HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)）。</span><span class="sxs-lookup"><span data-stu-id="4a7ea-118">Thus a debugger should drain the entire event queue (by calling [ICorDebugController::HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) before suspending or resuming threads.</span></span> <span data-ttu-id="4a7ea-119">否则，它可能会在其认为已挂起的线程上获取事件。</span><span class="sxs-lookup"><span data-stu-id="4a7ea-119">Else it may get events on a thread that it believes it has already suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a7ea-120">要求</span><span class="sxs-lookup"><span data-stu-id="4a7ea-120">Requirements</span></span>  
 <span data-ttu-id="4a7ea-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4a7ea-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a7ea-122">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a7ea-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a7ea-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a7ea-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a7ea-124">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a7ea-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
