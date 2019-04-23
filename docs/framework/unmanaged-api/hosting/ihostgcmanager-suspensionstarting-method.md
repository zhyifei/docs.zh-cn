---
title: IHostGCManager::SuspensionStarting 方法
ms.date: 03/30/2017
api_name:
- IHostGCManager.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionStarting
helpviewer_keywords:
- SuspensionStarting method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionStarting method [.NET Framework hosting]
ms.assetid: c381f524-94cf-4fa2-9298-50f847a03431
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47ef5bb2539820d5a7bcd4ca6b4de86564290709
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213085"
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="7a37f-102">IHostGCManager::SuspensionStarting 方法</span><span class="sxs-lookup"><span data-stu-id="7a37f-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="7a37f-103">公共语言运行时 (CLR) 正在挂起执行的任务，以执行垃圾回收通知主机。</span><span class="sxs-lookup"><span data-stu-id="7a37f-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a37f-104">语法</span><span class="sxs-lookup"><span data-stu-id="7a37f-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7a37f-105">返回值</span><span class="sxs-lookup"><span data-stu-id="7a37f-105">Return Value</span></span>  
  
|<span data-ttu-id="7a37f-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7a37f-106">HRESULT</span></span>|<span data-ttu-id="7a37f-107">描述</span><span class="sxs-lookup"><span data-stu-id="7a37f-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7a37f-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="7a37f-108">S_OK</span></span>|<span data-ttu-id="7a37f-109">`SuspensionStarting` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="7a37f-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="7a37f-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7a37f-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7a37f-111">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="7a37f-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7a37f-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7a37f-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7a37f-113">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="7a37f-113">The call timed out.</span></span>|  
|<span data-ttu-id="7a37f-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7a37f-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7a37f-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="7a37f-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7a37f-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7a37f-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7a37f-117">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="7a37f-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7a37f-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7a37f-118">E_FAIL</span></span>|<span data-ttu-id="7a37f-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="7a37f-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7a37f-120">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="7a37f-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7a37f-121">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="7a37f-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a37f-122">备注</span><span class="sxs-lookup"><span data-stu-id="7a37f-122">Remarks</span></span>  
 <span data-ttu-id="7a37f-123">CLR 调用`SuspensionStarting`通知发生垃圾回收的主机。</span><span class="sxs-lookup"><span data-stu-id="7a37f-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7a37f-124">不要重新安排此任务。</span><span class="sxs-lookup"><span data-stu-id="7a37f-124">Do not reschedule this task.</span></span> <span data-ttu-id="7a37f-125">主机必须重新计划任务时[ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)调用。</span><span class="sxs-lookup"><span data-stu-id="7a37f-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a37f-126">要求</span><span class="sxs-lookup"><span data-stu-id="7a37f-126">Requirements</span></span>  
 <span data-ttu-id="7a37f-127">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7a37f-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a37f-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7a37f-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7a37f-129">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7a37f-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7a37f-130">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a37f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a37f-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="7a37f-131">See also</span></span>

- [<span data-ttu-id="7a37f-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="7a37f-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="7a37f-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="7a37f-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="7a37f-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="7a37f-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="7a37f-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="7a37f-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="7a37f-136">IHostGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="7a37f-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
