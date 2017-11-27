---
title: "ICLRSyncManager::GetRWLockOwnerNext 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRSyncManager.GetRWLockOwnerNext
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRSyncManager::GetRWLockOwnerNext
helpviewer_keywords:
- ICLRSyncManager::GetRWLockOwnerNext method [.NET Framework hosting]
- GetRWLockOwnerNext method [.NET Framework hosting]
ms.assetid: 0e025b6a-280e-40a2-a2d0-b15f58777b81
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8551a6981efd1005f5433c8c862623766bf838f8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="af150-102">ICLRSyncManager::GetRWLockOwnerNext 方法</span><span class="sxs-lookup"><span data-stu-id="af150-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="af150-103">获取下一个[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)在当前的读取器 / 编写器锁被阻止的实例。</span><span class="sxs-lookup"><span data-stu-id="af150-103">Gets the next [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af150-104">语法</span><span class="sxs-lookup"><span data-stu-id="af150-104">Syntax</span></span>  
  
```  
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="af150-105">参数</span><span class="sxs-lookup"><span data-stu-id="af150-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="af150-106">[in]通过调用创建的迭代器[CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)。</span><span class="sxs-lookup"><span data-stu-id="af150-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="af150-107">[out]指向下一步的`IHostTask`，正在等待的锁或为 null 如果等待没有任何任务。</span><span class="sxs-lookup"><span data-stu-id="af150-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af150-108">返回值</span><span class="sxs-lookup"><span data-stu-id="af150-108">Return Value</span></span>  
  
|<span data-ttu-id="af150-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="af150-109">HRESULT</span></span>|<span data-ttu-id="af150-110">描述</span><span class="sxs-lookup"><span data-stu-id="af150-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="af150-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="af150-111">S_OK</span></span>|<span data-ttu-id="af150-112">`GetRWLockOwnerNext`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="af150-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="af150-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="af150-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="af150-114">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="af150-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="af150-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="af150-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="af150-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="af150-116">The call timed out.</span></span>|  
|<span data-ttu-id="af150-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="af150-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="af150-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="af150-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="af150-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="af150-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="af150-120">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="af150-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="af150-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="af150-121">E_FAIL</span></span>|<span data-ttu-id="af150-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="af150-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="af150-123">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="af150-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="af150-124">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="af150-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af150-125">备注</span><span class="sxs-lookup"><span data-stu-id="af150-125">Remarks</span></span>  
 <span data-ttu-id="af150-126">如果`ppOwnerHostTask`设置为 null，已经终止迭代，而且主机应调用[DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="af150-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af150-127">CLR 调用`AddRef`上`IHostTask`到`ppOwnerHostTask`点，以防止主机保持指针退出此任务。</span><span class="sxs-lookup"><span data-stu-id="af150-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="af150-128">宿主必须调用`Release`要完成后递减引用计数。</span><span class="sxs-lookup"><span data-stu-id="af150-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af150-129">要求</span><span class="sxs-lookup"><span data-stu-id="af150-129">Requirements</span></span>  
 <span data-ttu-id="af150-130">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="af150-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af150-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="af150-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="af150-132">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="af150-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="af150-133">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af150-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af150-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af150-134">See Also</span></span>  
 [<span data-ttu-id="af150-135">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="af150-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="af150-136">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="af150-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
