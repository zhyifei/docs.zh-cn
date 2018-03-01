---
title: "IHostTask::SetCLRTask 方法"
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
- IHostTask.SetCLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetCLRTask
helpviewer_keywords:
- SetCLRTask method [.NET Framework hosting]
- IHostTask::SetCLRTask method [.NET Framework hosting]
ms.assetid: e9d39c80-41a1-49e7-bb5e-ea3433bfb5d7
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 680ad2c13d8d6fc24134c9399cffb236bd637057
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="1d040-102">IHostTask::SetCLRTask 方法</span><span class="sxs-lookup"><span data-stu-id="1d040-102">IHostTask::SetCLRTask Method</span></span>
<span data-ttu-id="1d040-103">将相关联`ICLRTask`与当前实例[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="1d040-103">Associates an `ICLRTask` instance with the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d040-104">语法</span><span class="sxs-lookup"><span data-stu-id="1d040-104">Syntax</span></span>  
  
```  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1d040-105">参数</span><span class="sxs-lookup"><span data-stu-id="1d040-105">Parameters</span></span>  
 `pCLRTask`  
 <span data-ttu-id="1d040-106">[in]接口指针`ICLRTask`实例设置为与当前关联`IHostTask`实例。</span><span class="sxs-lookup"><span data-stu-id="1d040-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d040-107">返回值</span><span class="sxs-lookup"><span data-stu-id="1d040-107">Return Value</span></span>  
  
|<span data-ttu-id="1d040-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1d040-108">HRESULT</span></span>|<span data-ttu-id="1d040-109">描述</span><span class="sxs-lookup"><span data-stu-id="1d040-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1d040-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1d040-110">S_OK</span></span>|<span data-ttu-id="1d040-111">`SetCLRTask`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="1d040-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="1d040-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1d040-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1d040-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="1d040-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1d040-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1d040-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1d040-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="1d040-115">The call timed out.</span></span>|  
|<span data-ttu-id="1d040-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1d040-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1d040-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="1d040-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1d040-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1d040-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1d040-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="1d040-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1d040-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1d040-120">E_FAIL</span></span>|<span data-ttu-id="1d040-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="1d040-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1d040-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="1d040-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1d040-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="1d040-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d040-124">备注</span><span class="sxs-lookup"><span data-stu-id="1d040-124">Remarks</span></span>  
 <span data-ttu-id="1d040-125">CLR 调用`SetCLRTask`关联`ICLRTask`与当前实例`IHostTask`实例，这由调用[ihosttaskmanager:: Createtask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)。</span><span class="sxs-lookup"><span data-stu-id="1d040-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d040-126">惠?</span><span class="sxs-lookup"><span data-stu-id="1d040-126">Requirements</span></span>  
 <span data-ttu-id="1d040-127">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1d040-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d040-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1d040-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d040-129">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1d040-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d040-130">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d040-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d040-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="1d040-131">See Also</span></span>  
 [<span data-ttu-id="1d040-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="1d040-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="1d040-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="1d040-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="1d040-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="1d040-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="1d040-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="1d040-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
