---
title: ICLRTask::SwitchIn 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13e4119da7af4c54387c24ee576ff9577da56ca9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438036"
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="53862-102">ICLRTask::SwitchIn 方法</span><span class="sxs-lookup"><span data-stu-id="53862-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="53862-103">通知公共语言运行时 (CLR)，该任务的当前[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例所表示现处于可操作状态。</span><span class="sxs-lookup"><span data-stu-id="53862-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53862-104">语法</span><span class="sxs-lookup"><span data-stu-id="53862-104">Syntax</span></span>  
  
```  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="53862-105">参数</span><span class="sxs-lookup"><span data-stu-id="53862-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="53862-106">[in]在其由当前的所表示任务的物理线程的句柄`ICLRTask`实例正在执行。</span><span class="sxs-lookup"><span data-stu-id="53862-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="53862-107">返回值</span><span class="sxs-lookup"><span data-stu-id="53862-107">Return Value</span></span>  
  
|<span data-ttu-id="53862-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="53862-108">HRESULT</span></span>|<span data-ttu-id="53862-109">描述</span><span class="sxs-lookup"><span data-stu-id="53862-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="53862-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="53862-110">S_OK</span></span>|<span data-ttu-id="53862-111">`SwitchIn` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="53862-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="53862-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="53862-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="53862-113">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="53862-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="53862-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="53862-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="53862-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="53862-115">The call timed out.</span></span>|  
|<span data-ttu-id="53862-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="53862-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="53862-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="53862-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="53862-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="53862-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="53862-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="53862-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="53862-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="53862-120">E_FAIL</span></span>|<span data-ttu-id="53862-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="53862-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="53862-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="53862-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="53862-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="53862-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="53862-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="53862-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="53862-125">`SwitchIn` 已调用以前调用[SwitchOut 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)。</span><span class="sxs-lookup"><span data-stu-id="53862-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53862-126">备注</span><span class="sxs-lookup"><span data-stu-id="53862-126">Remarks</span></span>  
 <span data-ttu-id="53862-127">`threadHandle`参数表示在其由当前的所表示任务的操作系统线程的句柄`ICLRTask`计划实例。</span><span class="sxs-lookup"><span data-stu-id="53862-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="53862-128">如果该线程上已发生模拟，则必须调用[ihostsecuritymanager:: Reverttoself](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)之前在任务中切换。</span><span class="sxs-lookup"><span data-stu-id="53862-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53862-129">调用`SwitchIn`而无需以前调用`SwitchOut`失败，出现 HOST_E_INVALIDOPERATION 的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="53862-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53862-130">要求</span><span class="sxs-lookup"><span data-stu-id="53862-130">Requirements</span></span>  
 <span data-ttu-id="53862-131">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="53862-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53862-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="53862-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="53862-133">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="53862-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="53862-134">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53862-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53862-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="53862-135">See Also</span></span>  
 [<span data-ttu-id="53862-136">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="53862-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="53862-137">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="53862-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="53862-138">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="53862-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="53862-139">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="53862-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
