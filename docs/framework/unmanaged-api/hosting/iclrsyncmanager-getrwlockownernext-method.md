---
title: "ICLRSyncManager::GetRWLockOwnerNext 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRSyncManager.GetRWLockOwnerNext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetRWLockOwnerNext
helpviewer_keywords:
- ICLRSyncManager::GetRWLockOwnerNext method [.NET Framework hosting]
- GetRWLockOwnerNext method [.NET Framework hosting]
ms.assetid: 0e025b6a-280e-40a2-a2d0-b15f58777b81
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1181cbb71aa30281fbff634354162e1f245d05fe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="2d3de-102">ICLRSyncManager::GetRWLockOwnerNext 方法</span><span class="sxs-lookup"><span data-stu-id="2d3de-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="2d3de-103">获取下一个[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)在当前的读取器 / 编写器锁被阻止的实例。</span><span class="sxs-lookup"><span data-stu-id="2d3de-103">Gets the next [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d3de-104">语法</span><span class="sxs-lookup"><span data-stu-id="2d3de-104">Syntax</span></span>  
  
```  
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2d3de-105">参数</span><span class="sxs-lookup"><span data-stu-id="2d3de-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="2d3de-106">[in]通过调用创建的迭代器[CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)。</span><span class="sxs-lookup"><span data-stu-id="2d3de-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="2d3de-107">[out]指向下一步的`IHostTask`，正在等待的锁或为 null 如果等待没有任何任务。</span><span class="sxs-lookup"><span data-stu-id="2d3de-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d3de-108">返回值</span><span class="sxs-lookup"><span data-stu-id="2d3de-108">Return Value</span></span>  
  
|<span data-ttu-id="2d3de-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2d3de-109">HRESULT</span></span>|<span data-ttu-id="2d3de-110">描述</span><span class="sxs-lookup"><span data-stu-id="2d3de-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2d3de-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2d3de-111">S_OK</span></span>|<span data-ttu-id="2d3de-112">`GetRWLockOwnerNext`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="2d3de-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="2d3de-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2d3de-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2d3de-114">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="2d3de-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2d3de-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2d3de-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2d3de-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="2d3de-116">The call timed out.</span></span>|  
|<span data-ttu-id="2d3de-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2d3de-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2d3de-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="2d3de-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2d3de-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2d3de-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2d3de-120">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="2d3de-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2d3de-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2d3de-121">E_FAIL</span></span>|<span data-ttu-id="2d3de-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="2d3de-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2d3de-123">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="2d3de-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2d3de-124">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="2d3de-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d3de-125">备注</span><span class="sxs-lookup"><span data-stu-id="2d3de-125">Remarks</span></span>  
 <span data-ttu-id="2d3de-126">如果`ppOwnerHostTask`设置为 null，已经终止迭代，而且主机应调用[DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="2d3de-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d3de-127">CLR 调用`AddRef`上`IHostTask`到`ppOwnerHostTask`点，以防止主机保持指针退出此任务。</span><span class="sxs-lookup"><span data-stu-id="2d3de-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="2d3de-128">宿主必须调用`Release`要完成后递减引用计数。</span><span class="sxs-lookup"><span data-stu-id="2d3de-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d3de-129">惠?</span><span class="sxs-lookup"><span data-stu-id="2d3de-129">Requirements</span></span>  
 <span data-ttu-id="2d3de-130">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2d3de-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d3de-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2d3de-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2d3de-132">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2d3de-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2d3de-133">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d3de-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d3de-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d3de-134">See Also</span></span>  
 [<span data-ttu-id="2d3de-135">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="2d3de-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="2d3de-136">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="2d3de-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
