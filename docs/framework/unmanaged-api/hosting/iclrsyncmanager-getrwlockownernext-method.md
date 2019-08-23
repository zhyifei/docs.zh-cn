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
ms.openlocfilehash: dbc38d9cf88f2449bbf689e4cf1b4101f47a0577
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943251"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="69ed6-102">ICLRSyncManager::GetRWLockOwnerNext 方法</span><span class="sxs-lookup"><span data-stu-id="69ed6-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="69ed6-103">获取在当前读取器-编写器锁上被阻止的下一个[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="69ed6-103">Gets the next [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69ed6-104">语法</span><span class="sxs-lookup"><span data-stu-id="69ed6-104">Syntax</span></span>  
  
```  
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69ed6-105">参数</span><span class="sxs-lookup"><span data-stu-id="69ed6-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="69ed6-106">中使用对[CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)的调用创建的迭代器。</span><span class="sxs-lookup"><span data-stu-id="69ed6-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="69ed6-107">弄指向下一个`IHostTask`正在等待锁定的的指针; 如果没有正在等待的任务, 则为 null。</span><span class="sxs-lookup"><span data-stu-id="69ed6-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="69ed6-108">返回值</span><span class="sxs-lookup"><span data-stu-id="69ed6-108">Return Value</span></span>  
  
|<span data-ttu-id="69ed6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="69ed6-109">HRESULT</span></span>|<span data-ttu-id="69ed6-110">描述</span><span class="sxs-lookup"><span data-stu-id="69ed6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="69ed6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="69ed6-111">S_OK</span></span>|<span data-ttu-id="69ed6-112">`GetRWLockOwnerNext`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="69ed6-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="69ed6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="69ed6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="69ed6-114">公共语言运行时 (CLR) 未加载到进程中, 或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="69ed6-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="69ed6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="69ed6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="69ed6-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="69ed6-116">The call timed out.</span></span>|  
|<span data-ttu-id="69ed6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="69ed6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="69ed6-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="69ed6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="69ed6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="69ed6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="69ed6-120">已阻止的线程或纤程正在等待某个事件时, 该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="69ed6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="69ed6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="69ed6-121">E_FAIL</span></span>|<span data-ttu-id="69ed6-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="69ed6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="69ed6-123">当方法返回 E_FAIL 时, CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="69ed6-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="69ed6-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="69ed6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69ed6-125">备注</span><span class="sxs-lookup"><span data-stu-id="69ed6-125">Remarks</span></span>  
 <span data-ttu-id="69ed6-126">如果`ppOwnerHostTask`设置为 null, 则迭代已终止, 主机应调用[DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="69ed6-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="69ed6-127">CLR 对指向`AddRef`的`IHostTask` `ppOwnerHostTask`调用, 以防止该任务在宿主保存指针时退出。</span><span class="sxs-lookup"><span data-stu-id="69ed6-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="69ed6-128">宿主必须调用`Release` , 以在完成后减小引用计数。</span><span class="sxs-lookup"><span data-stu-id="69ed6-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69ed6-129">要求</span><span class="sxs-lookup"><span data-stu-id="69ed6-129">Requirements</span></span>  
 <span data-ttu-id="69ed6-130">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="69ed6-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69ed6-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="69ed6-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="69ed6-132">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="69ed6-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="69ed6-133">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69ed6-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69ed6-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="69ed6-134">See also</span></span>

- [<span data-ttu-id="69ed6-135">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="69ed6-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="69ed6-136">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="69ed6-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
