---
title: "ICLRTask 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask
helpviewer_keywords:
- ICLRTask interface [.NET Framework hosting]
ms.assetid: b3a44df3-578a-4451-b55e-70c8e7695f5e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6fcce85e56abae561b05364a925fdb6b55825669
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtask-interface"></a><span data-ttu-id="a0d5e-102">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="a0d5e-102">ICLRTask Interface</span></span>
<span data-ttu-id="a0d5e-103">提供允许宿主发出请求的公共语言运行时 (CLR)，或者向 CLR 有关关联的任务提供通知的方法。</span><span class="sxs-lookup"><span data-stu-id="a0d5e-103">Provides methods that allow the host to make requests of the common language runtime (CLR), or to provide notification to the CLR about the associated task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a0d5e-104">方法</span><span class="sxs-lookup"><span data-stu-id="a0d5e-104">Methods</span></span>  
  
|<span data-ttu-id="a0d5e-105">方法</span><span class="sxs-lookup"><span data-stu-id="a0d5e-105">Method</span></span>|<span data-ttu-id="a0d5e-106">描述</span><span class="sxs-lookup"><span data-stu-id="a0d5e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a0d5e-107">Abort 方法</span><span class="sxs-lookup"><span data-stu-id="a0d5e-107">Abort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-abort-method.md)|<span data-ttu-id="a0d5e-108">CLR 中止任务的请求的当前`ICLRTask`实例表示。</span><span class="sxs-lookup"><span data-stu-id="a0d5e-108">Requests that the CLR abort the task that the current `ICLRTask` instance represents.</span></span>|  
|[<span data-ttu-id="a0d5e-109">ExitTask 方法</span><span class="sxs-lookup"><span data-stu-id="a0d5e-109">ExitTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md)|<span data-ttu-id="a0d5e-110">通知与当前关联的任务的 CLR`ICLRTask`实例即将结束，并尝试正常关闭的任务。</span><span class="sxs-lookup"><span data-stu-id="a0d5e-110">Notifies the CLR that the task associated with the current `ICLRTask` instance is ending, and attempts to shut the task down gracefully.</span></span>|  
|[<span data-ttu-id="a0d5e-111">GetMemStats 方法</span><span class="sxs-lookup"><span data-stu-id="a0d5e-111">GetMemStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md)|<span data-ttu-id="a0d5e-112">获取表示由当前的任务上使用的内存资源的统计信息`ICLRTask`实例。</span><span class="sxs-lookup"><span data-stu-id="a0d5e-112">Gets statistical information on the use of memory resources by the task represented by the current `ICLRTask` instance.</span></span>|  
|[<span data-ttu-id="a0d5e-113">LocksHeld 方法</span><span class="sxs-lookup"><span data-stu-id="a0d5e-113">LocksHeld Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-locksheld-method.md)|<span data-ttu-id="a0d5e-114">获取当前在任务上所持有的锁数。</span><span class="sxs-lookup"><span data-stu-id="a0d5e-114">Gets the number of locks currently held on the task.</span></span>|  
|[<span data-ttu-id="a0d5e-115">NeedsPriorityScheduling 方法</span><span class="sxs-lookup"><span data-stu-id="a0d5e-115">NeedsPriorityScheduling Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-needspriorityscheduling-method.md)|<span data-ttu-id="a0d5e-116">获取一个值，该值指示主机是否应将高优先级分配给重新安排表示由当前的任务`ICLRTask`实例。</span><span class="sxs-lookup"><span data-stu-id="a0d5e-116">Gets a value indicating whether the host should assign a high priority to rescheduling the task represented by the current `ICLRTask` instance.</span></span>|  
|[<span data-ttu-id="a0d5e-117">Reset 方法</span><span class="sxs-lookup"><span data-stu-id="a0d5e-117">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-reset-method.md)|<span data-ttu-id="a0d5e-118">主机已完成一个任务，并使 CLR 重用当前通知 CLR`ICLRTask`实例来表示另一个任务。</span><span class="sxs-lookup"><span data-stu-id="a0d5e-118">Informs the CLR that the host has completed a task, and enables the CLR to reuse the current `ICLRTask` instance to represent another task.</span></span>|  
|[<span data-ttu-id="a0d5e-119">RudeAbort 方法</span><span class="sxs-lookup"><span data-stu-id="a0d5e-119">RudeAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-rudeabort-method.md)|<span data-ttu-id="a0d5e-120">会导致 CLR 中止表示由当前的任务`ICLRTask`实例立即，而无需保证将执行终结器。</span><span class="sxs-lookup"><span data-stu-id="a0d5e-120">Causes the CLR to abort the task represented by the current `ICLRTask` instance immediately, without a guarantee that finalizers will be executed.</span></span>|  
|[<span data-ttu-id="a0d5e-121">SetTaskIdentifier 方法</span><span class="sxs-lookup"><span data-stu-id="a0d5e-121">SetTaskIdentifier Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md)|<span data-ttu-id="a0d5e-122">设置为表示由当前的任务的唯一标识符`ICLRTask`实例，用于调试。</span><span class="sxs-lookup"><span data-stu-id="a0d5e-122">Sets a unique identifier for the task represented by the current `ICLRTask` instance, for use in debugging.</span></span>|  
|[<span data-ttu-id="a0d5e-123">SwitchIn 方法</span><span class="sxs-lookup"><span data-stu-id="a0d5e-123">SwitchIn Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchin-method.md)|<span data-ttu-id="a0d5e-124">通知当前所表示任务的 CLR`ICLRTask`实例处于可操作状态。</span><span class="sxs-lookup"><span data-stu-id="a0d5e-124">Notifies the CLR that the task represented by the current `ICLRTask` instance is in an operable state.</span></span>|  
|[<span data-ttu-id="a0d5e-125">SwitchOut 方法</span><span class="sxs-lookup"><span data-stu-id="a0d5e-125">SwitchOut Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)|<span data-ttu-id="a0d5e-126">通知当前所表示任务的 CLR`ICLRTask`实例不再处于可操作状态。</span><span class="sxs-lookup"><span data-stu-id="a0d5e-126">Notifies the CLR that the task represented by the current `ICLRTask` instance is no longer in an operable state.</span></span>|  
|[<span data-ttu-id="a0d5e-127">YieldTask 方法</span><span class="sxs-lookup"><span data-stu-id="a0d5e-127">YieldTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-yieldtask-method.md)|<span data-ttu-id="a0d5e-128">请求 CLR 分配处理器时间可供其他任务。</span><span class="sxs-lookup"><span data-stu-id="a0d5e-128">Requests that the CLR make processor time available to other tasks.</span></span> <span data-ttu-id="a0d5e-129">CLR 不保证该任务将被放在它可以产生处理时间的状态。</span><span class="sxs-lookup"><span data-stu-id="a0d5e-129">The CLR makes no guarantee that the task will be put in a state where it can yield processing time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0d5e-130">备注</span><span class="sxs-lookup"><span data-stu-id="a0d5e-130">Remarks</span></span>  
 <span data-ttu-id="a0d5e-131">`ICLRTask`是 CLR 任务的表示形式。</span><span class="sxs-lookup"><span data-stu-id="a0d5e-131">An `ICLRTask` is the representation of a task for the CLR.</span></span> <span data-ttu-id="a0d5e-132">在代码执行过程的任意位置，可以描述一项任务以运行或等待运行的形式。</span><span class="sxs-lookup"><span data-stu-id="a0d5e-132">At any point during code execution, a task can be described either as running or waiting to run.</span></span> <span data-ttu-id="a0d5e-133">宿主调用`ICLRTask::SwitchIn`方法来通知 CLR 的任务的当前`ICLRTask`实例所表示现处于可操作状态。</span><span class="sxs-lookup"><span data-stu-id="a0d5e-133">The host calls the `ICLRTask::SwitchIn` method to notify the CLR that the task that the current `ICLRTask` instance represents is now in an operable state.</span></span> <span data-ttu-id="a0d5e-134">调用了`ICLRTask::SwitchIn`，主机可以在其中运行时需要多个线程关联，通过调用指定的情况下除外安排任何操作系统线程，任务[ihosttaskmanager:: Beginthreadaffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)和[Ihosttaskmanager:: Endthreadaffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a0d5e-134">After a call to `ICLRTask::SwitchIn`, the host can schedule the task on any operating system thread, except in cases where the runtime requires thread-affinity, as specified by calls to the [IHostTaskManager::BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md) and [IHostTaskManager::EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md) methods.</span></span> <span data-ttu-id="a0d5e-135">一段时间后，系统可能会决定从线程中删除任务并将它放在非运行状态。</span><span class="sxs-lookup"><span data-stu-id="a0d5e-135">Some time later, the operating system might decide to remove the task from the thread and place it in a non-running state.</span></span> <span data-ttu-id="a0d5e-136">例如，这可能会发生时任务上同步基元，阻塞，或等待 I/O 操作完成。</span><span class="sxs-lookup"><span data-stu-id="a0d5e-136">For example, this might happen whenever the task blocks on synchronization primitives, or waits for I/O operations to complete.</span></span> <span data-ttu-id="a0d5e-137">宿主调用[SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)通知由当前所表示任务的 CLR`ICLRTask`实例不再处于可操作状态。</span><span class="sxs-lookup"><span data-stu-id="a0d5e-137">The host calls [SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md) to notify the CLR that the task represented by the current `ICLRTask` instance is no longer in an operable state.</span></span>  
  
 <span data-ttu-id="a0d5e-138">任务通常在执行代码的末尾终止。</span><span class="sxs-lookup"><span data-stu-id="a0d5e-138">A task typically terminates at the end of code execution.</span></span> <span data-ttu-id="a0d5e-139">此时，主机将调用`ICLRTask::ExitTask`销毁关联`ICLRTask`。</span><span class="sxs-lookup"><span data-stu-id="a0d5e-139">At that time, the host calls `ICLRTask::ExitTask` to destroy the associated `ICLRTask`.</span></span> <span data-ttu-id="a0d5e-140">但是，任务还都可以通过调用回收`ICLRTask::Reset`，这样，`ICLRTask`要再次使用实例。</span><span class="sxs-lookup"><span data-stu-id="a0d5e-140">However, tasks can also be recycled by using a call to `ICLRTask::Reset`, which allows the `ICLRTask` instance to be used again.</span></span> <span data-ttu-id="a0d5e-141">此方法可避免重复创建和销毁实例的开销。</span><span class="sxs-lookup"><span data-stu-id="a0d5e-141">This approach prevents the overhead of repeatedly creating and destroying instances.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0d5e-142">惠?</span><span class="sxs-lookup"><span data-stu-id="a0d5e-142">Requirements</span></span>  
 <span data-ttu-id="a0d5e-143">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a0d5e-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0d5e-144">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a0d5e-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0d5e-145">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a0d5e-145">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0d5e-146">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0d5e-146">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0d5e-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0d5e-147">See Also</span></span>  
 [<span data-ttu-id="a0d5e-148">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="a0d5e-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="a0d5e-149">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="a0d5e-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="a0d5e-150">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="a0d5e-150">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="a0d5e-151">承载接口</span><span class="sxs-lookup"><span data-stu-id="a0d5e-151">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="a0d5e-152">ICLRTask2 接口</span><span class="sxs-lookup"><span data-stu-id="a0d5e-152">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
