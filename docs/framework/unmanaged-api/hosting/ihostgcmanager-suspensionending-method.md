---
title: "IHostGCManager::SuspensionEnding 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostGCManager.SuspensionEnding
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostGCManager::SuspensionEnding
helpviewer_keywords:
- SuspensionEnding method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionEnding method [.NET Framework hosting]
ms.assetid: 8849a1db-17f0-44b7-880a-bd36d431eb91
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b9660a0aa755e297721679bcf6db798384f12abd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="74fd3-102">IHostGCManager::SuspensionEnding 方法</span><span class="sxs-lookup"><span data-stu-id="74fd3-102">IHostGCManager::SuspensionEnding Method</span></span>
<span data-ttu-id="74fd3-103">通知主机公共语言运行时 (CLR) 正在恢复已被挂起垃圾回收的线程上的任务的执行。</span><span class="sxs-lookup"><span data-stu-id="74fd3-103">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74fd3-104">语法</span><span class="sxs-lookup"><span data-stu-id="74fd3-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74fd3-105">参数</span><span class="sxs-lookup"><span data-stu-id="74fd3-105">Parameters</span></span>  
 `generation`  
 <span data-ttu-id="74fd3-106">[in]正在只需完成的垃圾回收代从中正在恢复线程。</span><span class="sxs-lookup"><span data-stu-id="74fd3-106">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74fd3-107">返回值</span><span class="sxs-lookup"><span data-stu-id="74fd3-107">Return Value</span></span>  
  
|<span data-ttu-id="74fd3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="74fd3-108">HRESULT</span></span>|<span data-ttu-id="74fd3-109">描述</span><span class="sxs-lookup"><span data-stu-id="74fd3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="74fd3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="74fd3-110">S_OK</span></span>|<span data-ttu-id="74fd3-111">`SuspensionEnding`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="74fd3-111">`SuspensionEnding` returned successfully.</span></span>|  
|<span data-ttu-id="74fd3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="74fd3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="74fd3-113">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="74fd3-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="74fd3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="74fd3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="74fd3-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="74fd3-115">The call timed out.</span></span>|  
|<span data-ttu-id="74fd3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="74fd3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="74fd3-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="74fd3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="74fd3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="74fd3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="74fd3-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="74fd3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="74fd3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="74fd3-120">E_FAIL</span></span>|<span data-ttu-id="74fd3-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="74fd3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="74fd3-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="74fd3-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="74fd3-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="74fd3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74fd3-124">备注</span><span class="sxs-lookup"><span data-stu-id="74fd3-124">Remarks</span></span>  
 <span data-ttu-id="74fd3-125">CLR 调用`SuspensionEnding`执行垃圾回收，以通知主机线程正在继续执行后。</span><span class="sxs-lookup"><span data-stu-id="74fd3-125">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="74fd3-126">不要重新安排从进行方法调用的线程。</span><span class="sxs-lookup"><span data-stu-id="74fd3-126">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74fd3-127">惠?</span><span class="sxs-lookup"><span data-stu-id="74fd3-127">Requirements</span></span>  
 <span data-ttu-id="74fd3-128">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="74fd3-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74fd3-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="74fd3-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="74fd3-130">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="74fd3-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74fd3-131">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74fd3-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74fd3-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="74fd3-132">See Also</span></span>  
 [<span data-ttu-id="74fd3-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="74fd3-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="74fd3-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="74fd3-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="74fd3-135">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="74fd3-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="74fd3-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="74fd3-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="74fd3-137">IHostGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="74fd3-137">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
