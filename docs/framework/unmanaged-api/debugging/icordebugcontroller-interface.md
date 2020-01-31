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
ms.openlocfilehash: d6c923f03309da3ad8092ea6119e7d850120ee2c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783808"
---
# <a name="icordebugcontroller-interface"></a><span data-ttu-id="8c592-102">ICorDebugController 接口</span><span class="sxs-lookup"><span data-stu-id="8c592-102">ICorDebugController Interface</span></span>

<span data-ttu-id="8c592-103">表示可以控制代码执行上下文的 <xref:System.Diagnostics.Process> 或 <xref:System.AppDomain> 范围。</span><span class="sxs-lookup"><span data-stu-id="8c592-103">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8c592-104">方法</span><span class="sxs-lookup"><span data-stu-id="8c592-104">Methods</span></span>  
  
|<span data-ttu-id="8c592-105">方法</span><span class="sxs-lookup"><span data-stu-id="8c592-105">Method</span></span>|<span data-ttu-id="8c592-106">描述</span><span class="sxs-lookup"><span data-stu-id="8c592-106">Description</span></span>|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|<span data-ttu-id="8c592-107">此方法已过时。</span><span class="sxs-lookup"><span data-stu-id="8c592-107">This method is obsolete.</span></span>|  
|`ICorDebugController::CommitChanges`|<span data-ttu-id="8c592-108">此方法已过时。</span><span class="sxs-lookup"><span data-stu-id="8c592-108">This method is obsolete.</span></span>|  
|[<span data-ttu-id="8c592-109">Continue 方法</span><span class="sxs-lookup"><span data-stu-id="8c592-109">Continue Method</span></span>](icordebugcontroller-continue-method.md)|<span data-ttu-id="8c592-110">调用[ICorDebugController：： Stop](icordebugcontroller-stop-method.md)后，继续执行托管线程。</span><span class="sxs-lookup"><span data-stu-id="8c592-110">Resumes execution of managed threads after a call to [ICorDebugController::Stop](icordebugcontroller-stop-method.md).</span></span>|  
|[<span data-ttu-id="8c592-111">Detach 方法</span><span class="sxs-lookup"><span data-stu-id="8c592-111">Detach Method</span></span>](icordebugcontroller-detach-method.md)|<span data-ttu-id="8c592-112">将调试器与进程或应用程序域分离。</span><span class="sxs-lookup"><span data-stu-id="8c592-112">Detaches the debugger from the process or application domain.</span></span>|  
|[<span data-ttu-id="8c592-113">EnumerateThreads 方法</span><span class="sxs-lookup"><span data-stu-id="8c592-113">EnumerateThreads Method</span></span>](icordebugcontroller-enumeratethreads-method.md)|<span data-ttu-id="8c592-114">获取进程中活动托管线程的枚举器。</span><span class="sxs-lookup"><span data-stu-id="8c592-114">Gets an enumerator for the active managed threads in the process.</span></span>|  
|[<span data-ttu-id="8c592-115">HasQueuedCallbacks 方法</span><span class="sxs-lookup"><span data-stu-id="8c592-115">HasQueuedCallbacks Method</span></span>](icordebugcontroller-hasqueuedcallbacks-method.md)|<span data-ttu-id="8c592-116">获取一个值，该值指示当前是否为指定线程排队任何托管回调。</span><span class="sxs-lookup"><span data-stu-id="8c592-116">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>|  
|[<span data-ttu-id="8c592-117">IsRunning 方法</span><span class="sxs-lookup"><span data-stu-id="8c592-117">IsRunning Method</span></span>](icordebugcontroller-isrunning-method.md)|<span data-ttu-id="8c592-118">获取一个值，该值指示进程中的线程当前是否可以自由运行。</span><span class="sxs-lookup"><span data-stu-id="8c592-118">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>|  
|[<span data-ttu-id="8c592-119">SetAllThreadsDebugState 方法</span><span class="sxs-lookup"><span data-stu-id="8c592-119">SetAllThreadsDebugState Method</span></span>](icordebugcontroller-setallthreadsdebugstate-method.md)|<span data-ttu-id="8c592-120">设置进程中所有托管线程的调试状态。</span><span class="sxs-lookup"><span data-stu-id="8c592-120">Sets the debug state of all managed threads in the process.</span></span>|  
|[<span data-ttu-id="8c592-121">Stop 方法</span><span class="sxs-lookup"><span data-stu-id="8c592-121">Stop Method</span></span>](icordebugcontroller-stop-method.md)|<span data-ttu-id="8c592-122">在进程中运行托管代码的所有线程上执行协作停止。</span><span class="sxs-lookup"><span data-stu-id="8c592-122">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>|  
|[<span data-ttu-id="8c592-123">Terminate 方法</span><span class="sxs-lookup"><span data-stu-id="8c592-123">Terminate Method</span></span>](icordebugcontroller-terminate-method.md)|<span data-ttu-id="8c592-124">用指定的退出代码终止进程。</span><span class="sxs-lookup"><span data-stu-id="8c592-124">Terminates the process with the specified exit code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c592-125">备注</span><span class="sxs-lookup"><span data-stu-id="8c592-125">Remarks</span></span>  
 <span data-ttu-id="8c592-126">如果 `ICorDebugController` 正在控制某个进程，则该范围将包括该进程的所有线程。</span><span class="sxs-lookup"><span data-stu-id="8c592-126">If `ICorDebugController` is controlling a process, the scope includes all threads of the process.</span></span> <span data-ttu-id="8c592-127">如果 `ICorDebugController` 正在控制某个应用程序域，则该作用域只包含该特定应用程序域的线程。</span><span class="sxs-lookup"><span data-stu-id="8c592-127">If `ICorDebugController` is controlling an application domain, the scope includes only the threads of that particular application domain.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8c592-128">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="8c592-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c592-129">需求</span><span class="sxs-lookup"><span data-stu-id="8c592-129">Requirements</span></span>  
 <span data-ttu-id="8c592-130">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8c592-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c592-131">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c592-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c592-132">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c592-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c592-133">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c592-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c592-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c592-134">See also</span></span>

- [<span data-ttu-id="8c592-135">调试接口</span><span class="sxs-lookup"><span data-stu-id="8c592-135">Debugging Interfaces</span></span>](debugging-interfaces.md)
