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
ms.openlocfilehash: aa67aabbe8a7a47a9b3036f508e2f8bb6082c3e0
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803555"
---
# <a name="ihostsemaphorereleasesemaphore-method"></a><span data-ttu-id="70434-102">IHostSemaphore::ReleaseSemaphore 方法</span><span class="sxs-lookup"><span data-stu-id="70434-102">IHostSemaphore::ReleaseSemaphore Method</span></span>
<span data-ttu-id="70434-103">按指定量增加当前[IHostSemaphore](ihostsemaphore-interface.md)实例的计数。</span><span class="sxs-lookup"><span data-stu-id="70434-103">Increases the count of the current [IHostSemaphore](ihostsemaphore-interface.md) instance by the specified amount.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70434-104">语法</span><span class="sxs-lookup"><span data-stu-id="70434-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70434-105">参数</span><span class="sxs-lookup"><span data-stu-id="70434-105">Parameters</span></span>  
 `lReleaseCount`  
 <span data-ttu-id="70434-106">中当前实例的计数的增加量 `IHostSemaphore` 。</span><span class="sxs-lookup"><span data-stu-id="70434-106">[in] The amount by which to increase the count of the current `IHostSemaphore` instance.</span></span> <span data-ttu-id="70434-107">此量必须大于零。</span><span class="sxs-lookup"><span data-stu-id="70434-107">This amount must be greater than zero.</span></span>  
  
 `lpPreviousCount`  
 <span data-ttu-id="70434-108">弄指向上一个计数的指针; 如果调用方不需要以前的计数，则为 null。</span><span class="sxs-lookup"><span data-stu-id="70434-108">[out] A pointer to the previous count, or null if the caller does not require the previous count.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70434-109">返回值</span><span class="sxs-lookup"><span data-stu-id="70434-109">Return Value</span></span>  
  
|<span data-ttu-id="70434-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="70434-110">HRESULT</span></span>|<span data-ttu-id="70434-111">说明</span><span class="sxs-lookup"><span data-stu-id="70434-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="70434-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="70434-112">S_OK</span></span>|<span data-ttu-id="70434-113">`ReleaseSemaphore`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="70434-113">`ReleaseSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="70434-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="70434-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="70434-115">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="70434-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="70434-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="70434-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="70434-117">调用超时。</span><span class="sxs-lookup"><span data-stu-id="70434-117">The call timed out.</span></span>|  
|<span data-ttu-id="70434-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="70434-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="70434-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="70434-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="70434-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="70434-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="70434-121">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="70434-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="70434-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="70434-122">E_FAIL</span></span>|<span data-ttu-id="70434-123">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="70434-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="70434-124">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="70434-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="70434-125">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="70434-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70434-126">备注</span><span class="sxs-lookup"><span data-stu-id="70434-126">Remarks</span></span>  
 <span data-ttu-id="70434-127">CLR 通常会调用 `ReleaseSemaphore` 以通知宿主它已使用完资源，并为参数传递值 1 `lReleaseCount` 。</span><span class="sxs-lookup"><span data-stu-id="70434-127">The CLR typically calls `ReleaseSemaphore` to notify the host that it has finished using a resource, passing a value of 1 for the `lReleaseCount` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70434-128">要求</span><span class="sxs-lookup"><span data-stu-id="70434-128">Requirements</span></span>  
 <span data-ttu-id="70434-129">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="70434-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70434-130">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="70434-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="70434-131">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="70434-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="70434-132">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70434-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70434-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70434-133">See also</span></span>

- [<span data-ttu-id="70434-134">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="70434-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="70434-135">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="70434-135">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="70434-136">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="70434-136">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="70434-137">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="70434-137">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="70434-138">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="70434-138">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
