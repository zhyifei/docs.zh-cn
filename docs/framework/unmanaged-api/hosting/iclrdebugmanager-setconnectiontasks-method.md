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
ms.openlocfilehash: d6092f16804fae39dd9496e8572edd64e1b7e9bd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129376"
---
# <a name="iclrdebugmanagersetconnectiontasks-method"></a><span data-ttu-id="c3e5a-102">ICLRDebugManager::SetConnectionTasks 方法</span><span class="sxs-lookup"><span data-stu-id="c3e5a-102">ICLRDebugManager::SetConnectionTasks Method</span></span>
<span data-ttu-id="c3e5a-103">将[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例列表与标识符和友好名称关联。</span><span class="sxs-lookup"><span data-stu-id="c3e5a-103">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3e5a-104">语法</span><span class="sxs-lookup"><span data-stu-id="c3e5a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetConnectionTasks (  
    [in] CONNID id,  
    [in] DWORD dwCount,  
    [in, size_is(dwCount)] ICLRTask **ppCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3e5a-105">参数</span><span class="sxs-lookup"><span data-stu-id="c3e5a-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="c3e5a-106">中与 `ppCLRTask` 数组关联的连接的主机特定标识符。</span><span class="sxs-lookup"><span data-stu-id="c3e5a-106">[in] The host-specific identifier for the connection with which to associate the `ppCLRTask` array.</span></span>  
  
 `dwCount`  
 <span data-ttu-id="c3e5a-107">中`ppCLRTask`的成员数。</span><span class="sxs-lookup"><span data-stu-id="c3e5a-107">[in] The number of members of `ppCLRTask`.</span></span> <span data-ttu-id="c3e5a-108">此数字必须大于零。</span><span class="sxs-lookup"><span data-stu-id="c3e5a-108">This number must be greater than zero.</span></span>  
  
 `ppCLRTask`  
 <span data-ttu-id="c3e5a-109">中一个 `ICLRTask` 指针数组，这些指针与 `id`所标识的连接关联。</span><span class="sxs-lookup"><span data-stu-id="c3e5a-109">[in] An array of `ICLRTask` pointers to associate with the connection identified by `id`.</span></span> <span data-ttu-id="c3e5a-110">此数组必须至少包含一个成员。</span><span class="sxs-lookup"><span data-stu-id="c3e5a-110">This array must contain at least one member.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3e5a-111">返回值</span><span class="sxs-lookup"><span data-stu-id="c3e5a-111">Return Value</span></span>  
  
|<span data-ttu-id="c3e5a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c3e5a-112">HRESULT</span></span>|<span data-ttu-id="c3e5a-113">描述</span><span class="sxs-lookup"><span data-stu-id="c3e5a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c3e5a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="c3e5a-114">S_OK</span></span>|<span data-ttu-id="c3e5a-115">`SetConnectionTasks` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="c3e5a-115">`SetConnectionTasks` returned successfully.</span></span>|  
|<span data-ttu-id="c3e5a-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c3e5a-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c3e5a-117">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="c3e5a-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c3e5a-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c3e5a-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c3e5a-119">调用超时。</span><span class="sxs-lookup"><span data-stu-id="c3e5a-119">The call timed out.</span></span>|  
|<span data-ttu-id="c3e5a-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c3e5a-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c3e5a-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="c3e5a-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c3e5a-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c3e5a-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c3e5a-123">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="c3e5a-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c3e5a-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c3e5a-124">E_FAIL</span></span>|<span data-ttu-id="c3e5a-125">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="c3e5a-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c3e5a-126">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="c3e5a-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c3e5a-127">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c3e5a-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c3e5a-128">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c3e5a-128">E_INVALIDARG</span></span>|<span data-ttu-id="c3e5a-129">尚未使用 `id`的此值调用[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) ，或者 `dwCount` 或 `id` 为零，或 `ppCLRTask` 的元素之一为 null。</span><span class="sxs-lookup"><span data-stu-id="c3e5a-129">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) has not been called using this value of `id`, or `dwCount` or `id` is zero, or one of the elements of `ppCLRTask` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3e5a-130">备注</span><span class="sxs-lookup"><span data-stu-id="c3e5a-130">Remarks</span></span>  
 <span data-ttu-id="c3e5a-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)提供了三种方法： `BeginConnection`、`SetConnectionTasks`和[EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)，将任务列表与标识符和友好名称关联起来。</span><span class="sxs-lookup"><span data-stu-id="c3e5a-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, `SetConnectionTasks`, and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c3e5a-132">对于每组任务，这三种方法都必须按特定的顺序进行调用。</span><span class="sxs-lookup"><span data-stu-id="c3e5a-132">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="c3e5a-133">首先调用 `BeginConnection`，建立新连接。</span><span class="sxs-lookup"><span data-stu-id="c3e5a-133">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="c3e5a-134">接下来调用 `SetConnectionTasks`，提供要与该连接相关联的一组任务。</span><span class="sxs-lookup"><span data-stu-id="c3e5a-134">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="c3e5a-135">最后调用 `EndConnection`，以删除任务列表与标识符和友好名称之间的关联。但是，可以嵌套不同连接的调用。</span><span class="sxs-lookup"><span data-stu-id="c3e5a-135">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3e5a-136">要求</span><span class="sxs-lookup"><span data-stu-id="c3e5a-136">Requirements</span></span>  
 <span data-ttu-id="c3e5a-137">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c3e5a-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3e5a-138">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c3e5a-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c3e5a-139">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c3e5a-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3e5a-140">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3e5a-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3e5a-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="c3e5a-141">See also</span></span>

- [<span data-ttu-id="c3e5a-142">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="c3e5a-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="c3e5a-143">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="c3e5a-143">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="c3e5a-144">BeginConnection 方法</span><span class="sxs-lookup"><span data-stu-id="c3e5a-144">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="c3e5a-145">EndConnection 方法</span><span class="sxs-lookup"><span data-stu-id="c3e5a-145">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="c3e5a-146">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="c3e5a-146">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
