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
ms.openlocfilehash: 821968fbde6d3f5434b83adf8c9661fe39d96293
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54742024"
---
# <a name="ihostcontrolgethostmanager-method"></a><span data-ttu-id="fd3bb-102">IHostControl::GetHostManager 方法</span><span class="sxs-lookup"><span data-stu-id="fd3bb-102">IHostControl::GetHostManager Method</span></span>
<span data-ttu-id="fd3bb-103">获取具有指定的接口指针接口的主机的实现`IID`。</span><span class="sxs-lookup"><span data-stu-id="fd3bb-103">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd3bb-104">语法</span><span class="sxs-lookup"><span data-stu-id="fd3bb-104">Syntax</span></span>  
  
```  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd3bb-105">参数</span><span class="sxs-lookup"><span data-stu-id="fd3bb-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="fd3bb-106">[in]`IID`公共语言运行时 (CLR) 所查询的接口。</span><span class="sxs-lookup"><span data-stu-id="fd3bb-106">[in] The `IID` of the interface that the common language runtime (CLR) is querying for.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="fd3bb-107">[out]宿主实现的接口或为 null，如果主机不支持此接口的指针。</span><span class="sxs-lookup"><span data-stu-id="fd3bb-107">[out] A pointer to the host-implemented interface, or null if the host does not support this interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd3bb-108">返回值</span><span class="sxs-lookup"><span data-stu-id="fd3bb-108">Return Value</span></span>  
  
|<span data-ttu-id="fd3bb-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fd3bb-109">HRESULT</span></span>|<span data-ttu-id="fd3bb-110">描述</span><span class="sxs-lookup"><span data-stu-id="fd3bb-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fd3bb-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fd3bb-111">S_OK</span></span>|<span data-ttu-id="fd3bb-112">`GetHostManager` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="fd3bb-112">`GetHostManager` returned successfully.</span></span>|  
|<span data-ttu-id="fd3bb-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fd3bb-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fd3bb-114">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="fd3bb-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fd3bb-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fd3bb-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fd3bb-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="fd3bb-116">The call timed out.</span></span>|  
|<span data-ttu-id="fd3bb-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fd3bb-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fd3bb-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="fd3bb-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fd3bb-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fd3bb-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fd3bb-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="fd3bb-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fd3bb-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fd3bb-121">E_FAIL</span></span>|<span data-ttu-id="fd3bb-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="fd3bb-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fd3bb-123">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="fd3bb-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fd3bb-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="fd3bb-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fd3bb-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="fd3bb-125">E_INVALIDARG</span></span>|<span data-ttu-id="fd3bb-126">请求`IID`无效。</span><span class="sxs-lookup"><span data-stu-id="fd3bb-126">The requested `IID` is not valid.</span></span>|  
|<span data-ttu-id="fd3bb-127">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="fd3bb-127">E_NOINTERFACE</span></span>|<span data-ttu-id="fd3bb-128">不支持所请求的接口。</span><span class="sxs-lookup"><span data-stu-id="fd3bb-128">The requested interface is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd3bb-129">备注</span><span class="sxs-lookup"><span data-stu-id="fd3bb-129">Remarks</span></span>  
 <span data-ttu-id="fd3bb-130">CLR 查询主机以确定它是否支持一个或多个以下接口：</span><span class="sxs-lookup"><span data-stu-id="fd3bb-130">The CLR queries the host to determine whether it supports one or more of the following interfaces:</span></span>  
  
-   [<span data-ttu-id="fd3bb-131">IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="fd3bb-131">IHostMemoryManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
  
-   [<span data-ttu-id="fd3bb-132">IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="fd3bb-132">IHostTaskManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
  
-   [<span data-ttu-id="fd3bb-133">IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="fd3bb-133">IHostThreadPoolManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
  
-   [<span data-ttu-id="fd3bb-134">IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="fd3bb-134">IHostIoCompletionManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
  
-   [<span data-ttu-id="fd3bb-135">IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="fd3bb-135">IHostSyncManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
  
-   [<span data-ttu-id="fd3bb-136">IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="fd3bb-136">IHostAssemblyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
  
-   [<span data-ttu-id="fd3bb-137">IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="fd3bb-137">IHostGCManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
  
-   [<span data-ttu-id="fd3bb-138">IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="fd3bb-138">IHostPolicyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
  
-   [<span data-ttu-id="fd3bb-139">IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="fd3bb-139">IHostSecurityManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
  
 <span data-ttu-id="fd3bb-140">如果主机支持指定的接口，它会设置`ppObject`到其实现该接口。</span><span class="sxs-lookup"><span data-stu-id="fd3bb-140">If the host supports the specified interface, it sets `ppObject` to its implementation of that interface.</span></span> <span data-ttu-id="fd3bb-141">否则，它设置`ppObject`为 null。</span><span class="sxs-lookup"><span data-stu-id="fd3bb-141">Otherwise, it sets `ppObject` to null.</span></span>  
  
 <span data-ttu-id="fd3bb-142">CLR 不会调用`Release`主机管理，即使你关闭。</span><span class="sxs-lookup"><span data-stu-id="fd3bb-142">The CLR does not call `Release` on host managers, even when you shut it down.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd3bb-143">要求</span><span class="sxs-lookup"><span data-stu-id="fd3bb-143">Requirements</span></span>  
 <span data-ttu-id="fd3bb-144">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fd3bb-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd3bb-145">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fd3bb-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fd3bb-146">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="fd3bb-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd3bb-147">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd3bb-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd3bb-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd3bb-148">See also</span></span>
- [<span data-ttu-id="fd3bb-149">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="fd3bb-149">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
