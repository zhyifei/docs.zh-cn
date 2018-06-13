---
title: ICorDebugController 接口 1
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 230488201b637c5a53f41dd4c3f204b37e8984fd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411465"
---
# <a name="icordebugcontroller-interface1"></a><span data-ttu-id="152bf-102">ICorDebugController 接口 1</span><span class="sxs-lookup"><span data-stu-id="152bf-102">ICorDebugController Interface1</span></span>
<span data-ttu-id="152bf-103">表示可以控制代码执行上下文的 <xref:System.Diagnostics.Process> 或 <xref:System.AppDomain> 范围。</span><span class="sxs-lookup"><span data-stu-id="152bf-103">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="152bf-104">方法</span><span class="sxs-lookup"><span data-stu-id="152bf-104">Methods</span></span>  
  
|<span data-ttu-id="152bf-105">方法</span><span class="sxs-lookup"><span data-stu-id="152bf-105">Method</span></span>|<span data-ttu-id="152bf-106">描述</span><span class="sxs-lookup"><span data-stu-id="152bf-106">Description</span></span>|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|<span data-ttu-id="152bf-107">此方法已过时。</span><span class="sxs-lookup"><span data-stu-id="152bf-107">This method is obsolete.</span></span>|  
|`ICorDebugController::CommitChanges`|<span data-ttu-id="152bf-108">此方法已过时。</span><span class="sxs-lookup"><span data-stu-id="152bf-108">This method is obsolete.</span></span>|  
|[<span data-ttu-id="152bf-109">Continue 方法</span><span class="sxs-lookup"><span data-stu-id="152bf-109">Continue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)|<span data-ttu-id="152bf-110">恢复后调用的托管线程的执行[icordebugcontroller:: Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)。</span><span class="sxs-lookup"><span data-stu-id="152bf-110">Resumes execution of managed threads after a call to [ICorDebugController::Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>|  
|[<span data-ttu-id="152bf-111">Detach 方法</span><span class="sxs-lookup"><span data-stu-id="152bf-111">Detach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-detach-method.md)|<span data-ttu-id="152bf-112">从分离调试器进程或应用程序域。</span><span class="sxs-lookup"><span data-stu-id="152bf-112">Detaches the debugger from the process or application domain.</span></span>|  
|[<span data-ttu-id="152bf-113">EnumerateThreads 方法</span><span class="sxs-lookup"><span data-stu-id="152bf-113">EnumerateThreads Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)|<span data-ttu-id="152bf-114">在过程中获取活动的托管线程的枚举数。</span><span class="sxs-lookup"><span data-stu-id="152bf-114">Gets an enumerator for the active managed threads in the process.</span></span>|  
|[<span data-ttu-id="152bf-115">HasQueuedCallbacks 方法</span><span class="sxs-lookup"><span data-stu-id="152bf-115">HasQueuedCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)|<span data-ttu-id="152bf-116">获取一个值，该值指示是否任何托管的回调当前正在排队等待指定的线程。</span><span class="sxs-lookup"><span data-stu-id="152bf-116">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>|  
|[<span data-ttu-id="152bf-117">IsRunning 方法</span><span class="sxs-lookup"><span data-stu-id="152bf-117">IsRunning Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-isrunning-method.md)|<span data-ttu-id="152bf-118">获取一个值，该值指示是否在进程中的线程当前自由地运行。</span><span class="sxs-lookup"><span data-stu-id="152bf-118">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>|  
|[<span data-ttu-id="152bf-119">SetAllThreadsDebugState 方法</span><span class="sxs-lookup"><span data-stu-id="152bf-119">SetAllThreadsDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)|<span data-ttu-id="152bf-120">设置进程中的所有托管线程调试状态。</span><span class="sxs-lookup"><span data-stu-id="152bf-120">Sets the debug state of all managed threads in the process.</span></span>|  
|[<span data-ttu-id="152bf-121">Stop 方法</span><span class="sxs-lookup"><span data-stu-id="152bf-121">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)|<span data-ttu-id="152bf-122">在进程中运行托管的代码的所有线程上执行协作停止。</span><span class="sxs-lookup"><span data-stu-id="152bf-122">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>|  
|[<span data-ttu-id="152bf-123">Terminate 方法</span><span class="sxs-lookup"><span data-stu-id="152bf-123">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-terminate-method.md)|<span data-ttu-id="152bf-124">终止指定的退出代码的进程。</span><span class="sxs-lookup"><span data-stu-id="152bf-124">Terminates the process with the specified exit code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="152bf-125">备注</span><span class="sxs-lookup"><span data-stu-id="152bf-125">Remarks</span></span>  
 <span data-ttu-id="152bf-126">如果`ICorDebugController`是控制某个进程的作用域包括进程的所有线程。</span><span class="sxs-lookup"><span data-stu-id="152bf-126">If `ICorDebugController` is controlling a process, the scope includes all threads of the process.</span></span> <span data-ttu-id="152bf-127">如果`ICorDebugController`是控制应用程序域的作用域包括仅该特定应用程序域的线程。</span><span class="sxs-lookup"><span data-stu-id="152bf-127">If `ICorDebugController` is controlling an application domain, the scope includes only the threads of that particular application domain.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="152bf-128">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="152bf-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="152bf-129">要求</span><span class="sxs-lookup"><span data-stu-id="152bf-129">Requirements</span></span>  
 <span data-ttu-id="152bf-130">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="152bf-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="152bf-131">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="152bf-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="152bf-132">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="152bf-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="152bf-133">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="152bf-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="152bf-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="152bf-134">See Also</span></span>  
 [<span data-ttu-id="152bf-135">调试接口</span><span class="sxs-lookup"><span data-stu-id="152bf-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
