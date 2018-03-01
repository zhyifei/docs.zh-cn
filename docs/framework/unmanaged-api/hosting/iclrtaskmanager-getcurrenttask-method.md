---
title: "ICLRTaskManager::GetCurrentTask 方法"
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
- ICLRTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: c0b82a9f-edc6-4878-9c81-48de53c02142
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 04d12e3ff17cc422121e62f08a77f0271ed78346
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskmanagergetcurrenttask-method"></a><span data-ttu-id="e6f64-102">ICLRTaskManager::GetCurrentTask 方法</span><span class="sxs-lookup"><span data-stu-id="e6f64-102">ICLRTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="e6f64-103">获取[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)在方法调用所源自的操作系统线程当前运行的实例。</span><span class="sxs-lookup"><span data-stu-id="e6f64-103">Gets the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance that is currently running on the operating system thread from which the method call originated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6f64-104">语法</span><span class="sxs-lookup"><span data-stu-id="e6f64-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTask (  
    [out] ICLRTask **ppTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e6f64-105">参数</span><span class="sxs-lookup"><span data-stu-id="e6f64-105">Parameters</span></span>  
 `ppTask`  
 <span data-ttu-id="e6f64-106">[out]指向的地址的指针`ICLRTask`源自调用的操作系统线程当前正在执行的实例或如果没有任何任务当前正在执行此线程的 null。</span><span class="sxs-lookup"><span data-stu-id="e6f64-106">[out] A pointer to the address of an `ICLRTask` instance that is currently executing on the operating system thread from which the call originated, or null if no task is currently executing on this thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6f64-107">返回值</span><span class="sxs-lookup"><span data-stu-id="e6f64-107">Return Value</span></span>  
  
|<span data-ttu-id="e6f64-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e6f64-108">HRESULT</span></span>|<span data-ttu-id="e6f64-109">描述</span><span class="sxs-lookup"><span data-stu-id="e6f64-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e6f64-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e6f64-110">S_OK</span></span>|<span data-ttu-id="e6f64-111">该方法返回成功。</span><span class="sxs-lookup"><span data-stu-id="e6f64-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="e6f64-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e6f64-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e6f64-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="e6f64-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e6f64-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e6f64-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e6f64-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="e6f64-115">The call timed out.</span></span>|  
|<span data-ttu-id="e6f64-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e6f64-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e6f64-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="e6f64-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e6f64-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e6f64-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e6f64-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="e6f64-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e6f64-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e6f64-120">E_FAIL</span></span>|<span data-ttu-id="e6f64-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="e6f64-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e6f64-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="e6f64-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e6f64-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="e6f64-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6f64-124">备注</span><span class="sxs-lookup"><span data-stu-id="e6f64-124">Remarks</span></span>  
 <span data-ttu-id="e6f64-125">`ICLRTask`实例`ppTask`参数指向表示当前正在执行的任务的 CLR。</span><span class="sxs-lookup"><span data-stu-id="e6f64-125">The `ICLRTask` instance that the `ppTask` parameter points to represents the currently executing task for the CLR.</span></span> <span data-ttu-id="e6f64-126">`ICLRTask`实例都与相应关联[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)主机表示任务的实例。</span><span class="sxs-lookup"><span data-stu-id="e6f64-126">The `ICLRTask` instance is associated with a corresponding [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the task for the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6f64-127">惠?</span><span class="sxs-lookup"><span data-stu-id="e6f64-127">Requirements</span></span>  
 <span data-ttu-id="e6f64-128">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e6f64-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6f64-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e6f64-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6f64-130">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e6f64-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6f64-131">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6f64-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6f64-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6f64-132">See Also</span></span>  
 [<span data-ttu-id="e6f64-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="e6f64-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="e6f64-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="e6f64-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="e6f64-135">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="e6f64-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="e6f64-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="e6f64-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
