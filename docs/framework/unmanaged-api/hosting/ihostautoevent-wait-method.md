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
ms.openlocfilehash: 0258999bae8b04ddaccf264276d1439b027b4a43
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195894"
---
# <a name="ihostautoeventwait-method"></a><span data-ttu-id="459a8-102">IHostAutoEvent::Wait 方法</span><span class="sxs-lookup"><span data-stu-id="459a8-102">IHostAutoEvent::Wait Method</span></span>
<span data-ttu-id="459a8-103">导致当前[IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)实例等待，直到其拥有或经过指定的时间量。</span><span class="sxs-lookup"><span data-stu-id="459a8-103">Causes the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to wait until it is owned or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="459a8-104">语法</span><span class="sxs-lookup"><span data-stu-id="459a8-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="459a8-105">参数</span><span class="sxs-lookup"><span data-stu-id="459a8-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="459a8-106">中当前 `IHostAutoEvent` 实例在返回之前应等待的毫秒数（如果没有线程或纤程获得所有权）。</span><span class="sxs-lookup"><span data-stu-id="459a8-106">[in] The number of milliseconds the current `IHostAutoEvent` instance should wait before returning, if no thread or fiber takes ownership.</span></span>  
  
 `option`  
 <span data-ttu-id="459a8-107">中[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)值之一，指定宿主在此操作阻止的情况下应执行的操作。</span><span class="sxs-lookup"><span data-stu-id="459a8-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, specifying the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="459a8-108">返回值</span><span class="sxs-lookup"><span data-stu-id="459a8-108">Return Value</span></span>  
  
|<span data-ttu-id="459a8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="459a8-109">HRESULT</span></span>|<span data-ttu-id="459a8-110">描述</span><span class="sxs-lookup"><span data-stu-id="459a8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="459a8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="459a8-111">S_OK</span></span>|<span data-ttu-id="459a8-112">`Wait` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="459a8-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="459a8-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="459a8-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="459a8-114">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="459a8-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="459a8-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="459a8-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="459a8-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="459a8-116">The call timed out.</span></span>|  
|<span data-ttu-id="459a8-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="459a8-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="459a8-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="459a8-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="459a8-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="459a8-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="459a8-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="459a8-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="459a8-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="459a8-121">E_FAIL</span></span>|<span data-ttu-id="459a8-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="459a8-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="459a8-123">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="459a8-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="459a8-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="459a8-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="459a8-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="459a8-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="459a8-126">主机在等待间隔期间检测到死锁，并选择由当前 `IHostAutoEvent` 实例表示为死锁牺牲品的事件。</span><span class="sxs-lookup"><span data-stu-id="459a8-126">The host detected a deadlock during the wait interval, and chose the event represented by the current `IHostAutoEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="459a8-127">要求</span><span class="sxs-lookup"><span data-stu-id="459a8-127">Requirements</span></span>  
 <span data-ttu-id="459a8-128">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="459a8-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="459a8-129">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="459a8-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="459a8-130">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="459a8-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="459a8-131">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="459a8-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="459a8-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="459a8-132">See also</span></span>

- [<span data-ttu-id="459a8-133">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="459a8-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="459a8-134">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="459a8-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="459a8-135">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="459a8-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="459a8-136">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="459a8-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
