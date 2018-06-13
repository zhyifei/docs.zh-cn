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
ms.openlocfilehash: 36403abcae4d4e691fe6362e61cf7fa979ec7f5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435733"
---
# <a name="iclrtaskneedspriorityscheduling-method"></a><span data-ttu-id="21f94-102">ICLRTask::NeedsPriorityScheduling 方法</span><span class="sxs-lookup"><span data-stu-id="21f94-102">ICLRTask::NeedsPriorityScheduling Method</span></span>
<span data-ttu-id="21f94-103">获取一个值，该值指示当前任务，正被切换出，是否需要将标记为高优先级以便重新计划。</span><span class="sxs-lookup"><span data-stu-id="21f94-103">Gets a value that indicates whether the current task, which is being switched out, needs to be marked as a high priority for rescheduling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21f94-104">语法</span><span class="sxs-lookup"><span data-stu-id="21f94-104">Syntax</span></span>  
  
```  
HRESULT NeedsPriorityScheduling (  
    [out] BOOL *pbNeedsPriorityScheduling  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="21f94-105">参数</span><span class="sxs-lookup"><span data-stu-id="21f94-105">Parameters</span></span>  
 `pbNeedsPriorityRescheduling`  
 <span data-ttu-id="21f94-106">[out]`true`，如果主机应尝试尽可能快地; 否则为重新计划当前的任务实例`false`。</span><span class="sxs-lookup"><span data-stu-id="21f94-106">[out] `true`, if the host should attempt to reschedule the current task instance as soon as possible; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21f94-107">返回值</span><span class="sxs-lookup"><span data-stu-id="21f94-107">Return Value</span></span>  
  
|<span data-ttu-id="21f94-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="21f94-108">HRESULT</span></span>|<span data-ttu-id="21f94-109">描述</span><span class="sxs-lookup"><span data-stu-id="21f94-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="21f94-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="21f94-110">S_OK</span></span>|<span data-ttu-id="21f94-111">`NeedsPriorityRescheduling` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="21f94-111">`NeedsPriorityRescheduling` returned successfully.</span></span>|  
|<span data-ttu-id="21f94-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="21f94-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="21f94-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="21f94-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="21f94-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="21f94-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="21f94-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="21f94-115">The call timed out.</span></span>|  
|<span data-ttu-id="21f94-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="21f94-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="21f94-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="21f94-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="21f94-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="21f94-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="21f94-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="21f94-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="21f94-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="21f94-120">E_FAIL</span></span>|<span data-ttu-id="21f94-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="21f94-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="21f94-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="21f94-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="21f94-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="21f94-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21f94-124">备注</span><span class="sxs-lookup"><span data-stu-id="21f94-124">Remarks</span></span>  
 <span data-ttu-id="21f94-125">在其中的任务是接近垃圾回收器收集的情况下，CLR 设置的值`pbNeedsPriorityScheduling`到`true`，，该值指示优先级较高重新安排。</span><span class="sxs-lookup"><span data-stu-id="21f94-125">In situations where the task is close to being collected by the garbage collector, the CLR sets the value of `pbNeedsPriorityScheduling` to `true`, indicating high-priority rescheduling.</span></span> <span data-ttu-id="21f94-126">这允许主机快速重新计划任务，从而将出现延迟，在垃圾回收的可能性降至最低并使主机和运行时能够共同协作来节省内存资源。</span><span class="sxs-lookup"><span data-stu-id="21f94-126">This allows the host to reschedule the task quickly, thereby minimizing the potential for delays in garbage collection, and enabling the host and the runtime to cooperate in conserving memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21f94-127">要求</span><span class="sxs-lookup"><span data-stu-id="21f94-127">Requirements</span></span>  
 <span data-ttu-id="21f94-128">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="21f94-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21f94-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="21f94-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="21f94-130">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="21f94-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="21f94-131">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21f94-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21f94-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="21f94-132">See Also</span></span>  
 [<span data-ttu-id="21f94-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="21f94-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="21f94-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="21f94-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="21f94-135">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="21f94-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="21f94-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="21f94-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
