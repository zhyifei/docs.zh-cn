---
title: ICLRDebugManager::BeginConnection 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: 2ac2b0dde97b883313e1bca17c5e99855484e4aa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126572"
---
# <a name="iclrdebugmanagerbeginconnection-method"></a><span data-ttu-id="abc27-102">ICLRDebugManager::BeginConnection 方法</span><span class="sxs-lookup"><span data-stu-id="abc27-102">ICLRDebugManager::BeginConnection Method</span></span>
<span data-ttu-id="abc27-103">在宿主和调试器之间建立新的连接，以将任务列表与标识符和友好名称关联起来。</span><span class="sxs-lookup"><span data-stu-id="abc27-103">Establishes a new connection between the host and the debugger to associate a list of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abc27-104">语法</span><span class="sxs-lookup"><span data-stu-id="abc27-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="abc27-105">参数</span><span class="sxs-lookup"><span data-stu-id="abc27-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="abc27-106">中与公共语言运行时（CLR）任务列表关联的标识符。</span><span class="sxs-lookup"><span data-stu-id="abc27-106">[in] An identifier to associate with the list of common language runtime (CLR) tasks.</span></span>  
  
 `szConnectionName`  
 <span data-ttu-id="abc27-107">中与 CLR 任务列表关联的友好名称。</span><span class="sxs-lookup"><span data-stu-id="abc27-107">[in] A friendly name to associate with the list of CLR tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="abc27-108">返回值</span><span class="sxs-lookup"><span data-stu-id="abc27-108">Return Value</span></span>  
  
|<span data-ttu-id="abc27-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="abc27-109">HRESULT</span></span>|<span data-ttu-id="abc27-110">描述</span><span class="sxs-lookup"><span data-stu-id="abc27-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="abc27-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="abc27-111">S_OK</span></span>|<span data-ttu-id="abc27-112">`BeginConnection` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="abc27-112">`BeginConnection` returned successfully.</span></span>|  
|<span data-ttu-id="abc27-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="abc27-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="abc27-114">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="abc27-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="abc27-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="abc27-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="abc27-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="abc27-116">The call timed out.</span></span>|  
|<span data-ttu-id="abc27-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="abc27-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="abc27-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="abc27-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="abc27-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="abc27-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="abc27-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="abc27-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="abc27-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="abc27-121">E_FAIL</span></span>|<span data-ttu-id="abc27-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="abc27-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="abc27-123">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="abc27-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="abc27-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="abc27-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="abc27-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="abc27-125">E_INVALIDARG</span></span>|<span data-ttu-id="abc27-126">`dwConnectionId` 为零，或已使用此 `dwConnectionId` 值调用 `BeginConnection`，或 `szConnectionName` 为 null。</span><span class="sxs-lookup"><span data-stu-id="abc27-126">`dwConnectionId` was zero, or `BeginConnection` was already called using this `dwConnectionId` value, or `szConnectionName` was null.</span></span>|  
|<span data-ttu-id="abc27-127">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="abc27-127">E_OUTOFMEMORY</span></span>|<span data-ttu-id="abc27-128">无法分配足够的内存来保存与此连接关联的任务列表。</span><span class="sxs-lookup"><span data-stu-id="abc27-128">Not enough memory could be allocated to hold the list of tasks associated with this connection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abc27-129">备注</span><span class="sxs-lookup"><span data-stu-id="abc27-129">Remarks</span></span>  
 <span data-ttu-id="abc27-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)提供了三种方法： `BeginConnection`、 [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)和[EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)，将任务列表与标识符和友好名称关联起来。</span><span class="sxs-lookup"><span data-stu-id="abc27-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="abc27-131">对于每组任务，这三种方法都必须按特定的顺序进行调用。</span><span class="sxs-lookup"><span data-stu-id="abc27-131">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="abc27-132">首先调用 `BeginConnection`，建立新连接。</span><span class="sxs-lookup"><span data-stu-id="abc27-132">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="abc27-133">接下来调用 `SetConnectionTasks`，提供要与该连接相关联的一组任务。</span><span class="sxs-lookup"><span data-stu-id="abc27-133">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="abc27-134">最后调用 `EndConnection`，以删除任务列表与标识符和友好名称之间的关联。但是，可以嵌套不同连接的调用。</span><span class="sxs-lookup"><span data-stu-id="abc27-134">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abc27-135">要求</span><span class="sxs-lookup"><span data-stu-id="abc27-135">Requirements</span></span>  
 <span data-ttu-id="abc27-136">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="abc27-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abc27-137">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="abc27-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="abc27-138">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="abc27-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="abc27-139">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abc27-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abc27-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="abc27-140">See also</span></span>

- [<span data-ttu-id="abc27-141">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="abc27-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="abc27-142">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="abc27-142">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="abc27-143">EndConnection 方法</span><span class="sxs-lookup"><span data-stu-id="abc27-143">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="abc27-144">SetConnectionTasks 方法</span><span class="sxs-lookup"><span data-stu-id="abc27-144">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="abc27-145">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="abc27-145">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
