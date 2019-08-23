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
ms.openlocfilehash: 622b6c523adfb7bae2fc38826152ef69709568cc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931080"
---
# <a name="ihostsyncmanagercreatecrst-method"></a><span data-ttu-id="08c04-102">IHostSyncManager::CreateCrst 方法</span><span class="sxs-lookup"><span data-stu-id="08c04-102">IHostSyncManager::CreateCrst Method</span></span>
<span data-ttu-id="08c04-103">创建用于同步的临界区对象。</span><span class="sxs-lookup"><span data-stu-id="08c04-103">Creates a critical section object for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08c04-104">语法</span><span class="sxs-lookup"><span data-stu-id="08c04-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrst (  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08c04-105">参数</span><span class="sxs-lookup"><span data-stu-id="08c04-105">Parameters</span></span>  
 `ppCrst`  
 <span data-ttu-id="08c04-106">弄指向主机实现的[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)实例的地址的指针; 如果无法创建关键节, 则为 null。</span><span class="sxs-lookup"><span data-stu-id="08c04-106">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance implemented by the host, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08c04-107">返回值</span><span class="sxs-lookup"><span data-stu-id="08c04-107">Return Value</span></span>  
  
|<span data-ttu-id="08c04-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="08c04-108">HRESULT</span></span>|<span data-ttu-id="08c04-109">描述</span><span class="sxs-lookup"><span data-stu-id="08c04-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="08c04-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="08c04-110">S_OK</span></span>|<span data-ttu-id="08c04-111">`CreateCrst`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="08c04-111">`CreateCrst` returned successfully.</span></span>|  
|<span data-ttu-id="08c04-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="08c04-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="08c04-113">公共语言运行时 (CLR) 未加载到进程中, 或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="08c04-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="08c04-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="08c04-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="08c04-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="08c04-115">The call timed out.</span></span>|  
|<span data-ttu-id="08c04-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="08c04-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="08c04-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="08c04-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="08c04-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="08c04-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="08c04-119">已阻止的线程或纤程正在等待某个事件时, 该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="08c04-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="08c04-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="08c04-120">E_FAIL</span></span>|<span data-ttu-id="08c04-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="08c04-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="08c04-122">当方法返回 E_FAIL 时, CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="08c04-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="08c04-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="08c04-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="08c04-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="08c04-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="08c04-125">没有足够的内存可用于创建请求的关键部分。</span><span class="sxs-lookup"><span data-stu-id="08c04-125">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08c04-126">备注</span><span class="sxs-lookup"><span data-stu-id="08c04-126">Remarks</span></span>  
 <span data-ttu-id="08c04-127">临界区对象提供与 mutex 对象提供的同步, 只不过临界区只能由单个进程的线程使用。</span><span class="sxs-lookup"><span data-stu-id="08c04-127">Critical section objects provide synchronization similar to that provided by a mutex object, except that critical sections can be used only by the threads of a single process.</span></span> <span data-ttu-id="08c04-128">`CreateCrst`对 Win32 `InitializeCriticalSection`函数进行镜像。</span><span class="sxs-lookup"><span data-stu-id="08c04-128">`CreateCrst` mirrors the Win32 `InitializeCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08c04-129">要求</span><span class="sxs-lookup"><span data-stu-id="08c04-129">Requirements</span></span>  
 <span data-ttu-id="08c04-130">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="08c04-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08c04-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="08c04-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="08c04-132">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="08c04-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="08c04-133">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08c04-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08c04-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="08c04-134">See also</span></span>

- [<span data-ttu-id="08c04-135">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="08c04-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="08c04-136">IHostCrst 接口</span><span class="sxs-lookup"><span data-stu-id="08c04-136">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="08c04-137">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="08c04-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="08c04-138">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="08c04-138">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="08c04-139">Mutex</span><span class="sxs-lookup"><span data-stu-id="08c04-139">Mutexes</span></span>](../../../standard/threading/mutexes.md)
- [<span data-ttu-id="08c04-140">Semaphore 和 SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="08c04-140">Semaphore and SemaphoreSlim</span></span>](../../../standard/threading/semaphore-and-semaphoreslim.md)
