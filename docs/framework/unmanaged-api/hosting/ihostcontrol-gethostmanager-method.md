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
ms.openlocfilehash: c23773dce448c8c98d4926dff3fa51100e683fd0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192039"
---
# <a name="ihostcontrolgethostmanager-method"></a><span data-ttu-id="31167-102">IHostControl::GetHostManager 方法</span><span class="sxs-lookup"><span data-stu-id="31167-102">IHostControl::GetHostManager Method</span></span>
<span data-ttu-id="31167-103">获取一个接口指针，该指针指向具有指定 `IID`的接口的主机实现。</span><span class="sxs-lookup"><span data-stu-id="31167-103">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31167-104">语法</span><span class="sxs-lookup"><span data-stu-id="31167-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31167-105">参数</span><span class="sxs-lookup"><span data-stu-id="31167-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="31167-106">中公共语言运行时（CLR）正在查询的接口的 `IID`。</span><span class="sxs-lookup"><span data-stu-id="31167-106">[in] The `IID` of the interface that the common language runtime (CLR) is querying for.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="31167-107">弄指向宿主实现的接口的指针; 如果主机不支持此接口，则为 null。</span><span class="sxs-lookup"><span data-stu-id="31167-107">[out] A pointer to the host-implemented interface, or null if the host does not support this interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="31167-108">返回值</span><span class="sxs-lookup"><span data-stu-id="31167-108">Return Value</span></span>  
  
|<span data-ttu-id="31167-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="31167-109">HRESULT</span></span>|<span data-ttu-id="31167-110">描述</span><span class="sxs-lookup"><span data-stu-id="31167-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="31167-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="31167-111">S_OK</span></span>|<span data-ttu-id="31167-112">`GetHostManager` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="31167-112">`GetHostManager` returned successfully.</span></span>|  
|<span data-ttu-id="31167-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="31167-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="31167-114">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="31167-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="31167-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="31167-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="31167-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="31167-116">The call timed out.</span></span>|  
|<span data-ttu-id="31167-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="31167-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="31167-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="31167-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="31167-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="31167-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="31167-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="31167-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="31167-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="31167-121">E_FAIL</span></span>|<span data-ttu-id="31167-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="31167-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="31167-123">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="31167-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="31167-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="31167-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="31167-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="31167-125">E_INVALIDARG</span></span>|<span data-ttu-id="31167-126">请求的 `IID` 无效。</span><span class="sxs-lookup"><span data-stu-id="31167-126">The requested `IID` is not valid.</span></span>|  
|<span data-ttu-id="31167-127">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="31167-127">E_NOINTERFACE</span></span>|<span data-ttu-id="31167-128">不支持请求的接口。</span><span class="sxs-lookup"><span data-stu-id="31167-128">The requested interface is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31167-129">备注</span><span class="sxs-lookup"><span data-stu-id="31167-129">Remarks</span></span>  
 <span data-ttu-id="31167-130">CLR 将查询宿主，以确定它是否支持以下一个或多个接口：</span><span class="sxs-lookup"><span data-stu-id="31167-130">The CLR queries the host to determine whether it supports one or more of the following interfaces:</span></span>  
  
- [<span data-ttu-id="31167-131">IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="31167-131">IHostMemoryManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
  
- [<span data-ttu-id="31167-132">IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="31167-132">IHostTaskManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
  
- [<span data-ttu-id="31167-133">IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="31167-133">IHostThreadPoolManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
  
- [<span data-ttu-id="31167-134">IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="31167-134">IHostIoCompletionManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
  
- [<span data-ttu-id="31167-135">IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="31167-135">IHostSyncManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
  
- [<span data-ttu-id="31167-136">IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="31167-136">IHostAssemblyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
  
- [<span data-ttu-id="31167-137">IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="31167-137">IHostGCManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
  
- [<span data-ttu-id="31167-138">IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="31167-138">IHostPolicyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
  
- [<span data-ttu-id="31167-139">IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="31167-139">IHostSecurityManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
  
 <span data-ttu-id="31167-140">如果宿主支持指定的接口，它会将 `ppObject` 设置为该接口的实现。</span><span class="sxs-lookup"><span data-stu-id="31167-140">If the host supports the specified interface, it sets `ppObject` to its implementation of that interface.</span></span> <span data-ttu-id="31167-141">否则，它会将 `ppObject` 设置为 null。</span><span class="sxs-lookup"><span data-stu-id="31167-141">Otherwise, it sets `ppObject` to null.</span></span>  
  
 <span data-ttu-id="31167-142">即使您关闭了主机管理器，CLR 也不会对主机管理器调用 `Release`。</span><span class="sxs-lookup"><span data-stu-id="31167-142">The CLR does not call `Release` on host managers, even when you shut it down.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31167-143">要求</span><span class="sxs-lookup"><span data-stu-id="31167-143">Requirements</span></span>  
 <span data-ttu-id="31167-144">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="31167-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31167-145">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="31167-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="31167-146">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="31167-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="31167-147">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31167-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31167-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="31167-148">See also</span></span>

- [<span data-ttu-id="31167-149">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="31167-149">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
