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
ms.openlocfilehash: bf09f7bc6c3e3aabfc16f9cad277c46be024b01d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139450"
---
# <a name="ihostsemaphorewait-method"></a><span data-ttu-id="c4f64-102">IHostSemaphore::Wait 方法</span><span class="sxs-lookup"><span data-stu-id="c4f64-102">IHostSemaphore::Wait Method</span></span>
<span data-ttu-id="c4f64-103">导致当前[IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)实例等待，直到其拥有或经过指定的时间量。</span><span class="sxs-lookup"><span data-stu-id="c4f64-103">Causes the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance to wait until it is owned or the specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4f64-104">语法</span><span class="sxs-lookup"><span data-stu-id="c4f64-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4f64-105">参数</span><span class="sxs-lookup"><span data-stu-id="c4f64-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="c4f64-106">中如果当前 `IHostSemaphore` 实例不是所有实例，则返回前等待的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="c4f64-106">[in] The number of milliseconds to wait before returning, if the current `IHostSemaphore` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="c4f64-107">中[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)值之一，指定主机在此操作阻止的情况下应执行的操作。</span><span class="sxs-lookup"><span data-stu-id="c4f64-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, specifying what action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c4f64-108">返回值</span><span class="sxs-lookup"><span data-stu-id="c4f64-108">Return Value</span></span>  
  
|<span data-ttu-id="c4f64-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c4f64-109">HRESULT</span></span>|<span data-ttu-id="c4f64-110">描述</span><span class="sxs-lookup"><span data-stu-id="c4f64-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c4f64-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c4f64-111">S_OK</span></span>|<span data-ttu-id="c4f64-112">`Wait` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="c4f64-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="c4f64-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c4f64-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c4f64-114">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="c4f64-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c4f64-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c4f64-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c4f64-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="c4f64-116">The call timed out.</span></span>|  
|<span data-ttu-id="c4f64-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c4f64-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c4f64-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="c4f64-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c4f64-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c4f64-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c4f64-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="c4f64-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c4f64-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c4f64-121">E_FAIL</span></span>|<span data-ttu-id="c4f64-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="c4f64-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c4f64-123">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="c4f64-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c4f64-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c4f64-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c4f64-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="c4f64-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="c4f64-126">主机在等待间隔期间检测到死锁，并选择当前 `IHostSemaphore` 实例作为死锁牺牲品。</span><span class="sxs-lookup"><span data-stu-id="c4f64-126">The host detected a deadlock during the wait interval, and chose the current `IHostSemaphore` instance as a deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c4f64-127">要求</span><span class="sxs-lookup"><span data-stu-id="c4f64-127">Requirements</span></span>  
 <span data-ttu-id="c4f64-128">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c4f64-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4f64-129">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c4f64-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c4f64-130">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c4f64-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c4f64-131">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4f64-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4f64-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4f64-132">See also</span></span>

- [<span data-ttu-id="c4f64-133">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="c4f64-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="c4f64-134">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="c4f64-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="c4f64-135">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="c4f64-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="c4f64-136">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="c4f64-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="c4f64-137">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="c4f64-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
