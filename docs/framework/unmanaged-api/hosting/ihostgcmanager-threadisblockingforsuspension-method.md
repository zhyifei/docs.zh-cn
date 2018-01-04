---
title: "IHostGCManager::ThreadIsBlockingForSuspension 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostGCManager.ThreadIsBlockingForSuspension
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostGCManager::ThreadIsBlockingForSuspension
helpviewer_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: 2657d45d-26d2-4d0a-8473-32b652e3321d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 93f17e687ebc3d121db36d8fce8b6bd514867a91
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostgcmanagerthreadisblockingforsuspension-method"></a><span data-ttu-id="a210e-102">IHostGCManager::ThreadIsBlockingForSuspension 方法</span><span class="sxs-lookup"><span data-stu-id="a210e-102">IHostGCManager::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="a210e-103">通知主机从中进行方法调用的线程即将阻止垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="a210e-103">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a210e-104">语法</span><span class="sxs-lookup"><span data-stu-id="a210e-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForSuspension ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a210e-105">返回值</span><span class="sxs-lookup"><span data-stu-id="a210e-105">Return Value</span></span>  
  
|<span data-ttu-id="a210e-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a210e-106">HRESULT</span></span>|<span data-ttu-id="a210e-107">描述</span><span class="sxs-lookup"><span data-stu-id="a210e-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a210e-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="a210e-108">S_OK</span></span>|<span data-ttu-id="a210e-109">`ThreadIsBlockingForSuspension`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="a210e-109">`ThreadIsBlockingForSuspension` returned successfully.</span></span>|  
|<span data-ttu-id="a210e-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a210e-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a210e-111">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="a210e-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a210e-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a210e-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a210e-113">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="a210e-113">The call timed out.</span></span>|  
|<span data-ttu-id="a210e-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a210e-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a210e-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="a210e-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a210e-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a210e-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a210e-117">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="a210e-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a210e-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a210e-118">E_FAIL</span></span>|<span data-ttu-id="a210e-119">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="a210e-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a210e-120">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="a210e-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a210e-121">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="a210e-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a210e-122">备注</span><span class="sxs-lookup"><span data-stu-id="a210e-122">Remarks</span></span>  
 <span data-ttu-id="a210e-123">CLR 通常调用`ThreadIsBlockForSuspension`准备垃圾回收，以便主机有机会非托管任务的线程，重新计划中的方法。</span><span class="sxs-lookup"><span data-stu-id="a210e-123">The CLR typically calls the `ThreadIsBlockForSuspension` method in preparation for a garbage collection, to give the host an opportunity to reschedule the thread for unmanaged tasks.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a210e-124">仅在调用后，主机可以重新计划任务`ThreadIsBlockingForSuspension`。</span><span class="sxs-lookup"><span data-stu-id="a210e-124">The host can reschedule tasks only after a call to `ThreadIsBlockingForSuspension`.</span></span> <span data-ttu-id="a210e-125">在运行时调用后[SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)，主机必须不重新安排任务。</span><span class="sxs-lookup"><span data-stu-id="a210e-125">After the runtime calls [SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md), the host must not reschedule a task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a210e-126">惠?</span><span class="sxs-lookup"><span data-stu-id="a210e-126">Requirements</span></span>  
 <span data-ttu-id="a210e-127">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a210e-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a210e-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a210e-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a210e-129">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a210e-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a210e-130">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a210e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a210e-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="a210e-131">See Also</span></span>  
 [<span data-ttu-id="a210e-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="a210e-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="a210e-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="a210e-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="a210e-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="a210e-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="a210e-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="a210e-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="a210e-136">IHostGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="a210e-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
