---
title: "IHostGCManager::SuspensionStarting 方法"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 30f6c611dc719fa6f1162498082cc9a60fb5059b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="9e76a-102">IHostGCManager::SuspensionStarting 方法</span><span class="sxs-lookup"><span data-stu-id="9e76a-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="9e76a-103">通知主机公共语言运行时 (CLR) 正在挂起任务，以执行垃圾回收的执行。</span><span class="sxs-lookup"><span data-stu-id="9e76a-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e76a-104">语法</span><span class="sxs-lookup"><span data-stu-id="9e76a-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9e76a-105">返回值</span><span class="sxs-lookup"><span data-stu-id="9e76a-105">Return Value</span></span>  
  
|<span data-ttu-id="9e76a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9e76a-106">HRESULT</span></span>|<span data-ttu-id="9e76a-107">描述</span><span class="sxs-lookup"><span data-stu-id="9e76a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9e76a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9e76a-108">S_OK</span></span>|<span data-ttu-id="9e76a-109">`SuspensionStarting`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="9e76a-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="9e76a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9e76a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9e76a-111">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="9e76a-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9e76a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9e76a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9e76a-113">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="9e76a-113">The call timed out.</span></span>|  
|<span data-ttu-id="9e76a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9e76a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9e76a-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="9e76a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9e76a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9e76a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9e76a-117">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="9e76a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9e76a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9e76a-118">E_FAIL</span></span>|<span data-ttu-id="9e76a-119">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="9e76a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9e76a-120">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="9e76a-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9e76a-121">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="9e76a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e76a-122">备注</span><span class="sxs-lookup"><span data-stu-id="9e76a-122">Remarks</span></span>  
 <span data-ttu-id="9e76a-123">CLR 调用`SuspensionStarting`以通知发生垃圾回收的主机。</span><span class="sxs-lookup"><span data-stu-id="9e76a-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9e76a-124">不要重新安排此任务。</span><span class="sxs-lookup"><span data-stu-id="9e76a-124">Do not reschedule this task.</span></span> <span data-ttu-id="9e76a-125">主机必须重新计划任务时[ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)调用。</span><span class="sxs-lookup"><span data-stu-id="9e76a-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e76a-126">惠?</span><span class="sxs-lookup"><span data-stu-id="9e76a-126">Requirements</span></span>  
 <span data-ttu-id="9e76a-127">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9e76a-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e76a-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9e76a-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9e76a-129">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9e76a-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9e76a-130">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e76a-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e76a-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e76a-131">See Also</span></span>  
 [<span data-ttu-id="9e76a-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="9e76a-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="9e76a-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="9e76a-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="9e76a-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="9e76a-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="9e76a-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="9e76a-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="9e76a-136">IHostGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="9e76a-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
