---
title: ICLRTask::Reset 方法
ms.date: 03/30/2017
api_name:
- ICLRTask.Reset
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Reset
helpviewer_keywords:
- ICLRTask::Reset method [.NET Framework hosting]
- Reset method, ICLRTask interface [.NET Framework hosting]
ms.assetid: 1bfb5d3a-0ffd-4bb4-9bf6-aec00cb675b7
topic_type:
- apiref
ms.openlocfilehash: 17fca3e5a2d763277d3a5f9f72e2d35be6fc350c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124640"
---
# <a name="iclrtaskreset-method"></a><span data-ttu-id="9aea0-102">ICLRTask::Reset 方法</span><span class="sxs-lookup"><span data-stu-id="9aea0-102">ICLRTask::Reset Method</span></span>
<span data-ttu-id="9aea0-103">通知公共语言运行时（CLR）宿主已经完成了一个任务，并使 CLR 能够重复使用当前的[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例来表示其他任务。</span><span class="sxs-lookup"><span data-stu-id="9aea0-103">Informs the common language runtime (CLR) that the host has completed a task, and enables the CLR to reuse the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance to represent another task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9aea0-104">语法</span><span class="sxs-lookup"><span data-stu-id="9aea0-104">Syntax</span></span>  
  
```cpp  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9aea0-105">参数</span><span class="sxs-lookup"><span data-stu-id="9aea0-105">Parameters</span></span>  
 `fFull`  
 <span data-ttu-id="9aea0-106">[in] 如果除了与当前 `ICLRTask` 实例相关的安全性和区域设置信息，运行时还应重置与线程相关的所有静态值，请 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="9aea0-106">[in] `true`, if the runtime should reset all thread-related static values in addition to the security and locale information related to the current `ICLRTask` instance; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="9aea0-107">如果 `true`值，则运行时将重置使用 <xref:System.Threading.Thread.AllocateDataSlot%2A> 或 <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>存储的数据。</span><span class="sxs-lookup"><span data-stu-id="9aea0-107">If the value is `true`, the runtime resets data that was stored using <xref:System.Threading.Thread.AllocateDataSlot%2A> or <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9aea0-108">返回值</span><span class="sxs-lookup"><span data-stu-id="9aea0-108">Return Value</span></span>  
  
|<span data-ttu-id="9aea0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9aea0-109">HRESULT</span></span>|<span data-ttu-id="9aea0-110">描述</span><span class="sxs-lookup"><span data-stu-id="9aea0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9aea0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9aea0-111">S_OK</span></span>|<span data-ttu-id="9aea0-112">`Reset` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="9aea0-112">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="9aea0-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9aea0-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9aea0-114">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="9aea0-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="9aea0-115">顺利</span><span class="sxs-lookup"><span data-stu-id="9aea0-115">successfully</span></span>|  
|<span data-ttu-id="9aea0-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9aea0-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9aea0-117">调用超时。</span><span class="sxs-lookup"><span data-stu-id="9aea0-117">The call timed out.</span></span>|  
|<span data-ttu-id="9aea0-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9aea0-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9aea0-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="9aea0-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9aea0-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9aea0-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9aea0-121">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="9aea0-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9aea0-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9aea0-122">E_FAIL</span></span>|<span data-ttu-id="9aea0-123">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="9aea0-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9aea0-124">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="9aea0-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9aea0-125">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="9aea0-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9aea0-126">备注</span><span class="sxs-lookup"><span data-stu-id="9aea0-126">Remarks</span></span>  
 <span data-ttu-id="9aea0-127">CLR 可以回收以前创建的 `ICLRTask` 实例，以避免在每次需要全新任务时重复创建新实例的系统开销。</span><span class="sxs-lookup"><span data-stu-id="9aea0-127">The CLR can recycle previously created `ICLRTask` instances to avoid the overhead of repeatedly creating new instances every time it needs a fresh task.</span></span> <span data-ttu-id="9aea0-128">当主机完成任务时，主机会通过调用 `ICLRTask::Reset` 而不是[ICLRTask：： ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md)来启用此功能。</span><span class="sxs-lookup"><span data-stu-id="9aea0-128">The host enables this feature by calling `ICLRTask::Reset` instead of [ICLRTask::ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) when it has completed a task.</span></span> <span data-ttu-id="9aea0-129">下面的列表总结了 `ICLRTask` 实例的正常生命周期：</span><span class="sxs-lookup"><span data-stu-id="9aea0-129">The following list summarizes the normal life cycle of an `ICLRTask` instance:</span></span>  
  
1. <span data-ttu-id="9aea0-130">运行时创建新的 `ICLRTask` 实例。</span><span class="sxs-lookup"><span data-stu-id="9aea0-130">The runtime creates a new `ICLRTask` instance.</span></span>  
  
2. <span data-ttu-id="9aea0-131">运行时调用[IHostTaskManager：： GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md)以获取对当前宿主任务的引用。</span><span class="sxs-lookup"><span data-stu-id="9aea0-131">The runtime calls [IHostTaskManager::GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) to get a reference to the current host task.</span></span>  
  
3. <span data-ttu-id="9aea0-132">运行时调用[IHostTask：： SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)以将新实例与宿主任务相关联。</span><span class="sxs-lookup"><span data-stu-id="9aea0-132">The runtime calls [IHostTask::SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) to associate the new instance with the host task.</span></span>  
  
4. <span data-ttu-id="9aea0-133">任务执行并完成。</span><span class="sxs-lookup"><span data-stu-id="9aea0-133">The task executes and completes.</span></span>  
  
5. <span data-ttu-id="9aea0-134">宿主通过调用 `ICLRTask::ExitTask`来销毁任务。</span><span class="sxs-lookup"><span data-stu-id="9aea0-134">The host destroys the task by calling `ICLRTask::ExitTask`.</span></span>  
  
 <span data-ttu-id="9aea0-135">`Reset` 通过两种方式改变此方案。</span><span class="sxs-lookup"><span data-stu-id="9aea0-135">`Reset` alters this scenario in two ways.</span></span> <span data-ttu-id="9aea0-136">在上面的步骤5中，主机调用 `Reset` 将任务重置为干净状态，然后将 `ICLRTask` 实例从其关联的[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)实例中分离。</span><span class="sxs-lookup"><span data-stu-id="9aea0-136">In step 5 above, the host calls `Reset` to reset the task to a clean state, and then decouples the `ICLRTask` instance from its associated [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span> <span data-ttu-id="9aea0-137">如果需要，主机还可以缓存 `IHostTask` 实例以供重用。</span><span class="sxs-lookup"><span data-stu-id="9aea0-137">If desired, the host can also cache the `IHostTask` instance for reuse.</span></span> <span data-ttu-id="9aea0-138">在上面的步骤1中，运行时从缓存中提取回收的 `ICLRTask`，而不是创建新的实例。</span><span class="sxs-lookup"><span data-stu-id="9aea0-138">In step 1 above, the runtime pulls a recycled `ICLRTask` from the cache instead of creating a new instance.</span></span>  
  
 <span data-ttu-id="9aea0-139">当主机还具有可重复使用的辅助角色任务池时，此方法非常有效。</span><span class="sxs-lookup"><span data-stu-id="9aea0-139">This approach works well when the host also has a pool of reusable worker tasks.</span></span> <span data-ttu-id="9aea0-140">当主机销毁其某个 `IHostTask` 实例时，它会通过调用 `ExitTask`销毁相应的 `ICLRTask`。</span><span class="sxs-lookup"><span data-stu-id="9aea0-140">When the host destroys one of its `IHostTask` instances, it destroys the corresponding `ICLRTask` by calling `ExitTask`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9aea0-141">要求</span><span class="sxs-lookup"><span data-stu-id="9aea0-141">Requirements</span></span>  
 <span data-ttu-id="9aea0-142">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9aea0-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9aea0-143">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9aea0-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9aea0-144">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="9aea0-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9aea0-145">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9aea0-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aea0-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="9aea0-146">See also</span></span>

- [<span data-ttu-id="9aea0-147">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="9aea0-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="9aea0-148">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="9aea0-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="9aea0-149">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="9aea0-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="9aea0-150">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="9aea0-150">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
