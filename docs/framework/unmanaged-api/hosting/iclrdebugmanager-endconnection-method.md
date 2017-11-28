---
title: "ICLRDebugManager::EndConnection 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager.EndConnection
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager::EndConnection
helpviewer_keywords:
- ICLRDebugManager::EndConnection method [.NET Framework hosting]
- EndConnection method [.NET Framework hosting]
ms.assetid: 89dc7363-2f29-4eb2-8f23-fccdda6a76a6
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 114f2217d22fc270b03d271db4acc44f0edbcca8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="b2556-102">ICLRDebugManager::EndConnection 方法</span><span class="sxs-lookup"><span data-stu-id="b2556-102">ICLRDebugManager::EndConnection Method</span></span>
<span data-ttu-id="b2556-103">删除的任务列表和标识符和友好名称之间的关联。</span><span class="sxs-lookup"><span data-stu-id="b2556-103">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2556-104">语法</span><span class="sxs-lookup"><span data-stu-id="b2556-104">Syntax</span></span>  
  
```  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b2556-105">参数</span><span class="sxs-lookup"><span data-stu-id="b2556-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="b2556-106">[in]连接和关联的公共语言运行时 (CLR) 任务列表的特定于宿主的标识符。</span><span class="sxs-lookup"><span data-stu-id="b2556-106">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2556-107">返回值</span><span class="sxs-lookup"><span data-stu-id="b2556-107">Return Value</span></span>  
  
|<span data-ttu-id="b2556-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b2556-108">HRESULT</span></span>|<span data-ttu-id="b2556-109">描述</span><span class="sxs-lookup"><span data-stu-id="b2556-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b2556-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b2556-110">S_OK</span></span>|<span data-ttu-id="b2556-111">`EndConnection`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="b2556-111">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="b2556-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b2556-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b2556-113">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="b2556-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b2556-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b2556-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b2556-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="b2556-115">The call timed out.</span></span>|  
|<span data-ttu-id="b2556-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b2556-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b2556-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="b2556-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b2556-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b2556-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b2556-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="b2556-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b2556-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b2556-120">E_FAIL</span></span>|<span data-ttu-id="b2556-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="b2556-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b2556-122">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="b2556-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b2556-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="b2556-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b2556-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b2556-124">E_INVALIDARG</span></span>|<span data-ttu-id="b2556-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)永远不会使用调用`dwConnectionId`，或`dwConnectionId`为零。</span><span class="sxs-lookup"><span data-stu-id="b2556-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2556-126">备注</span><span class="sxs-lookup"><span data-stu-id="b2556-126">Remarks</span></span>  
 <span data-ttu-id="b2556-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)提供三种方法， `BeginConnection`， [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)，和`EndConnection`，将任务列表标识符和友好名称与相关联。</span><span class="sxs-lookup"><span data-stu-id="b2556-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b2556-128">必须按特定顺序为每一组任务调用这三种方法。</span><span class="sxs-lookup"><span data-stu-id="b2556-128">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="b2556-129">`BeginConnection`都会首先调用来建立新连接。</span><span class="sxs-lookup"><span data-stu-id="b2556-129">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="b2556-130">`SetConnectionTasks`调用下一步可提供的任务与该连接关联集。</span><span class="sxs-lookup"><span data-stu-id="b2556-130">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="b2556-131">`EndConnection`调用上一次可删除任务列表的标识符和友好名称之间的关联。但是，可以嵌套不同连接的调用。</span><span class="sxs-lookup"><span data-stu-id="b2556-131">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2556-132">要求</span><span class="sxs-lookup"><span data-stu-id="b2556-132">Requirements</span></span>  
 <span data-ttu-id="b2556-133">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b2556-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2556-134">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b2556-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b2556-135">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b2556-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2556-136">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2556-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2556-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2556-137">See Also</span></span>  
 [<span data-ttu-id="b2556-138">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="b2556-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="b2556-139">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="b2556-139">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="b2556-140">BeginConnection 方法</span><span class="sxs-lookup"><span data-stu-id="b2556-140">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)  
 [<span data-ttu-id="b2556-141">SetConnectionTasks 方法</span><span class="sxs-lookup"><span data-stu-id="b2556-141">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)  
 [<span data-ttu-id="b2556-142">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="b2556-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
