---
title: "IHostSemaphore::ReleaseSemaphore 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostSemaphore.ReleaseSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore::ReleaseSemaphore
helpviewer_keywords:
- ReleaseSemaphore method [.NET Framework hosting]
- IHostSemaphore::ReleaseSemaphore method [.NET Framework hosting]
ms.assetid: a343d197-979a-4ac6-ab8c-cb8a05f3120e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6828726fe81cc99adc719659a6eb1b15afda84c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsemaphorereleasesemaphore-method"></a><span data-ttu-id="5e9e6-102">IHostSemaphore::ReleaseSemaphore 方法</span><span class="sxs-lookup"><span data-stu-id="5e9e6-102">IHostSemaphore::ReleaseSemaphore Method</span></span>
<span data-ttu-id="5e9e6-103">当前的计数增加[IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)指定的量的实例。</span><span class="sxs-lookup"><span data-stu-id="5e9e6-103">Increases the count of the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance by the specified amount.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e9e6-104">语法</span><span class="sxs-lookup"><span data-stu-id="5e9e6-104">Syntax</span></span>  
  
```  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5e9e6-105">参数</span><span class="sxs-lookup"><span data-stu-id="5e9e6-105">Parameters</span></span>  
 `lReleaseCount`  
 <span data-ttu-id="5e9e6-106">[in]乘幂的当前计数量`IHostSemaphore`实例。</span><span class="sxs-lookup"><span data-stu-id="5e9e6-106">[in] The amount by which to increase the count of the current `IHostSemaphore` instance.</span></span> <span data-ttu-id="5e9e6-107">此数量必须大于零。</span><span class="sxs-lookup"><span data-stu-id="5e9e6-107">This amount must be greater than zero.</span></span>  
  
 `lpPreviousCount`  
 <span data-ttu-id="5e9e6-108">[out]指向前一个计数或如果调用方不需要的前一个计数的 null 指针。</span><span class="sxs-lookup"><span data-stu-id="5e9e6-108">[out] A pointer to the previous count, or null if the caller does not require the previous count.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5e9e6-109">返回值</span><span class="sxs-lookup"><span data-stu-id="5e9e6-109">Return Value</span></span>  
  
|<span data-ttu-id="5e9e6-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5e9e6-110">HRESULT</span></span>|<span data-ttu-id="5e9e6-111">描述</span><span class="sxs-lookup"><span data-stu-id="5e9e6-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5e9e6-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="5e9e6-112">S_OK</span></span>|<span data-ttu-id="5e9e6-113">`ReleaseSemaphore`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="5e9e6-113">`ReleaseSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="5e9e6-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5e9e6-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5e9e6-115">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="5e9e6-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5e9e6-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5e9e6-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5e9e6-117">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="5e9e6-117">The call timed out.</span></span>|  
|<span data-ttu-id="5e9e6-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5e9e6-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5e9e6-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="5e9e6-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5e9e6-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5e9e6-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5e9e6-121">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="5e9e6-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5e9e6-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5e9e6-122">E_FAIL</span></span>|<span data-ttu-id="5e9e6-123">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="5e9e6-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5e9e6-124">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="5e9e6-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5e9e6-125">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="5e9e6-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e9e6-126">备注</span><span class="sxs-lookup"><span data-stu-id="5e9e6-126">Remarks</span></span>  
 <span data-ttu-id="5e9e6-127">CLR 通常调用`ReleaseSemaphore`用于通知宿主它已完成使用的资源，将为 1 的值传递`lReleaseCount`参数。</span><span class="sxs-lookup"><span data-stu-id="5e9e6-127">The CLR typically calls `ReleaseSemaphore` to notify the host that it has finished using a resource, passing a value of 1 for the `lReleaseCount` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e9e6-128">惠?</span><span class="sxs-lookup"><span data-stu-id="5e9e6-128">Requirements</span></span>  
 <span data-ttu-id="5e9e6-129">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5e9e6-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e9e6-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5e9e6-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5e9e6-131">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5e9e6-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5e9e6-132">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e9e6-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e9e6-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="5e9e6-133">See Also</span></span>  
 [<span data-ttu-id="5e9e6-134">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="5e9e6-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="5e9e6-135">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="5e9e6-135">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="5e9e6-136">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="5e9e6-136">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="5e9e6-137">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="5e9e6-137">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="5e9e6-138">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="5e9e6-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
