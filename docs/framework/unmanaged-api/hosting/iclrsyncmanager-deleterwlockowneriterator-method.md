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
ms.openlocfilehash: fb02b5c941e15d172140565e8efb625234947cd7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130575"
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="b4bbe-102">ICLRSyncManager::DeleteRWLockOwnerIterator 方法</span><span class="sxs-lookup"><span data-stu-id="b4bbe-102">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>
<span data-ttu-id="b4bbe-103">请求公共语言运行时（CLR）销毁通过调用[ICLRSyncManager：： CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)创建的迭代器。</span><span class="sxs-lookup"><span data-stu-id="b4bbe-103">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4bbe-104">语法</span><span class="sxs-lookup"><span data-stu-id="b4bbe-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4bbe-105">参数</span><span class="sxs-lookup"><span data-stu-id="b4bbe-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="b4bbe-106">中使用对 `CreateRWLockOwnerIterator`的调用创建的迭代器。</span><span class="sxs-lookup"><span data-stu-id="b4bbe-106">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4bbe-107">返回值</span><span class="sxs-lookup"><span data-stu-id="b4bbe-107">Return Value</span></span>  
  
|<span data-ttu-id="b4bbe-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b4bbe-108">HRESULT</span></span>|<span data-ttu-id="b4bbe-109">描述</span><span class="sxs-lookup"><span data-stu-id="b4bbe-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b4bbe-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b4bbe-110">S_OK</span></span>|<span data-ttu-id="b4bbe-111">`DeleteRWLockOwnerIterator` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="b4bbe-111">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="b4bbe-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b4bbe-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b4bbe-113">CLR 尚未加载到进程中，或处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="b4bbe-113">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="b4bbe-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b4bbe-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b4bbe-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="b4bbe-115">The call timed out.</span></span>|  
|<span data-ttu-id="b4bbe-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b4bbe-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b4bbe-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="b4bbe-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b4bbe-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b4bbe-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b4bbe-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="b4bbe-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b4bbe-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b4bbe-120">E_FAIL</span></span>|<span data-ttu-id="b4bbe-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="b4bbe-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b4bbe-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="b4bbe-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b4bbe-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="b4bbe-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4bbe-124">备注</span><span class="sxs-lookup"><span data-stu-id="b4bbe-124">Remarks</span></span>  
 <span data-ttu-id="b4bbe-125">宿主可以调用此方法并 `CreateRWLockOwnerIterator`，以确保它的线程实现保持同步。</span><span class="sxs-lookup"><span data-stu-id="b4bbe-125">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4bbe-126">要求</span><span class="sxs-lookup"><span data-stu-id="b4bbe-126">Requirements</span></span>  
 <span data-ttu-id="b4bbe-127">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b4bbe-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4bbe-128">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b4bbe-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b4bbe-129">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="b4bbe-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4bbe-130">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4bbe-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4bbe-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4bbe-131">See also</span></span>

- [<span data-ttu-id="b4bbe-132">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="b4bbe-132">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="b4bbe-133">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="b4bbe-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
