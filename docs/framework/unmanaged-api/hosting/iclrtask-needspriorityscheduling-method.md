---
title: ICLRTask::NeedsPriorityScheduling 方法
ms.date: 03/30/2017
api_name:
- ICLRTask.NeedsPriorityScheduling
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::NeedsPriorityScheduling
helpviewer_keywords:
- ICLRTask::NeedsPriorityScheduling method [.NET Framework hosting]
- NeedsPriorityScheduling method [.NET Framework hosting]
ms.assetid: 9c9db3f3-26bf-4317-88de-5eb926a22a1d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91c7235fb8790783b05b217cad755d8eedc88971
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59092679"
---
# <a name="iclrtaskneedspriorityscheduling-method"></a><span data-ttu-id="15325-102">ICLRTask::NeedsPriorityScheduling 方法</span><span class="sxs-lookup"><span data-stu-id="15325-102">ICLRTask::NeedsPriorityScheduling Method</span></span>
<span data-ttu-id="15325-103">获取一个值，该值指示当前任务，正被切换出，是否需要将其标记为高优先级以便重新计划。</span><span class="sxs-lookup"><span data-stu-id="15325-103">Gets a value that indicates whether the current task, which is being switched out, needs to be marked as a high priority for rescheduling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15325-104">语法</span><span class="sxs-lookup"><span data-stu-id="15325-104">Syntax</span></span>  
  
```  
HRESULT NeedsPriorityScheduling (  
    [out] BOOL *pbNeedsPriorityScheduling  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15325-105">参数</span><span class="sxs-lookup"><span data-stu-id="15325-105">Parameters</span></span>  
 `pbNeedsPriorityRescheduling`  
 <span data-ttu-id="15325-106">[out]`true`，如果主机应尝试尽可能快; 否则为重新计划当前的任务实例`false`。</span><span class="sxs-lookup"><span data-stu-id="15325-106">[out] `true`, if the host should attempt to reschedule the current task instance as soon as possible; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15325-107">返回值</span><span class="sxs-lookup"><span data-stu-id="15325-107">Return Value</span></span>  
  
|<span data-ttu-id="15325-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="15325-108">HRESULT</span></span>|<span data-ttu-id="15325-109">描述</span><span class="sxs-lookup"><span data-stu-id="15325-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="15325-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="15325-110">S_OK</span></span>|<span data-ttu-id="15325-111">`NeedsPriorityRescheduling` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="15325-111">`NeedsPriorityRescheduling` returned successfully.</span></span>|  
|<span data-ttu-id="15325-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="15325-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="15325-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="15325-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="15325-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="15325-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="15325-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="15325-115">The call timed out.</span></span>|  
|<span data-ttu-id="15325-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="15325-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="15325-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="15325-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="15325-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="15325-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="15325-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="15325-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="15325-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="15325-120">E_FAIL</span></span>|<span data-ttu-id="15325-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="15325-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="15325-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="15325-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="15325-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="15325-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15325-124">备注</span><span class="sxs-lookup"><span data-stu-id="15325-124">Remarks</span></span>  
 <span data-ttu-id="15325-125">在其中的任务是接近于收集的垃圾回收器的情况下，CLR 设置的值`pbNeedsPriorityScheduling`到`true`，指示重新安排高优先级。</span><span class="sxs-lookup"><span data-stu-id="15325-125">In situations where the task is close to being collected by the garbage collector, the CLR sets the value of `pbNeedsPriorityScheduling` to `true`, indicating high-priority rescheduling.</span></span> <span data-ttu-id="15325-126">这允许主机快速重新计划任务，从而最大程度减少垃圾回收中出现延迟的可能性，并使宿主和运行时能够共同协作来节约内存资源。</span><span class="sxs-lookup"><span data-stu-id="15325-126">This allows the host to reschedule the task quickly, thereby minimizing the potential for delays in garbage collection, and enabling the host and the runtime to cooperate in conserving memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15325-127">要求</span><span class="sxs-lookup"><span data-stu-id="15325-127">Requirements</span></span>  
 <span data-ttu-id="15325-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="15325-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15325-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="15325-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="15325-130">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="15325-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15325-131">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15325-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15325-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="15325-132">See also</span></span>

- [<span data-ttu-id="15325-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="15325-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="15325-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="15325-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="15325-135">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="15325-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="15325-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="15325-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
