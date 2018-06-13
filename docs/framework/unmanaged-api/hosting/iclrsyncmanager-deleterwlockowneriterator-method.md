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
ms.openlocfilehash: 5ee4a09902be093bdbfe0b367f4add35bdda571c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434062"
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="03172-102">ICLRSyncManager::DeleteRWLockOwnerIterator 方法</span><span class="sxs-lookup"><span data-stu-id="03172-102">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>
<span data-ttu-id="03172-103">请求公共语言运行时 (CLR) 销毁由调用的迭代器[iclrsyncmanager:: Createrwlockowneriterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)。</span><span class="sxs-lookup"><span data-stu-id="03172-103">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03172-104">语法</span><span class="sxs-lookup"><span data-stu-id="03172-104">Syntax</span></span>  
  
```  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="03172-105">参数</span><span class="sxs-lookup"><span data-stu-id="03172-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="03172-106">[in]通过调用创建的迭代器`CreateRWLockOwnerIterator`。</span><span class="sxs-lookup"><span data-stu-id="03172-106">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="03172-107">返回值</span><span class="sxs-lookup"><span data-stu-id="03172-107">Return Value</span></span>  
  
|<span data-ttu-id="03172-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="03172-108">HRESULT</span></span>|<span data-ttu-id="03172-109">描述</span><span class="sxs-lookup"><span data-stu-id="03172-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="03172-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="03172-110">S_OK</span></span>|<span data-ttu-id="03172-111">`DeleteRWLockOwnerIterator` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="03172-111">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="03172-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="03172-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="03172-113">CLR 尚未加载到进程，或者处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="03172-113">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="03172-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="03172-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="03172-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="03172-115">The call timed out.</span></span>|  
|<span data-ttu-id="03172-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="03172-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="03172-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="03172-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="03172-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="03172-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="03172-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="03172-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="03172-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="03172-120">E_FAIL</span></span>|<span data-ttu-id="03172-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="03172-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="03172-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="03172-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="03172-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="03172-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03172-124">备注</span><span class="sxs-lookup"><span data-stu-id="03172-124">Remarks</span></span>  
 <span data-ttu-id="03172-125">主机可以调用此方法和`CreateRWLockOwnerIterator`以确保其线程实现保持同步。</span><span class="sxs-lookup"><span data-stu-id="03172-125">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03172-126">要求</span><span class="sxs-lookup"><span data-stu-id="03172-126">Requirements</span></span>  
 <span data-ttu-id="03172-127">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="03172-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03172-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="03172-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="03172-129">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="03172-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="03172-130">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03172-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03172-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="03172-131">See Also</span></span>  
 [<span data-ttu-id="03172-132">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="03172-132">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="03172-133">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="03172-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
