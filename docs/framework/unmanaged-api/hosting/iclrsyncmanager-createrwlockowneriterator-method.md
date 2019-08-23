---
title: ICLRSyncManager::CreateRWLockOwnerIterator 方法
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.CreateRWLockOwnerIterator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator method [.NET Framework hosting]
- CreateRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: b5535b87-9439-424e-b9b3-7d6fafb9819e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64179e132cfaffbb1fcdc2cd0a47bbcc11be2ff0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943262"
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a><span data-ttu-id="0763a-102">ICLRSyncManager::CreateRWLockOwnerIterator 方法</span><span class="sxs-lookup"><span data-stu-id="0763a-102">ICLRSyncManager::CreateRWLockOwnerIterator Method</span></span>
<span data-ttu-id="0763a-103">请求公共语言运行时 (CLR) 为主机创建迭代器, 以用于确定等待读取器-编写器锁的任务集。</span><span class="sxs-lookup"><span data-stu-id="0763a-103">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0763a-104">语法</span><span class="sxs-lookup"><span data-stu-id="0763a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0763a-105">参数</span><span class="sxs-lookup"><span data-stu-id="0763a-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="0763a-106">中与所需的读取器锁关联的 cookie。</span><span class="sxs-lookup"><span data-stu-id="0763a-106">[in] The cookie associated with the desired reader-writer lock.</span></span>  
  
 `pIterator`  
 <span data-ttu-id="0763a-107">弄指向可传递给[GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md)和[DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md)方法的迭代器的指针。</span><span class="sxs-lookup"><span data-stu-id="0763a-107">[out] A pointer to an iterator that can be passed to the [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) and [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0763a-108">返回值</span><span class="sxs-lookup"><span data-stu-id="0763a-108">Return Value</span></span>  
  
|<span data-ttu-id="0763a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0763a-109">HRESULT</span></span>|<span data-ttu-id="0763a-110">描述</span><span class="sxs-lookup"><span data-stu-id="0763a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0763a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0763a-111">S_OK</span></span>|<span data-ttu-id="0763a-112">`CreateRWLockOwnerIterator`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="0763a-112">`CreateRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="0763a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0763a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0763a-114">CLR 未加载到进程中, 或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="0763a-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0763a-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0763a-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0763a-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="0763a-116">The call timed out.</span></span>|  
|<span data-ttu-id="0763a-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0763a-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0763a-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="0763a-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0763a-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0763a-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0763a-120">已阻止的线程或纤程正在等待某个事件时, 该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="0763a-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0763a-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0763a-121">E_FAIL</span></span>|<span data-ttu-id="0763a-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="0763a-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0763a-123">当方法返回 E_FAIL 时, CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="0763a-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0763a-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="0763a-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0763a-125">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="0763a-125">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="0763a-126">`CreateRWLockOwnerIterator`在当前正在运行托管代码的线程上调用了。</span><span class="sxs-lookup"><span data-stu-id="0763a-126">`CreateRWLockOwnerIterator` was called on a thread that is currently running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0763a-127">备注</span><span class="sxs-lookup"><span data-stu-id="0763a-127">Remarks</span></span>  
 <span data-ttu-id="0763a-128">在死锁检测`CreateRWLockOwnerIterator`期间`DeleteRWLockOwnerIterator`, 主机`GetRWLockOwnerNext`通常会调用、和方法。</span><span class="sxs-lookup"><span data-stu-id="0763a-128">Hosts typically call the `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, and `GetRWLockOwnerNext` methods during deadlock detection.</span></span> <span data-ttu-id="0763a-129">宿主负责确保读取器-编写器锁仍有效, 因为 CLR 不会尝试使读取器-编写器锁保持活动状态。</span><span class="sxs-lookup"><span data-stu-id="0763a-129">The host is responsible for ensuring that the reader-writer lock is still valid, because the CLR makes no attempt to keep the reader-writer lock alive.</span></span> <span data-ttu-id="0763a-130">主机可以使用多种策略来确保锁的有效性:</span><span class="sxs-lookup"><span data-stu-id="0763a-130">Several strategies are available for the host to ensure the validity of the lock:</span></span>  
  
- <span data-ttu-id="0763a-131">宿主可以阻止读取器-编写器锁 (例如, [IHostSemaphore:: ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) 上的释放调用, 同时确保此块不会导致死锁。</span><span class="sxs-lookup"><span data-stu-id="0763a-131">The host can block release calls on the reader-writer lock (for example, [IHostSemaphore::ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) while ensuring that this block does not cause deadlock.</span></span>  
  
- <span data-ttu-id="0763a-132">宿主可以阻止退出等待与读取器-编写器锁关联的事件对象, 并再次确保此块不会导致死锁。</span><span class="sxs-lookup"><span data-stu-id="0763a-132">The host can block the exit from waiting on the event object associated with the reader-writer lock, again ensuring that this block does not cause deadlock.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0763a-133">`CreateRWLockOwnerIterator`只能在当前正在执行非托管代码的线程上调用。</span><span class="sxs-lookup"><span data-stu-id="0763a-133">`CreateRWLockOwnerIterator` must be called only on threads that are currently executing unmanaged code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0763a-134">要求</span><span class="sxs-lookup"><span data-stu-id="0763a-134">Requirements</span></span>  
 <span data-ttu-id="0763a-135">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0763a-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0763a-136">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0763a-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0763a-137">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="0763a-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0763a-138">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0763a-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0763a-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="0763a-139">See also</span></span>

- [<span data-ttu-id="0763a-140">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="0763a-140">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="0763a-141">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="0763a-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
