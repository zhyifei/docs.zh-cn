---
title: ICLRDebugManager::SetConnectionTasks 方法
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.SetConnectionTasks
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetConnectionTasks
helpviewer_keywords:
- SetConnectionTasks method [.NET Framework hosting]
- ICLRDebugManager::SetConnectionTasks method [.NET Framework hosting]
ms.assetid: b38bbc9a-872c-41a9-b8c3-ca011d25456a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cb4210972ba15a7ba3c7df5981e668cb5542f5c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471402"
---
# <a name="iclrdebugmanagersetconnectiontasks-method"></a><span data-ttu-id="bfad0-102">ICLRDebugManager::SetConnectionTasks 方法</span><span class="sxs-lookup"><span data-stu-id="bfad0-102">ICLRDebugManager::SetConnectionTasks Method</span></span>
<span data-ttu-id="bfad0-103">将一组相关联[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例标识符和友好名称。</span><span class="sxs-lookup"><span data-stu-id="bfad0-103">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfad0-104">语法</span><span class="sxs-lookup"><span data-stu-id="bfad0-104">Syntax</span></span>  
  
```  
HRESULT SetConnectionTasks (  
    [in] CONNID id,  
    [in] DWORD dwCount,  
    [in, size_is(dwCount)] ICLRTask **ppCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfad0-105">参数</span><span class="sxs-lookup"><span data-stu-id="bfad0-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="bfad0-106">[in]要与关联的连接的特定于宿主的标识符`ppCLRTask`数组。</span><span class="sxs-lookup"><span data-stu-id="bfad0-106">[in] The host-specific identifier for the connection with which to associate the `ppCLRTask` array.</span></span>  
  
 `dwCount`  
 <span data-ttu-id="bfad0-107">[in]成员数`ppCLRTask`。</span><span class="sxs-lookup"><span data-stu-id="bfad0-107">[in] The number of members of `ppCLRTask`.</span></span> <span data-ttu-id="bfad0-108">此数字必须大于零。</span><span class="sxs-lookup"><span data-stu-id="bfad0-108">This number must be greater than zero.</span></span>  
  
 `ppCLRTask`  
 <span data-ttu-id="bfad0-109">[in]一个数组`ICLRTask`指针，以便与连接由标识关联`id`。</span><span class="sxs-lookup"><span data-stu-id="bfad0-109">[in] An array of `ICLRTask` pointers to associate with the connection identified by `id`.</span></span> <span data-ttu-id="bfad0-110">此数组必须包含至少一个成员。</span><span class="sxs-lookup"><span data-stu-id="bfad0-110">This array must contain at least one member.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bfad0-111">返回值</span><span class="sxs-lookup"><span data-stu-id="bfad0-111">Return Value</span></span>  
  
|<span data-ttu-id="bfad0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bfad0-112">HRESULT</span></span>|<span data-ttu-id="bfad0-113">描述</span><span class="sxs-lookup"><span data-stu-id="bfad0-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bfad0-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="bfad0-114">S_OK</span></span>|<span data-ttu-id="bfad0-115">`SetConnectionTasks` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="bfad0-115">`SetConnectionTasks` returned successfully.</span></span>|  
|<span data-ttu-id="bfad0-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bfad0-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bfad0-117">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="bfad0-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bfad0-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bfad0-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bfad0-119">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="bfad0-119">The call timed out.</span></span>|  
|<span data-ttu-id="bfad0-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bfad0-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bfad0-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="bfad0-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bfad0-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bfad0-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bfad0-123">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="bfad0-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bfad0-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bfad0-124">E_FAIL</span></span>|<span data-ttu-id="bfad0-125">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="bfad0-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bfad0-126">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="bfad0-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bfad0-127">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="bfad0-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="bfad0-128">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="bfad0-128">E_INVALIDARG</span></span>|<span data-ttu-id="bfad0-129">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)尚未使用此值调用`id`，或`dwCount`或`id`是零个或一个元素的`ppCLRTask`为 null。</span><span class="sxs-lookup"><span data-stu-id="bfad0-129">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) has not been called using this value of `id`, or `dwCount` or `id` is zero, or one of the elements of `ppCLRTask` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfad0-130">备注</span><span class="sxs-lookup"><span data-stu-id="bfad0-130">Remarks</span></span>  
 <span data-ttu-id="bfad0-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)提供三种方法， `BeginConnection`， `SetConnectionTasks`，和[EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)，用于将任务列表相关联的标识符和友好名称。</span><span class="sxs-lookup"><span data-stu-id="bfad0-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, `SetConnectionTasks`, and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bfad0-132">必须为每个组的任务特定的顺序调用这三种方法。</span><span class="sxs-lookup"><span data-stu-id="bfad0-132">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="bfad0-133">`BeginConnection` 首先调用来建立新连接。</span><span class="sxs-lookup"><span data-stu-id="bfad0-133">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="bfad0-134">`SetConnectionTasks` 将调用下一步来提供要与该连接相关联的任务组。</span><span class="sxs-lookup"><span data-stu-id="bfad0-134">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="bfad0-135">`EndConnection` 最后调用以删除任务列表的标识符和友好名称之间的关联。但是，可以嵌套调用不同的连接。</span><span class="sxs-lookup"><span data-stu-id="bfad0-135">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfad0-136">要求</span><span class="sxs-lookup"><span data-stu-id="bfad0-136">Requirements</span></span>  
 <span data-ttu-id="bfad0-137">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bfad0-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfad0-138">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bfad0-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bfad0-139">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="bfad0-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bfad0-140">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfad0-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfad0-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="bfad0-141">See also</span></span>
- [<span data-ttu-id="bfad0-142">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="bfad0-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="bfad0-143">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="bfad0-143">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="bfad0-144">BeginConnection 方法</span><span class="sxs-lookup"><span data-stu-id="bfad0-144">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="bfad0-145">EndConnection 方法</span><span class="sxs-lookup"><span data-stu-id="bfad0-145">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="bfad0-146">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="bfad0-146">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
