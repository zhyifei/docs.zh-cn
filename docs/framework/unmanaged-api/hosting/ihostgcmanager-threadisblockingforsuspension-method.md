---
title: IHostGCManager::ThreadIsBlockingForSuspension 方法
ms.date: 03/30/2017
api_name:
- IHostGCManager.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension
helpviewer_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: 2657d45d-26d2-4d0a-8473-32b652e3321d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d338b03247f1304f065afc459eb70aac725937c8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709801"
---
# <a name="ihostgcmanagerthreadisblockingforsuspension-method"></a><span data-ttu-id="9e6e2-102">IHostGCManager::ThreadIsBlockingForSuspension 方法</span><span class="sxs-lookup"><span data-stu-id="9e6e2-102">IHostGCManager::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="9e6e2-103">通知主机发出方法调用的线程即将进行垃圾回收阻止。</span><span class="sxs-lookup"><span data-stu-id="9e6e2-103">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e6e2-104">语法</span><span class="sxs-lookup"><span data-stu-id="9e6e2-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForSuspension ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9e6e2-105">返回值</span><span class="sxs-lookup"><span data-stu-id="9e6e2-105">Return Value</span></span>  
  
|<span data-ttu-id="9e6e2-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9e6e2-106">HRESULT</span></span>|<span data-ttu-id="9e6e2-107">描述</span><span class="sxs-lookup"><span data-stu-id="9e6e2-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9e6e2-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9e6e2-108">S_OK</span></span>|<span data-ttu-id="9e6e2-109">`ThreadIsBlockingForSuspension` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="9e6e2-109">`ThreadIsBlockingForSuspension` returned successfully.</span></span>|  
|<span data-ttu-id="9e6e2-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9e6e2-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9e6e2-111">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="9e6e2-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9e6e2-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9e6e2-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9e6e2-113">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="9e6e2-113">The call timed out.</span></span>|  
|<span data-ttu-id="9e6e2-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9e6e2-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9e6e2-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="9e6e2-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9e6e2-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9e6e2-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9e6e2-117">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="9e6e2-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9e6e2-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9e6e2-118">E_FAIL</span></span>|<span data-ttu-id="9e6e2-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="9e6e2-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9e6e2-120">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="9e6e2-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9e6e2-121">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="9e6e2-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e6e2-122">备注</span><span class="sxs-lookup"><span data-stu-id="9e6e2-122">Remarks</span></span>  
 <span data-ttu-id="9e6e2-123">CLR 通常会调用`ThreadIsBlockForSuspension`准备垃圾回收，以便主机有机会重新计划的非托管任务的线程中的方法。</span><span class="sxs-lookup"><span data-stu-id="9e6e2-123">The CLR typically calls the `ThreadIsBlockForSuspension` method in preparation for a garbage collection, to give the host an opportunity to reschedule the thread for unmanaged tasks.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9e6e2-124">仅在调用后，主机可以重新计划任务`ThreadIsBlockingForSuspension`。</span><span class="sxs-lookup"><span data-stu-id="9e6e2-124">The host can reschedule tasks only after a call to `ThreadIsBlockingForSuspension`.</span></span> <span data-ttu-id="9e6e2-125">运行时调用后[SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)，主机必须重新安排任务。</span><span class="sxs-lookup"><span data-stu-id="9e6e2-125">After the runtime calls [SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md), the host must not reschedule a task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e6e2-126">要求</span><span class="sxs-lookup"><span data-stu-id="9e6e2-126">Requirements</span></span>  
 <span data-ttu-id="9e6e2-127">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9e6e2-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e6e2-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9e6e2-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9e6e2-129">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9e6e2-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9e6e2-130">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e6e2-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e6e2-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e6e2-131">See also</span></span>
- [<span data-ttu-id="9e6e2-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="9e6e2-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="9e6e2-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="9e6e2-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="9e6e2-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="9e6e2-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="9e6e2-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="9e6e2-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="9e6e2-136">IHostGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="9e6e2-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
