---
title: "IHostCrst::SetSpinCount 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst.SetSpinCount
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst::SetSpinCount
helpviewer_keywords:
- IHostCrst::SetSpinCount method [.NET Framework hosting]
- SetSpinCount method [.NET Framework hosting]
ms.assetid: 863fc8ce-9b8a-477e-8dd8-75c8544bb43a
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 19172c6d498e5066c102c642105d78d10b26212c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="0bd38-102">IHostCrst::SetSpinCount 方法</span><span class="sxs-lookup"><span data-stu-id="0bd38-102">IHostCrst::SetSpinCount Method</span></span>
<span data-ttu-id="0bd38-103">设置当前的旋转计数[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="0bd38-103">Sets the spin count for the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bd38-104">语法</span><span class="sxs-lookup"><span data-stu-id="0bd38-104">Syntax</span></span>  
  
```  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0bd38-105">参数</span><span class="sxs-lookup"><span data-stu-id="0bd38-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="0bd38-106">[in]当前的新旋转计数`IHostCrst`实例。</span><span class="sxs-lookup"><span data-stu-id="0bd38-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0bd38-107">返回值</span><span class="sxs-lookup"><span data-stu-id="0bd38-107">Return Value</span></span>  
  
|<span data-ttu-id="0bd38-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0bd38-108">HRESULT</span></span>|<span data-ttu-id="0bd38-109">描述</span><span class="sxs-lookup"><span data-stu-id="0bd38-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0bd38-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0bd38-110">S_OK</span></span>|<span data-ttu-id="0bd38-111">`SetSpinCount`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="0bd38-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="0bd38-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0bd38-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0bd38-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="0bd38-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0bd38-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0bd38-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0bd38-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="0bd38-115">The call timed out.</span></span>|  
|<span data-ttu-id="0bd38-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0bd38-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0bd38-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="0bd38-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0bd38-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0bd38-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0bd38-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="0bd38-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0bd38-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0bd38-120">E_FAIL</span></span>|<span data-ttu-id="0bd38-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="0bd38-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0bd38-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="0bd38-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0bd38-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="0bd38-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0bd38-124">备注</span><span class="sxs-lookup"><span data-stu-id="0bd38-124">Remarks</span></span>  
 <span data-ttu-id="0bd38-125">在多处理器系统中，如果由当前的临界区表示`IHostCrst`实例不可用，则调用线程旋转`dwSpinCount`在调用之前的时间[ihostsemaphore:: Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)上关联的信号量与关键部分。</span><span class="sxs-lookup"><span data-stu-id="0bd38-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="0bd38-126">如果数值调节钮操作期间，临界区变得可用，调用线程可避免等待操作。</span><span class="sxs-lookup"><span data-stu-id="0bd38-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="0bd38-127">使用情况`dwSpinCount`等同于 Win32 中的相同名称的参数的使用情况`InitializeCriticalSectionAndSpinCount`函数。</span><span class="sxs-lookup"><span data-stu-id="0bd38-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bd38-128">要求</span><span class="sxs-lookup"><span data-stu-id="0bd38-128">Requirements</span></span>  
 <span data-ttu-id="0bd38-129">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0bd38-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bd38-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0bd38-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0bd38-131">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0bd38-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0bd38-132">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bd38-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bd38-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0bd38-133">See Also</span></span>  
 [<span data-ttu-id="0bd38-134">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="0bd38-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="0bd38-135">IHostCrst 接口</span><span class="sxs-lookup"><span data-stu-id="0bd38-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="0bd38-136">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="0bd38-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
