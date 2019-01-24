---
title: IHostManualEvent::Wait 方法
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Wait
helpviewer_keywords:
- IHostManualEvent::Wait method [.NET Framework hosting]
- Wait method, IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 1fbb7d8b-8a23-4c2b-8376-1a70cd2d6030
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 242c13a381445d5fe9551553cd1e3febc81cb2fc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638213"
---
# <a name="ihostmanualeventwait-method"></a><span data-ttu-id="8674f-102">IHostManualEvent::Wait 方法</span><span class="sxs-lookup"><span data-stu-id="8674f-102">IHostManualEvent::Wait Method</span></span>
<span data-ttu-id="8674f-103">导致当前[IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)实例等待，直到拥有它或指定的经历的时间量。</span><span class="sxs-lookup"><span data-stu-id="8674f-103">Causes the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to wait until it is owned, or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8674f-104">语法</span><span class="sxs-lookup"><span data-stu-id="8674f-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8674f-105">参数</span><span class="sxs-lookup"><span data-stu-id="8674f-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="8674f-106">[in]如果返回前, 等待的毫秒数当前`IHostManualEvent`不属于实例。</span><span class="sxs-lookup"><span data-stu-id="8674f-106">[in] The number of milliseconds to wait before returning, if the current `IHostManualEvent` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="8674f-107">[in]之一[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)值，如果此主机应采取的操作，该值指示操作阻止。</span><span class="sxs-lookup"><span data-stu-id="8674f-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8674f-108">返回值</span><span class="sxs-lookup"><span data-stu-id="8674f-108">Return Value</span></span>  
  
|<span data-ttu-id="8674f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8674f-109">HRESULT</span></span>|<span data-ttu-id="8674f-110">描述</span><span class="sxs-lookup"><span data-stu-id="8674f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8674f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8674f-111">S_OK</span></span>|<span data-ttu-id="8674f-112">`Wait` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="8674f-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="8674f-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8674f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8674f-114">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="8674f-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8674f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8674f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8674f-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="8674f-116">The call timed out.</span></span>|  
|<span data-ttu-id="8674f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8674f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8674f-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="8674f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8674f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8674f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8674f-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="8674f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8674f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8674f-121">E_FAIL</span></span>|<span data-ttu-id="8674f-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="8674f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8674f-123">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="8674f-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8674f-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="8674f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8674f-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="8674f-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="8674f-126">宿主的等待时间间隔，期间检测到死锁，并选择当前`IHostManualEvent`实例作为死锁牺牲品。</span><span class="sxs-lookup"><span data-stu-id="8674f-126">The host detected a deadlock during the wait interval, and chose the current `IHostManualEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8674f-127">要求</span><span class="sxs-lookup"><span data-stu-id="8674f-127">Requirements</span></span>  
 <span data-ttu-id="8674f-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8674f-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8674f-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8674f-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8674f-130">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8674f-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8674f-131">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8674f-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8674f-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="8674f-132">See also</span></span>
- [<span data-ttu-id="8674f-133">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="8674f-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="8674f-134">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="8674f-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="8674f-135">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="8674f-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="8674f-136">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="8674f-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="8674f-137">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="8674f-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
