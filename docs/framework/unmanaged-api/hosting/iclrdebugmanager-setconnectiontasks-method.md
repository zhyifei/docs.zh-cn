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
ms.openlocfilehash: 85db4247ebe4a488f7907e195bb0f25f72d87e9b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951354"
---
# <a name="iclrdebugmanagersetconnectiontasks-method"></a><span data-ttu-id="fadc5-102">ICLRDebugManager::SetConnectionTasks 方法</span><span class="sxs-lookup"><span data-stu-id="fadc5-102">ICLRDebugManager::SetConnectionTasks Method</span></span>
<span data-ttu-id="fadc5-103">将[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例列表与标识符和友好名称关联。</span><span class="sxs-lookup"><span data-stu-id="fadc5-103">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fadc5-104">语法</span><span class="sxs-lookup"><span data-stu-id="fadc5-104">Syntax</span></span>  
  
```cpp  
HRESULT SetConnectionTasks (  
    [in] CONNID id,  
    [in] DWORD dwCount,  
    [in, size_is(dwCount)] ICLRTask **ppCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fadc5-105">参数</span><span class="sxs-lookup"><span data-stu-id="fadc5-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="fadc5-106">中要与`ppCLRTask`数组关联的连接的主机特定标识符。</span><span class="sxs-lookup"><span data-stu-id="fadc5-106">[in] The host-specific identifier for the connection with which to associate the `ppCLRTask` array.</span></span>  
  
 `dwCount`  
 <span data-ttu-id="fadc5-107">中的成员`ppCLRTask`数。</span><span class="sxs-lookup"><span data-stu-id="fadc5-107">[in] The number of members of `ppCLRTask`.</span></span> <span data-ttu-id="fadc5-108">此数字必须大于零。</span><span class="sxs-lookup"><span data-stu-id="fadc5-108">This number must be greater than zero.</span></span>  
  
 `ppCLRTask`  
 <span data-ttu-id="fadc5-109">中`ICLRTask` 与`id`标识的连接关联的指针数组。</span><span class="sxs-lookup"><span data-stu-id="fadc5-109">[in] An array of `ICLRTask` pointers to associate with the connection identified by `id`.</span></span> <span data-ttu-id="fadc5-110">此数组必须至少包含一个成员。</span><span class="sxs-lookup"><span data-stu-id="fadc5-110">This array must contain at least one member.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fadc5-111">返回值</span><span class="sxs-lookup"><span data-stu-id="fadc5-111">Return Value</span></span>  
  
|<span data-ttu-id="fadc5-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fadc5-112">HRESULT</span></span>|<span data-ttu-id="fadc5-113">描述</span><span class="sxs-lookup"><span data-stu-id="fadc5-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fadc5-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="fadc5-114">S_OK</span></span>|<span data-ttu-id="fadc5-115">`SetConnectionTasks`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="fadc5-115">`SetConnectionTasks` returned successfully.</span></span>|  
|<span data-ttu-id="fadc5-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fadc5-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fadc5-117">公共语言运行时 (CLR) 未加载到进程中, 或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="fadc5-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fadc5-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fadc5-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fadc5-119">调用超时。</span><span class="sxs-lookup"><span data-stu-id="fadc5-119">The call timed out.</span></span>|  
|<span data-ttu-id="fadc5-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fadc5-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fadc5-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="fadc5-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fadc5-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fadc5-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fadc5-123">已阻止的线程或纤程正在等待某个事件时, 该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="fadc5-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fadc5-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fadc5-124">E_FAIL</span></span>|<span data-ttu-id="fadc5-125">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="fadc5-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fadc5-126">方法返回 E_FAIL 后, CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="fadc5-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fadc5-127">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="fadc5-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fadc5-128">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="fadc5-128">E_INVALIDARG</span></span>|<span data-ttu-id="fadc5-129">尚未使用的`id` `id` `ppCLRTask`此值调用[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) , 或者或为零,或的一个元素为空。`dwCount`</span><span class="sxs-lookup"><span data-stu-id="fadc5-129">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) has not been called using this value of `id`, or `dwCount` or `id` is zero, or one of the elements of `ppCLRTask` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fadc5-130">备注</span><span class="sxs-lookup"><span data-stu-id="fadc5-130">Remarks</span></span>  
 <span data-ttu-id="fadc5-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)提供了三种`BeginConnection`方法`SetConnectionTasks`:、和[EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), 用于将任务列表与标识符和友好名称关联起来。</span><span class="sxs-lookup"><span data-stu-id="fadc5-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, `SetConnectionTasks`, and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="fadc5-132">对于每组任务, 这三种方法都必须按特定的顺序进行调用。</span><span class="sxs-lookup"><span data-stu-id="fadc5-132">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="fadc5-133">`BeginConnection`首先调用以建立新连接。</span><span class="sxs-lookup"><span data-stu-id="fadc5-133">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="fadc5-134">`SetConnectionTasks`在旁边调用, 提供要与该连接相关联的一组任务。</span><span class="sxs-lookup"><span data-stu-id="fadc5-134">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="fadc5-135">`EndConnection`最后调用, 以删除任务列表与标识符和友好名称之间的关联。但是, 可以嵌套不同连接的调用。</span><span class="sxs-lookup"><span data-stu-id="fadc5-135">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fadc5-136">要求</span><span class="sxs-lookup"><span data-stu-id="fadc5-136">Requirements</span></span>  
 <span data-ttu-id="fadc5-137">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fadc5-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fadc5-138">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fadc5-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fadc5-139">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="fadc5-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fadc5-140">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fadc5-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fadc5-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="fadc5-141">See also</span></span>

- [<span data-ttu-id="fadc5-142">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="fadc5-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="fadc5-143">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="fadc5-143">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="fadc5-144">BeginConnection 方法</span><span class="sxs-lookup"><span data-stu-id="fadc5-144">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="fadc5-145">EndConnection 方法</span><span class="sxs-lookup"><span data-stu-id="fadc5-145">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="fadc5-146">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="fadc5-146">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
