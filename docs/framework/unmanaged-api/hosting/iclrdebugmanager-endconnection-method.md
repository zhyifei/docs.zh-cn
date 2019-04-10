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
ms.openlocfilehash: cf21e1844ea99b231054f8350ddacb8bb707a94e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200099"
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="0c857-102">ICLRDebugManager::EndConnection 方法</span><span class="sxs-lookup"><span data-stu-id="0c857-102">ICLRDebugManager::EndConnection Method</span></span>
<span data-ttu-id="0c857-103">删除任务列表和标识符和友好名称之间的关联。</span><span class="sxs-lookup"><span data-stu-id="0c857-103">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c857-104">语法</span><span class="sxs-lookup"><span data-stu-id="0c857-104">Syntax</span></span>  
  
```  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c857-105">参数</span><span class="sxs-lookup"><span data-stu-id="0c857-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="0c857-106">[in]连接和关联的公共语言运行时 (CLR) 任务列表的特定于宿主的标识符。</span><span class="sxs-lookup"><span data-stu-id="0c857-106">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c857-107">返回值</span><span class="sxs-lookup"><span data-stu-id="0c857-107">Return Value</span></span>  
  
|<span data-ttu-id="0c857-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0c857-108">HRESULT</span></span>|<span data-ttu-id="0c857-109">描述</span><span class="sxs-lookup"><span data-stu-id="0c857-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0c857-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0c857-110">S_OK</span></span>|`EndConnection` <span data-ttu-id="0c857-111">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="0c857-111">returned successfully.</span></span>|  
|<span data-ttu-id="0c857-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0c857-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0c857-113">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="0c857-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0c857-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0c857-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0c857-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="0c857-115">The call timed out.</span></span>|  
|<span data-ttu-id="0c857-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0c857-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0c857-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="0c857-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0c857-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0c857-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0c857-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="0c857-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0c857-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0c857-120">E_FAIL</span></span>|<span data-ttu-id="0c857-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="0c857-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0c857-122">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="0c857-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0c857-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="0c857-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0c857-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0c857-124">E_INVALIDARG</span></span>|<span data-ttu-id="0c857-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)永远不会使用调用`dwConnectionId`，或`dwConnectionId`为零。</span><span class="sxs-lookup"><span data-stu-id="0c857-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c857-126">备注</span><span class="sxs-lookup"><span data-stu-id="0c857-126">Remarks</span></span>  
 <span data-ttu-id="0c857-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)提供三种方法， `BeginConnection`， [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)，和`EndConnection`，用于将任务列表相关联的标识符和友好名称。</span><span class="sxs-lookup"><span data-stu-id="0c857-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0c857-128">必须为每个组的任务特定的顺序调用这三种方法。</span><span class="sxs-lookup"><span data-stu-id="0c857-128">These three methods must be called in a specific order for each set of tasks.</span></span> `BeginConnection` <span data-ttu-id="0c857-129">首先调用来建立新连接。</span><span class="sxs-lookup"><span data-stu-id="0c857-129">is called first to establish a new connection.</span></span> `SetConnectionTasks` <span data-ttu-id="0c857-130">将调用下一步来提供要与该连接相关联的任务组。</span><span class="sxs-lookup"><span data-stu-id="0c857-130">is called next to provide the set of tasks to be associated with that connection.</span></span> `EndConnection` <span data-ttu-id="0c857-131">最后调用以删除任务列表的标识符和友好名称之间的关联。但是，可以嵌套调用不同的连接。</span><span class="sxs-lookup"><span data-stu-id="0c857-131">is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c857-132">要求</span><span class="sxs-lookup"><span data-stu-id="0c857-132">Requirements</span></span>  
 <span data-ttu-id="0c857-133">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0c857-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c857-134">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0c857-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0c857-135">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0c857-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="0c857-136">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="0c857-136">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0c857-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c857-137">See also</span></span>

- [<span data-ttu-id="0c857-138">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="0c857-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="0c857-139">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="0c857-139">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="0c857-140">BeginConnection 方法</span><span class="sxs-lookup"><span data-stu-id="0c857-140">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="0c857-141">SetConnectionTasks 方法</span><span class="sxs-lookup"><span data-stu-id="0c857-141">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="0c857-142">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="0c857-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
