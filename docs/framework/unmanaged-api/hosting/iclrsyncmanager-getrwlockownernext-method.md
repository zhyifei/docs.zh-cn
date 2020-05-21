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
ms.openlocfilehash: e5a8f69e66bb4b6373aea2c753bff9351bff8128
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762482"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="134fa-102">ICLRSyncManager::GetRWLockOwnerNext 方法</span><span class="sxs-lookup"><span data-stu-id="134fa-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="134fa-103">获取在当前读取器-编写器锁上被阻止的下一个[IHostTask](ihosttask-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="134fa-103">Gets the next [IHostTask](ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="134fa-104">语法</span><span class="sxs-lookup"><span data-stu-id="134fa-104">Syntax</span></span>  
  
```cpp
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="134fa-105">参数</span><span class="sxs-lookup"><span data-stu-id="134fa-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="134fa-106">中使用对[CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md)的调用创建的迭代器。</span><span class="sxs-lookup"><span data-stu-id="134fa-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="134fa-107">弄指向下一个正在 `IHostTask` 等待锁定的的指针; 如果没有正在等待的任务，则为 null。</span><span class="sxs-lookup"><span data-stu-id="134fa-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="134fa-108">返回值</span><span class="sxs-lookup"><span data-stu-id="134fa-108">Return Value</span></span>  
  
|<span data-ttu-id="134fa-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="134fa-109">HRESULT</span></span>|<span data-ttu-id="134fa-110">说明</span><span class="sxs-lookup"><span data-stu-id="134fa-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="134fa-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="134fa-111">S_OK</span></span>|<span data-ttu-id="134fa-112">`GetRWLockOwnerNext`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="134fa-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="134fa-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="134fa-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="134fa-114">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="134fa-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="134fa-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="134fa-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="134fa-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="134fa-116">The call timed out.</span></span>|  
|<span data-ttu-id="134fa-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="134fa-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="134fa-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="134fa-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="134fa-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="134fa-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="134fa-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="134fa-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="134fa-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="134fa-121">E_FAIL</span></span>|<span data-ttu-id="134fa-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="134fa-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="134fa-123">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="134fa-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="134fa-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="134fa-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="134fa-125">注解</span><span class="sxs-lookup"><span data-stu-id="134fa-125">Remarks</span></span>  
 <span data-ttu-id="134fa-126">如果 `ppOwnerHostTask` 设置为 null，则迭代已终止，主机应调用[DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="134fa-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="134fa-127">CLR 对指向的调用，以 `AddRef` `IHostTask` `ppOwnerHostTask` 防止该任务在宿主保存指针时退出。</span><span class="sxs-lookup"><span data-stu-id="134fa-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="134fa-128">宿主必须调用 `Release` ，以在完成后减小引用计数。</span><span class="sxs-lookup"><span data-stu-id="134fa-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="134fa-129">要求</span><span class="sxs-lookup"><span data-stu-id="134fa-129">Requirements</span></span>  
 <span data-ttu-id="134fa-130">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="134fa-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="134fa-131">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="134fa-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="134fa-132">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="134fa-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="134fa-133">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="134fa-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="134fa-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="134fa-134">See also</span></span>

- [<span data-ttu-id="134fa-135">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="134fa-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="134fa-136">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="134fa-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
