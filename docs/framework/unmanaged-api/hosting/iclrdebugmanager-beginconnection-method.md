---
title: "ICLRDebugManager::BeginConnection 方法"
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
- ICLRDebugManager.BeginConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::BeginConnection
helpviewer_keywords:
- ICLRDebugManager::BeginConnection method [.NET Framework hosting]
- BeginConnection method [.NET Framework hosting]
ms.assetid: bdd98146-ff4d-4150-a264-a4c1a32d31f3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a637ba71dc966cf311526f468393ef4207e10460
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebugmanagerbeginconnection-method"></a><span data-ttu-id="0baae-102">ICLRDebugManager::BeginConnection 方法</span><span class="sxs-lookup"><span data-stu-id="0baae-102">ICLRDebugManager::BeginConnection Method</span></span>
<span data-ttu-id="0baae-103">建立在主机和调试器标识符和友好名称与关联的任务的列表之间的新连接。</span><span class="sxs-lookup"><span data-stu-id="0baae-103">Establishes a new connection between the host and the debugger to associate a list of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0baae-104">语法</span><span class="sxs-lookup"><span data-stu-id="0baae-104">Syntax</span></span>  
  
```  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0baae-105">参数</span><span class="sxs-lookup"><span data-stu-id="0baae-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="0baae-106">[in]使用标识符来将与公共语言运行时 (CLR) 任务的列表相关联。</span><span class="sxs-lookup"><span data-stu-id="0baae-106">[in] An identifier to associate with the list of common language runtime (CLR) tasks.</span></span>  
  
 `szConnectionName`  
 <span data-ttu-id="0baae-107">[in]要将与列表中的 CLR 任务相关联的友好名称。</span><span class="sxs-lookup"><span data-stu-id="0baae-107">[in] A friendly name to associate with the list of CLR tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0baae-108">返回值</span><span class="sxs-lookup"><span data-stu-id="0baae-108">Return Value</span></span>  
  
|<span data-ttu-id="0baae-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0baae-109">HRESULT</span></span>|<span data-ttu-id="0baae-110">描述</span><span class="sxs-lookup"><span data-stu-id="0baae-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0baae-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0baae-111">S_OK</span></span>|<span data-ttu-id="0baae-112">`BeginConnection`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="0baae-112">`BeginConnection` returned successfully.</span></span>|  
|<span data-ttu-id="0baae-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0baae-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0baae-114">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="0baae-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0baae-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0baae-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0baae-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="0baae-116">The call timed out.</span></span>|  
|<span data-ttu-id="0baae-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0baae-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0baae-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="0baae-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0baae-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0baae-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0baae-120">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="0baae-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0baae-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0baae-121">E_FAIL</span></span>|<span data-ttu-id="0baae-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="0baae-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0baae-123">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="0baae-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0baae-124">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="0baae-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0baae-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0baae-125">E_INVALIDARG</span></span>|<span data-ttu-id="0baae-126">`dwConnectionId`为零，或`BeginConnection`已调用使用此`dwConnectionId`值，或`szConnectionName`为 null。</span><span class="sxs-lookup"><span data-stu-id="0baae-126">`dwConnectionId` was zero, or `BeginConnection` was already called using this `dwConnectionId` value, or `szConnectionName` was null.</span></span>|  
|<span data-ttu-id="0baae-127">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0baae-127">E_OUTOFMEMORY</span></span>|<span data-ttu-id="0baae-128">无法分配没有足够的内存来保存与此连接关联的任务列表。</span><span class="sxs-lookup"><span data-stu-id="0baae-128">Not enough memory could be allocated to hold the list of tasks associated with this connection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0baae-129">备注</span><span class="sxs-lookup"><span data-stu-id="0baae-129">Remarks</span></span>  
 <span data-ttu-id="0baae-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)提供三种方法， `BeginConnection`， [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)，和[EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)，将任务列表标识符和友好名称与相关联。</span><span class="sxs-lookup"><span data-stu-id="0baae-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0baae-131">必须按特定顺序为每一组任务调用这三种方法。</span><span class="sxs-lookup"><span data-stu-id="0baae-131">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="0baae-132">`BeginConnection`都会首先调用来建立新连接。</span><span class="sxs-lookup"><span data-stu-id="0baae-132">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="0baae-133">`SetConnectionTasks`调用下一步可提供的任务与该连接关联集。</span><span class="sxs-lookup"><span data-stu-id="0baae-133">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="0baae-134">`EndConnection`调用上一次可删除任务列表的标识符和友好名称之间的关联。但是，可以嵌套不同连接的调用。</span><span class="sxs-lookup"><span data-stu-id="0baae-134">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0baae-135">惠?</span><span class="sxs-lookup"><span data-stu-id="0baae-135">Requirements</span></span>  
 <span data-ttu-id="0baae-136">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0baae-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0baae-137">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0baae-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0baae-138">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0baae-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0baae-139">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0baae-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0baae-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="0baae-140">See Also</span></span>  
 [<span data-ttu-id="0baae-141">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="0baae-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="0baae-142">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="0baae-142">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="0baae-143">EndConnection 方法</span><span class="sxs-lookup"><span data-stu-id="0baae-143">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)  
 [<span data-ttu-id="0baae-144">SetConnectionTasks 方法</span><span class="sxs-lookup"><span data-stu-id="0baae-144">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)  
 [<span data-ttu-id="0baae-145">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="0baae-145">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
