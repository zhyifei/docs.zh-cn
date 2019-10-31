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
ms.openlocfilehash: ab3819d5c33f090fda1ca9c3dccb5d08ab8f84cc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131464"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a><span data-ttu-id="7dcf5-102">ICorDebugManagedCallback2::MDANotification 方法</span><span class="sxs-lookup"><span data-stu-id="7dcf5-102">ICorDebugManagedCallback2::MDANotification Method</span></span>
<span data-ttu-id="7dcf5-103">提供一些通知，指出代码执行在要调试的应用程序中遇到了托管调试助手（MDA）。</span><span class="sxs-lookup"><span data-stu-id="7dcf5-103">Provides notification that code execution has encountered a managed debugging assistant (MDA) in the application that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dcf5-104">语法</span><span class="sxs-lookup"><span data-stu-id="7dcf5-104">Syntax</span></span>  
  
```cpp  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7dcf5-105">参数</span><span class="sxs-lookup"><span data-stu-id="7dcf5-105">Parameters</span></span>  
 `pController`  
 <span data-ttu-id="7dcf5-106">中指向 ICorDebugController 接口的指针，该接口公开发生 MDA 的进程或应用程序域。</span><span class="sxs-lookup"><span data-stu-id="7dcf5-106">[in] A pointer to an ICorDebugController interface that exposes the process or application domain in which the MDA occurred.</span></span>  
  
 <span data-ttu-id="7dcf5-107">调试器不应对控制器是进程还是应用程序域作出任何假设，尽管它可以始终查询接口来做出决定。</span><span class="sxs-lookup"><span data-stu-id="7dcf5-107">A debugger should not make any assumptions about whether the controller is a process or an application domain, although it can always query the interface to make a determination.</span></span>  
  
 `pThread`  
 <span data-ttu-id="7dcf5-108">中指向 ICorDebugThread 接口的指针，该接口公开发生调试事件的托管线程。</span><span class="sxs-lookup"><span data-stu-id="7dcf5-108">[in] A pointer to an ICorDebugThread interface that exposes the managed thread on which the debug event occurred.</span></span>  
  
 <span data-ttu-id="7dcf5-109">如果在非托管线程上发生 MDA，则 `pThread` 的值将为 null。</span><span class="sxs-lookup"><span data-stu-id="7dcf5-109">If the MDA occurred on an unmanaged thread, the value of `pThread` will be null.</span></span>  
  
 <span data-ttu-id="7dcf5-110">必须从 MDA 对象本身获得操作系统（OS）线程 ID。</span><span class="sxs-lookup"><span data-stu-id="7dcf5-110">You must get the operating system (OS) thread ID from the MDA object itself.</span></span>  
  
 `pMDA`  
 <span data-ttu-id="7dcf5-111">中指向公开 MDA 信息的[ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="7dcf5-111">[in] A pointer to an [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) interface that exposes the MDA information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7dcf5-112">备注</span><span class="sxs-lookup"><span data-stu-id="7dcf5-112">Remarks</span></span>  
 <span data-ttu-id="7dcf5-113">MDA 是启发式警告，不需要任何显式调试器操作，只需调用[ICorDebugController：： Continue 继续](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)执行正在调试的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7dcf5-113">An MDA is a heuristic warning and does not require any explicit debugger action except for calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to resume execution of the application that is being debugged.</span></span>  
  
 <span data-ttu-id="7dcf5-114">公共语言运行时（CLR）可以确定哪些 Mda 被激发，哪些数据在任意时间点处于任意给定的 MDA。</span><span class="sxs-lookup"><span data-stu-id="7dcf5-114">The common language runtime (CLR) can determine which MDAs are fired and which data is in any given MDA at any point.</span></span> <span data-ttu-id="7dcf5-115">因此，调试器不应生成需要特定 MDA 模式的任何功能。</span><span class="sxs-lookup"><span data-stu-id="7dcf5-115">Therefore, debuggers should not build any functionality requiring specific MDA patterns.</span></span>  
  
 <span data-ttu-id="7dcf5-116">Mda 可以排队，并在遇到 MDA 之后立即触发。</span><span class="sxs-lookup"><span data-stu-id="7dcf5-116">MDAs may be queued and fired shortly after the MDA is encountered.</span></span> <span data-ttu-id="7dcf5-117">如果运行时需要等待到一个安全点来激发 MDA，则会发生这种情况，而不是在遇到 MDA 时激发 MDA。</span><span class="sxs-lookup"><span data-stu-id="7dcf5-117">This could happen if the runtime needs to wait until it reaches a safe point for firing the MDA, instead of firing the MDA when it encounters it.</span></span> <span data-ttu-id="7dcf5-118">这也意味着，运行时可能会在一组排队的回调中引发许多 Mda （类似于 "附加" 事件操作）。</span><span class="sxs-lookup"><span data-stu-id="7dcf5-118">It also means that the runtime may fire a number of MDAs in a single set of queued callbacks (similar to an "attach" event operation).</span></span>  
  
 <span data-ttu-id="7dcf5-119">调试器应在从 `MDANotification` 回调返回后立即释放对 `ICorDebugMDA` 实例的引用，以允许 CLR 回收 MDA 使用的内存。</span><span class="sxs-lookup"><span data-stu-id="7dcf5-119">A debugger should release the reference to an `ICorDebugMDA` instance immediately after returning from the `MDANotification` callback, to allow the CLR to recycle the memory consumed by an MDA.</span></span> <span data-ttu-id="7dcf5-120">如果激发多个 Mda，则释放实例可以提高性能。</span><span class="sxs-lookup"><span data-stu-id="7dcf5-120">Releasing the instance may improve performance if many MDAs are firing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7dcf5-121">要求</span><span class="sxs-lookup"><span data-stu-id="7dcf5-121">Requirements</span></span>  
 <span data-ttu-id="7dcf5-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7dcf5-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7dcf5-123">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7dcf5-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7dcf5-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7dcf5-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7dcf5-125">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7dcf5-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dcf5-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="7dcf5-126">See also</span></span>

- [<span data-ttu-id="7dcf5-127">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="7dcf5-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="7dcf5-128">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="7dcf5-128">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="7dcf5-129">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="7dcf5-129">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
