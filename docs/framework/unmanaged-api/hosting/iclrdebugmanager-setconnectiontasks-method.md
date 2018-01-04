---
title: "ICLRDebugManager::SetConnectionTasks 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager.SetConnectionTasks
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager::SetConnectionTasks
helpviewer_keywords:
- SetConnectionTasks method [.NET Framework hosting]
- ICLRDebugManager::SetConnectionTasks method [.NET Framework hosting]
ms.assetid: b38bbc9a-872c-41a9-b8c3-ca011d25456a
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 09f7e47acfcfbde8d5d9724c3a37303f1a584adb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebugmanagersetconnectiontasks-method"></a><span data-ttu-id="e6748-102">ICLRDebugManager::SetConnectionTasks 方法</span><span class="sxs-lookup"><span data-stu-id="e6748-102">ICLRDebugManager::SetConnectionTasks Method</span></span>
<span data-ttu-id="e6748-103">将相关联的列表[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)标识符并具有友好名称的实例。</span><span class="sxs-lookup"><span data-stu-id="e6748-103">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6748-104">语法</span><span class="sxs-lookup"><span data-stu-id="e6748-104">Syntax</span></span>  
  
```  
HRESULT SetConnectionTasks (  
    [in] CONNID id,  
    [in] DWORD dwCount,  
    [in, size_is(dwCount)] ICLRTask **ppCLRTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e6748-105">参数</span><span class="sxs-lookup"><span data-stu-id="e6748-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="e6748-106">[in]要与关联的连接的特定于宿主的标识符`ppCLRTask`数组。</span><span class="sxs-lookup"><span data-stu-id="e6748-106">[in] The host-specific identifier for the connection with which to associate the `ppCLRTask` array.</span></span>  
  
 `dwCount`  
 <span data-ttu-id="e6748-107">[in]成员数`ppCLRTask`。</span><span class="sxs-lookup"><span data-stu-id="e6748-107">[in] The number of members of `ppCLRTask`.</span></span> <span data-ttu-id="e6748-108">此数字必须大于零。</span><span class="sxs-lookup"><span data-stu-id="e6748-108">This number must be greater than zero.</span></span>  
  
 `ppCLRTask`  
 <span data-ttu-id="e6748-109">[in]数组`ICLRTask`指针，以便将与由标识连接关联`id`。</span><span class="sxs-lookup"><span data-stu-id="e6748-109">[in] An array of `ICLRTask` pointers to associate with the connection identified by `id`.</span></span> <span data-ttu-id="e6748-110">此数组必须包含至少一个成员。</span><span class="sxs-lookup"><span data-stu-id="e6748-110">This array must contain at least one member.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6748-111">返回值</span><span class="sxs-lookup"><span data-stu-id="e6748-111">Return Value</span></span>  
  
|<span data-ttu-id="e6748-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e6748-112">HRESULT</span></span>|<span data-ttu-id="e6748-113">描述</span><span class="sxs-lookup"><span data-stu-id="e6748-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e6748-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="e6748-114">S_OK</span></span>|<span data-ttu-id="e6748-115">`SetConnectionTasks`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="e6748-115">`SetConnectionTasks` returned successfully.</span></span>|  
|<span data-ttu-id="e6748-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e6748-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e6748-117">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="e6748-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e6748-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e6748-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e6748-119">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="e6748-119">The call timed out.</span></span>|  
|<span data-ttu-id="e6748-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e6748-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e6748-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="e6748-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e6748-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e6748-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e6748-123">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="e6748-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e6748-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e6748-124">E_FAIL</span></span>|<span data-ttu-id="e6748-125">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="e6748-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e6748-126">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="e6748-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e6748-127">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="e6748-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e6748-128">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="e6748-128">E_INVALIDARG</span></span>|<span data-ttu-id="e6748-129">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)不使用此值已调用`id`，或`dwCount`或`id`为零，则的元素中的一个`ppCLRTask`为 null。</span><span class="sxs-lookup"><span data-stu-id="e6748-129">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) has not been called using this value of `id`, or `dwCount` or `id` is zero, or one of the elements of `ppCLRTask` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6748-130">备注</span><span class="sxs-lookup"><span data-stu-id="e6748-130">Remarks</span></span>  
 <span data-ttu-id="e6748-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)提供三种方法， `BeginConnection`， `SetConnectionTasks`，和[EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)，将任务列表标识符和友好名称与相关联。</span><span class="sxs-lookup"><span data-stu-id="e6748-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, `SetConnectionTasks`, and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e6748-132">必须按特定顺序为每一组任务调用这三种方法。</span><span class="sxs-lookup"><span data-stu-id="e6748-132">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="e6748-133">`BeginConnection`都会首先调用来建立新连接。</span><span class="sxs-lookup"><span data-stu-id="e6748-133">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="e6748-134">`SetConnectionTasks`调用下一步可提供的任务与该连接关联集。</span><span class="sxs-lookup"><span data-stu-id="e6748-134">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="e6748-135">`EndConnection`调用上一次可删除任务列表的标识符和友好名称之间的关联。但是，可以嵌套不同连接的调用。</span><span class="sxs-lookup"><span data-stu-id="e6748-135">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6748-136">惠?</span><span class="sxs-lookup"><span data-stu-id="e6748-136">Requirements</span></span>  
 <span data-ttu-id="e6748-137">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e6748-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6748-138">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e6748-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6748-139">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e6748-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6748-140">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6748-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6748-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6748-141">See Also</span></span>  
 [<span data-ttu-id="e6748-142">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="e6748-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="e6748-143">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="e6748-143">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="e6748-144">BeginConnection 方法</span><span class="sxs-lookup"><span data-stu-id="e6748-144">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)  
 [<span data-ttu-id="e6748-145">EndConnection 方法</span><span class="sxs-lookup"><span data-stu-id="e6748-145">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)  
 [<span data-ttu-id="e6748-146">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="e6748-146">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
