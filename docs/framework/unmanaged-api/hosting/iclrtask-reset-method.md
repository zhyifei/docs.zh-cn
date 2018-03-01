---
title: "ICLRTask::Reset 方法"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8dc37f47fc01d73ff499ef974a2e11345a95286a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskreset-method"></a><span data-ttu-id="d800b-102">ICLRTask::Reset 方法</span><span class="sxs-lookup"><span data-stu-id="d800b-102">ICLRTask::Reset Method</span></span>
<span data-ttu-id="d800b-103">通知公共语言运行时 (CLR)，主机具有完成某项任务，并使 CLR 重用当前[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例来表示另一个任务。</span><span class="sxs-lookup"><span data-stu-id="d800b-103">Informs the common language runtime (CLR) that the host has completed a task, and enables the CLR to reuse the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance to represent another task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d800b-104">语法</span><span class="sxs-lookup"><span data-stu-id="d800b-104">Syntax</span></span>  
  
```  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d800b-105">参数</span><span class="sxs-lookup"><span data-stu-id="d800b-105">Parameters</span></span>  
 `fFull`  
 <span data-ttu-id="d800b-106">[in]`true`，如果运行时应重置所有与线程相关静态值以及与当前相关的安全和区域设置信息`ICLRTask`实例; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="d800b-106">[in] `true`, if the runtime should reset all thread-related static values in addition to the security and locale information related to the current `ICLRTask` instance; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="d800b-107">如果值为`true`，运行时将使用已存储的数据重置<xref:System.Threading.Thread.AllocateDataSlot%2A>或<xref:System.Threading.Thread.AllocateNamedDataSlot%2A>。</span><span class="sxs-lookup"><span data-stu-id="d800b-107">If the value is `true`, the runtime resets data that was stored using <xref:System.Threading.Thread.AllocateDataSlot%2A> or <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d800b-108">返回值</span><span class="sxs-lookup"><span data-stu-id="d800b-108">Return Value</span></span>  
  
|<span data-ttu-id="d800b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d800b-109">HRESULT</span></span>|<span data-ttu-id="d800b-110">描述</span><span class="sxs-lookup"><span data-stu-id="d800b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d800b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d800b-111">S_OK</span></span>|<span data-ttu-id="d800b-112">`Reset`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="d800b-112">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="d800b-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d800b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d800b-114">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="d800b-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="d800b-115">已成功</span><span class="sxs-lookup"><span data-stu-id="d800b-115">successfully</span></span>|  
|<span data-ttu-id="d800b-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d800b-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d800b-117">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="d800b-117">The call timed out.</span></span>|  
|<span data-ttu-id="d800b-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d800b-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d800b-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="d800b-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d800b-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d800b-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d800b-121">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="d800b-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d800b-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d800b-122">E_FAIL</span></span>|<span data-ttu-id="d800b-123">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="d800b-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d800b-124">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="d800b-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d800b-125">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="d800b-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d800b-126">备注</span><span class="sxs-lookup"><span data-stu-id="d800b-126">Remarks</span></span>  
 <span data-ttu-id="d800b-127">CLR 可以回收以前创建`ICLRTask`实例，以避免重复创建新的实例，每次需要新任务的系统开销。</span><span class="sxs-lookup"><span data-stu-id="d800b-127">The CLR can recycle previously created `ICLRTask` instances to avoid the overhead of repeatedly creating new instances every time it needs a fresh task.</span></span> <span data-ttu-id="d800b-128">主机启用此功能通过调用`ICLRTask::Reset`而不是[iclrtask:: Exittask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md)当它已完成任务。</span><span class="sxs-lookup"><span data-stu-id="d800b-128">The host enables this feature by calling `ICLRTask::Reset` instead of [ICLRTask::ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) when it has completed a task.</span></span> <span data-ttu-id="d800b-129">以下列表总结了正常的生命周期的`ICLRTask`实例：</span><span class="sxs-lookup"><span data-stu-id="d800b-129">The following list summarizes the normal life cycle of an `ICLRTask` instance:</span></span>  
  
1.  <span data-ttu-id="d800b-130">运行时创建一个新`ICLRTask`实例。</span><span class="sxs-lookup"><span data-stu-id="d800b-130">The runtime creates a new `ICLRTask` instance.</span></span>  
  
2.  <span data-ttu-id="d800b-131">在运行时调用[ihosttaskmanager:: Getcurrenttask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md)以获取对当前的主机任务的引用。</span><span class="sxs-lookup"><span data-stu-id="d800b-131">The runtime calls [IHostTaskManager::GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) to get a reference to the current host task.</span></span>  
  
3.  <span data-ttu-id="d800b-132">在运行时调用[ihosttask:: Setclrtask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)要主机任务相关联的新实例。</span><span class="sxs-lookup"><span data-stu-id="d800b-132">The runtime calls [IHostTask::SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) to associate the new instance with the host task.</span></span>  
  
4.  <span data-ttu-id="d800b-133">该任务执行，并完成。</span><span class="sxs-lookup"><span data-stu-id="d800b-133">The task executes and completes.</span></span>  
  
5.  <span data-ttu-id="d800b-134">宿主通过调用销毁任务`ICLRTask::ExitTask`。</span><span class="sxs-lookup"><span data-stu-id="d800b-134">The host destroys the task by calling `ICLRTask::ExitTask`.</span></span>  
  
 <span data-ttu-id="d800b-135">`Reset`将更改这种情况下，两种方式。</span><span class="sxs-lookup"><span data-stu-id="d800b-135">`Reset` alters this scenario in two ways.</span></span> <span data-ttu-id="d800b-136">在上面的步骤 5，宿主调用`Reset`将任务重置为空白状态，然后将脱耦和`ICLRTask`从及其关联的实例[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="d800b-136">In step 5 above, the host calls `Reset` to reset the task to a clean state, and then decouples the `ICLRTask` instance from its associated [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span> <span data-ttu-id="d800b-137">如果需要，主机也可以缓存`IHostTask`以供重复使用的实例。</span><span class="sxs-lookup"><span data-stu-id="d800b-137">If desired, the host can also cache the `IHostTask` instance for reuse.</span></span> <span data-ttu-id="d800b-138">在上面第一步，运行时中提取回收`ICLRTask`从缓存而不是创建的新实例。</span><span class="sxs-lookup"><span data-stu-id="d800b-138">In step 1 above, the runtime pulls a recycled `ICLRTask` from the cache instead of creating a new instance.</span></span>  
  
 <span data-ttu-id="d800b-139">此方法适用于主机还具有可重用工作线程任务的池。</span><span class="sxs-lookup"><span data-stu-id="d800b-139">This approach works well when the host also has a pool of reusable worker tasks.</span></span> <span data-ttu-id="d800b-140">当主机销毁之一其`IHostTask`实例，它将销毁相应`ICLRTask`通过调用`ExitTask`。</span><span class="sxs-lookup"><span data-stu-id="d800b-140">When the host destroys one of its `IHostTask` instances, it destroys the corresponding `ICLRTask` by calling `ExitTask`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d800b-141">惠?</span><span class="sxs-lookup"><span data-stu-id="d800b-141">Requirements</span></span>  
 <span data-ttu-id="d800b-142">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d800b-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d800b-143">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d800b-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d800b-144">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d800b-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d800b-145">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d800b-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d800b-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="d800b-146">See Also</span></span>  
 [<span data-ttu-id="d800b-147">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="d800b-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="d800b-148">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="d800b-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="d800b-149">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="d800b-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="d800b-150">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="d800b-150">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
