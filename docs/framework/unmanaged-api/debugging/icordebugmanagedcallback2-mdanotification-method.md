---
title: ICorDebugManagedCallback2::MDANotification 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.MDANotification
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::MDANotification
helpviewer_keywords:
- MDANotification method [.NET Framework debugging]
- ICorDebugManagedCallback2::MDANotification method [.NET Framework debugging]
ms.assetid: 93f79627-bd31-4f4f-b95d-46a032a52fe4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 15addd0b35c43945f643386f8983fc14c9312bae
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492330"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a><span data-ttu-id="b9e83-102">ICorDebugManagedCallback2::MDANotification 方法</span><span class="sxs-lookup"><span data-stu-id="b9e83-102">ICorDebugManagedCallback2::MDANotification Method</span></span>
<span data-ttu-id="b9e83-103">提供了执行代码遇到正在调试的应用程序中托管调试助手 (MDA) 的通知。</span><span class="sxs-lookup"><span data-stu-id="b9e83-103">Provides notification that code execution has encountered a managed debugging assistant (MDA) in the application that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9e83-104">语法</span><span class="sxs-lookup"><span data-stu-id="b9e83-104">Syntax</span></span>  
  
```  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9e83-105">参数</span><span class="sxs-lookup"><span data-stu-id="b9e83-105">Parameters</span></span>  
 `pController`  
 <span data-ttu-id="b9e83-106">[in]ICorDebugController 接口公开进程或在其中发生 MDA 的应用程序域的指针。</span><span class="sxs-lookup"><span data-stu-id="b9e83-106">[in] A pointer to an ICorDebugController interface that exposes the process or application domain in which the MDA occurred.</span></span>  
  
 <span data-ttu-id="b9e83-107">调试程序不应造成任何假设控制器是一个进程或应用程序域，但它始终可以查询接口来确定。</span><span class="sxs-lookup"><span data-stu-id="b9e83-107">A debugger should not make any assumptions about whether the controller is a process or an application domain, although it can always query the interface to make a determination.</span></span>  
  
 `pThread`  
 <span data-ttu-id="b9e83-108">[in]指向公开托管的线程在其调试事件发生的 ICorDebugThread 接口的指针。</span><span class="sxs-lookup"><span data-stu-id="b9e83-108">[in] A pointer to an ICorDebugThread interface that exposes the managed thread on which the debug event occurred.</span></span>  
  
 <span data-ttu-id="b9e83-109">如果 MDA 将出现在非托管线程，值`pThread`将为 null。</span><span class="sxs-lookup"><span data-stu-id="b9e83-109">If the MDA occurred on an unmanaged thread, the value of `pThread` will be null.</span></span>  
  
 <span data-ttu-id="b9e83-110">你必须从 MDA 对象本身获取操作系统 (OS) 线程 ID。</span><span class="sxs-lookup"><span data-stu-id="b9e83-110">You must get the operating system (OS) thread ID from the MDA object itself.</span></span>  
  
 `pMDA`  
 <span data-ttu-id="b9e83-111">[in]一个指向[ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)公开 MDA 的信息的接口。</span><span class="sxs-lookup"><span data-stu-id="b9e83-111">[in] A pointer to an [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) interface that exposes the MDA information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9e83-112">备注</span><span class="sxs-lookup"><span data-stu-id="b9e83-112">Remarks</span></span>  
 <span data-ttu-id="b9e83-113">MDA 是启发式警告，无需任何显式调试器操作调用除外[icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)恢复正在调试的应用程序的执行。</span><span class="sxs-lookup"><span data-stu-id="b9e83-113">An MDA is a heuristic warning and does not require any explicit debugger action except for calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to resume execution of the application that is being debugged.</span></span>  
  
 <span data-ttu-id="b9e83-114">公共语言运行时 (CLR) 可以确定哪些 Mda 会触发，以及哪些数据是在任意给定 MDA 在任何时间。</span><span class="sxs-lookup"><span data-stu-id="b9e83-114">The common language runtime (CLR) can determine which MDAs are fired and which data is in any given MDA at any point.</span></span> <span data-ttu-id="b9e83-115">因此，调试器不应生成需要特定的 MDA 模式的任何功能。</span><span class="sxs-lookup"><span data-stu-id="b9e83-115">Therefore, debuggers should not build any functionality requiring specific MDA patterns.</span></span>  
  
 <span data-ttu-id="b9e83-116">可能已排队并触发遇到 MDA 后不久 Mda。</span><span class="sxs-lookup"><span data-stu-id="b9e83-116">MDAs may be queued and fired shortly after the MDA is encountered.</span></span> <span data-ttu-id="b9e83-117">如果运行时需要等待，直到它达到中用于引发 MDA，而不是 MDA 激发，则当它遇到某一安全点，则可能发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="b9e83-117">This could happen if the runtime needs to wait until it reaches a safe point for firing the MDA, instead of firing the MDA when it encounters it.</span></span> <span data-ttu-id="b9e83-118">这还意味着在运行时可能会激发在排队的回调 （类似于"附加"事件操作） 的一组多个 Mda。</span><span class="sxs-lookup"><span data-stu-id="b9e83-118">It also means that the runtime may fire a number of MDAs in a single set of queued callbacks (similar to an "attach" event operation).</span></span>  
  
 <span data-ttu-id="b9e83-119">调试程序应发布到的引用`ICorDebugMDA`后立即从返回的实例`MDANotification`回调，以允许 CLR 回收 MDA 所占用的内存。</span><span class="sxs-lookup"><span data-stu-id="b9e83-119">A debugger should release the reference to an `ICorDebugMDA` instance immediately after returning from the `MDANotification` callback, to allow the CLR to recycle the memory consumed by an MDA.</span></span> <span data-ttu-id="b9e83-120">如果多个 Mda 还将触发，释放实例可能会提高性能。</span><span class="sxs-lookup"><span data-stu-id="b9e83-120">Releasing the instance may improve performance if many MDAs are firing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9e83-121">要求</span><span class="sxs-lookup"><span data-stu-id="b9e83-121">Requirements</span></span>  
 <span data-ttu-id="b9e83-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b9e83-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9e83-123">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9e83-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9e83-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9e83-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9e83-125">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9e83-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9e83-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9e83-126">See also</span></span>
- [<span data-ttu-id="b9e83-127">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="b9e83-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="b9e83-128">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="b9e83-128">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="b9e83-129">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="b9e83-129">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
