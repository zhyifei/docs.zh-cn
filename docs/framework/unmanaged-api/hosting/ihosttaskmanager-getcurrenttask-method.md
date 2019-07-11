---
title: IHostTaskManager::GetCurrentTask 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: f17bca49-90bd-4dee-a5e1-b9a57ea46f85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb3044927e0d9975ed9347cd4f4896b3b75d3e29
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749632"
---
# <a name="ihosttaskmanagergetcurrenttask-method"></a><span data-ttu-id="8ef4b-102">IHostTaskManager::GetCurrentTask 方法</span><span class="sxs-lookup"><span data-stu-id="8ef4b-102">IHostTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="8ef4b-103">获取从其进行此调用的操作系统线程当前正在执行的任务的接口指针。</span><span class="sxs-lookup"><span data-stu-id="8ef4b-103">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ef4b-104">语法</span><span class="sxs-lookup"><span data-stu-id="8ef4b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] IHostTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ef4b-105">参数</span><span class="sxs-lookup"><span data-stu-id="8ef4b-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="8ef4b-106">[out]指向的地址的指针[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)实例，它表示当前正在执行的任务中，则为 null，如果没有任何任务当前正在执行。</span><span class="sxs-lookup"><span data-stu-id="8ef4b-106">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the currently executing task, or null, if no task is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ef4b-107">返回值</span><span class="sxs-lookup"><span data-stu-id="8ef4b-107">Return Value</span></span>  
  
|<span data-ttu-id="8ef4b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8ef4b-108">HRESULT</span></span>|<span data-ttu-id="8ef4b-109">描述</span><span class="sxs-lookup"><span data-stu-id="8ef4b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8ef4b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8ef4b-110">S_OK</span></span>|<span data-ttu-id="8ef4b-111">`GetCurrentTask` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="8ef4b-111">`GetCurrentTask` returned successfully.</span></span>|  
|<span data-ttu-id="8ef4b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8ef4b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8ef4b-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="8ef4b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8ef4b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8ef4b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8ef4b-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="8ef4b-115">The call timed out.</span></span>|  
|<span data-ttu-id="8ef4b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8ef4b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8ef4b-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="8ef4b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8ef4b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8ef4b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8ef4b-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="8ef4b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8ef4b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8ef4b-120">E_FAIL</span></span>|<span data-ttu-id="8ef4b-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="8ef4b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8ef4b-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="8ef4b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8ef4b-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="8ef4b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8ef4b-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="8ef4b-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="8ef4b-125">`GetCurrentTask` 主机控件范围之外的操作系统线程上调用。</span><span class="sxs-lookup"><span data-stu-id="8ef4b-125">`GetCurrentTask` was called on an operating system thread outside the control of the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ef4b-126">备注</span><span class="sxs-lookup"><span data-stu-id="8ef4b-126">Remarks</span></span>  
 <span data-ttu-id="8ef4b-127">主机还可以设置`pTask`参数为 null，以防止它未启动的任务输入 CLR。</span><span class="sxs-lookup"><span data-stu-id="8ef4b-127">The host can also set the `pTask` parameter to null to prevent a task that it did not initiate from entering the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ef4b-128">要求</span><span class="sxs-lookup"><span data-stu-id="8ef4b-128">Requirements</span></span>  
 <span data-ttu-id="8ef4b-129">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8ef4b-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ef4b-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8ef4b-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8ef4b-131">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8ef4b-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ef4b-132">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ef4b-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ef4b-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ef4b-133">See also</span></span>

- [<span data-ttu-id="8ef4b-134">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="8ef4b-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="8ef4b-135">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="8ef4b-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="8ef4b-136">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="8ef4b-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="8ef4b-137">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="8ef4b-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
