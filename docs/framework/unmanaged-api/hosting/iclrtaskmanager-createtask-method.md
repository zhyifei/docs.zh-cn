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
ms.openlocfilehash: a89ea76d78431ae8833602588379d5150e473710
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938309"
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="0fa4c-102">ICLRTaskManager::CreateTask 方法</span><span class="sxs-lookup"><span data-stu-id="0fa4c-102">ICLRTaskManager::CreateTask Method</span></span>
<span data-ttu-id="0fa4c-103">显式请求公共语言运行时 (CLR) 创建新任务。</span><span class="sxs-lookup"><span data-stu-id="0fa4c-103">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fa4c-104">语法</span><span class="sxs-lookup"><span data-stu-id="0fa4c-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fa4c-105">参数</span><span class="sxs-lookup"><span data-stu-id="0fa4c-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="0fa4c-106">弄指向新创建的[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)的地址的指针; 如果无法创建任务, 则为 null。</span><span class="sxs-lookup"><span data-stu-id="0fa4c-106">[out] A pointer to the address of a newly created [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0fa4c-107">返回值</span><span class="sxs-lookup"><span data-stu-id="0fa4c-107">Return Value</span></span>  
  
|<span data-ttu-id="0fa4c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0fa4c-108">HRESULT</span></span>|<span data-ttu-id="0fa4c-109">描述</span><span class="sxs-lookup"><span data-stu-id="0fa4c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0fa4c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0fa4c-110">S_OK</span></span>|<span data-ttu-id="0fa4c-111">方法已成功返回。</span><span class="sxs-lookup"><span data-stu-id="0fa4c-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="0fa4c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0fa4c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0fa4c-113">CLR 未加载到进程中, 或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="0fa4c-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0fa4c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0fa4c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0fa4c-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="0fa4c-115">The call timed out.</span></span>|  
|<span data-ttu-id="0fa4c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0fa4c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0fa4c-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="0fa4c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0fa4c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0fa4c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0fa4c-119">已阻止的线程或纤程正在等待某个事件时, 该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="0fa4c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0fa4c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0fa4c-120">E_FAIL</span></span>|<span data-ttu-id="0fa4c-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="0fa4c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0fa4c-122">当方法返回 E_FAIL 时, CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="0fa4c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0fa4c-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="0fa4c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0fa4c-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0fa4c-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="0fa4c-125">没有足够的内存可用于分配请求的资源。</span><span class="sxs-lookup"><span data-stu-id="0fa4c-125">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0fa4c-126">备注</span><span class="sxs-lookup"><span data-stu-id="0fa4c-126">Remarks</span></span>  
 <span data-ttu-id="0fa4c-127">当用户代码通过使用<xref:System.Threading>命名空间中的类型创建线程时, 或者当线程池的大小增加时, CLR 将自动创建一个新任务。</span><span class="sxs-lookup"><span data-stu-id="0fa4c-127">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="0fa4c-128">当非托管代码调用托管函数时, 它还会创建任务。</span><span class="sxs-lookup"><span data-stu-id="0fa4c-128">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 <span data-ttu-id="0fa4c-129">`CreateTask`允许宿主发出显式请求, 指示 CLR 创建了一个新的任务。</span><span class="sxs-lookup"><span data-stu-id="0fa4c-129">`CreateTask` allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="0fa4c-130">例如, 宿主可以调用此方法来预先初始化数据结构。</span><span class="sxs-lookup"><span data-stu-id="0fa4c-130">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0fa4c-131">新任务在挂起状态返回, 并保持挂起状态, 直到主机显式调用[IHostTask:: Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)。</span><span class="sxs-lookup"><span data-stu-id="0fa4c-131">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fa4c-132">要求</span><span class="sxs-lookup"><span data-stu-id="0fa4c-132">Requirements</span></span>  
 <span data-ttu-id="0fa4c-133">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0fa4c-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fa4c-134">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0fa4c-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0fa4c-135">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="0fa4c-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0fa4c-136">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fa4c-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fa4c-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="0fa4c-137">See also</span></span>

- [<span data-ttu-id="0fa4c-138">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="0fa4c-138">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="0fa4c-139">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="0fa4c-139">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="0fa4c-140">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="0fa4c-140">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="0fa4c-141">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="0fa4c-141">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
