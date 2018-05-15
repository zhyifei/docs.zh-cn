---
title: IHostSyncManager::CreateCrst 方法
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateCrst
helpviewer_keywords:
- CreateCrst method [.NET Framework hosting]
- IHostSyncManager::CreateCrst method [.NET Framework hosting]
ms.assetid: ac278cc8-2540-4a6c-b5c6-b90c3970b4f4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 101a652aa77e587003fb7e773e00ba9b77461a06
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="ihostsyncmanagercreatecrst-method"></a><span data-ttu-id="76a30-102">IHostSyncManager::CreateCrst 方法</span><span class="sxs-lookup"><span data-stu-id="76a30-102">IHostSyncManager::CreateCrst Method</span></span>
<span data-ttu-id="76a30-103">创建同步的关键部分对象。</span><span class="sxs-lookup"><span data-stu-id="76a30-103">Creates a critical section object for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76a30-104">语法</span><span class="sxs-lookup"><span data-stu-id="76a30-104">Syntax</span></span>  
  
```  
HRESULT CreateCrst (  
    [out] IHostCrst** ppCrst  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="76a30-105">参数</span><span class="sxs-lookup"><span data-stu-id="76a30-105">Parameters</span></span>  
 `ppCrst`  
 <span data-ttu-id="76a30-106">[out]指向的地址的指针[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)实例实现的主机，或者，如果无法创建关键部分。</span><span class="sxs-lookup"><span data-stu-id="76a30-106">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance implemented by the host, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76a30-107">返回值</span><span class="sxs-lookup"><span data-stu-id="76a30-107">Return Value</span></span>  
  
|<span data-ttu-id="76a30-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="76a30-108">HRESULT</span></span>|<span data-ttu-id="76a30-109">描述</span><span class="sxs-lookup"><span data-stu-id="76a30-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="76a30-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="76a30-110">S_OK</span></span>|<span data-ttu-id="76a30-111">`CreateCrst` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="76a30-111">`CreateCrst` returned successfully.</span></span>|  
|<span data-ttu-id="76a30-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="76a30-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="76a30-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="76a30-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="76a30-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="76a30-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="76a30-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="76a30-115">The call timed out.</span></span>|  
|<span data-ttu-id="76a30-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="76a30-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="76a30-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="76a30-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="76a30-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="76a30-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="76a30-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="76a30-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="76a30-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="76a30-120">E_FAIL</span></span>|<span data-ttu-id="76a30-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="76a30-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="76a30-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="76a30-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="76a30-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="76a30-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="76a30-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="76a30-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="76a30-125">没有足够的内存已可用于创建请求的关键部分。</span><span class="sxs-lookup"><span data-stu-id="76a30-125">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76a30-126">备注</span><span class="sxs-lookup"><span data-stu-id="76a30-126">Remarks</span></span>  
 <span data-ttu-id="76a30-127">关键部分对象提供类似于所提供的 mutex 对象、 同步，只不过可以仅由单一进程的线程使用临界区。</span><span class="sxs-lookup"><span data-stu-id="76a30-127">Critical section objects provide synchronization similar to that provided by a mutex object, except that critical sections can be used only by the threads of a single process.</span></span> <span data-ttu-id="76a30-128">`CreateCrst` 镜像 Win32`InitializeCriticalSection`函数。</span><span class="sxs-lookup"><span data-stu-id="76a30-128">`CreateCrst` mirrors the Win32 `InitializeCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76a30-129">要求</span><span class="sxs-lookup"><span data-stu-id="76a30-129">Requirements</span></span>  
 <span data-ttu-id="76a30-130">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="76a30-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76a30-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="76a30-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="76a30-132">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="76a30-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76a30-133">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76a30-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76a30-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="76a30-134">See Also</span></span>  
 [<span data-ttu-id="76a30-135">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="76a30-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="76a30-136">IHostCrst 接口</span><span class="sxs-lookup"><span data-stu-id="76a30-136">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="76a30-137">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="76a30-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="76a30-138">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="76a30-138">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="76a30-139">Mutex</span><span class="sxs-lookup"><span data-stu-id="76a30-139">Mutexes</span></span>](../../../../docs/standard/threading/mutexes.md)  
 [<span data-ttu-id="76a30-140">Semaphore 和 SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="76a30-140">Semaphore and SemaphoreSlim</span></span>](../../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
