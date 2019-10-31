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
ms.openlocfilehash: bf1b830f55110c00356527bc9caa41dfd94ae377
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130457"
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="5c3a1-102">IHostGCManager::SuspensionStarting 方法</span><span class="sxs-lookup"><span data-stu-id="5c3a1-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="5c3a1-103">通知宿主公共语言运行时（CLR）正在挂起任务的执行，以执行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="5c3a1-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c3a1-104">语法</span><span class="sxs-lookup"><span data-stu-id="5c3a1-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5c3a1-105">返回值</span><span class="sxs-lookup"><span data-stu-id="5c3a1-105">Return Value</span></span>  
  
|<span data-ttu-id="5c3a1-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5c3a1-106">HRESULT</span></span>|<span data-ttu-id="5c3a1-107">描述</span><span class="sxs-lookup"><span data-stu-id="5c3a1-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5c3a1-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="5c3a1-108">S_OK</span></span>|<span data-ttu-id="5c3a1-109">`SuspensionStarting` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="5c3a1-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="5c3a1-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5c3a1-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5c3a1-111">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="5c3a1-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5c3a1-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5c3a1-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5c3a1-113">调用超时。</span><span class="sxs-lookup"><span data-stu-id="5c3a1-113">The call timed out.</span></span>|  
|<span data-ttu-id="5c3a1-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5c3a1-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5c3a1-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="5c3a1-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5c3a1-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5c3a1-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5c3a1-117">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="5c3a1-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5c3a1-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5c3a1-118">E_FAIL</span></span>|<span data-ttu-id="5c3a1-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="5c3a1-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5c3a1-120">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="5c3a1-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5c3a1-121">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="5c3a1-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c3a1-122">备注</span><span class="sxs-lookup"><span data-stu-id="5c3a1-122">Remarks</span></span>  
 <span data-ttu-id="5c3a1-123">CLR 调用 `SuspensionStarting` 来通知主机发生垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="5c3a1-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="5c3a1-124">不要重新计划此任务。</span><span class="sxs-lookup"><span data-stu-id="5c3a1-124">Do not reschedule this task.</span></span> <span data-ttu-id="5c3a1-125">调用[ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)时，主机必须重新安排任务。</span><span class="sxs-lookup"><span data-stu-id="5c3a1-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c3a1-126">要求</span><span class="sxs-lookup"><span data-stu-id="5c3a1-126">Requirements</span></span>  
 <span data-ttu-id="5c3a1-127">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5c3a1-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c3a1-128">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5c3a1-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5c3a1-129">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="5c3a1-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c3a1-130">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c3a1-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c3a1-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c3a1-131">See also</span></span>

- [<span data-ttu-id="5c3a1-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="5c3a1-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="5c3a1-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="5c3a1-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="5c3a1-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="5c3a1-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="5c3a1-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="5c3a1-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="5c3a1-136">IHostGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="5c3a1-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
