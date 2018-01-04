---
title: "IHostTaskManager::BeginDelayAbort 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.BeginDelayAbort
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::BeginDelayAbort
helpviewer_keywords:
- BeginDelayAbort method [.NET Framework hosting]
- IHostTaskManager::BeginDelayAbort method [.NET Framework hosting]
ms.assetid: 75f42a8b-ed68-4718-a030-a179cfba7d72
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a6b37c87f26013dab95f7607e03463437b9797a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="9716a-102">IHostTaskManager::BeginDelayAbort 方法</span><span class="sxs-lookup"><span data-stu-id="9716a-102">IHostTaskManager::BeginDelayAbort Method</span></span>
<span data-ttu-id="9716a-103">通知宿主托管代码正在进入不能在其中中止当前任务的周期。</span><span class="sxs-lookup"><span data-stu-id="9716a-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9716a-104">语法</span><span class="sxs-lookup"><span data-stu-id="9716a-104">Syntax</span></span>  
  
```  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9716a-105">返回值</span><span class="sxs-lookup"><span data-stu-id="9716a-105">Return Value</span></span>  
  
|<span data-ttu-id="9716a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9716a-106">HRESULT</span></span>|<span data-ttu-id="9716a-107">描述</span><span class="sxs-lookup"><span data-stu-id="9716a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9716a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9716a-108">S_OK</span></span>|<span data-ttu-id="9716a-109">`BeginDelayAbort`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="9716a-109">`BeginDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="9716a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9716a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9716a-111">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="9716a-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9716a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9716a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9716a-113">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="9716a-113">The call timed out.</span></span>|  
|<span data-ttu-id="9716a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9716a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9716a-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="9716a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9716a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9716a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9716a-117">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="9716a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9716a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9716a-118">E_FAIL</span></span>|<span data-ttu-id="9716a-119">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="9716a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9716a-120">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="9716a-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9716a-121">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="9716a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9716a-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="9716a-122">E_UNEXPECTED</span></span>|<span data-ttu-id="9716a-123">`BeginDelayAbort`已调用，但相应地调用[EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md)尚未收到。</span><span class="sxs-lookup"><span data-stu-id="9716a-123">`BeginDelayAbort` has already been called, but the corresponding call to [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9716a-124">备注</span><span class="sxs-lookup"><span data-stu-id="9716a-124">Remarks</span></span>  
 <span data-ttu-id="9716a-125">主机必须中止当前的任务，直到`EndDelayAbort`调用。</span><span class="sxs-lookup"><span data-stu-id="9716a-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="9716a-126">如果再次调用`BeginDelayAbort`对的干预调用，不建立`EndDelayAbort`，主机应返回从 E_UNEXPECTED `BeginDelayAbort`，并且应采取任何操作。</span><span class="sxs-lookup"><span data-stu-id="9716a-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9716a-127">惠?</span><span class="sxs-lookup"><span data-stu-id="9716a-127">Requirements</span></span>  
 <span data-ttu-id="9716a-128">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9716a-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9716a-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9716a-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9716a-130">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9716a-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9716a-131">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9716a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9716a-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="9716a-132">See Also</span></span>  
 [<span data-ttu-id="9716a-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="9716a-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="9716a-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="9716a-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="9716a-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="9716a-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="9716a-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="9716a-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
