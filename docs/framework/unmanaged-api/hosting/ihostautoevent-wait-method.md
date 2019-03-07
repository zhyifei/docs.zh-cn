---
title: IHostAutoEvent::Wait 方法
ms.date: 03/30/2017
api_name:
- IHostAutoEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent::Wait
helpviewer_keywords:
- Wait method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Wait method [.NET Framework hosting]
ms.assetid: 535d51c5-9112-401b-8c36-85f35d7ee609
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b282ca35135fd16dceb92e6a0eeab15837d9b10d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491446"
---
# <a name="ihostautoeventwait-method"></a><span data-ttu-id="eb0c6-102">IHostAutoEvent::Wait 方法</span><span class="sxs-lookup"><span data-stu-id="eb0c6-102">IHostAutoEvent::Wait Method</span></span>
<span data-ttu-id="eb0c6-103">导致当前[IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)等待，直到它拥有的实例或指定的经历的时间量。</span><span class="sxs-lookup"><span data-stu-id="eb0c6-103">Causes the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to wait until it is owned or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb0c6-104">语法</span><span class="sxs-lookup"><span data-stu-id="eb0c6-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb0c6-105">参数</span><span class="sxs-lookup"><span data-stu-id="eb0c6-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="eb0c6-106">[in]毫秒数当前`IHostAutoEvent`实例应返回前的等待，如果没有线程或纤程取得所有权。</span><span class="sxs-lookup"><span data-stu-id="eb0c6-106">[in] The number of milliseconds the current `IHostAutoEvent` instance should wait before returning, if no thread or fiber takes ownership.</span></span>  
  
 `option`  
 <span data-ttu-id="eb0c6-107">[in]之一[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)值，指定如果此主机应采取的操作操作阻止。</span><span class="sxs-lookup"><span data-stu-id="eb0c6-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, specifying the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eb0c6-108">返回值</span><span class="sxs-lookup"><span data-stu-id="eb0c6-108">Return Value</span></span>  
  
|<span data-ttu-id="eb0c6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eb0c6-109">HRESULT</span></span>|<span data-ttu-id="eb0c6-110">描述</span><span class="sxs-lookup"><span data-stu-id="eb0c6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eb0c6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="eb0c6-111">S_OK</span></span>|<span data-ttu-id="eb0c6-112">`Wait` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="eb0c6-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="eb0c6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="eb0c6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="eb0c6-114">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="eb0c6-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="eb0c6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="eb0c6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="eb0c6-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="eb0c6-116">The call timed out.</span></span>|  
|<span data-ttu-id="eb0c6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="eb0c6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="eb0c6-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="eb0c6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="eb0c6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="eb0c6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="eb0c6-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="eb0c6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="eb0c6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="eb0c6-121">E_FAIL</span></span>|<span data-ttu-id="eb0c6-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="eb0c6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="eb0c6-123">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="eb0c6-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="eb0c6-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="eb0c6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="eb0c6-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="eb0c6-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="eb0c6-126">宿主的等待时间间隔，期间检测到死锁，并选择所表示的当前事件`IHostAutoEvent`实例作为死锁牺牲品。</span><span class="sxs-lookup"><span data-stu-id="eb0c6-126">The host detected a deadlock during the wait interval, and chose the event represented by the current `IHostAutoEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eb0c6-127">要求</span><span class="sxs-lookup"><span data-stu-id="eb0c6-127">Requirements</span></span>  
 <span data-ttu-id="eb0c6-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eb0c6-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb0c6-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="eb0c6-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eb0c6-130">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="eb0c6-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eb0c6-131">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb0c6-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb0c6-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="eb0c6-132">See also</span></span>
- [<span data-ttu-id="eb0c6-133">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="eb0c6-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="eb0c6-134">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="eb0c6-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="eb0c6-135">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="eb0c6-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="eb0c6-136">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="eb0c6-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
