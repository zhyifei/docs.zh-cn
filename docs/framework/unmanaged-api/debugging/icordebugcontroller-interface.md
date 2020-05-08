---
title: ICorDebugController 接口
ms.date: 03/30/2017
api_name:
- ICorDebugController
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController
helpviewer_keywords:
- ICorDebugController interface [.NET Framework debugging]
ms.assetid: dbb1c4dc-269a-459b-ab1d-6c70788782ce
topic_type:
- apiref
ms.openlocfilehash: e494bbb24e8f2245593e7945625e72e70ae1dde5
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892774"
---
# <a name="icordebugcontroller-interface"></a><span data-ttu-id="c4fe4-102">ICorDebugController 接口</span><span class="sxs-lookup"><span data-stu-id="c4fe4-102">ICorDebugController Interface</span></span>

<span data-ttu-id="c4fe4-103">表示可以控制代码执行上下文的 <xref:System.Diagnostics.Process> 或 <xref:System.AppDomain> 范围。</span><span class="sxs-lookup"><span data-stu-id="c4fe4-103">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c4fe4-104">方法</span><span class="sxs-lookup"><span data-stu-id="c4fe4-104">Methods</span></span>  
  
|<span data-ttu-id="c4fe4-105">方法</span><span class="sxs-lookup"><span data-stu-id="c4fe4-105">Method</span></span>|<span data-ttu-id="c4fe4-106">说明</span><span class="sxs-lookup"><span data-stu-id="c4fe4-106">Description</span></span>|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|<span data-ttu-id="c4fe4-107">此方法已过时。</span><span class="sxs-lookup"><span data-stu-id="c4fe4-107">This method is obsolete.</span></span>|  
|`ICorDebugController::CommitChanges`|<span data-ttu-id="c4fe4-108">此方法已过时。</span><span class="sxs-lookup"><span data-stu-id="c4fe4-108">This method is obsolete.</span></span>|  
|[<span data-ttu-id="c4fe4-109">Continue 方法</span><span class="sxs-lookup"><span data-stu-id="c4fe4-109">Continue Method</span></span>](icordebugcontroller-continue-method.md)|<span data-ttu-id="c4fe4-110">调用[ICorDebugController：： Stop](icordebugcontroller-stop-method.md)后，继续执行托管线程。</span><span class="sxs-lookup"><span data-stu-id="c4fe4-110">Resumes execution of managed threads after a call to [ICorDebugController::Stop](icordebugcontroller-stop-method.md).</span></span>|  
|[<span data-ttu-id="c4fe4-111">Detach 方法</span><span class="sxs-lookup"><span data-stu-id="c4fe4-111">Detach Method</span></span>](icordebugcontroller-detach-method.md)|<span data-ttu-id="c4fe4-112">将调试器与进程或应用程序域分离。</span><span class="sxs-lookup"><span data-stu-id="c4fe4-112">Detaches the debugger from the process or application domain.</span></span>|  
|[<span data-ttu-id="c4fe4-113">EnumerateThreads 方法</span><span class="sxs-lookup"><span data-stu-id="c4fe4-113">EnumerateThreads Method</span></span>](icordebugcontroller-enumeratethreads-method.md)|<span data-ttu-id="c4fe4-114">获取进程中活动托管线程的枚举器。</span><span class="sxs-lookup"><span data-stu-id="c4fe4-114">Gets an enumerator for the active managed threads in the process.</span></span>|  
|[<span data-ttu-id="c4fe4-115">HasQueuedCallbacks 方法</span><span class="sxs-lookup"><span data-stu-id="c4fe4-115">HasQueuedCallbacks Method</span></span>](icordebugcontroller-hasqueuedcallbacks-method.md)|<span data-ttu-id="c4fe4-116">获取一个值，该值指示当前是否为指定线程排队任何托管回调。</span><span class="sxs-lookup"><span data-stu-id="c4fe4-116">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>|  
|[<span data-ttu-id="c4fe4-117">IsRunning 方法</span><span class="sxs-lookup"><span data-stu-id="c4fe4-117">IsRunning Method</span></span>](icordebugcontroller-isrunning-method.md)|<span data-ttu-id="c4fe4-118">获取一个值，该值指示进程中的线程当前是否可以自由运行。</span><span class="sxs-lookup"><span data-stu-id="c4fe4-118">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>|  
|[<span data-ttu-id="c4fe4-119">SetAllThreadsDebugState 方法</span><span class="sxs-lookup"><span data-stu-id="c4fe4-119">SetAllThreadsDebugState Method</span></span>](icordebugcontroller-setallthreadsdebugstate-method.md)|<span data-ttu-id="c4fe4-120">设置进程中所有托管线程的调试状态。</span><span class="sxs-lookup"><span data-stu-id="c4fe4-120">Sets the debug state of all managed threads in the process.</span></span>|  
|[<span data-ttu-id="c4fe4-121">Stop 方法</span><span class="sxs-lookup"><span data-stu-id="c4fe4-121">Stop Method</span></span>](icordebugcontroller-stop-method.md)|<span data-ttu-id="c4fe4-122">在进程中运行托管代码的所有线程上执行协作停止。</span><span class="sxs-lookup"><span data-stu-id="c4fe4-122">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>|  
|[<span data-ttu-id="c4fe4-123">Terminate 方法</span><span class="sxs-lookup"><span data-stu-id="c4fe4-123">Terminate Method</span></span>](icordebugcontroller-terminate-method.md)|<span data-ttu-id="c4fe4-124">用指定的退出代码终止进程。</span><span class="sxs-lookup"><span data-stu-id="c4fe4-124">Terminates the process with the specified exit code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4fe4-125">备注</span><span class="sxs-lookup"><span data-stu-id="c4fe4-125">Remarks</span></span>  
 <span data-ttu-id="c4fe4-126">如果`ICorDebugController`正在控制某个进程，则该范围将包括该进程的所有线程。</span><span class="sxs-lookup"><span data-stu-id="c4fe4-126">If `ICorDebugController` is controlling a process, the scope includes all threads of the process.</span></span> <span data-ttu-id="c4fe4-127">如果`ICorDebugController`正在控制某个应用程序域，则该作用域只包含该特定应用程序域的线程。</span><span class="sxs-lookup"><span data-stu-id="c4fe4-127">If `ICorDebugController` is controlling an application domain, the scope includes only the threads of that particular application domain.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c4fe4-128">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="c4fe4-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4fe4-129">要求</span><span class="sxs-lookup"><span data-stu-id="c4fe4-129">Requirements</span></span>  
 <span data-ttu-id="c4fe4-130">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c4fe4-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4fe4-131">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4fe4-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4fe4-132">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4fe4-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4fe4-133">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4fe4-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4fe4-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4fe4-134">See also</span></span>

- [<span data-ttu-id="c4fe4-135">调试接口</span><span class="sxs-lookup"><span data-stu-id="c4fe4-135">Debugging Interfaces</span></span>](debugging-interfaces.md)
