---
title: "ICLRTask::SwitchIn 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRTask.SwitchIn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchIn
helpviewer_keywords:
- ICLRTask::SwitchIn method [.NET Framework hosting]
- SwitchIn method [.NET Framework hosting]
ms.assetid: 3d37ce20-aa65-4043-8f13-7c728b5d8a52
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e99fc43dea70d456bbaab9bba63e5a018e9e9201
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="7a516-102">ICLRTask::SwitchIn 方法</span><span class="sxs-lookup"><span data-stu-id="7a516-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="7a516-103">通知公共语言运行时 (CLR)，该任务的当前[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例所表示现处于可操作状态。</span><span class="sxs-lookup"><span data-stu-id="7a516-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a516-104">语法</span><span class="sxs-lookup"><span data-stu-id="7a516-104">Syntax</span></span>  
  
```  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7a516-105">参数</span><span class="sxs-lookup"><span data-stu-id="7a516-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="7a516-106">[in]在其由当前的所表示任务的物理线程的句柄`ICLRTask`实例正在执行。</span><span class="sxs-lookup"><span data-stu-id="7a516-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a516-107">返回值</span><span class="sxs-lookup"><span data-stu-id="7a516-107">Return Value</span></span>  
  
|<span data-ttu-id="7a516-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7a516-108">HRESULT</span></span>|<span data-ttu-id="7a516-109">描述</span><span class="sxs-lookup"><span data-stu-id="7a516-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7a516-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7a516-110">S_OK</span></span>|<span data-ttu-id="7a516-111">`SwitchIn`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="7a516-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="7a516-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7a516-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7a516-113">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="7a516-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7a516-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7a516-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7a516-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="7a516-115">The call timed out.</span></span>|  
|<span data-ttu-id="7a516-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7a516-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7a516-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="7a516-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7a516-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7a516-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7a516-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="7a516-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7a516-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7a516-120">E_FAIL</span></span>|<span data-ttu-id="7a516-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="7a516-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7a516-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="7a516-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7a516-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="7a516-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7a516-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="7a516-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="7a516-125">`SwitchIn`已调用以前调用[SwitchOut 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)。</span><span class="sxs-lookup"><span data-stu-id="7a516-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a516-126">备注</span><span class="sxs-lookup"><span data-stu-id="7a516-126">Remarks</span></span>  
 <span data-ttu-id="7a516-127">`threadHandle`参数表示在其由当前的所表示任务的操作系统线程的句柄`ICLRTask`计划实例。</span><span class="sxs-lookup"><span data-stu-id="7a516-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="7a516-128">如果该线程上已发生模拟，则必须调用[ihostsecuritymanager:: Reverttoself](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)之前在任务中切换。</span><span class="sxs-lookup"><span data-stu-id="7a516-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a516-129">调用`SwitchIn`而无需以前调用`SwitchOut`失败，出现 HOST_E_INVALIDOPERATION 的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="7a516-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a516-130">惠?</span><span class="sxs-lookup"><span data-stu-id="7a516-130">Requirements</span></span>  
 <span data-ttu-id="7a516-131">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7a516-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a516-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7a516-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7a516-133">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7a516-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7a516-134">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a516-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a516-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="7a516-135">See Also</span></span>  
 [<span data-ttu-id="7a516-136">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="7a516-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="7a516-137">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="7a516-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="7a516-138">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="7a516-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="7a516-139">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="7a516-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
