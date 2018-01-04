---
title: "IHostTaskManager::CreateTask 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.CreateTask
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::CreateTask
helpviewer_keywords:
- CreateTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::CreateTask method [.NET Framework hosting]
ms.assetid: a6f8ad36-61e1-42b0-9db2-add575646d18
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e5346b2e5395f3d56120ae529a44e3551c00c354
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagercreatetask-method"></a><span data-ttu-id="249d4-102">IHostTaskManager::CreateTask 方法</span><span class="sxs-lookup"><span data-stu-id="249d4-102">IHostTaskManager::CreateTask Method</span></span>
<span data-ttu-id="249d4-103">主机创建一个新的任务的请求。</span><span class="sxs-lookup"><span data-stu-id="249d4-103">Requests that the host create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="249d4-104">语法</span><span class="sxs-lookup"><span data-stu-id="249d4-104">Syntax</span></span>  
  
```  
HRESULT CreateTask (  
    [in]  DWORD stacksize,   
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="249d4-105">参数</span><span class="sxs-lookup"><span data-stu-id="249d4-105">Parameters</span></span>  
 `stacksize`  
 <span data-ttu-id="249d4-106">[in]请求的大小，以字节为单位，请求的堆栈，或 0 （零） 的默认大小。</span><span class="sxs-lookup"><span data-stu-id="249d4-106">[in] The requested size, in bytes, of the requested stack, or 0 (zero) for the default size.</span></span>  
  
 `pStartAddress`  
 <span data-ttu-id="249d4-107">[in]指向函数的任务是执行。</span><span class="sxs-lookup"><span data-stu-id="249d4-107">[in] A pointer to the function the task is to execute.</span></span>  
  
 `pParameter`  
 <span data-ttu-id="249d4-108">[in]指向要传递给函数或如果该函数的用户数据的不带任何参数。</span><span class="sxs-lookup"><span data-stu-id="249d4-108">[in] A pointer to the user data to be passed to the function, or null if the function takes no parameters.</span></span>  
  
 `ppTask`  
 <span data-ttu-id="249d4-109">[out]指向的地址的指针[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)如果无法创建的任务创建的主机或为 null 的实例。</span><span class="sxs-lookup"><span data-stu-id="249d4-109">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance created by the host, or null if the task cannot be created.</span></span> <span data-ttu-id="249d4-110">任务仍保留在挂起状态中显式启动通过调用之前[ihosttask:: Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)。</span><span class="sxs-lookup"><span data-stu-id="249d4-110">The task remains in a suspended state until it is explicitly started by a call to [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="249d4-111">返回值</span><span class="sxs-lookup"><span data-stu-id="249d4-111">Return Value</span></span>  
  
|<span data-ttu-id="249d4-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="249d4-112">HRESULT</span></span>|<span data-ttu-id="249d4-113">描述</span><span class="sxs-lookup"><span data-stu-id="249d4-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="249d4-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="249d4-114">S_OK</span></span>|<span data-ttu-id="249d4-115">`CreateTask`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="249d4-115">`CreateTask` returned successfully.</span></span>|  
|<span data-ttu-id="249d4-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="249d4-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="249d4-117">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="249d4-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="249d4-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="249d4-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="249d4-119">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="249d4-119">The call timed out.</span></span>|  
|<span data-ttu-id="249d4-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="249d4-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="249d4-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="249d4-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="249d4-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="249d4-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="249d4-123">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="249d4-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="249d4-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="249d4-124">E_FAIL</span></span>|<span data-ttu-id="249d4-125">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="249d4-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="249d4-126">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="249d4-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="249d4-127">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="249d4-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="249d4-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="249d4-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="249d4-129">没有足够的内存已可用于创建请求的任务。</span><span class="sxs-lookup"><span data-stu-id="249d4-129">Not enough memory was available to create the requested task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="249d4-130">备注</span><span class="sxs-lookup"><span data-stu-id="249d4-130">Remarks</span></span>  
 <span data-ttu-id="249d4-131">CLR 调用`CreateTask`请求主机创建一个新的任务。</span><span class="sxs-lookup"><span data-stu-id="249d4-131">The CLR calls `CreateTask` to request that the host create a new task.</span></span> <span data-ttu-id="249d4-132">主机返回到的接口指针`IHostTask`实例。</span><span class="sxs-lookup"><span data-stu-id="249d4-132">The host returns an interface pointer to an `IHostTask` instance.</span></span> <span data-ttu-id="249d4-133">通过调用显式启动之前，返回的任务必须保持挂起`IHostTask::Start`。</span><span class="sxs-lookup"><span data-stu-id="249d4-133">The returned task must remain suspended until it is explicitly started by a call to `IHostTask::Start`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="249d4-134">惠?</span><span class="sxs-lookup"><span data-stu-id="249d4-134">Requirements</span></span>  
 <span data-ttu-id="249d4-135">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="249d4-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="249d4-136">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="249d4-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="249d4-137">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="249d4-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="249d4-138">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="249d4-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="249d4-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="249d4-139">See Also</span></span>  
 [<span data-ttu-id="249d4-140">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="249d4-140">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="249d4-141">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="249d4-141">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="249d4-142">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="249d4-142">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="249d4-143">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="249d4-143">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
