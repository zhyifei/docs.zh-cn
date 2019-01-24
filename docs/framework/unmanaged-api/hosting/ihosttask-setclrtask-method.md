---
title: IHostTask::SetCLRTask 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bce823bd6a9ad26a705649a666aeb97dcfa0cdbc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54636542"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="c9603-102">IHostTask::SetCLRTask 方法</span><span class="sxs-lookup"><span data-stu-id="c9603-102">IHostTask::SetCLRTask Method</span></span>
<span data-ttu-id="c9603-103">将相关联`ICLRTask`实例与当前[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="c9603-103">Associates an `ICLRTask` instance with the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9603-104">语法</span><span class="sxs-lookup"><span data-stu-id="c9603-104">Syntax</span></span>  
  
```  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c9603-105">参数</span><span class="sxs-lookup"><span data-stu-id="c9603-105">Parameters</span></span>  
 `pCLRTask`  
 <span data-ttu-id="c9603-106">[in]接口指针`ICLRTask`实例与当前相关联`IHostTask`实例。</span><span class="sxs-lookup"><span data-stu-id="c9603-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9603-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c9603-107">Return Value</span></span>  
  
|<span data-ttu-id="c9603-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c9603-108">HRESULT</span></span>|<span data-ttu-id="c9603-109">描述</span><span class="sxs-lookup"><span data-stu-id="c9603-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c9603-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c9603-110">S_OK</span></span>|<span data-ttu-id="c9603-111">`SetCLRTask` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="c9603-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="c9603-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c9603-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c9603-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="c9603-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c9603-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c9603-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c9603-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="c9603-115">The call timed out.</span></span>|  
|<span data-ttu-id="c9603-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c9603-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c9603-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="c9603-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c9603-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c9603-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c9603-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="c9603-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c9603-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c9603-120">E_FAIL</span></span>|<span data-ttu-id="c9603-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="c9603-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c9603-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="c9603-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c9603-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c9603-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9603-124">备注</span><span class="sxs-lookup"><span data-stu-id="c9603-124">Remarks</span></span>  
 <span data-ttu-id="c9603-125">CLR 调用`SetCLRTask`相关联`ICLRTask`实例与当前`IHostTask`实例，已通过调用[ihosttaskmanager:: Createtask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)。</span><span class="sxs-lookup"><span data-stu-id="c9603-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9603-126">要求</span><span class="sxs-lookup"><span data-stu-id="c9603-126">Requirements</span></span>  
 <span data-ttu-id="c9603-127">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c9603-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9603-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c9603-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c9603-129">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c9603-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c9603-130">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9603-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9603-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9603-131">See also</span></span>
- [<span data-ttu-id="c9603-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="c9603-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="c9603-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="c9603-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="c9603-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="c9603-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="c9603-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="c9603-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
