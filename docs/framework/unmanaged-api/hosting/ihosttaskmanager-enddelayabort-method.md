---
title: "IHostTaskManager::EndDelayAbort 方法"
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
- IHostTaskManager.EndDelayAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndDelayAbort
helpviewer_keywords:
- EndDelayAbort method [.NET Framework hosting]
- IHostTaskManager::EndDelayAbort method [.NET Framework hosting]
ms.assetid: 6e02facb-2504-4356-9af5-0cee1f8436a7
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7a38f024c408065ffcd0e0278b76c064ff148bc6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagerenddelayabort-method"></a><span data-ttu-id="2b9b0-102">IHostTaskManager::EndDelayAbort 方法</span><span class="sxs-lookup"><span data-stu-id="2b9b0-102">IHostTaskManager::EndDelayAbort Method</span></span>
<span data-ttu-id="2b9b0-103">通知宿主托管代码正在退出在其中不必须中止当前的任务，周期以下以前调用[ihosttaskmanager:: Begindelayabort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md)。</span><span class="sxs-lookup"><span data-stu-id="2b9b0-103">Notifies the host that managed code is exiting the period in which the current task must not be aborted, following an earlier call to [IHostTaskManager::BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b9b0-104">语法</span><span class="sxs-lookup"><span data-stu-id="2b9b0-104">Syntax</span></span>  
  
```  
HRESULT EndDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2b9b0-105">返回值</span><span class="sxs-lookup"><span data-stu-id="2b9b0-105">Return Value</span></span>  
  
|<span data-ttu-id="2b9b0-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2b9b0-106">HRESULT</span></span>|<span data-ttu-id="2b9b0-107">描述</span><span class="sxs-lookup"><span data-stu-id="2b9b0-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2b9b0-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="2b9b0-108">S_OK</span></span>|<span data-ttu-id="2b9b0-109">`EndDelayAbort`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="2b9b0-109">`EndDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="2b9b0-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2b9b0-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2b9b0-111">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="2b9b0-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2b9b0-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2b9b0-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2b9b0-113">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="2b9b0-113">The call timed out.</span></span>|  
|<span data-ttu-id="2b9b0-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2b9b0-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2b9b0-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="2b9b0-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2b9b0-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2b9b0-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2b9b0-117">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="2b9b0-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2b9b0-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2b9b0-118">E_FAIL</span></span>|<span data-ttu-id="2b9b0-119">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="2b9b0-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2b9b0-120">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="2b9b0-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2b9b0-121">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="2b9b0-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2b9b0-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="2b9b0-122">E_UNEXPECTED</span></span>|<span data-ttu-id="2b9b0-123">`EndDelayAbort`已调用相应地调用`BeginDelayAbort`。</span><span class="sxs-lookup"><span data-stu-id="2b9b0-123">`EndDelayAbort` was called without a corresponding call to `BeginDelayAbort`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b9b0-124">备注</span><span class="sxs-lookup"><span data-stu-id="2b9b0-124">Remarks</span></span>  
 <span data-ttu-id="2b9b0-125">CLR 将对应调用`BeginDelayAbort`在当前任务之前调用`EndDelayAbort`。</span><span class="sxs-lookup"><span data-stu-id="2b9b0-125">The CLR makes a corresponding call to `BeginDelayAbort` on the current task before calling `EndDelayAbort`.</span></span> <span data-ttu-id="2b9b0-126">此类相应地调用，没有主机的实现[IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)应返回从 E_UNEXPECTED `EndDelayAbort`，并且应采取任何操作。</span><span class="sxs-lookup"><span data-stu-id="2b9b0-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED from `EndDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b9b0-127">惠?</span><span class="sxs-lookup"><span data-stu-id="2b9b0-127">Requirements</span></span>  
 <span data-ttu-id="2b9b0-128">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2b9b0-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b9b0-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2b9b0-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2b9b0-130">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2b9b0-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2b9b0-131">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b9b0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b9b0-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b9b0-132">See Also</span></span>  
 <xref:System.Threading>  
 [<span data-ttu-id="2b9b0-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="2b9b0-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="2b9b0-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="2b9b0-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="2b9b0-135">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="2b9b0-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="2b9b0-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="2b9b0-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
