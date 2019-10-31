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
ms.openlocfilehash: 860a818b08cb88b0fa17adccdfac5c81c0ec502c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130561"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="2609f-102">ICLRSyncManager::GetRWLockOwnerNext 方法</span><span class="sxs-lookup"><span data-stu-id="2609f-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="2609f-103">获取在当前读取器-编写器锁上被阻止的下一个[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="2609f-103">Gets the next [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2609f-104">语法</span><span class="sxs-lookup"><span data-stu-id="2609f-104">Syntax</span></span>  
  
```cpp
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2609f-105">参数</span><span class="sxs-lookup"><span data-stu-id="2609f-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="2609f-106">中使用对[CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)的调用创建的迭代器。</span><span class="sxs-lookup"><span data-stu-id="2609f-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="2609f-107">弄指向下一个正在等待锁的 `IHostTask` 的指针; 如果没有任务正在等待，则为 null。</span><span class="sxs-lookup"><span data-stu-id="2609f-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2609f-108">返回值</span><span class="sxs-lookup"><span data-stu-id="2609f-108">Return Value</span></span>  
  
|<span data-ttu-id="2609f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2609f-109">HRESULT</span></span>|<span data-ttu-id="2609f-110">描述</span><span class="sxs-lookup"><span data-stu-id="2609f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2609f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2609f-111">S_OK</span></span>|<span data-ttu-id="2609f-112">`GetRWLockOwnerNext` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="2609f-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="2609f-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2609f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2609f-114">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="2609f-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2609f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2609f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2609f-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="2609f-116">The call timed out.</span></span>|  
|<span data-ttu-id="2609f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2609f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2609f-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="2609f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2609f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2609f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2609f-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="2609f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2609f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2609f-121">E_FAIL</span></span>|<span data-ttu-id="2609f-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="2609f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2609f-123">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="2609f-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2609f-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="2609f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2609f-125">备注</span><span class="sxs-lookup"><span data-stu-id="2609f-125">Remarks</span></span>  
 <span data-ttu-id="2609f-126">如果 `ppOwnerHostTask` 设置为 null，则迭代已终止，主机应调用[DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="2609f-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2609f-127">CLR 对 `IHostTask` 调用 `AddRef`，`ppOwnerHostTask` 点来阻止该任务在宿主保存指针时退出。</span><span class="sxs-lookup"><span data-stu-id="2609f-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="2609f-128">宿主必须调用 `Release` 以便在引用计数完成后将其递减。</span><span class="sxs-lookup"><span data-stu-id="2609f-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2609f-129">要求</span><span class="sxs-lookup"><span data-stu-id="2609f-129">Requirements</span></span>  
 <span data-ttu-id="2609f-130">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2609f-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2609f-131">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2609f-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2609f-132">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="2609f-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2609f-133">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2609f-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2609f-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="2609f-134">See also</span></span>

- [<span data-ttu-id="2609f-135">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="2609f-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="2609f-136">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="2609f-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
