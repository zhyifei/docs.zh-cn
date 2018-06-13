---
title: IHostControl::GetHostManager 方法
ms.date: 03/30/2017
api_name:
- IHostControl.GetHostManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::GetHostManager
helpviewer_keywords:
- GetHostManager method [.NET Framework hosting]
- IHostControl::GetHostManager method [.NET Framework hosting]
ms.assetid: 0fa34bca-ed18-4626-9e78-d33684d18edb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 355d2e259adb13da44b09e19872337c17ac20ade
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439317"
---
# <a name="ihostcontrolgethostmanager-method"></a><span data-ttu-id="a90db-102">IHostControl::GetHostManager 方法</span><span class="sxs-lookup"><span data-stu-id="a90db-102">IHostControl::GetHostManager Method</span></span>
<span data-ttu-id="a90db-103">获取具有指定的接口指针接口的主机的实现`IID`。</span><span class="sxs-lookup"><span data-stu-id="a90db-103">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a90db-104">语法</span><span class="sxs-lookup"><span data-stu-id="a90db-104">Syntax</span></span>  
  
```  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a90db-105">参数</span><span class="sxs-lookup"><span data-stu-id="a90db-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="a90db-106">[in]`IID`公共语言运行时 (CLR) 查询的接口。</span><span class="sxs-lookup"><span data-stu-id="a90db-106">[in] The `IID` of the interface that the common language runtime (CLR) is querying for.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="a90db-107">[out]指向主机实现的接口或为空，如果主机不支持此接口的指针。</span><span class="sxs-lookup"><span data-stu-id="a90db-107">[out] A pointer to the host-implemented interface, or null if the host does not support this interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a90db-108">返回值</span><span class="sxs-lookup"><span data-stu-id="a90db-108">Return Value</span></span>  
  
|<span data-ttu-id="a90db-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a90db-109">HRESULT</span></span>|<span data-ttu-id="a90db-110">描述</span><span class="sxs-lookup"><span data-stu-id="a90db-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a90db-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a90db-111">S_OK</span></span>|<span data-ttu-id="a90db-112">`GetHostManager` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="a90db-112">`GetHostManager` returned successfully.</span></span>|  
|<span data-ttu-id="a90db-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a90db-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a90db-114">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="a90db-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a90db-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a90db-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a90db-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="a90db-116">The call timed out.</span></span>|  
|<span data-ttu-id="a90db-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a90db-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a90db-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="a90db-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a90db-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a90db-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a90db-120">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="a90db-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a90db-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a90db-121">E_FAIL</span></span>|<span data-ttu-id="a90db-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="a90db-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a90db-123">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="a90db-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a90db-124">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="a90db-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a90db-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a90db-125">E_INVALIDARG</span></span>|<span data-ttu-id="a90db-126">请求`IID`无效。</span><span class="sxs-lookup"><span data-stu-id="a90db-126">The requested `IID` is not valid.</span></span>|  
|<span data-ttu-id="a90db-127">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="a90db-127">E_NOINTERFACE</span></span>|<span data-ttu-id="a90db-128">不支持所请求的接口。</span><span class="sxs-lookup"><span data-stu-id="a90db-128">The requested interface is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a90db-129">备注</span><span class="sxs-lookup"><span data-stu-id="a90db-129">Remarks</span></span>  
 <span data-ttu-id="a90db-130">CLR 查询宿主以确定它是否支持一个或多个以下接口：</span><span class="sxs-lookup"><span data-stu-id="a90db-130">The CLR queries the host to determine whether it supports one or more of the following interfaces:</span></span>  
  
-   [<span data-ttu-id="a90db-131">IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="a90db-131">IHostMemoryManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
  
-   [<span data-ttu-id="a90db-132">IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="a90db-132">IHostTaskManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
  
-   [<span data-ttu-id="a90db-133">IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="a90db-133">IHostThreadPoolManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
  
-   [<span data-ttu-id="a90db-134">IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="a90db-134">IHostIoCompletionManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
  
-   [<span data-ttu-id="a90db-135">IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="a90db-135">IHostSyncManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
  
-   [<span data-ttu-id="a90db-136">IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="a90db-136">IHostAssemblyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
  
-   [<span data-ttu-id="a90db-137">IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="a90db-137">IHostGCManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
  
-   [<span data-ttu-id="a90db-138">IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="a90db-138">IHostPolicyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
  
-   [<span data-ttu-id="a90db-139">IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="a90db-139">IHostSecurityManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
  
 <span data-ttu-id="a90db-140">如果主机支持指定的接口，则将设置`ppObject`到其实现该接口。</span><span class="sxs-lookup"><span data-stu-id="a90db-140">If the host supports the specified interface, it sets `ppObject` to its implementation of that interface.</span></span> <span data-ttu-id="a90db-141">否则，它将设置`ppObject`为 null。</span><span class="sxs-lookup"><span data-stu-id="a90db-141">Otherwise, it sets `ppObject` to null.</span></span>  
  
 <span data-ttu-id="a90db-142">CLR 不调用`Release`主机管理，即使你将其关闭。</span><span class="sxs-lookup"><span data-stu-id="a90db-142">The CLR does not call `Release` on host managers, even when you shut it down.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a90db-143">要求</span><span class="sxs-lookup"><span data-stu-id="a90db-143">Requirements</span></span>  
 <span data-ttu-id="a90db-144">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a90db-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a90db-145">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a90db-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a90db-146">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a90db-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a90db-147">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a90db-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a90db-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="a90db-148">See Also</span></span>  
 [<span data-ttu-id="a90db-149">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="a90db-149">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
