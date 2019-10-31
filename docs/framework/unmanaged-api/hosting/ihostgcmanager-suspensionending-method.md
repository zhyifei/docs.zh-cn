---
title: IHostGCManager::SuspensionEnding 方法
ms.date: 03/30/2017
api_name:
- IHostGCManager.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionEnding
helpviewer_keywords:
- SuspensionEnding method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionEnding method [.NET Framework hosting]
ms.assetid: 8849a1db-17f0-44b7-880a-bd36d431eb91
topic_type:
- apiref
ms.openlocfilehash: 6ef04799c0062c40f1671cbe6d897a148e1b93bb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130474"
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="a1af3-102">IHostGCManager::SuspensionEnding 方法</span><span class="sxs-lookup"><span data-stu-id="a1af3-102">IHostGCManager::SuspensionEnding Method</span></span>
<span data-ttu-id="a1af3-103">向宿主通知公共语言运行时（CLR）正在恢复在已挂起的垃圾回收的线程上执行任务。</span><span class="sxs-lookup"><span data-stu-id="a1af3-103">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1af3-104">语法</span><span class="sxs-lookup"><span data-stu-id="a1af3-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1af3-105">参数</span><span class="sxs-lookup"><span data-stu-id="a1af3-105">Parameters</span></span>  
 `generation`  
 <span data-ttu-id="a1af3-106">中刚完成的垃圾回收生成，线程将从该生成中恢复。</span><span class="sxs-lookup"><span data-stu-id="a1af3-106">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1af3-107">返回值</span><span class="sxs-lookup"><span data-stu-id="a1af3-107">Return Value</span></span>  
  
|<span data-ttu-id="a1af3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a1af3-108">HRESULT</span></span>|<span data-ttu-id="a1af3-109">描述</span><span class="sxs-lookup"><span data-stu-id="a1af3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a1af3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a1af3-110">S_OK</span></span>|<span data-ttu-id="a1af3-111">`SuspensionEnding` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="a1af3-111">`SuspensionEnding` returned successfully.</span></span>|  
|<span data-ttu-id="a1af3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a1af3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a1af3-113">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="a1af3-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a1af3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a1af3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a1af3-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="a1af3-115">The call timed out.</span></span>|  
|<span data-ttu-id="a1af3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a1af3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a1af3-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="a1af3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a1af3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a1af3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a1af3-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="a1af3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a1af3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a1af3-120">E_FAIL</span></span>|<span data-ttu-id="a1af3-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="a1af3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a1af3-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="a1af3-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a1af3-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="a1af3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1af3-124">备注</span><span class="sxs-lookup"><span data-stu-id="a1af3-124">Remarks</span></span>  
 <span data-ttu-id="a1af3-125">CLR 在执行垃圾回收后调用 `SuspensionEnding`，以通知主机线程正在继续执行。</span><span class="sxs-lookup"><span data-stu-id="a1af3-125">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a1af3-126">不要重新安排从其进行方法调用的线程。</span><span class="sxs-lookup"><span data-stu-id="a1af3-126">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1af3-127">要求</span><span class="sxs-lookup"><span data-stu-id="a1af3-127">Requirements</span></span>  
 <span data-ttu-id="a1af3-128">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a1af3-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1af3-129">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a1af3-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a1af3-130">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="a1af3-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a1af3-131">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1af3-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1af3-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1af3-132">See also</span></span>

- [<span data-ttu-id="a1af3-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="a1af3-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="a1af3-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="a1af3-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="a1af3-135">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="a1af3-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="a1af3-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="a1af3-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="a1af3-137">IHostGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="a1af3-137">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
