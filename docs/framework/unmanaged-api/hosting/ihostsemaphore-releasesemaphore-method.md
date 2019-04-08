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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24ec56345a5b48540d2451769f739a236a85e47b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100608"
---
# <a name="ihostsemaphorereleasesemaphore-method"></a><span data-ttu-id="c0934-102">IHostSemaphore::ReleaseSemaphore 方法</span><span class="sxs-lookup"><span data-stu-id="c0934-102">IHostSemaphore::ReleaseSemaphore Method</span></span>
<span data-ttu-id="c0934-103">当前计数[IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)实例指定的量。</span><span class="sxs-lookup"><span data-stu-id="c0934-103">Increases the count of the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance by the specified amount.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0934-104">语法</span><span class="sxs-lookup"><span data-stu-id="c0934-104">Syntax</span></span>  
  
```  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0934-105">参数</span><span class="sxs-lookup"><span data-stu-id="c0934-105">Parameters</span></span>  
 `lReleaseCount`  
 <span data-ttu-id="c0934-106">[in]当前计数增加的量`IHostSemaphore`实例。</span><span class="sxs-lookup"><span data-stu-id="c0934-106">[in] The amount by which to increase the count of the current `IHostSemaphore` instance.</span></span> <span data-ttu-id="c0934-107">此数量必须大于零。</span><span class="sxs-lookup"><span data-stu-id="c0934-107">This amount must be greater than zero.</span></span>  
  
 `lpPreviousCount`  
 <span data-ttu-id="c0934-108">[out]一个指向前一个计数或如果调用方不需要前一个计数，则为 null。</span><span class="sxs-lookup"><span data-stu-id="c0934-108">[out] A pointer to the previous count, or null if the caller does not require the previous count.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c0934-109">返回值</span><span class="sxs-lookup"><span data-stu-id="c0934-109">Return Value</span></span>  
  
|<span data-ttu-id="c0934-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c0934-110">HRESULT</span></span>|<span data-ttu-id="c0934-111">描述</span><span class="sxs-lookup"><span data-stu-id="c0934-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c0934-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c0934-112">S_OK</span></span>|`ReleaseSemaphore` <span data-ttu-id="c0934-113">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="c0934-113">returned successfully.</span></span>|  
|<span data-ttu-id="c0934-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c0934-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c0934-115">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="c0934-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c0934-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c0934-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c0934-117">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="c0934-117">The call timed out.</span></span>|  
|<span data-ttu-id="c0934-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c0934-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c0934-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="c0934-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c0934-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c0934-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c0934-121">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="c0934-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c0934-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c0934-122">E_FAIL</span></span>|<span data-ttu-id="c0934-123">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="c0934-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c0934-124">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="c0934-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c0934-125">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c0934-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0934-126">备注</span><span class="sxs-lookup"><span data-stu-id="c0934-126">Remarks</span></span>  
 <span data-ttu-id="c0934-127">CLR 通常会调用`ReleaseSemaphore`用于通知宿主，它已完成使用资源，将为 1 的值传递`lReleaseCount`参数。</span><span class="sxs-lookup"><span data-stu-id="c0934-127">The CLR typically calls `ReleaseSemaphore` to notify the host that it has finished using a resource, passing a value of 1 for the `lReleaseCount` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0934-128">要求</span><span class="sxs-lookup"><span data-stu-id="c0934-128">Requirements</span></span>  
 <span data-ttu-id="c0934-129">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c0934-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0934-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c0934-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c0934-131">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c0934-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c0934-132">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="c0934-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c0934-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0934-133">See also</span></span>

- [<span data-ttu-id="c0934-134">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="c0934-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="c0934-135">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="c0934-135">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="c0934-136">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="c0934-136">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="c0934-137">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="c0934-137">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="c0934-138">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="c0934-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
