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
ms.openlocfilehash: 3aec11674275769bb5c4b68521a40a72a1d68a22
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124686"
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a><span data-ttu-id="a1627-102">ICLRSyncManager::GetMonitorOwner 方法</span><span class="sxs-lookup"><span data-stu-id="a1627-102">ICLRSyncManager::GetMonitorOwner Method</span></span>
<span data-ttu-id="a1627-103">获取拥有由指定 cookie 标识的监视器的[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="a1627-103">Gets the [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that owns the monitor identified by the specified cookie.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1627-104">语法</span><span class="sxs-lookup"><span data-stu-id="a1627-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1627-105">参数</span><span class="sxs-lookup"><span data-stu-id="a1627-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="a1627-106">中与监视器关联的 cookie。</span><span class="sxs-lookup"><span data-stu-id="a1627-106">[in] The cookie associated with the monitor.</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="a1627-107">弄指向当前拥有监视器的 `IHostTask` 的指针; 如果没有任务具有所有权，则为 null。</span><span class="sxs-lookup"><span data-stu-id="a1627-107">[out] A pointer to the `IHostTask` that currently owns the monitor, or null if no task has ownership.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1627-108">返回值</span><span class="sxs-lookup"><span data-stu-id="a1627-108">Return Value</span></span>  
  
|<span data-ttu-id="a1627-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a1627-109">HRESULT</span></span>|<span data-ttu-id="a1627-110">描述</span><span class="sxs-lookup"><span data-stu-id="a1627-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a1627-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a1627-111">S_OK</span></span>|<span data-ttu-id="a1627-112">`GetMonitorOwner` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="a1627-112">`GetMonitorOwner` returned successfully.</span></span>|  
|<span data-ttu-id="a1627-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a1627-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a1627-114">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="a1627-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a1627-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a1627-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a1627-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="a1627-116">The call timed out.</span></span>|  
|<span data-ttu-id="a1627-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a1627-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a1627-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="a1627-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a1627-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a1627-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a1627-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="a1627-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a1627-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a1627-121">E_FAIL</span></span>|<span data-ttu-id="a1627-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="a1627-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a1627-123">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="a1627-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a1627-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="a1627-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1627-125">备注</span><span class="sxs-lookup"><span data-stu-id="a1627-125">Remarks</span></span>  
 <span data-ttu-id="a1627-126">宿主通常将 `GetMonitorOwner` 称为 "死锁检测机制" 的一部分。</span><span class="sxs-lookup"><span data-stu-id="a1627-126">The host typically calls `GetMonitorOwner` as part of a deadlock-detection mechanism.</span></span> <span data-ttu-id="a1627-127">当使用[IHostSyncManager：： CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)调用创建该 cookie 时，该 cookie 与监视器相关联。</span><span class="sxs-lookup"><span data-stu-id="a1627-127">The cookie is associated with a monitor when it is created by using a call to [IHostSyncManager::CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a1627-128">如果调用此方法的调用当前对与该监视器关联的 cookie 有效，则调用会阻止该调用，但不会死锁。</span><span class="sxs-lookup"><span data-stu-id="a1627-128">A call to release the event underlying the monitor might block—but will not deadlock—if a call to this method is currently in effect on the cookie associated with that monitor.</span></span> <span data-ttu-id="a1627-129">其他任务也可能会在尝试获取此监视器时阻止。</span><span class="sxs-lookup"><span data-stu-id="a1627-129">Other tasks might also block if they attempt to acquire this monitor.</span></span>  
  
 <span data-ttu-id="a1627-130">`GetMonitorOwner` 始终立即返回，并且可以在对 `CreateMonitorEvent`的调用之后随时调用。</span><span class="sxs-lookup"><span data-stu-id="a1627-130">`GetMonitorOwner` always returns immediately and can be called any time after a call to `CreateMonitorEvent`.</span></span> <span data-ttu-id="a1627-131">宿主无需等待，直到任务等待事件。</span><span class="sxs-lookup"><span data-stu-id="a1627-131">The host does not need to wait until a task is waiting on the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1627-132">要求</span><span class="sxs-lookup"><span data-stu-id="a1627-132">Requirements</span></span>  
 <span data-ttu-id="a1627-133">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a1627-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1627-134">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a1627-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a1627-135">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="a1627-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a1627-136">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1627-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1627-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1627-137">See also</span></span>

- [<span data-ttu-id="a1627-138">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="a1627-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="a1627-139">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="a1627-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
