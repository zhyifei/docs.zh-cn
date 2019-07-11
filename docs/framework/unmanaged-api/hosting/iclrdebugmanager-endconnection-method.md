---
title: ICLRDebugManager::EndConnection 方法
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.EndConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::EndConnection
helpviewer_keywords:
- ICLRDebugManager::EndConnection method [.NET Framework hosting]
- EndConnection method [.NET Framework hosting]
ms.assetid: 89dc7363-2f29-4eb2-8f23-fccdda6a76a6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc9d32f83b4b6384e28f012b9329ea18913a1218
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773159"
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="d40fc-102">ICLRDebugManager::EndConnection 方法</span><span class="sxs-lookup"><span data-stu-id="d40fc-102">ICLRDebugManager::EndConnection Method</span></span>
<span data-ttu-id="d40fc-103">删除任务列表和标识符和友好名称之间的关联。</span><span class="sxs-lookup"><span data-stu-id="d40fc-103">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d40fc-104">语法</span><span class="sxs-lookup"><span data-stu-id="d40fc-104">Syntax</span></span>  
  
```cpp  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d40fc-105">参数</span><span class="sxs-lookup"><span data-stu-id="d40fc-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="d40fc-106">[in]连接和关联的公共语言运行时 (CLR) 任务列表的特定于宿主的标识符。</span><span class="sxs-lookup"><span data-stu-id="d40fc-106">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d40fc-107">返回值</span><span class="sxs-lookup"><span data-stu-id="d40fc-107">Return Value</span></span>  
  
|<span data-ttu-id="d40fc-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d40fc-108">HRESULT</span></span>|<span data-ttu-id="d40fc-109">描述</span><span class="sxs-lookup"><span data-stu-id="d40fc-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d40fc-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d40fc-110">S_OK</span></span>|<span data-ttu-id="d40fc-111">`EndConnection` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="d40fc-111">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="d40fc-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d40fc-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d40fc-113">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="d40fc-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d40fc-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d40fc-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d40fc-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="d40fc-115">The call timed out.</span></span>|  
|<span data-ttu-id="d40fc-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d40fc-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d40fc-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="d40fc-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d40fc-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d40fc-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d40fc-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="d40fc-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d40fc-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d40fc-120">E_FAIL</span></span>|<span data-ttu-id="d40fc-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="d40fc-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d40fc-122">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="d40fc-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d40fc-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="d40fc-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d40fc-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d40fc-124">E_INVALIDARG</span></span>|<span data-ttu-id="d40fc-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)永远不会使用调用`dwConnectionId`，或`dwConnectionId`为零。</span><span class="sxs-lookup"><span data-stu-id="d40fc-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d40fc-126">备注</span><span class="sxs-lookup"><span data-stu-id="d40fc-126">Remarks</span></span>  
 <span data-ttu-id="d40fc-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)提供三种方法， `BeginConnection`， [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)，和`EndConnection`，用于将任务列表相关联的标识符和友好名称。</span><span class="sxs-lookup"><span data-stu-id="d40fc-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d40fc-128">必须为每个组的任务特定的顺序调用这三种方法。</span><span class="sxs-lookup"><span data-stu-id="d40fc-128">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="d40fc-129">`BeginConnection` 首先调用来建立新连接。</span><span class="sxs-lookup"><span data-stu-id="d40fc-129">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="d40fc-130">`SetConnectionTasks` 将调用下一步来提供要与该连接相关联的任务组。</span><span class="sxs-lookup"><span data-stu-id="d40fc-130">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="d40fc-131">`EndConnection` 最后调用以删除任务列表的标识符和友好名称之间的关联。但是，可以嵌套调用不同的连接。</span><span class="sxs-lookup"><span data-stu-id="d40fc-131">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d40fc-132">要求</span><span class="sxs-lookup"><span data-stu-id="d40fc-132">Requirements</span></span>  
 <span data-ttu-id="d40fc-133">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d40fc-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d40fc-134">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d40fc-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d40fc-135">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d40fc-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d40fc-136">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d40fc-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d40fc-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="d40fc-137">See also</span></span>

- [<span data-ttu-id="d40fc-138">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="d40fc-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="d40fc-139">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="d40fc-139">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="d40fc-140">BeginConnection 方法</span><span class="sxs-lookup"><span data-stu-id="d40fc-140">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="d40fc-141">SetConnectionTasks 方法</span><span class="sxs-lookup"><span data-stu-id="d40fc-141">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="d40fc-142">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="d40fc-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
