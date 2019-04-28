---
title: ICLRSyncManager::GetMonitorOwner 方法
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetMonitorOwner
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetMonitorOwner
helpviewer_keywords:
- ICLRSyncManager::GetMonitorOwner method [.NET Framework hosting]
- GetMonitorOwner method [.NET Framework hosting]
ms.assetid: 840983a4-396d-47b4-86a0-d35f9b437cdb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b14421bbe71b68ca677cf712512a7f10aa30583
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763615"
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a><span data-ttu-id="36155-102">ICLRSyncManager::GetMonitorOwner 方法</span><span class="sxs-lookup"><span data-stu-id="36155-102">ICLRSyncManager::GetMonitorOwner Method</span></span>
<span data-ttu-id="36155-103">获取[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)拥有由指定的 cookie 标识的监视器的实例。</span><span class="sxs-lookup"><span data-stu-id="36155-103">Gets the [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that owns the monitor identified by the specified cookie.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36155-104">语法</span><span class="sxs-lookup"><span data-stu-id="36155-104">Syntax</span></span>  
  
```  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36155-105">参数</span><span class="sxs-lookup"><span data-stu-id="36155-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="36155-106">[in]与监视器关联的 cookie。</span><span class="sxs-lookup"><span data-stu-id="36155-106">[in] The cookie associated with the monitor.</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="36155-107">[out]一个指向`IHostTask`，当前拥有的监视器或为 null 如果没有任何任务有所有权。</span><span class="sxs-lookup"><span data-stu-id="36155-107">[out] A pointer to the `IHostTask` that currently owns the monitor, or null if no task has ownership.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36155-108">返回值</span><span class="sxs-lookup"><span data-stu-id="36155-108">Return Value</span></span>  
  
|<span data-ttu-id="36155-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="36155-109">HRESULT</span></span>|<span data-ttu-id="36155-110">描述</span><span class="sxs-lookup"><span data-stu-id="36155-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="36155-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="36155-111">S_OK</span></span>|<span data-ttu-id="36155-112">`GetMonitorOwner` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="36155-112">`GetMonitorOwner` returned successfully.</span></span>|  
|<span data-ttu-id="36155-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="36155-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="36155-114">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="36155-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="36155-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="36155-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="36155-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="36155-116">The call timed out.</span></span>|  
|<span data-ttu-id="36155-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="36155-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="36155-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="36155-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="36155-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="36155-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="36155-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="36155-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="36155-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="36155-121">E_FAIL</span></span>|<span data-ttu-id="36155-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="36155-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="36155-123">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="36155-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="36155-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="36155-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36155-125">备注</span><span class="sxs-lookup"><span data-stu-id="36155-125">Remarks</span></span>  
 <span data-ttu-id="36155-126">主机通常会调用`GetMonitorOwner`作为死锁检测机制的一部分。</span><span class="sxs-lookup"><span data-stu-id="36155-126">The host typically calls `GetMonitorOwner` as part of a deadlock-detection mechanism.</span></span> <span data-ttu-id="36155-127">创建使用调用时，cookie 是与监视器关联[ihostsyncmanager:: Createmonitorevent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)。</span><span class="sxs-lookup"><span data-stu-id="36155-127">The cookie is associated with a monitor when it is created by using a call to [IHostSyncManager::CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36155-128">一个调用来发布监视器的支持事件可能会阻止 — 但不是会死锁，如果调用此方法目前正在实行上与该监视器关联的 cookie。</span><span class="sxs-lookup"><span data-stu-id="36155-128">A call to release the event underlying the monitor might block—but will not deadlock—if a call to this method is currently in effect on the cookie associated with that monitor.</span></span> <span data-ttu-id="36155-129">如果用户尝试获得此监视器，也可能会阻止其他任务。</span><span class="sxs-lookup"><span data-stu-id="36155-129">Other tasks might also block if they attempt to acquire this monitor.</span></span>  
  
 <span data-ttu-id="36155-130">`GetMonitorOwner` 始终会立即返回，可以在调用后调用的任何时间`CreateMonitorEvent`。</span><span class="sxs-lookup"><span data-stu-id="36155-130">`GetMonitorOwner` always returns immediately and can be called any time after a call to `CreateMonitorEvent`.</span></span> <span data-ttu-id="36155-131">主机不需要等待，直到某任务正在等待事件。</span><span class="sxs-lookup"><span data-stu-id="36155-131">The host does not need to wait until a task is waiting on the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36155-132">要求</span><span class="sxs-lookup"><span data-stu-id="36155-132">Requirements</span></span>  
 <span data-ttu-id="36155-133">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="36155-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36155-134">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="36155-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="36155-135">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="36155-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="36155-136">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36155-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36155-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="36155-137">See also</span></span>

- [<span data-ttu-id="36155-138">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="36155-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="36155-139">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="36155-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
