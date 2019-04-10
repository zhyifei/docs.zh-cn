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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 527607d5c39e7f698ab44baf4af0e7600ae2f473
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222817"
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="d0861-102">IHostGCManager::SuspensionEnding 方法</span><span class="sxs-lookup"><span data-stu-id="d0861-102">IHostGCManager::SuspensionEnding Method</span></span>
<span data-ttu-id="d0861-103">通知宿主公共语言运行时 (CLR) 继续执行过程中被挂起垃圾回收的线程上的任务。</span><span class="sxs-lookup"><span data-stu-id="d0861-103">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0861-104">语法</span><span class="sxs-lookup"><span data-stu-id="d0861-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0861-105">参数</span><span class="sxs-lookup"><span data-stu-id="d0861-105">Parameters</span></span>  
 `generation`  
 <span data-ttu-id="d0861-106">[in]正在只需完成的垃圾回收生成从中正在恢复该线程。</span><span class="sxs-lookup"><span data-stu-id="d0861-106">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0861-107">返回值</span><span class="sxs-lookup"><span data-stu-id="d0861-107">Return Value</span></span>  
  
|<span data-ttu-id="d0861-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d0861-108">HRESULT</span></span>|<span data-ttu-id="d0861-109">描述</span><span class="sxs-lookup"><span data-stu-id="d0861-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d0861-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d0861-110">S_OK</span></span>|`SuspensionEnding` <span data-ttu-id="d0861-111">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="d0861-111">returned successfully.</span></span>|  
|<span data-ttu-id="d0861-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d0861-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d0861-113">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="d0861-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d0861-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d0861-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d0861-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="d0861-115">The call timed out.</span></span>|  
|<span data-ttu-id="d0861-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d0861-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d0861-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="d0861-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d0861-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d0861-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d0861-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="d0861-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d0861-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d0861-120">E_FAIL</span></span>|<span data-ttu-id="d0861-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="d0861-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d0861-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="d0861-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d0861-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="d0861-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0861-124">备注</span><span class="sxs-lookup"><span data-stu-id="d0861-124">Remarks</span></span>  
 <span data-ttu-id="d0861-125">CLR 调用`SuspensionEnding`它执行垃圾回收，来通知宿主线程正在继续执行后。</span><span class="sxs-lookup"><span data-stu-id="d0861-125">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d0861-126">不要重新安排从进行方法调用的线程。</span><span class="sxs-lookup"><span data-stu-id="d0861-126">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0861-127">要求</span><span class="sxs-lookup"><span data-stu-id="d0861-127">Requirements</span></span>  
 <span data-ttu-id="d0861-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d0861-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0861-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d0861-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d0861-130">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d0861-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d0861-131">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="d0861-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d0861-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0861-132">See also</span></span>

- [<span data-ttu-id="d0861-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="d0861-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="d0861-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="d0861-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="d0861-135">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="d0861-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="d0861-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="d0861-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="d0861-137">IHostGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="d0861-137">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
