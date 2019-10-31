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
ms.openlocfilehash: fcb78dd5374ff97f23d7dfea63fe33fa96836958
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124532"
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="eaa85-102">ICLRTaskManager::CreateTask 方法</span><span class="sxs-lookup"><span data-stu-id="eaa85-102">ICLRTaskManager::CreateTask Method</span></span>
<span data-ttu-id="eaa85-103">显式请求公共语言运行时（CLR）创建新任务。</span><span class="sxs-lookup"><span data-stu-id="eaa85-103">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaa85-104">语法</span><span class="sxs-lookup"><span data-stu-id="eaa85-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eaa85-105">参数</span><span class="sxs-lookup"><span data-stu-id="eaa85-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="eaa85-106">弄指向新创建的[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)的地址的指针; 如果无法创建任务，则为 null。</span><span class="sxs-lookup"><span data-stu-id="eaa85-106">[out] A pointer to the address of a newly created [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eaa85-107">返回值</span><span class="sxs-lookup"><span data-stu-id="eaa85-107">Return Value</span></span>  
  
|<span data-ttu-id="eaa85-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eaa85-108">HRESULT</span></span>|<span data-ttu-id="eaa85-109">描述</span><span class="sxs-lookup"><span data-stu-id="eaa85-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eaa85-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="eaa85-110">S_OK</span></span>|<span data-ttu-id="eaa85-111">方法已成功返回。</span><span class="sxs-lookup"><span data-stu-id="eaa85-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="eaa85-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="eaa85-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="eaa85-113">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="eaa85-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="eaa85-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="eaa85-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="eaa85-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="eaa85-115">The call timed out.</span></span>|  
|<span data-ttu-id="eaa85-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="eaa85-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="eaa85-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="eaa85-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="eaa85-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="eaa85-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="eaa85-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="eaa85-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="eaa85-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="eaa85-120">E_FAIL</span></span>|<span data-ttu-id="eaa85-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="eaa85-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="eaa85-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="eaa85-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="eaa85-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="eaa85-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="eaa85-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="eaa85-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="eaa85-125">没有足够的内存可用于分配请求的资源。</span><span class="sxs-lookup"><span data-stu-id="eaa85-125">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eaa85-126">备注</span><span class="sxs-lookup"><span data-stu-id="eaa85-126">Remarks</span></span>  
 <span data-ttu-id="eaa85-127">当用户代码通过使用 <xref:System.Threading> 命名空间中的类型创建线程时，或者当线程池的大小增加时，CLR 将自动创建一个新任务。</span><span class="sxs-lookup"><span data-stu-id="eaa85-127">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="eaa85-128">当非托管代码调用托管函数时，它还会创建任务。</span><span class="sxs-lookup"><span data-stu-id="eaa85-128">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 <span data-ttu-id="eaa85-129">`CreateTask` 允许主机发出显式请求，指示 CLR 创建新任务。</span><span class="sxs-lookup"><span data-stu-id="eaa85-129">`CreateTask` allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="eaa85-130">例如，宿主可以调用此方法来预先初始化数据结构。</span><span class="sxs-lookup"><span data-stu-id="eaa85-130">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="eaa85-131">新任务在挂起状态返回，并保持挂起状态，直到主机显式调用[IHostTask：： Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)。</span><span class="sxs-lookup"><span data-stu-id="eaa85-131">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eaa85-132">要求</span><span class="sxs-lookup"><span data-stu-id="eaa85-132">Requirements</span></span>  
 <span data-ttu-id="eaa85-133">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eaa85-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eaa85-134">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="eaa85-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eaa85-135">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="eaa85-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eaa85-136">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eaa85-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaa85-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="eaa85-137">See also</span></span>

- [<span data-ttu-id="eaa85-138">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="eaa85-138">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="eaa85-139">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="eaa85-139">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="eaa85-140">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="eaa85-140">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="eaa85-141">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="eaa85-141">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
