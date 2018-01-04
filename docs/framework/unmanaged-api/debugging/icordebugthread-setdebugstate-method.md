---
title: "ICorDebugThread::SetDebugState 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.SetDebugState
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::SetDebugState
helpviewer_keywords:
- ICorDebugThread::SetDebugState method [.NET Framework debugging]
- SetDebugState method [.NET Framework debugging]
ms.assetid: 6382bdf6-d488-4952-b653-cb09b6e1c6c2
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f2754caf11f89358b3e81e6324835d5b2e12f17e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadsetdebugstate-method"></a><span data-ttu-id="33e92-102">ICorDebugThread::SetDebugState 方法</span><span class="sxs-lookup"><span data-stu-id="33e92-102">ICorDebugThread::SetDebugState Method</span></span>
<span data-ttu-id="33e92-103">设置描述此 ICorDebugThread 调试状态的标志。</span><span class="sxs-lookup"><span data-stu-id="33e92-103">Sets flags that describe the debugging state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33e92-104">语法</span><span class="sxs-lookup"><span data-stu-id="33e92-104">Syntax</span></span>  
  
```  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="33e92-105">参数</span><span class="sxs-lookup"><span data-stu-id="33e92-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="33e92-106">[in]指定此线程调试状态的 CorDebugThreadState 枚举值的按位组合。</span><span class="sxs-lookup"><span data-stu-id="33e92-106">[in] A bitwise combination of CorDebugThreadState enumeration values that specify the debugging state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33e92-107">备注</span><span class="sxs-lookup"><span data-stu-id="33e92-107">Remarks</span></span>  
 <span data-ttu-id="33e92-108">`SetDebugState`设置线程的当前的调试状态。</span><span class="sxs-lookup"><span data-stu-id="33e92-108">`SetDebugState` sets the current debug state of the thread.</span></span> <span data-ttu-id="33e92-109">（"当前调试状态"表示调试状态进程是否必须继续进行，不会在实际当前状态。）此标准的值是 THREAD_RUNNING。</span><span class="sxs-lookup"><span data-stu-id="33e92-109">(The "current debug state" represents the debug state if the process were to be continued, not the actual current state.) The normal value for this is THREAD_RUNNING.</span></span> <span data-ttu-id="33e92-110">只有调试器可能会影响线程调试状态。</span><span class="sxs-lookup"><span data-stu-id="33e92-110">Only the debugger can affect the debug state of a thread.</span></span> <span data-ttu-id="33e92-111">调试状态执行上一次跨仍然存在，因此如果你想要保留的线程通过多个 thread_suspend 继续，你可以设置一次和以后便不必担心。</span><span class="sxs-lookup"><span data-stu-id="33e92-111">Debug states do last across continues, so if you want to keep a thread THREAD_SUSPENDed over multiple continues, you can set it once and thereafter not have to worry about it.</span></span> <span data-ttu-id="33e92-112">挂起线程和继续执行该过程可能会导致死锁，尽管通常可能性很小。</span><span class="sxs-lookup"><span data-stu-id="33e92-112">Suspending threads and resuming the process can cause deadlocks, though it's usually unlikely.</span></span> <span data-ttu-id="33e92-113">这是一种固有的质量的线程和进程，按设计。</span><span class="sxs-lookup"><span data-stu-id="33e92-113">This is an intrinsic quality of threads and processes and is by-design.</span></span> <span data-ttu-id="33e92-114">调试器可以以异步方式中断和继续线程，以中断死锁。</span><span class="sxs-lookup"><span data-stu-id="33e92-114">A debugger can asynchronously break and resume the threads to break the deadlock.</span></span> <span data-ttu-id="33e92-115">如果线程的用户状态包括 USER_UNSAFE_POINT，该线程可能会阻止垃圾回收 (GC)。</span><span class="sxs-lookup"><span data-stu-id="33e92-115">If the thread's user state includes USER_UNSAFE_POINT, then the thread may block a garbage collection (GC).</span></span> <span data-ttu-id="33e92-116">这意味着挂起的线程具有更高版本可能导致死锁。</span><span class="sxs-lookup"><span data-stu-id="33e92-116">This means the suspended thread has a much higher chance of causing a deadlock.</span></span> <span data-ttu-id="33e92-117">这可能会影响的调试事件已排入队列。</span><span class="sxs-lookup"><span data-stu-id="33e92-117">This may not affect debug events already queued.</span></span> <span data-ttu-id="33e92-118">因此，调试器应耗尽整个事件队列 (通过调用[icordebugcontroller:: Hasqueuedcallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) 之前暂停或恢复线程。</span><span class="sxs-lookup"><span data-stu-id="33e92-118">Thus a debugger should drain the entire event queue (by calling [ICorDebugController::HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) before suspending or resuming threads.</span></span> <span data-ttu-id="33e92-119">否则，它可能认为它已有挂起的线程上获取事件。</span><span class="sxs-lookup"><span data-stu-id="33e92-119">Else it may get events on a thread that it believes it has already suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33e92-120">惠?</span><span class="sxs-lookup"><span data-stu-id="33e92-120">Requirements</span></span>  
 <span data-ttu-id="33e92-121">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="33e92-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33e92-122">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33e92-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33e92-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33e92-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33e92-124">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33e92-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
