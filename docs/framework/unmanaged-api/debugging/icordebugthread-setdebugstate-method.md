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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d29f5cefd22592fa8949ff5361109c09c0972b24
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499688"
---
# <a name="icordebugthreadsetdebugstate-method"></a><span data-ttu-id="c343e-102">ICorDebugThread::SetDebugState 方法</span><span class="sxs-lookup"><span data-stu-id="c343e-102">ICorDebugThread::SetDebugState Method</span></span>
<span data-ttu-id="c343e-103">设置描述此 ICorDebugThread 的调试状态的标志。</span><span class="sxs-lookup"><span data-stu-id="c343e-103">Sets flags that describe the debugging state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c343e-104">语法</span><span class="sxs-lookup"><span data-stu-id="c343e-104">Syntax</span></span>  
  
```  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c343e-105">参数</span><span class="sxs-lookup"><span data-stu-id="c343e-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="c343e-106">[in]CorDebugThreadState 枚举值，用于指定此线程调试状态的按位组合。</span><span class="sxs-lookup"><span data-stu-id="c343e-106">[in] A bitwise combination of CorDebugThreadState enumeration values that specify the debugging state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c343e-107">备注</span><span class="sxs-lookup"><span data-stu-id="c343e-107">Remarks</span></span>  
 <span data-ttu-id="c343e-108">`SetDebugState` 设置线程的当前调试状态。</span><span class="sxs-lookup"><span data-stu-id="c343e-108">`SetDebugState` sets the current debug state of the thread.</span></span> <span data-ttu-id="c343e-109">（"当前的调试状态"表示的调试状态进程是否要继续，不实际的当前状态。）为此标准的值是 THREAD_RUNNING。</span><span class="sxs-lookup"><span data-stu-id="c343e-109">(The "current debug state" represents the debug state if the process were to be continued, not the actual current state.) The normal value for this is THREAD_RUNNING.</span></span> <span data-ttu-id="c343e-110">仅在调试器可能会影响线程的调试状态。</span><span class="sxs-lookup"><span data-stu-id="c343e-110">Only the debugger can affect the debug state of a thread.</span></span> <span data-ttu-id="c343e-111">调试状态执行上一次之间仍然存在，因此如果你想要保留多个通过 thread_suspend 继续一个线程，你可以设置一次和此后不需要担心。</span><span class="sxs-lookup"><span data-stu-id="c343e-111">Debug states do last across continues, so if you want to keep a thread THREAD_SUSPENDed over multiple continues, you can set it once and thereafter not have to worry about it.</span></span> <span data-ttu-id="c343e-112">挂起线程和继续执行该过程可能会导致死锁，但通常不大可能。</span><span class="sxs-lookup"><span data-stu-id="c343e-112">Suspending threads and resuming the process can cause deadlocks, though it's usually unlikely.</span></span> <span data-ttu-id="c343e-113">这是一种内部函数的质量的线程和进程，按设计。</span><span class="sxs-lookup"><span data-stu-id="c343e-113">This is an intrinsic quality of threads and processes and is by-design.</span></span> <span data-ttu-id="c343e-114">调试程序可以以异步方式中断和恢复来打断死锁的线程。</span><span class="sxs-lookup"><span data-stu-id="c343e-114">A debugger can asynchronously break and resume the threads to break the deadlock.</span></span> <span data-ttu-id="c343e-115">如果线程的用户状态包括 USER_UNSAFE_POINT，线程可能会阻止垃圾回收 (GC)。</span><span class="sxs-lookup"><span data-stu-id="c343e-115">If the thread's user state includes USER_UNSAFE_POINT, then the thread may block a garbage collection (GC).</span></span> <span data-ttu-id="c343e-116">这意味着暂停的线程具有较高可能导致死锁。</span><span class="sxs-lookup"><span data-stu-id="c343e-116">This means the suspended thread has a much higher chance of causing a deadlock.</span></span> <span data-ttu-id="c343e-117">这可能会影响的调试事件已排入队列。</span><span class="sxs-lookup"><span data-stu-id="c343e-117">This may not affect debug events already queued.</span></span> <span data-ttu-id="c343e-118">因此，调试程序应漏整个事件队列 (通过调用[icordebugcontroller:: Hasqueuedcallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) 挂起或恢复线程之前。</span><span class="sxs-lookup"><span data-stu-id="c343e-118">Thus a debugger should drain the entire event queue (by calling [ICorDebugController::HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) before suspending or resuming threads.</span></span> <span data-ttu-id="c343e-119">否则它可能会认为它已经具有挂起的线程上收到事件。</span><span class="sxs-lookup"><span data-stu-id="c343e-119">Else it may get events on a thread that it believes it has already suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c343e-120">要求</span><span class="sxs-lookup"><span data-stu-id="c343e-120">Requirements</span></span>  
 <span data-ttu-id="c343e-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c343e-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c343e-122">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c343e-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c343e-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c343e-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c343e-124">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c343e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
