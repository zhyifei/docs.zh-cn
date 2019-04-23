---
title: ICLRTask 接口
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1baeac5db41aa64380d694ebab5419229d8adb4c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59088195"
---
# <a name="iclrtask-interface"></a><span data-ttu-id="13a46-102">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="13a46-102">ICLRTask Interface</span></span>
<span data-ttu-id="13a46-103">提供允许主机发出请求的公共语言运行时 (CLR)，或向 CLR 有关关联的任务提供通知的方法。</span><span class="sxs-lookup"><span data-stu-id="13a46-103">Provides methods that allow the host to make requests of the common language runtime (CLR), or to provide notification to the CLR about the associated task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="13a46-104">方法</span><span class="sxs-lookup"><span data-stu-id="13a46-104">Methods</span></span>  
  
|<span data-ttu-id="13a46-105">方法</span><span class="sxs-lookup"><span data-stu-id="13a46-105">Method</span></span>|<span data-ttu-id="13a46-106">描述</span><span class="sxs-lookup"><span data-stu-id="13a46-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="13a46-107">Abort 方法</span><span class="sxs-lookup"><span data-stu-id="13a46-107">Abort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-abort-method.md)|<span data-ttu-id="13a46-108">CLR 中止任务的请求的当前`ICLRTask`实例所表示。</span><span class="sxs-lookup"><span data-stu-id="13a46-108">Requests that the CLR abort the task that the current `ICLRTask` instance represents.</span></span>|  
|[<span data-ttu-id="13a46-109">ExitTask 方法</span><span class="sxs-lookup"><span data-stu-id="13a46-109">ExitTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md)|<span data-ttu-id="13a46-110">通知与当前任务关联的 CLR`ICLRTask`实例即将结束，并尝试正常关闭任务。</span><span class="sxs-lookup"><span data-stu-id="13a46-110">Notifies the CLR that the task associated with the current `ICLRTask` instance is ending, and attempts to shut the task down gracefully.</span></span>|  
|[<span data-ttu-id="13a46-111">GetMemStats 方法</span><span class="sxs-lookup"><span data-stu-id="13a46-111">GetMemStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md)|<span data-ttu-id="13a46-112">获取由当前任务的内存资源使用统计信息`ICLRTask`实例。</span><span class="sxs-lookup"><span data-stu-id="13a46-112">Gets statistical information on the use of memory resources by the task represented by the current `ICLRTask` instance.</span></span>|  
|[<span data-ttu-id="13a46-113">LocksHeld 方法</span><span class="sxs-lookup"><span data-stu-id="13a46-113">LocksHeld Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-locksheld-method.md)|<span data-ttu-id="13a46-114">获取当前任务上持有的锁数。</span><span class="sxs-lookup"><span data-stu-id="13a46-114">Gets the number of locks currently held on the task.</span></span>|  
|[<span data-ttu-id="13a46-115">NeedsPriorityScheduling 方法</span><span class="sxs-lookup"><span data-stu-id="13a46-115">NeedsPriorityScheduling Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-needspriorityscheduling-method.md)|<span data-ttu-id="13a46-116">获取一个值，该值指示主机是否应将高优先级分配给重新安排任务由当前`ICLRTask`实例。</span><span class="sxs-lookup"><span data-stu-id="13a46-116">Gets a value indicating whether the host should assign a high priority to rescheduling the task represented by the current `ICLRTask` instance.</span></span>|  
|[<span data-ttu-id="13a46-117">Reset 方法</span><span class="sxs-lookup"><span data-stu-id="13a46-117">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-reset-method.md)|<span data-ttu-id="13a46-118">通知 CLR，宿主完成某项任务，并使 CLR 能够重复使用当前`ICLRTask`实例来表示另一个任务。</span><span class="sxs-lookup"><span data-stu-id="13a46-118">Informs the CLR that the host has completed a task, and enables the CLR to reuse the current `ICLRTask` instance to represent another task.</span></span>|  
|[<span data-ttu-id="13a46-119">RudeAbort 方法</span><span class="sxs-lookup"><span data-stu-id="13a46-119">RudeAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-rudeabort-method.md)|<span data-ttu-id="13a46-120">会导致 CLR 中止表示由当前的任务`ICLRTask`实例立即，不保证会执行终结器。</span><span class="sxs-lookup"><span data-stu-id="13a46-120">Causes the CLR to abort the task represented by the current `ICLRTask` instance immediately, without a guarantee that finalizers will be executed.</span></span>|  
|[<span data-ttu-id="13a46-121">SetTaskIdentifier 方法</span><span class="sxs-lookup"><span data-stu-id="13a46-121">SetTaskIdentifier Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md)|<span data-ttu-id="13a46-122">设置表示由当前的任务的唯一标识符`ICLRTask`实例，以便在调试中使用。</span><span class="sxs-lookup"><span data-stu-id="13a46-122">Sets a unique identifier for the task represented by the current `ICLRTask` instance, for use in debugging.</span></span>|  
|[<span data-ttu-id="13a46-123">SwitchIn 方法</span><span class="sxs-lookup"><span data-stu-id="13a46-123">SwitchIn Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchin-method.md)|<span data-ttu-id="13a46-124">通知当前所表示的任务的 CLR`ICLRTask`实例处于可操作状态。</span><span class="sxs-lookup"><span data-stu-id="13a46-124">Notifies the CLR that the task represented by the current `ICLRTask` instance is in an operable state.</span></span>|  
|[<span data-ttu-id="13a46-125">SwitchOut 方法</span><span class="sxs-lookup"><span data-stu-id="13a46-125">SwitchOut Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)|<span data-ttu-id="13a46-126">通知当前所表示的任务的 CLR`ICLRTask`实例不再处于可操作状态。</span><span class="sxs-lookup"><span data-stu-id="13a46-126">Notifies the CLR that the task represented by the current `ICLRTask` instance is no longer in an operable state.</span></span>|  
|[<span data-ttu-id="13a46-127">YieldTask 方法</span><span class="sxs-lookup"><span data-stu-id="13a46-127">YieldTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-yieldtask-method.md)|<span data-ttu-id="13a46-128">请求的 CLR 分配处理器时间供其他任务。</span><span class="sxs-lookup"><span data-stu-id="13a46-128">Requests that the CLR make processor time available to other tasks.</span></span> <span data-ttu-id="13a46-129">CLR 不保证将该任务处于它可以产生的处理时间的状态。</span><span class="sxs-lookup"><span data-stu-id="13a46-129">The CLR makes no guarantee that the task will be put in a state where it can yield processing time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13a46-130">备注</span><span class="sxs-lookup"><span data-stu-id="13a46-130">Remarks</span></span>  
 <span data-ttu-id="13a46-131">`ICLRTask` CLR 任务的表示形式。</span><span class="sxs-lookup"><span data-stu-id="13a46-131">An `ICLRTask` is the representation of a task for the CLR.</span></span> <span data-ttu-id="13a46-132">在代码执行期间任何时候，可以描述任务作为运行或等待运行。</span><span class="sxs-lookup"><span data-stu-id="13a46-132">At any point during code execution, a task can be described either as running or waiting to run.</span></span> <span data-ttu-id="13a46-133">在宿主调用`ICLRTask::SwitchIn`方法以通知 CLR 的任务的当前`ICLRTask`实例表示现在处于可操作的状态。</span><span class="sxs-lookup"><span data-stu-id="13a46-133">The host calls the `ICLRTask::SwitchIn` method to notify the CLR that the task that the current `ICLRTask` instance represents is now in an operable state.</span></span> <span data-ttu-id="13a46-134">在调用`ICLRTask::SwitchIn`，主机可以在运行时要求线程关联，通过调用指定的位置的情况下除外计划在任何操作系统线程，任务[ihosttaskmanager:: Beginthreadaffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)和[Ihosttaskmanager:: Endthreadaffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="13a46-134">After a call to `ICLRTask::SwitchIn`, the host can schedule the task on any operating system thread, except in cases where the runtime requires thread-affinity, as specified by calls to the [IHostTaskManager::BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md) and [IHostTaskManager::EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md) methods.</span></span> <span data-ttu-id="13a46-135">一段时间后，操作系统可能会决定从线程中删除任务并将其放到非运行状态。</span><span class="sxs-lookup"><span data-stu-id="13a46-135">Some time later, the operating system might decide to remove the task from the thread and place it in a non-running state.</span></span> <span data-ttu-id="13a46-136">例如，可能发生此错误时任务同步基元上阻塞，或等待 I/O 操作完成。</span><span class="sxs-lookup"><span data-stu-id="13a46-136">For example, this might happen whenever the task blocks on synchronization primitives, or waits for I/O operations to complete.</span></span> <span data-ttu-id="13a46-137">在宿主调用[SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)来通知任务表示由当前 CLR`ICLRTask`实例不再处于可操作状态。</span><span class="sxs-lookup"><span data-stu-id="13a46-137">The host calls [SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md) to notify the CLR that the task represented by the current `ICLRTask` instance is no longer in an operable state.</span></span>  
  
 <span data-ttu-id="13a46-138">执行代码的结尾通常终止任务。</span><span class="sxs-lookup"><span data-stu-id="13a46-138">A task typically terminates at the end of code execution.</span></span> <span data-ttu-id="13a46-139">此时，主机将调用`ICLRTask::ExitTask`销毁关联`ICLRTask`。</span><span class="sxs-lookup"><span data-stu-id="13a46-139">At that time, the host calls `ICLRTask::ExitTask` to destroy the associated `ICLRTask`.</span></span> <span data-ttu-id="13a46-140">但是，任务也都可以通过使用调用回收`ICLRTask::Reset`，它允许`ICLRTask`实例，若要再次使用。</span><span class="sxs-lookup"><span data-stu-id="13a46-140">However, tasks can also be recycled by using a call to `ICLRTask::Reset`, which allows the `ICLRTask` instance to be used again.</span></span> <span data-ttu-id="13a46-141">这种方法可以防止反复创建和销毁实例的开销。</span><span class="sxs-lookup"><span data-stu-id="13a46-141">This approach prevents the overhead of repeatedly creating and destroying instances.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13a46-142">要求</span><span class="sxs-lookup"><span data-stu-id="13a46-142">Requirements</span></span>  
 <span data-ttu-id="13a46-143">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="13a46-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13a46-144">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="13a46-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="13a46-145">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="13a46-145">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13a46-146">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13a46-146">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13a46-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="13a46-147">See also</span></span>

- [<span data-ttu-id="13a46-148">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="13a46-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="13a46-149">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="13a46-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="13a46-150">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="13a46-150">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="13a46-151">承载接口</span><span class="sxs-lookup"><span data-stu-id="13a46-151">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="13a46-152">ICLRTask2 接口</span><span class="sxs-lookup"><span data-stu-id="13a46-152">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
