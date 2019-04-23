---
title: IHostTaskManager::BeginDelayAbort 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginDelayAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginDelayAbort
helpviewer_keywords:
- BeginDelayAbort method [.NET Framework hosting]
- IHostTaskManager::BeginDelayAbort method [.NET Framework hosting]
ms.assetid: 75f42a8b-ed68-4718-a030-a179cfba7d72
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 328462343669b3ea6bed2d86514ea348f6ae2b1e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197966"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="f4c7c-102">IHostTaskManager::BeginDelayAbort 方法</span><span class="sxs-lookup"><span data-stu-id="f4c7c-102">IHostTaskManager::BeginDelayAbort Method</span></span>
<span data-ttu-id="f4c7c-103">通知宿主托管代码进入不能在其中中止当前任务的周期。</span><span class="sxs-lookup"><span data-stu-id="f4c7c-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4c7c-104">语法</span><span class="sxs-lookup"><span data-stu-id="f4c7c-104">Syntax</span></span>  
  
```  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f4c7c-105">返回值</span><span class="sxs-lookup"><span data-stu-id="f4c7c-105">Return Value</span></span>  
  
|<span data-ttu-id="f4c7c-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f4c7c-106">HRESULT</span></span>|<span data-ttu-id="f4c7c-107">描述</span><span class="sxs-lookup"><span data-stu-id="f4c7c-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f4c7c-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f4c7c-108">S_OK</span></span>|<span data-ttu-id="f4c7c-109">`BeginDelayAbort` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="f4c7c-109">`BeginDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="f4c7c-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f4c7c-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f4c7c-111">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="f4c7c-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f4c7c-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f4c7c-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f4c7c-113">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="f4c7c-113">The call timed out.</span></span>|  
|<span data-ttu-id="f4c7c-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f4c7c-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f4c7c-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="f4c7c-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f4c7c-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f4c7c-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f4c7c-117">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="f4c7c-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f4c7c-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f4c7c-118">E_FAIL</span></span>|<span data-ttu-id="f4c7c-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="f4c7c-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f4c7c-120">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="f4c7c-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f4c7c-121">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="f4c7c-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f4c7c-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="f4c7c-122">E_UNEXPECTED</span></span>|<span data-ttu-id="f4c7c-123">`BeginDelayAbort` 已调用，但相应地调用[EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md)尚未收到。</span><span class="sxs-lookup"><span data-stu-id="f4c7c-123">`BeginDelayAbort` has already been called, but the corresponding call to [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4c7c-124">备注</span><span class="sxs-lookup"><span data-stu-id="f4c7c-124">Remarks</span></span>  
 <span data-ttu-id="f4c7c-125">主机必须中止当前任务之前`EndDelayAbort`调用。</span><span class="sxs-lookup"><span data-stu-id="f4c7c-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="f4c7c-126">如果另一个调用`BeginDelayAbort`对的干预调用不建立`EndDelayAbort`，主机应返回 E_UNEXPECTED 从`BeginDelayAbort`，并且应采取任何操作。</span><span class="sxs-lookup"><span data-stu-id="f4c7c-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4c7c-127">要求</span><span class="sxs-lookup"><span data-stu-id="f4c7c-127">Requirements</span></span>  
 <span data-ttu-id="f4c7c-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f4c7c-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4c7c-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f4c7c-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f4c7c-130">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f4c7c-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f4c7c-131">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4c7c-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4c7c-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4c7c-132">See also</span></span>

- [<span data-ttu-id="f4c7c-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="f4c7c-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="f4c7c-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="f4c7c-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="f4c7c-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="f4c7c-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
