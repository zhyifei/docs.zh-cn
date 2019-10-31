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
ms.openlocfilehash: 91c1ea51969447861ff6d0956c5714baa0054450
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124672"
---
# <a name="iclrtaskneedspriorityscheduling-method"></a><span data-ttu-id="c4841-102">ICLRTask::NeedsPriorityScheduling 方法</span><span class="sxs-lookup"><span data-stu-id="c4841-102">ICLRTask::NeedsPriorityScheduling Method</span></span>
<span data-ttu-id="c4841-103">获取一个值，该值指示当前要切换的任务是否需要标记为高优先级才能进行重新计划。</span><span class="sxs-lookup"><span data-stu-id="c4841-103">Gets a value that indicates whether the current task, which is being switched out, needs to be marked as a high priority for rescheduling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4841-104">语法</span><span class="sxs-lookup"><span data-stu-id="c4841-104">Syntax</span></span>  
  
```cpp  
HRESULT NeedsPriorityScheduling (  
    [out] BOOL *pbNeedsPriorityScheduling  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4841-105">参数</span><span class="sxs-lookup"><span data-stu-id="c4841-105">Parameters</span></span>  
 `pbNeedsPriorityRescheduling`  
 <span data-ttu-id="c4841-106">[out] 如果宿主应尝试尽快重新计划当前任务实例，则为 [out] `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="c4841-106">[out] `true`, if the host should attempt to reschedule the current task instance as soon as possible; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c4841-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c4841-107">Return Value</span></span>  
  
|<span data-ttu-id="c4841-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c4841-108">HRESULT</span></span>|<span data-ttu-id="c4841-109">描述</span><span class="sxs-lookup"><span data-stu-id="c4841-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c4841-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c4841-110">S_OK</span></span>|<span data-ttu-id="c4841-111">`NeedsPriorityRescheduling` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="c4841-111">`NeedsPriorityRescheduling` returned successfully.</span></span>|  
|<span data-ttu-id="c4841-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c4841-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c4841-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="c4841-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c4841-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c4841-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c4841-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="c4841-115">The call timed out.</span></span>|  
|<span data-ttu-id="c4841-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c4841-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c4841-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="c4841-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c4841-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c4841-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c4841-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="c4841-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c4841-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c4841-120">E_FAIL</span></span>|<span data-ttu-id="c4841-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="c4841-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c4841-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="c4841-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c4841-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c4841-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4841-124">备注</span><span class="sxs-lookup"><span data-stu-id="c4841-124">Remarks</span></span>  
 <span data-ttu-id="c4841-125">在任务接近于垃圾回收器收集的情况下，CLR 将 `pbNeedsPriorityScheduling` 的值设置为 `true`，这表示高优先级的重新计划。</span><span class="sxs-lookup"><span data-stu-id="c4841-125">In situations where the task is close to being collected by the garbage collector, the CLR sets the value of `pbNeedsPriorityScheduling` to `true`, indicating high-priority rescheduling.</span></span> <span data-ttu-id="c4841-126">这使主机可以快速重新计划任务，从而最大程度地减少垃圾回收延迟的可能性，并使宿主和运行时能够在保存内存资源时进行合作。</span><span class="sxs-lookup"><span data-stu-id="c4841-126">This allows the host to reschedule the task quickly, thereby minimizing the potential for delays in garbage collection, and enabling the host and the runtime to cooperate in conserving memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4841-127">要求</span><span class="sxs-lookup"><span data-stu-id="c4841-127">Requirements</span></span>  
 <span data-ttu-id="c4841-128">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c4841-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4841-129">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c4841-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c4841-130">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c4841-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c4841-131">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4841-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4841-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4841-132">See also</span></span>

- [<span data-ttu-id="c4841-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="c4841-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="c4841-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="c4841-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="c4841-135">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="c4841-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="c4841-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="c4841-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
