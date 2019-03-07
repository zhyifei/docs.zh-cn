---
title: IHostSemaphore::Wait 方法
ms.date: 03/30/2017
api_name:
- IHostSemaphore.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore::Wait
helpviewer_keywords:
- IHostSemaphore::Wait method [.NET Framework hosting]
- Wait method, IHostSemaphore interface [.NET Framework hosting]
ms.assetid: 0da962a3-ce55-44dd-ab7a-14ad7105af4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9933948a5e67b91106cdadc6f747c1b1c4121813
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489990"
---
# <a name="ihostsemaphorewait-method"></a><span data-ttu-id="52ebd-102">IHostSemaphore::Wait 方法</span><span class="sxs-lookup"><span data-stu-id="52ebd-102">IHostSemaphore::Wait Method</span></span>
<span data-ttu-id="52ebd-103">导致当前[IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)等待，直到它拥有的实例或指定的经历的时间量。</span><span class="sxs-lookup"><span data-stu-id="52ebd-103">Causes the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance to wait until it is owned or the specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52ebd-104">语法</span><span class="sxs-lookup"><span data-stu-id="52ebd-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52ebd-105">参数</span><span class="sxs-lookup"><span data-stu-id="52ebd-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="52ebd-106">[in]如果返回前, 等待的毫秒数当前`IHostSemaphore`不属于实例。</span><span class="sxs-lookup"><span data-stu-id="52ebd-106">[in] The number of milliseconds to wait before returning, if the current `IHostSemaphore` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="52ebd-107">[in]之一[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)值，指定如果此主机应采取什么操作操作阻止。</span><span class="sxs-lookup"><span data-stu-id="52ebd-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, specifying what action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52ebd-108">返回值</span><span class="sxs-lookup"><span data-stu-id="52ebd-108">Return Value</span></span>  
  
|<span data-ttu-id="52ebd-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="52ebd-109">HRESULT</span></span>|<span data-ttu-id="52ebd-110">描述</span><span class="sxs-lookup"><span data-stu-id="52ebd-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="52ebd-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="52ebd-111">S_OK</span></span>|<span data-ttu-id="52ebd-112">`Wait` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="52ebd-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="52ebd-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="52ebd-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="52ebd-114">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="52ebd-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="52ebd-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="52ebd-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="52ebd-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="52ebd-116">The call timed out.</span></span>|  
|<span data-ttu-id="52ebd-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="52ebd-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="52ebd-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="52ebd-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="52ebd-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="52ebd-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="52ebd-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="52ebd-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="52ebd-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="52ebd-121">E_FAIL</span></span>|<span data-ttu-id="52ebd-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="52ebd-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="52ebd-123">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="52ebd-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="52ebd-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="52ebd-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="52ebd-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="52ebd-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="52ebd-126">宿主的等待时间间隔，期间检测到死锁，并选择当前`IHostSemaphore`实例作为死锁牺牲品。</span><span class="sxs-lookup"><span data-stu-id="52ebd-126">The host detected a deadlock during the wait interval, and chose the current `IHostSemaphore` instance as a deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="52ebd-127">要求</span><span class="sxs-lookup"><span data-stu-id="52ebd-127">Requirements</span></span>  
 <span data-ttu-id="52ebd-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="52ebd-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52ebd-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="52ebd-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="52ebd-130">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="52ebd-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="52ebd-131">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52ebd-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52ebd-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="52ebd-132">See also</span></span>
- [<span data-ttu-id="52ebd-133">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="52ebd-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="52ebd-134">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="52ebd-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="52ebd-135">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="52ebd-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="52ebd-136">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="52ebd-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="52ebd-137">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="52ebd-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
