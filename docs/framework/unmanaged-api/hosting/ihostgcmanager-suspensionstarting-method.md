---
title: "IHostGCManager::SuspensionStarting 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostGCManager.SuspensionStarting
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostGCManager::SuspensionStarting
helpviewer_keywords:
- SuspensionStarting method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionStarting method [.NET Framework hosting]
ms.assetid: c381f524-94cf-4fa2-9298-50f847a03431
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9c807a124570f38922509d27e52936b980e36fba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="fb2f9-102">IHostGCManager::SuspensionStarting 方法</span><span class="sxs-lookup"><span data-stu-id="fb2f9-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="fb2f9-103">通知主机公共语言运行时 (CLR) 正在挂起任务，以执行垃圾回收的执行。</span><span class="sxs-lookup"><span data-stu-id="fb2f9-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb2f9-104">语法</span><span class="sxs-lookup"><span data-stu-id="fb2f9-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="fb2f9-105">返回值</span><span class="sxs-lookup"><span data-stu-id="fb2f9-105">Return Value</span></span>  
  
|<span data-ttu-id="fb2f9-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fb2f9-106">HRESULT</span></span>|<span data-ttu-id="fb2f9-107">描述</span><span class="sxs-lookup"><span data-stu-id="fb2f9-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fb2f9-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="fb2f9-108">S_OK</span></span>|<span data-ttu-id="fb2f9-109">`SuspensionStarting`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="fb2f9-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="fb2f9-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fb2f9-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fb2f9-111">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="fb2f9-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fb2f9-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fb2f9-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fb2f9-113">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="fb2f9-113">The call timed out.</span></span>|  
|<span data-ttu-id="fb2f9-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fb2f9-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fb2f9-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="fb2f9-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fb2f9-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fb2f9-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fb2f9-117">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="fb2f9-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fb2f9-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fb2f9-118">E_FAIL</span></span>|<span data-ttu-id="fb2f9-119">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="fb2f9-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fb2f9-120">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="fb2f9-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fb2f9-121">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="fb2f9-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb2f9-122">备注</span><span class="sxs-lookup"><span data-stu-id="fb2f9-122">Remarks</span></span>  
 <span data-ttu-id="fb2f9-123">CLR 调用`SuspensionStarting`以通知发生垃圾回收的主机。</span><span class="sxs-lookup"><span data-stu-id="fb2f9-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fb2f9-124">不要重新安排此任务。</span><span class="sxs-lookup"><span data-stu-id="fb2f9-124">Do not reschedule this task.</span></span> <span data-ttu-id="fb2f9-125">主机必须重新计划任务时[ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)调用。</span><span class="sxs-lookup"><span data-stu-id="fb2f9-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb2f9-126">要求</span><span class="sxs-lookup"><span data-stu-id="fb2f9-126">Requirements</span></span>  
 <span data-ttu-id="fb2f9-127">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fb2f9-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb2f9-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fb2f9-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fb2f9-129">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="fb2f9-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb2f9-130">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb2f9-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb2f9-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb2f9-131">See Also</span></span>  
 [<span data-ttu-id="fb2f9-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="fb2f9-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="fb2f9-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="fb2f9-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="fb2f9-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="fb2f9-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="fb2f9-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="fb2f9-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="fb2f9-136">IHostGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="fb2f9-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
