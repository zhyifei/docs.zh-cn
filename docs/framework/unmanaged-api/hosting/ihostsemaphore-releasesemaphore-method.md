---
title: IHostSemaphore::ReleaseSemaphore 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: 33a92365e7765befe669439eabefac607232ff15
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139460"
---
# <a name="ihostsemaphorereleasesemaphore-method"></a><span data-ttu-id="22221-102">IHostSemaphore::ReleaseSemaphore 方法</span><span class="sxs-lookup"><span data-stu-id="22221-102">IHostSemaphore::ReleaseSemaphore Method</span></span>
<span data-ttu-id="22221-103">按指定量增加当前[IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)实例的计数。</span><span class="sxs-lookup"><span data-stu-id="22221-103">Increases the count of the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance by the specified amount.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22221-104">语法</span><span class="sxs-lookup"><span data-stu-id="22221-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22221-105">参数</span><span class="sxs-lookup"><span data-stu-id="22221-105">Parameters</span></span>  
 `lReleaseCount`  
 <span data-ttu-id="22221-106">中当前 `IHostSemaphore` 实例的计数的增加量。</span><span class="sxs-lookup"><span data-stu-id="22221-106">[in] The amount by which to increase the count of the current `IHostSemaphore` instance.</span></span> <span data-ttu-id="22221-107">此量必须大于零。</span><span class="sxs-lookup"><span data-stu-id="22221-107">This amount must be greater than zero.</span></span>  
  
 `lpPreviousCount`  
 <span data-ttu-id="22221-108">弄指向上一个计数的指针; 如果调用方不需要以前的计数，则为 null。</span><span class="sxs-lookup"><span data-stu-id="22221-108">[out] A pointer to the previous count, or null if the caller does not require the previous count.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22221-109">返回值</span><span class="sxs-lookup"><span data-stu-id="22221-109">Return Value</span></span>  
  
|<span data-ttu-id="22221-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="22221-110">HRESULT</span></span>|<span data-ttu-id="22221-111">描述</span><span class="sxs-lookup"><span data-stu-id="22221-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="22221-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="22221-112">S_OK</span></span>|<span data-ttu-id="22221-113">`ReleaseSemaphore` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="22221-113">`ReleaseSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="22221-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="22221-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="22221-115">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="22221-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="22221-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="22221-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="22221-117">调用超时。</span><span class="sxs-lookup"><span data-stu-id="22221-117">The call timed out.</span></span>|  
|<span data-ttu-id="22221-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="22221-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="22221-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="22221-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="22221-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="22221-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="22221-121">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="22221-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="22221-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="22221-122">E_FAIL</span></span>|<span data-ttu-id="22221-123">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="22221-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="22221-124">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="22221-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="22221-125">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="22221-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22221-126">备注</span><span class="sxs-lookup"><span data-stu-id="22221-126">Remarks</span></span>  
 <span data-ttu-id="22221-127">CLR 通常会调用 `ReleaseSemaphore` 来通知主机它已使用完资源，并为 `lReleaseCount` 参数传递值1。</span><span class="sxs-lookup"><span data-stu-id="22221-127">The CLR typically calls `ReleaseSemaphore` to notify the host that it has finished using a resource, passing a value of 1 for the `lReleaseCount` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22221-128">要求</span><span class="sxs-lookup"><span data-stu-id="22221-128">Requirements</span></span>  
 <span data-ttu-id="22221-129">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="22221-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22221-130">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="22221-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="22221-131">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="22221-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22221-132">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22221-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22221-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="22221-133">See also</span></span>

- [<span data-ttu-id="22221-134">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="22221-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="22221-135">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="22221-135">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="22221-136">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="22221-136">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="22221-137">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="22221-137">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="22221-138">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="22221-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
