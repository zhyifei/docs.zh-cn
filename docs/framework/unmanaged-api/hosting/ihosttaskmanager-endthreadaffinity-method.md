---
title: IHostTaskManager::EndThreadAffinity 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndThreadAffinity
helpviewer_keywords:
- EndThreadAffinity method [.NET Framework hosting]
- IHostTaskManager::EndThreadAffinity method [.NET Framework hosting]
ms.assetid: 7738a904-0cd7-4fde-a3eb-2323a5533157
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb07e38542893b26595b67d6cf0fa77c522b4def
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="ihosttaskmanagerendthreadaffinity-method"></a><span data-ttu-id="7019f-102">IHostTaskManager::EndThreadAffinity 方法</span><span class="sxs-lookup"><span data-stu-id="7019f-102">IHostTaskManager::EndThreadAffinity Method</span></span>
<span data-ttu-id="7019f-103">通知宿主托管代码正在退出不能在其中当前任务移动到另一个操作系统线程，周期以下以前调用[ihosttaskmanager:: Beginthreadaffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)。</span><span class="sxs-lookup"><span data-stu-id="7019f-103">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to [IHostTaskManager::BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7019f-104">语法</span><span class="sxs-lookup"><span data-stu-id="7019f-104">Syntax</span></span>  
  
```  
HRESULT EndThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7019f-105">返回值</span><span class="sxs-lookup"><span data-stu-id="7019f-105">Return Value</span></span>  
  
|<span data-ttu-id="7019f-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7019f-106">HRESULT</span></span>|<span data-ttu-id="7019f-107">描述</span><span class="sxs-lookup"><span data-stu-id="7019f-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7019f-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="7019f-108">S_OK</span></span>|<span data-ttu-id="7019f-109">`EndThreadAffinity` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="7019f-109">`EndThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="7019f-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7019f-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7019f-111">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="7019f-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7019f-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7019f-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7019f-113">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="7019f-113">The call timed out.</span></span>|  
|<span data-ttu-id="7019f-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7019f-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7019f-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="7019f-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7019f-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7019f-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7019f-117">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="7019f-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7019f-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7019f-118">E_FAIL</span></span>|<span data-ttu-id="7019f-119">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="7019f-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7019f-120">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="7019f-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7019f-121">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="7019f-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7019f-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="7019f-122">E_UNEXPECTED</span></span>|<span data-ttu-id="7019f-123">`EndThreadAffinity` 已调用前面相应地调用`BeginThreadAffinity`。</span><span class="sxs-lookup"><span data-stu-id="7019f-123">`EndThreadAffinity` was called without an earlier corresponding call to `BeginThreadAffinity`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7019f-124">备注</span><span class="sxs-lookup"><span data-stu-id="7019f-124">Remarks</span></span>  
 <span data-ttu-id="7019f-125">CLR 将对应调用`BeginThreadAffinity`在当前任务之前调用`EndThreadAffinity`。</span><span class="sxs-lookup"><span data-stu-id="7019f-125">The CLR makes a corresponding call to `BeginThreadAffinity` on the current task before calling `EndThreadAffinity`.</span></span> <span data-ttu-id="7019f-126">此类相应地调用，没有主机的实现[IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)应返回 E_UNEXPECTED，并且不采取任何操作。</span><span class="sxs-lookup"><span data-stu-id="7019f-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED, and take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7019f-127">要求</span><span class="sxs-lookup"><span data-stu-id="7019f-127">Requirements</span></span>  
 <span data-ttu-id="7019f-128">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7019f-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7019f-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7019f-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7019f-130">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7019f-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7019f-131">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7019f-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7019f-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="7019f-132">See Also</span></span>  
 <xref:System.Threading>  
 [<span data-ttu-id="7019f-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="7019f-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="7019f-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="7019f-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="7019f-135">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="7019f-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="7019f-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="7019f-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
