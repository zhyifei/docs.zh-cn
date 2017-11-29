---
title: "IHostTaskManager::GetCurrentTask 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.GetCurrentTask
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: f17bca49-90bd-4dee-a5e1-b9a57ea46f85
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 92b4ed0cd33d2e9d3399e409d2dba4eeb14a2f5e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagergetcurrenttask-method"></a><span data-ttu-id="09226-102">IHostTaskManager::GetCurrentTask 方法</span><span class="sxs-lookup"><span data-stu-id="09226-102">IHostTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="09226-103">获取从中进行此调用的操作系统线程当前正在执行的任务的接口指针。</span><span class="sxs-lookup"><span data-stu-id="09226-103">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09226-104">语法</span><span class="sxs-lookup"><span data-stu-id="09226-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTask (  
    [out] IHostTask **pTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="09226-105">参数</span><span class="sxs-lookup"><span data-stu-id="09226-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="09226-106">[out]指向的地址的指针[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)表示的当前正在执行的任务或为 null，如果没有任何任务当前正在执行的实例。</span><span class="sxs-lookup"><span data-stu-id="09226-106">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the currently executing task, or null, if no task is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09226-107">返回值</span><span class="sxs-lookup"><span data-stu-id="09226-107">Return Value</span></span>  
  
|<span data-ttu-id="09226-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="09226-108">HRESULT</span></span>|<span data-ttu-id="09226-109">描述</span><span class="sxs-lookup"><span data-stu-id="09226-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="09226-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="09226-110">S_OK</span></span>|<span data-ttu-id="09226-111">`GetCurrentTask`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="09226-111">`GetCurrentTask` returned successfully.</span></span>|  
|<span data-ttu-id="09226-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="09226-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="09226-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="09226-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="09226-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="09226-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="09226-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="09226-115">The call timed out.</span></span>|  
|<span data-ttu-id="09226-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="09226-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="09226-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="09226-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="09226-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="09226-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="09226-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="09226-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="09226-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="09226-120">E_FAIL</span></span>|<span data-ttu-id="09226-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="09226-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="09226-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="09226-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="09226-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="09226-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="09226-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="09226-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="09226-125">`GetCurrentTask`主机控件范围之外的操作系统线程上调用。</span><span class="sxs-lookup"><span data-stu-id="09226-125">`GetCurrentTask` was called on an operating system thread outside the control of the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09226-126">备注</span><span class="sxs-lookup"><span data-stu-id="09226-126">Remarks</span></span>  
 <span data-ttu-id="09226-127">主机还可以设置`pTask`参数为 null，以便防止它未启动的任务进入 CLR。</span><span class="sxs-lookup"><span data-stu-id="09226-127">The host can also set the `pTask` parameter to null to prevent a task that it did not initiate from entering the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09226-128">要求</span><span class="sxs-lookup"><span data-stu-id="09226-128">Requirements</span></span>  
 <span data-ttu-id="09226-129">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="09226-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09226-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="09226-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="09226-131">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="09226-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="09226-132">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09226-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09226-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09226-133">See Also</span></span>  
 [<span data-ttu-id="09226-134">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="09226-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="09226-135">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="09226-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="09226-136">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="09226-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="09226-137">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="09226-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
