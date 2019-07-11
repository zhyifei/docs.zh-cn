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
ms.openlocfilehash: 88b7b2093ecb2c601e57eca32e25c21e91641281
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753470"
---
# <a name="ihostsyncmanagercreatecrst-method"></a><span data-ttu-id="ce7c3-102">IHostSyncManager::CreateCrst 方法</span><span class="sxs-lookup"><span data-stu-id="ce7c3-102">IHostSyncManager::CreateCrst Method</span></span>
<span data-ttu-id="ce7c3-103">创建用于同步的关键部分对象。</span><span class="sxs-lookup"><span data-stu-id="ce7c3-103">Creates a critical section object for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce7c3-104">语法</span><span class="sxs-lookup"><span data-stu-id="ce7c3-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrst (  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce7c3-105">参数</span><span class="sxs-lookup"><span data-stu-id="ce7c3-105">Parameters</span></span>  
 `ppCrst`  
 <span data-ttu-id="ce7c3-106">[out]指向的地址的指针[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)实例实现的主机，或者，如果无法创建关键部分。</span><span class="sxs-lookup"><span data-stu-id="ce7c3-106">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance implemented by the host, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce7c3-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ce7c3-107">Return Value</span></span>  
  
|<span data-ttu-id="ce7c3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ce7c3-108">HRESULT</span></span>|<span data-ttu-id="ce7c3-109">描述</span><span class="sxs-lookup"><span data-stu-id="ce7c3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ce7c3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ce7c3-110">S_OK</span></span>|<span data-ttu-id="ce7c3-111">`CreateCrst` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="ce7c3-111">`CreateCrst` returned successfully.</span></span>|  
|<span data-ttu-id="ce7c3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ce7c3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ce7c3-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="ce7c3-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ce7c3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ce7c3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ce7c3-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="ce7c3-115">The call timed out.</span></span>|  
|<span data-ttu-id="ce7c3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ce7c3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ce7c3-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="ce7c3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ce7c3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ce7c3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ce7c3-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="ce7c3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ce7c3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ce7c3-120">E_FAIL</span></span>|<span data-ttu-id="ce7c3-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="ce7c3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ce7c3-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="ce7c3-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ce7c3-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="ce7c3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ce7c3-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ce7c3-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ce7c3-125">没有足够的内存是可用于创建请求的关键部分。</span><span class="sxs-lookup"><span data-stu-id="ce7c3-125">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce7c3-126">备注</span><span class="sxs-lookup"><span data-stu-id="ce7c3-126">Remarks</span></span>  
 <span data-ttu-id="ce7c3-127">关键节对象提供类似于所提供的 mutex 对象、 同步只不过临界区可以仅由单个进程的线程。</span><span class="sxs-lookup"><span data-stu-id="ce7c3-127">Critical section objects provide synchronization similar to that provided by a mutex object, except that critical sections can be used only by the threads of a single process.</span></span> <span data-ttu-id="ce7c3-128">`CreateCrst` 镜像 Win32`InitializeCriticalSection`函数。</span><span class="sxs-lookup"><span data-stu-id="ce7c3-128">`CreateCrst` mirrors the Win32 `InitializeCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce7c3-129">要求</span><span class="sxs-lookup"><span data-stu-id="ce7c3-129">Requirements</span></span>  
 <span data-ttu-id="ce7c3-130">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ce7c3-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce7c3-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ce7c3-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ce7c3-132">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ce7c3-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce7c3-133">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce7c3-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce7c3-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="ce7c3-134">See also</span></span>

- [<span data-ttu-id="ce7c3-135">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="ce7c3-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="ce7c3-136">IHostCrst 接口</span><span class="sxs-lookup"><span data-stu-id="ce7c3-136">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="ce7c3-137">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="ce7c3-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="ce7c3-138">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="ce7c3-138">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="ce7c3-139">Mutex</span><span class="sxs-lookup"><span data-stu-id="ce7c3-139">Mutexes</span></span>](../../../../docs/standard/threading/mutexes.md)
- [<span data-ttu-id="ce7c3-140">Semaphore 和 SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="ce7c3-140">Semaphore and SemaphoreSlim</span></span>](../../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
