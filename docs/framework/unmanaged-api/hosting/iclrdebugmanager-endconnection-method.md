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
ms.openlocfilehash: f524cadf77caec0823411784c68f339207433601
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615775"
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="49879-102">ICLRDebugManager::EndConnection 方法</span><span class="sxs-lookup"><span data-stu-id="49879-102">ICLRDebugManager::EndConnection Method</span></span>
<span data-ttu-id="49879-103">删除任务列表与标识符和友好名称之间的关联。</span><span class="sxs-lookup"><span data-stu-id="49879-103">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49879-104">语法</span><span class="sxs-lookup"><span data-stu-id="49879-104">Syntax</span></span>  
  
```cpp  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49879-105">参数</span><span class="sxs-lookup"><span data-stu-id="49879-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="49879-106">中连接的主机特定标识符和公共语言运行时（CLR）任务的关联列表。</span><span class="sxs-lookup"><span data-stu-id="49879-106">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49879-107">返回值</span><span class="sxs-lookup"><span data-stu-id="49879-107">Return Value</span></span>  
  
|<span data-ttu-id="49879-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="49879-108">HRESULT</span></span>|<span data-ttu-id="49879-109">说明</span><span class="sxs-lookup"><span data-stu-id="49879-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="49879-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="49879-110">S_OK</span></span>|<span data-ttu-id="49879-111">`EndConnection`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="49879-111">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="49879-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="49879-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="49879-113">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="49879-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="49879-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="49879-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="49879-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="49879-115">The call timed out.</span></span>|  
|<span data-ttu-id="49879-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="49879-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="49879-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="49879-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="49879-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="49879-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="49879-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="49879-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="49879-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="49879-120">E_FAIL</span></span>|<span data-ttu-id="49879-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="49879-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="49879-122">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="49879-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="49879-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="49879-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="49879-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="49879-124">E_INVALIDARG</span></span>|<span data-ttu-id="49879-125">[BeginConnection](iclrdebugmanager-beginconnection-method.md)从不使用调用 `dwConnectionId` ，或为 `dwConnectionId` 零。</span><span class="sxs-lookup"><span data-stu-id="49879-125">[BeginConnection](iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49879-126">备注</span><span class="sxs-lookup"><span data-stu-id="49879-126">Remarks</span></span>  
 <span data-ttu-id="49879-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)提供了三种方法：、 `BeginConnection` [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md)和 `EndConnection` ，以将任务列表与标识符和友好名称关联起来。</span><span class="sxs-lookup"><span data-stu-id="49879-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="49879-128">对于每组任务，这三种方法都必须按特定的顺序进行调用。</span><span class="sxs-lookup"><span data-stu-id="49879-128">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="49879-129">`BeginConnection`首先调用以建立新连接。</span><span class="sxs-lookup"><span data-stu-id="49879-129">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="49879-130">`SetConnectionTasks`在旁边调用，提供要与该连接相关联的一组任务。</span><span class="sxs-lookup"><span data-stu-id="49879-130">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="49879-131">`EndConnection`最后调用，以删除任务列表与标识符和友好名称之间的关联。但是，可以嵌套不同连接的调用。</span><span class="sxs-lookup"><span data-stu-id="49879-131">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49879-132">要求</span><span class="sxs-lookup"><span data-stu-id="49879-132">Requirements</span></span>  
 <span data-ttu-id="49879-133">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="49879-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49879-134">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="49879-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="49879-135">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="49879-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="49879-136">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49879-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49879-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49879-137">See also</span></span>

- [<span data-ttu-id="49879-138">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="49879-138">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="49879-139">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="49879-139">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="49879-140">BeginConnection 方法</span><span class="sxs-lookup"><span data-stu-id="49879-140">BeginConnection Method</span></span>](iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="49879-141">SetConnectionTasks 方法</span><span class="sxs-lookup"><span data-stu-id="49879-141">SetConnectionTasks Method</span></span>](iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="49879-142">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="49879-142">IHostControl Interface</span></span>](ihostcontrol-interface.md)
