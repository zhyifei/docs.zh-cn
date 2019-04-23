---
title: ICLRSyncManager::GetRWLockOwnerNext 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3efe80c0442e765274b309e39a79cc867676043
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59169645"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="3f583-102">ICLRSyncManager::GetRWLockOwnerNext 方法</span><span class="sxs-lookup"><span data-stu-id="3f583-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="3f583-103">获取下一步[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)实例上当前的读取器 / 编写器锁上阻塞。</span><span class="sxs-lookup"><span data-stu-id="3f583-103">Gets the next [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f583-104">语法</span><span class="sxs-lookup"><span data-stu-id="3f583-104">Syntax</span></span>  
  
```  
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f583-105">参数</span><span class="sxs-lookup"><span data-stu-id="3f583-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="3f583-106">[in]已通过使用调用迭代器[CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)。</span><span class="sxs-lookup"><span data-stu-id="3f583-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="3f583-107">[out]到下一个指针`IHostTask`，如果没有在任务等待正在等待锁，或为 null。</span><span class="sxs-lookup"><span data-stu-id="3f583-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f583-108">返回值</span><span class="sxs-lookup"><span data-stu-id="3f583-108">Return Value</span></span>  
  
|<span data-ttu-id="3f583-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3f583-109">HRESULT</span></span>|<span data-ttu-id="3f583-110">描述</span><span class="sxs-lookup"><span data-stu-id="3f583-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3f583-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3f583-111">S_OK</span></span>|<span data-ttu-id="3f583-112">`GetRWLockOwnerNext` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="3f583-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="3f583-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3f583-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3f583-114">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="3f583-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3f583-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3f583-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3f583-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="3f583-116">The call timed out.</span></span>|  
|<span data-ttu-id="3f583-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3f583-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3f583-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="3f583-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3f583-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3f583-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3f583-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="3f583-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3f583-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3f583-121">E_FAIL</span></span>|<span data-ttu-id="3f583-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="3f583-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3f583-123">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="3f583-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3f583-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="3f583-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f583-125">备注</span><span class="sxs-lookup"><span data-stu-id="3f583-125">Remarks</span></span>  
 <span data-ttu-id="3f583-126">如果`ppOwnerHostTask`设置为 null，迭代已终止，并应调用在主机[DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="3f583-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f583-127">CLR 调用`AddRef`上`IHostTask`到`ppOwnerHostTask`点若要防止此任务退出时将指针停留在主机。</span><span class="sxs-lookup"><span data-stu-id="3f583-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="3f583-128">宿主必须调用`Release`要完成后递减引用计数。</span><span class="sxs-lookup"><span data-stu-id="3f583-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f583-129">要求</span><span class="sxs-lookup"><span data-stu-id="3f583-129">Requirements</span></span>  
 <span data-ttu-id="3f583-130">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3f583-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f583-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3f583-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3f583-132">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3f583-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3f583-133">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f583-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f583-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f583-134">See also</span></span>

- [<span data-ttu-id="3f583-135">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="3f583-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="3f583-136">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="3f583-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
