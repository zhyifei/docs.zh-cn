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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b365aaa13b3070662a74ebcfc914f5ed3d291d76
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133986"
---
# <a name="iclrdebugmanagerbeginconnection-method"></a><span data-ttu-id="22799-102">ICLRDebugManager::BeginConnection 方法</span><span class="sxs-lookup"><span data-stu-id="22799-102">ICLRDebugManager::BeginConnection Method</span></span>
<span data-ttu-id="22799-103">建立主机与调试器能够标识符和友好名称相关联的任务的列表之间的新连接。</span><span class="sxs-lookup"><span data-stu-id="22799-103">Establishes a new connection between the host and the debugger to associate a list of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22799-104">语法</span><span class="sxs-lookup"><span data-stu-id="22799-104">Syntax</span></span>  
  
```  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22799-105">参数</span><span class="sxs-lookup"><span data-stu-id="22799-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="22799-106">[in]一个标识符，以将与公共语言运行时 (CLR) 任务列表相关联。</span><span class="sxs-lookup"><span data-stu-id="22799-106">[in] An identifier to associate with the list of common language runtime (CLR) tasks.</span></span>  
  
 `szConnectionName`  
 <span data-ttu-id="22799-107">[in]使用 CLR 任务列表中的关联的友好名称。</span><span class="sxs-lookup"><span data-stu-id="22799-107">[in] A friendly name to associate with the list of CLR tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22799-108">返回值</span><span class="sxs-lookup"><span data-stu-id="22799-108">Return Value</span></span>  
  
|<span data-ttu-id="22799-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="22799-109">HRESULT</span></span>|<span data-ttu-id="22799-110">描述</span><span class="sxs-lookup"><span data-stu-id="22799-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="22799-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="22799-111">S_OK</span></span>|`BeginConnection` <span data-ttu-id="22799-112">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="22799-112">returned successfully.</span></span>|  
|<span data-ttu-id="22799-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="22799-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="22799-114">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="22799-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="22799-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="22799-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="22799-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="22799-116">The call timed out.</span></span>|  
|<span data-ttu-id="22799-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="22799-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="22799-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="22799-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="22799-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="22799-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="22799-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="22799-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="22799-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="22799-121">E_FAIL</span></span>|<span data-ttu-id="22799-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="22799-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="22799-123">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="22799-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="22799-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="22799-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="22799-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="22799-125">E_INVALIDARG</span></span>|`dwConnectionId` <span data-ttu-id="22799-126">是零，或`BeginConnection`已使用此调用`dwConnectionId`值，或`szConnectionName`为 null。</span><span class="sxs-lookup"><span data-stu-id="22799-126">was zero, or `BeginConnection` was already called using this `dwConnectionId` value, or `szConnectionName` was null.</span></span>|  
|<span data-ttu-id="22799-127">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="22799-127">E_OUTOFMEMORY</span></span>|<span data-ttu-id="22799-128">未能分配没有足够的内存来保存与此连接关联的任务列表。</span><span class="sxs-lookup"><span data-stu-id="22799-128">Not enough memory could be allocated to hold the list of tasks associated with this connection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22799-129">备注</span><span class="sxs-lookup"><span data-stu-id="22799-129">Remarks</span></span>  
 <span data-ttu-id="22799-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)提供三种方法， `BeginConnection`， [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)，并[EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)，用于将任务列表相关联的标识符和友好名称。</span><span class="sxs-lookup"><span data-stu-id="22799-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="22799-131">必须为每个组的任务特定的顺序调用这三种方法。</span><span class="sxs-lookup"><span data-stu-id="22799-131">These three methods must be called in a specific order for each set of tasks.</span></span> `BeginConnection` <span data-ttu-id="22799-132">首先调用来建立新连接。</span><span class="sxs-lookup"><span data-stu-id="22799-132">is called first to establish a new connection.</span></span> `SetConnectionTasks` <span data-ttu-id="22799-133">将调用下一步来提供要与该连接相关联的任务组。</span><span class="sxs-lookup"><span data-stu-id="22799-133">is called next to provide the set of tasks to be associated with that connection.</span></span> `EndConnection` <span data-ttu-id="22799-134">最后调用以删除任务列表的标识符和友好名称之间的关联。但是，可以嵌套调用不同的连接。</span><span class="sxs-lookup"><span data-stu-id="22799-134">is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22799-135">要求</span><span class="sxs-lookup"><span data-stu-id="22799-135">Requirements</span></span>  
 <span data-ttu-id="22799-136">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="22799-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22799-137">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="22799-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="22799-138">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="22799-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="22799-139">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="22799-139">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="22799-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="22799-140">See also</span></span>

- [<span data-ttu-id="22799-141">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="22799-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="22799-142">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="22799-142">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="22799-143">EndConnection 方法</span><span class="sxs-lookup"><span data-stu-id="22799-143">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="22799-144">SetConnectionTasks 方法</span><span class="sxs-lookup"><span data-stu-id="22799-144">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="22799-145">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="22799-145">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
