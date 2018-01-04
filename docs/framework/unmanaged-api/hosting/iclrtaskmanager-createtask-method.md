---
title: "ICLRTaskManager::CreateTask 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTaskManager.CreateTask
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTaskManager::CreateTask
helpviewer_keywords:
- ICLRTaskManager::CreateTask method [.NET Framework hosting]
- CreateTask method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: eea570d9-2e53-4320-9ea0-eb777bf9dcf3
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e9e78db6e43397709f913f8f79a617221f98db87
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="b02e2-102">ICLRTaskManager::CreateTask 方法</span><span class="sxs-lookup"><span data-stu-id="b02e2-102">ICLRTaskManager::CreateTask Method</span></span>
<span data-ttu-id="b02e2-103">显式请求公共语言运行时 (CLR) 创建新任务。</span><span class="sxs-lookup"><span data-stu-id="b02e2-103">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b02e2-104">语法</span><span class="sxs-lookup"><span data-stu-id="b02e2-104">Syntax</span></span>  
  
```  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b02e2-105">参数</span><span class="sxs-lookup"><span data-stu-id="b02e2-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="b02e2-106">[out]新创建的地址指针[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)，则为 null，如果无法创建任务。</span><span class="sxs-lookup"><span data-stu-id="b02e2-106">[out] A pointer to the address of a newly created [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b02e2-107">返回值</span><span class="sxs-lookup"><span data-stu-id="b02e2-107">Return Value</span></span>  
  
|<span data-ttu-id="b02e2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b02e2-108">HRESULT</span></span>|<span data-ttu-id="b02e2-109">描述</span><span class="sxs-lookup"><span data-stu-id="b02e2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b02e2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b02e2-110">S_OK</span></span>|<span data-ttu-id="b02e2-111">该方法返回成功。</span><span class="sxs-lookup"><span data-stu-id="b02e2-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="b02e2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b02e2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b02e2-113">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="b02e2-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b02e2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b02e2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b02e2-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="b02e2-115">The call timed out.</span></span>|  
|<span data-ttu-id="b02e2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b02e2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b02e2-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="b02e2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b02e2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b02e2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b02e2-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="b02e2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b02e2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b02e2-120">E_FAIL</span></span>|<span data-ttu-id="b02e2-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="b02e2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b02e2-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="b02e2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b02e2-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="b02e2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b02e2-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b02e2-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="b02e2-125">没有足够的内存可分配请求的资源。</span><span class="sxs-lookup"><span data-stu-id="b02e2-125">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b02e2-126">备注</span><span class="sxs-lookup"><span data-stu-id="b02e2-126">Remarks</span></span>  
 <span data-ttu-id="b02e2-127">用户代码创建一个线程通过使用中的类型时，CLR 将创建新任务自动进行初始化，<xref:System.Threading>命名空间，或当增加线程池的大小。</span><span class="sxs-lookup"><span data-stu-id="b02e2-127">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="b02e2-128">它还会在非托管的代码调用托管函数创建任务。</span><span class="sxs-lookup"><span data-stu-id="b02e2-128">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 <span data-ttu-id="b02e2-129">`CreateTask`允许宿主发出显式请求 CLR 创建新任务。</span><span class="sxs-lookup"><span data-stu-id="b02e2-129">`CreateTask` allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="b02e2-130">例如，主机可以调用此方法来预先初始化数据结构。</span><span class="sxs-lookup"><span data-stu-id="b02e2-130">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b02e2-131">新的任务返回处于挂起状态和向导仍然保持挂起，直到主机显式调用[ihosttask:: Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)。</span><span class="sxs-lookup"><span data-stu-id="b02e2-131">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b02e2-132">惠?</span><span class="sxs-lookup"><span data-stu-id="b02e2-132">Requirements</span></span>  
 <span data-ttu-id="b02e2-133">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b02e2-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b02e2-134">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b02e2-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b02e2-135">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b02e2-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b02e2-136">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b02e2-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b02e2-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="b02e2-137">See Also</span></span>  
 [<span data-ttu-id="b02e2-138">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="b02e2-138">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="b02e2-139">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="b02e2-139">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="b02e2-140">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="b02e2-140">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="b02e2-141">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="b02e2-141">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
