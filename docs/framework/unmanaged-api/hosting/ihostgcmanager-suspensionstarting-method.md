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
ms.openlocfilehash: 6a84da2a337554873e94b47eb51916088edbb5a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439028"
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="f096e-102">IHostGCManager::SuspensionStarting 方法</span><span class="sxs-lookup"><span data-stu-id="f096e-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="f096e-103">通知主机公共语言运行时 (CLR) 正在挂起任务，以执行垃圾回收的执行。</span><span class="sxs-lookup"><span data-stu-id="f096e-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f096e-104">语法</span><span class="sxs-lookup"><span data-stu-id="f096e-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f096e-105">返回值</span><span class="sxs-lookup"><span data-stu-id="f096e-105">Return Value</span></span>  
  
|<span data-ttu-id="f096e-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f096e-106">HRESULT</span></span>|<span data-ttu-id="f096e-107">描述</span><span class="sxs-lookup"><span data-stu-id="f096e-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f096e-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f096e-108">S_OK</span></span>|<span data-ttu-id="f096e-109">`SuspensionStarting` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="f096e-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="f096e-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f096e-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f096e-111">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="f096e-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f096e-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f096e-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f096e-113">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="f096e-113">The call timed out.</span></span>|  
|<span data-ttu-id="f096e-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f096e-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f096e-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="f096e-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f096e-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f096e-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f096e-117">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="f096e-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f096e-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f096e-118">E_FAIL</span></span>|<span data-ttu-id="f096e-119">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="f096e-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f096e-120">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="f096e-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f096e-121">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="f096e-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f096e-122">备注</span><span class="sxs-lookup"><span data-stu-id="f096e-122">Remarks</span></span>  
 <span data-ttu-id="f096e-123">CLR 调用`SuspensionStarting`以通知发生垃圾回收的主机。</span><span class="sxs-lookup"><span data-stu-id="f096e-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f096e-124">不要重新安排此任务。</span><span class="sxs-lookup"><span data-stu-id="f096e-124">Do not reschedule this task.</span></span> <span data-ttu-id="f096e-125">主机必须重新计划任务时[ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)调用。</span><span class="sxs-lookup"><span data-stu-id="f096e-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f096e-126">要求</span><span class="sxs-lookup"><span data-stu-id="f096e-126">Requirements</span></span>  
 <span data-ttu-id="f096e-127">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f096e-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f096e-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f096e-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f096e-129">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f096e-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f096e-130">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f096e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f096e-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="f096e-131">See Also</span></span>  
 [<span data-ttu-id="f096e-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="f096e-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="f096e-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="f096e-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="f096e-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="f096e-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="f096e-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="f096e-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="f096e-136">IHostGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="f096e-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
