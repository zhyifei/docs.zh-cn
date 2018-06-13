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
ms.openlocfilehash: 7431e1cb40da93f1e2f67e598d3915265ad7fba4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440453"
---
# <a name="ihostmanualeventwait-method"></a><span data-ttu-id="60086-102">IHostManualEvent::Wait 方法</span><span class="sxs-lookup"><span data-stu-id="60086-102">IHostManualEvent::Wait Method</span></span>
<span data-ttu-id="60086-103">导致当前[IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)等待，直到其拥有的实例或指定的经历的时间量。</span><span class="sxs-lookup"><span data-stu-id="60086-103">Causes the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to wait until it is owned, or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60086-104">语法</span><span class="sxs-lookup"><span data-stu-id="60086-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="60086-105">参数</span><span class="sxs-lookup"><span data-stu-id="60086-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="60086-106">[in]如果在返回之前, 等待的毫秒数当前`IHostManualEvent`实例不拥有。</span><span class="sxs-lookup"><span data-stu-id="60086-106">[in] The number of milliseconds to wait before returning, if the current `IHostManualEvent` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="60086-107">[in]之一[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)值，如果此主机应采取的操作，该值指示操作块。</span><span class="sxs-lookup"><span data-stu-id="60086-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60086-108">返回值</span><span class="sxs-lookup"><span data-stu-id="60086-108">Return Value</span></span>  
  
|<span data-ttu-id="60086-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="60086-109">HRESULT</span></span>|<span data-ttu-id="60086-110">描述</span><span class="sxs-lookup"><span data-stu-id="60086-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="60086-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="60086-111">S_OK</span></span>|<span data-ttu-id="60086-112">`Wait` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="60086-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="60086-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="60086-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="60086-114">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="60086-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="60086-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="60086-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="60086-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="60086-116">The call timed out.</span></span>|  
|<span data-ttu-id="60086-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="60086-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="60086-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="60086-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="60086-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="60086-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="60086-120">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="60086-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="60086-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="60086-121">E_FAIL</span></span>|<span data-ttu-id="60086-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="60086-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="60086-123">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="60086-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="60086-124">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="60086-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="60086-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="60086-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="60086-126">宿主在等待期间，检测到死锁，并选择当前`IHostManualEvent`实例作为死锁牺牲品。</span><span class="sxs-lookup"><span data-stu-id="60086-126">The host detected a deadlock during the wait interval, and chose the current `IHostManualEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="60086-127">要求</span><span class="sxs-lookup"><span data-stu-id="60086-127">Requirements</span></span>  
 <span data-ttu-id="60086-128">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="60086-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60086-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="60086-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="60086-130">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="60086-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="60086-131">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60086-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60086-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="60086-132">See Also</span></span>  
 [<span data-ttu-id="60086-133">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="60086-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="60086-134">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="60086-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="60086-135">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="60086-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="60086-136">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="60086-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="60086-137">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="60086-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
