---
title: "IHostSyncManager::CreateCrstWithSpinCount 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateCrstWithSpinCount
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateCrstWithSpinCount
helpviewer_keywords:
- CreateCrstWithSpinCount method [.NET Framework hosting]
- IHostSyncManager::CreateCrstWithSpinCount method [.NET Framework hosting]
ms.assetid: 7280fa8c-3639-4abf-91cb-bc343da742d1
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41031a5e3d423f0c1d7459250073634592e0291e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a><span data-ttu-id="8e200-102">IHostSyncManager::CreateCrstWithSpinCount 方法</span><span class="sxs-lookup"><span data-stu-id="8e200-102">IHostSyncManager::CreateCrstWithSpinCount Method</span></span>
<span data-ttu-id="8e200-103">创建具有同步的重试次数的关键部分对象。</span><span class="sxs-lookup"><span data-stu-id="8e200-103">Creates a critical section object with spin count for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e200-104">语法</span><span class="sxs-lookup"><span data-stu-id="8e200-104">Syntax</span></span>  
  
```  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8e200-105">参数</span><span class="sxs-lookup"><span data-stu-id="8e200-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="8e200-106">[in]指定关键部分对象的旋转计数。</span><span class="sxs-lookup"><span data-stu-id="8e200-106">[in] Specifies the spin count for the critical section object.</span></span>  
  
 `ppCrst`  
 <span data-ttu-id="8e200-107">[out]指向的地址的指针[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)实例，或如果无法创建关键部分则为 null。</span><span class="sxs-lookup"><span data-stu-id="8e200-107">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e200-108">返回值</span><span class="sxs-lookup"><span data-stu-id="8e200-108">Return Value</span></span>  
  
|<span data-ttu-id="8e200-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8e200-109">HRESULT</span></span>|<span data-ttu-id="8e200-110">描述</span><span class="sxs-lookup"><span data-stu-id="8e200-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8e200-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8e200-111">S_OK</span></span>|<span data-ttu-id="8e200-112">`CreateCrstWithSpinCount`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="8e200-112">`CreateCrstWithSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="8e200-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8e200-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8e200-114">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="8e200-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8e200-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8e200-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8e200-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="8e200-116">The call timed out.</span></span>|  
|<span data-ttu-id="8e200-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8e200-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8e200-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="8e200-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8e200-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8e200-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8e200-120">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="8e200-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8e200-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8e200-121">E_FAIL</span></span>|<span data-ttu-id="8e200-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="8e200-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8e200-123">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="8e200-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8e200-124">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="8e200-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8e200-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="8e200-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="8e200-126">没有足够的内存已可用于创建请求的关键部分。</span><span class="sxs-lookup"><span data-stu-id="8e200-126">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e200-127">备注</span><span class="sxs-lookup"><span data-stu-id="8e200-127">Remarks</span></span>  
 <span data-ttu-id="8e200-128">只能在多处理器系统上使用数值调节钮计数。</span><span class="sxs-lookup"><span data-stu-id="8e200-128">A spin count is used only on a multi-processor system.</span></span> <span data-ttu-id="8e200-129">数值调节钮计数指定的执行与不可用的关键部分的信号量上等待操作之前，必须启动调用线程的次数。</span><span class="sxs-lookup"><span data-stu-id="8e200-129">The spin count specifies the number of times a calling thread must spin before it performs a wait operation on a semaphore that is associated with an unavailable critical section.</span></span> <span data-ttu-id="8e200-130">如果数值调节钮操作期间，临界区变得可用，调用线程可避免等待操作。</span><span class="sxs-lookup"><span data-stu-id="8e200-130">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span> <span data-ttu-id="8e200-131">`CreateCrstWithSpinCount`镜像 Win32`InitializeCriticalSectionAndSpinCount`函数。</span><span class="sxs-lookup"><span data-stu-id="8e200-131">`CreateCrstWithSpinCount` mirrors the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e200-132">要求</span><span class="sxs-lookup"><span data-stu-id="8e200-132">Requirements</span></span>  
 <span data-ttu-id="8e200-133">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8e200-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e200-134">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8e200-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8e200-135">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8e200-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e200-136">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e200-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e200-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e200-137">See Also</span></span>  
 [<span data-ttu-id="8e200-138">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="8e200-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="8e200-139">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="8e200-139">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="8e200-140">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="8e200-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
