---
title: IHostTaskManager::CreateTask 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CreateTask
helpviewer_keywords:
- CreateTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::CreateTask method [.NET Framework hosting]
ms.assetid: a6f8ad36-61e1-42b0-9db2-add575646d18
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2eddb11ab56bae5243ea7d00614090bbfe774f71
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096376"
---
# <a name="ihosttaskmanagercreatetask-method"></a><span data-ttu-id="f25e5-102">IHostTaskManager::CreateTask 方法</span><span class="sxs-lookup"><span data-stu-id="f25e5-102">IHostTaskManager::CreateTask Method</span></span>
<span data-ttu-id="f25e5-103">主机创建新的任务的请求。</span><span class="sxs-lookup"><span data-stu-id="f25e5-103">Requests that the host create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f25e5-104">语法</span><span class="sxs-lookup"><span data-stu-id="f25e5-104">Syntax</span></span>  
  
```  
HRESULT CreateTask (  
    [in]  DWORD stacksize,   
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f25e5-105">参数</span><span class="sxs-lookup"><span data-stu-id="f25e5-105">Parameters</span></span>  
 `stacksize`  
 <span data-ttu-id="f25e5-106">[in]请求的大小，以字节为单位的所请求的堆栈或事件的默认大小为 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="f25e5-106">[in] The requested size, in bytes, of the requested stack, or 0 (zero) for the default size.</span></span>  
  
 `pStartAddress`  
 <span data-ttu-id="f25e5-107">[in]指向函数的任务是执行。</span><span class="sxs-lookup"><span data-stu-id="f25e5-107">[in] A pointer to the function the task is to execute.</span></span>  
  
 `pParameter`  
 <span data-ttu-id="f25e5-108">[in]对用户数据将传递给函数，则为 null 函数的指针不带任何参数。</span><span class="sxs-lookup"><span data-stu-id="f25e5-108">[in] A pointer to the user data to be passed to the function, or null if the function takes no parameters.</span></span>  
  
 `ppTask`  
 <span data-ttu-id="f25e5-109">[out]指向的地址的指针[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)创建主机，则为 null，如果不能创建任务实例。</span><span class="sxs-lookup"><span data-stu-id="f25e5-109">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance created by the host, or null if the task cannot be created.</span></span> <span data-ttu-id="f25e5-110">任务保持挂起状态，直到它显式启动通过调用[ihosttask:: Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)。</span><span class="sxs-lookup"><span data-stu-id="f25e5-110">The task remains in a suspended state until it is explicitly started by a call to [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f25e5-111">返回值</span><span class="sxs-lookup"><span data-stu-id="f25e5-111">Return Value</span></span>  
  
|<span data-ttu-id="f25e5-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f25e5-112">HRESULT</span></span>|<span data-ttu-id="f25e5-113">描述</span><span class="sxs-lookup"><span data-stu-id="f25e5-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f25e5-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="f25e5-114">S_OK</span></span>|`CreateTask` <span data-ttu-id="f25e5-115">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="f25e5-115">returned successfully.</span></span>|  
|<span data-ttu-id="f25e5-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f25e5-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f25e5-117">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="f25e5-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f25e5-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f25e5-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f25e5-119">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="f25e5-119">The call timed out.</span></span>|  
|<span data-ttu-id="f25e5-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f25e5-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f25e5-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="f25e5-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f25e5-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f25e5-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f25e5-123">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="f25e5-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f25e5-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f25e5-124">E_FAIL</span></span>|<span data-ttu-id="f25e5-125">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="f25e5-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f25e5-126">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="f25e5-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f25e5-127">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="f25e5-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f25e5-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f25e5-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="f25e5-129">没有足够的内存是可用于创建请求的任务。</span><span class="sxs-lookup"><span data-stu-id="f25e5-129">Not enough memory was available to create the requested task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f25e5-130">备注</span><span class="sxs-lookup"><span data-stu-id="f25e5-130">Remarks</span></span>  
 <span data-ttu-id="f25e5-131">CLR 调用`CreateTask`请求主机创建新的任务。</span><span class="sxs-lookup"><span data-stu-id="f25e5-131">The CLR calls `CreateTask` to request that the host create a new task.</span></span> <span data-ttu-id="f25e5-132">主机返回到的接口指针`IHostTask`实例。</span><span class="sxs-lookup"><span data-stu-id="f25e5-132">The host returns an interface pointer to an `IHostTask` instance.</span></span> <span data-ttu-id="f25e5-133">返回的任务必须保持挂起状态直到显式首先调用`IHostTask::Start`。</span><span class="sxs-lookup"><span data-stu-id="f25e5-133">The returned task must remain suspended until it is explicitly started by a call to `IHostTask::Start`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f25e5-134">要求</span><span class="sxs-lookup"><span data-stu-id="f25e5-134">Requirements</span></span>  
 <span data-ttu-id="f25e5-135">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f25e5-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f25e5-136">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f25e5-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f25e5-137">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f25e5-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="f25e5-138">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="f25e5-138">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f25e5-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="f25e5-139">See also</span></span>

- [<span data-ttu-id="f25e5-140">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="f25e5-140">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="f25e5-141">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="f25e5-141">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="f25e5-142">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="f25e5-142">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="f25e5-143">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="f25e5-143">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
