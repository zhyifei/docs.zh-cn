---
title: ICLRTaskManager::CreateTask 方法
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::CreateTask
helpviewer_keywords:
- ICLRTaskManager::CreateTask method [.NET Framework hosting]
- CreateTask method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: eea570d9-2e53-4320-9ea0-eb777bf9dcf3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 804a295cf74067eb23ed8e8c860252a1f2fcf5d5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770187"
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="65dc6-102">ICLRTaskManager::CreateTask 方法</span><span class="sxs-lookup"><span data-stu-id="65dc6-102">ICLRTaskManager::CreateTask Method</span></span>
<span data-ttu-id="65dc6-103">显式请求公共语言运行时 (CLR) 创建新的任务。</span><span class="sxs-lookup"><span data-stu-id="65dc6-103">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65dc6-104">语法</span><span class="sxs-lookup"><span data-stu-id="65dc6-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65dc6-105">参数</span><span class="sxs-lookup"><span data-stu-id="65dc6-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="65dc6-106">[out]指向新创建的地址的指针[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)，则为 null，如果无法创建该任务。</span><span class="sxs-lookup"><span data-stu-id="65dc6-106">[out] A pointer to the address of a newly created [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65dc6-107">返回值</span><span class="sxs-lookup"><span data-stu-id="65dc6-107">Return Value</span></span>  
  
|<span data-ttu-id="65dc6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="65dc6-108">HRESULT</span></span>|<span data-ttu-id="65dc6-109">描述</span><span class="sxs-lookup"><span data-stu-id="65dc6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="65dc6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="65dc6-110">S_OK</span></span>|<span data-ttu-id="65dc6-111">该方法成功返回。</span><span class="sxs-lookup"><span data-stu-id="65dc6-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="65dc6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="65dc6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="65dc6-113">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="65dc6-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="65dc6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="65dc6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="65dc6-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="65dc6-115">The call timed out.</span></span>|  
|<span data-ttu-id="65dc6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="65dc6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="65dc6-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="65dc6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="65dc6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="65dc6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="65dc6-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="65dc6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="65dc6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="65dc6-120">E_FAIL</span></span>|<span data-ttu-id="65dc6-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="65dc6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="65dc6-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="65dc6-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="65dc6-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="65dc6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="65dc6-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="65dc6-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="65dc6-125">没有足够的内存是可用于分配请求的资源。</span><span class="sxs-lookup"><span data-stu-id="65dc6-125">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65dc6-126">备注</span><span class="sxs-lookup"><span data-stu-id="65dc6-126">Remarks</span></span>  
 <span data-ttu-id="65dc6-127">用户代码创建一个线程使用中的类型时，CLR 将创建新任务时初始化，自动<xref:System.Threading>命名空间，或如果增加线程池的大小。</span><span class="sxs-lookup"><span data-stu-id="65dc6-127">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="65dc6-128">当非托管的代码到托管函数的调用时，它还会创建任务。</span><span class="sxs-lookup"><span data-stu-id="65dc6-128">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 <span data-ttu-id="65dc6-129">`CreateTask` 允许主机以使 CLR 创建新的任务的显式请求。</span><span class="sxs-lookup"><span data-stu-id="65dc6-129">`CreateTask` allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="65dc6-130">例如，主机可以调用此方法来预先初始化数据结构。</span><span class="sxs-lookup"><span data-stu-id="65dc6-130">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="65dc6-131">新的任务返回一个处于挂起状态并保持挂起状态，直到主机显式调用[ihosttask:: Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)。</span><span class="sxs-lookup"><span data-stu-id="65dc6-131">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65dc6-132">要求</span><span class="sxs-lookup"><span data-stu-id="65dc6-132">Requirements</span></span>  
 <span data-ttu-id="65dc6-133">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="65dc6-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65dc6-134">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="65dc6-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="65dc6-135">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="65dc6-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65dc6-136">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65dc6-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65dc6-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="65dc6-137">See also</span></span>

- [<span data-ttu-id="65dc6-138">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="65dc6-138">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="65dc6-139">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="65dc6-139">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="65dc6-140">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="65dc6-140">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="65dc6-141">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="65dc6-141">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
