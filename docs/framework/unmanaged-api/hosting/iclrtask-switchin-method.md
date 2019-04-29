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
ms.openlocfilehash: 5f36a963417aba082667bb9fb609e0d1dcad7b09
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763446"
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="be0c2-102">ICLRTask::SwitchIn 方法</span><span class="sxs-lookup"><span data-stu-id="be0c2-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="be0c2-103">通知公共语言运行时 (CLR) 的任务的当前[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例表示现在处于可操作的状态。</span><span class="sxs-lookup"><span data-stu-id="be0c2-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be0c2-104">语法</span><span class="sxs-lookup"><span data-stu-id="be0c2-104">Syntax</span></span>  
  
```  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be0c2-105">参数</span><span class="sxs-lookup"><span data-stu-id="be0c2-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="be0c2-106">[in]该任务表示由当前在其的物理线程的句柄`ICLRTask`执行实例。</span><span class="sxs-lookup"><span data-stu-id="be0c2-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="be0c2-107">返回值</span><span class="sxs-lookup"><span data-stu-id="be0c2-107">Return Value</span></span>  
  
|<span data-ttu-id="be0c2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="be0c2-108">HRESULT</span></span>|<span data-ttu-id="be0c2-109">描述</span><span class="sxs-lookup"><span data-stu-id="be0c2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="be0c2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="be0c2-110">S_OK</span></span>|<span data-ttu-id="be0c2-111">`SwitchIn` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="be0c2-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="be0c2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="be0c2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="be0c2-113">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="be0c2-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="be0c2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="be0c2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="be0c2-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="be0c2-115">The call timed out.</span></span>|  
|<span data-ttu-id="be0c2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="be0c2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="be0c2-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="be0c2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="be0c2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="be0c2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="be0c2-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="be0c2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="be0c2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="be0c2-120">E_FAIL</span></span>|<span data-ttu-id="be0c2-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="be0c2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="be0c2-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="be0c2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="be0c2-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="be0c2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="be0c2-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="be0c2-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="be0c2-125">`SwitchIn` 不到的早期调用的情况下调用了[SwitchOut 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)。</span><span class="sxs-lookup"><span data-stu-id="be0c2-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be0c2-126">备注</span><span class="sxs-lookup"><span data-stu-id="be0c2-126">Remarks</span></span>  
 <span data-ttu-id="be0c2-127">`threadHandle`参数表示当前在其表示任务的操作系统线程的句柄`ICLRTask`已计划实例。</span><span class="sxs-lookup"><span data-stu-id="be0c2-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="be0c2-128">如果此线程上已发生模拟，则必须调用[ihostsecuritymanager:: Reverttoself](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)之前在任务中切换。</span><span class="sxs-lookup"><span data-stu-id="be0c2-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be0c2-129">调用`SwitchIn`而无需对的早期调用`SwitchOut`失败，出现 HOST_E_INVALIDOPERATION 的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="be0c2-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be0c2-130">要求</span><span class="sxs-lookup"><span data-stu-id="be0c2-130">Requirements</span></span>  
 <span data-ttu-id="be0c2-131">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="be0c2-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be0c2-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="be0c2-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="be0c2-133">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="be0c2-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="be0c2-134">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be0c2-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be0c2-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="be0c2-135">See also</span></span>

- [<span data-ttu-id="be0c2-136">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="be0c2-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="be0c2-137">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="be0c2-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="be0c2-138">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="be0c2-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="be0c2-139">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="be0c2-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
