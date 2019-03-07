---
title: ICLRSyncManager::DeleteRWLockOwnerIterator 方法
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.DeleteRWLockOwnerIterator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::DeleteRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::DeleteRWLockOwnerIterator method [.NET Framework hosting]
- DeleteRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: fcfd340a-b7d6-44e4-8167-2c05b789d483
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ba0cabfe9e96ace255235f1aa7d2b80452c4d72e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482881"
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="b1e14-102">ICLRSyncManager::DeleteRWLockOwnerIterator 方法</span><span class="sxs-lookup"><span data-stu-id="b1e14-102">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>
<span data-ttu-id="b1e14-103">请求公共语言运行时 (CLR) 销毁一个迭代器，已通过调用[iclrsyncmanager:: Createrwlockowneriterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)。</span><span class="sxs-lookup"><span data-stu-id="b1e14-103">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1e14-104">语法</span><span class="sxs-lookup"><span data-stu-id="b1e14-104">Syntax</span></span>  
  
```  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1e14-105">参数</span><span class="sxs-lookup"><span data-stu-id="b1e14-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="b1e14-106">[in]已通过使用调用迭代器`CreateRWLockOwnerIterator`。</span><span class="sxs-lookup"><span data-stu-id="b1e14-106">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b1e14-107">返回值</span><span class="sxs-lookup"><span data-stu-id="b1e14-107">Return Value</span></span>  
  
|<span data-ttu-id="b1e14-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b1e14-108">HRESULT</span></span>|<span data-ttu-id="b1e14-109">描述</span><span class="sxs-lookup"><span data-stu-id="b1e14-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b1e14-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b1e14-110">S_OK</span></span>|<span data-ttu-id="b1e14-111">`DeleteRWLockOwnerIterator` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="b1e14-111">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="b1e14-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b1e14-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b1e14-113">CLR 尚未加载到进程，或处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="b1e14-113">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="b1e14-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b1e14-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b1e14-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="b1e14-115">The call timed out.</span></span>|  
|<span data-ttu-id="b1e14-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b1e14-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b1e14-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="b1e14-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b1e14-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b1e14-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b1e14-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="b1e14-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b1e14-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b1e14-120">E_FAIL</span></span>|<span data-ttu-id="b1e14-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="b1e14-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b1e14-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="b1e14-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b1e14-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="b1e14-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1e14-124">备注</span><span class="sxs-lookup"><span data-stu-id="b1e14-124">Remarks</span></span>  
 <span data-ttu-id="b1e14-125">主机可以调用此方法和`CreateRWLockOwnerIterator`以确保其线程实现保持同步。</span><span class="sxs-lookup"><span data-stu-id="b1e14-125">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1e14-126">要求</span><span class="sxs-lookup"><span data-stu-id="b1e14-126">Requirements</span></span>  
 <span data-ttu-id="b1e14-127">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b1e14-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1e14-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b1e14-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b1e14-129">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b1e14-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b1e14-130">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1e14-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1e14-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="b1e14-131">See also</span></span>
- [<span data-ttu-id="b1e14-132">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="b1e14-132">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="b1e14-133">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="b1e14-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
