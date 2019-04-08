---
title: IHostSyncManager::CreateCrstWithSpinCount 方法
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateCrstWithSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateCrstWithSpinCount
helpviewer_keywords:
- CreateCrstWithSpinCount method [.NET Framework hosting]
- IHostSyncManager::CreateCrstWithSpinCount method [.NET Framework hosting]
ms.assetid: 7280fa8c-3639-4abf-91cb-bc343da742d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a288edc89029804de277484741c1895af7859b1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081523"
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a><span data-ttu-id="07b13-102">IHostSyncManager::CreateCrstWithSpinCount 方法</span><span class="sxs-lookup"><span data-stu-id="07b13-102">IHostSyncManager::CreateCrstWithSpinCount Method</span></span>
<span data-ttu-id="07b13-103">创建具有同步的重试次数的关键部分对象。</span><span class="sxs-lookup"><span data-stu-id="07b13-103">Creates a critical section object with spin count for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07b13-104">语法</span><span class="sxs-lookup"><span data-stu-id="07b13-104">Syntax</span></span>  
  
```  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07b13-105">参数</span><span class="sxs-lookup"><span data-stu-id="07b13-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="07b13-106">[in]指定关键部分对象的旋转计数。</span><span class="sxs-lookup"><span data-stu-id="07b13-106">[in] Specifies the spin count for the critical section object.</span></span>  
  
 `ppCrst`  
 <span data-ttu-id="07b13-107">[out]指向的地址的指针[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)实例，或如果无法创建关键节，则为 null。</span><span class="sxs-lookup"><span data-stu-id="07b13-107">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="07b13-108">返回值</span><span class="sxs-lookup"><span data-stu-id="07b13-108">Return Value</span></span>  
  
|<span data-ttu-id="07b13-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="07b13-109">HRESULT</span></span>|<span data-ttu-id="07b13-110">描述</span><span class="sxs-lookup"><span data-stu-id="07b13-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="07b13-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="07b13-111">S_OK</span></span>|`CreateCrstWithSpinCount` <span data-ttu-id="07b13-112">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="07b13-112">returned successfully.</span></span>|  
|<span data-ttu-id="07b13-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="07b13-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="07b13-114">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="07b13-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="07b13-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="07b13-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="07b13-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="07b13-116">The call timed out.</span></span>|  
|<span data-ttu-id="07b13-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="07b13-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="07b13-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="07b13-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="07b13-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="07b13-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="07b13-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="07b13-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="07b13-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="07b13-121">E_FAIL</span></span>|<span data-ttu-id="07b13-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="07b13-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="07b13-123">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="07b13-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="07b13-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="07b13-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="07b13-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="07b13-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="07b13-126">没有足够的内存是可用于创建请求的关键部分。</span><span class="sxs-lookup"><span data-stu-id="07b13-126">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07b13-127">备注</span><span class="sxs-lookup"><span data-stu-id="07b13-127">Remarks</span></span>  
 <span data-ttu-id="07b13-128">只能在多处理器系统上使用旋转计数。</span><span class="sxs-lookup"><span data-stu-id="07b13-128">A spin count is used only on a multi-processor system.</span></span> <span data-ttu-id="07b13-129">旋转计数指定的执行与不可用的关键部分关联的信号量上等待操作之前，必须启动调用线程的次数。</span><span class="sxs-lookup"><span data-stu-id="07b13-129">The spin count specifies the number of times a calling thread must spin before it performs a wait operation on a semaphore that is associated with an unavailable critical section.</span></span> <span data-ttu-id="07b13-130">如果数值调节钮操作期间，临界区变得可用，调用线程可以避免等待操作。</span><span class="sxs-lookup"><span data-stu-id="07b13-130">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span> `CreateCrstWithSpinCount` <span data-ttu-id="07b13-131">镜像 Win32`InitializeCriticalSectionAndSpinCount`函数。</span><span class="sxs-lookup"><span data-stu-id="07b13-131">mirrors the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07b13-132">要求</span><span class="sxs-lookup"><span data-stu-id="07b13-132">Requirements</span></span>  
 <span data-ttu-id="07b13-133">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="07b13-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07b13-134">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="07b13-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="07b13-135">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="07b13-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="07b13-136">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="07b13-136">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="07b13-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="07b13-137">See also</span></span>

- [<span data-ttu-id="07b13-138">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="07b13-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="07b13-139">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="07b13-139">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="07b13-140">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="07b13-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
