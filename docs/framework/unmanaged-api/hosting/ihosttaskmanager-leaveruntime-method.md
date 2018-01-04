---
title: "IHostTaskManager::LeaveRuntime 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.LeaveRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::LeaveRuntime
helpviewer_keywords:
- IHostTaskManager::LeaveRuntime method [.NET Framework hosting]
- LeaveRuntime method [.NET Framework hosting]
ms.assetid: 43689cc4-e48e-46e5-a22d-bafd768b8759
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a4c168cffba44a21d6705e8abd921ecbf8a9da6b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagerleaveruntime-method"></a><span data-ttu-id="1b293-102">IHostTaskManager::LeaveRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="1b293-102">IHostTaskManager::LeaveRuntime Method</span></span>
<span data-ttu-id="1b293-103">通知主机当前正在执行的任务来保持公共语言运行时 (CLR)，然后输入非托管的代码。</span><span class="sxs-lookup"><span data-stu-id="1b293-103">Notifies the host that the currently executing task is about to leave the common language runtime (CLR) and enter unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1b293-104">相应地调用[ihosttaskmanager:: Enterruntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)通知主机当前正在执行的任务重新进入托管的代码。</span><span class="sxs-lookup"><span data-stu-id="1b293-104">A corresponding call to [IHostTaskManager::EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifies the host that the currently executing task is reentering managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b293-105">语法</span><span class="sxs-lookup"><span data-stu-id="1b293-105">Syntax</span></span>  
  
```  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1b293-106">参数</span><span class="sxs-lookup"><span data-stu-id="1b293-106">Parameters</span></span>  
 `target`  
 <span data-ttu-id="1b293-107">[in]要调用的非托管函数的映射可移植可执行文件内的地址。</span><span class="sxs-lookup"><span data-stu-id="1b293-107">[in] The address within the mapped portable executable file of the unmanaged function to be called.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b293-108">返回值</span><span class="sxs-lookup"><span data-stu-id="1b293-108">Return Value</span></span>  
  
|<span data-ttu-id="1b293-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1b293-109">HRESULT</span></span>|<span data-ttu-id="1b293-110">描述</span><span class="sxs-lookup"><span data-stu-id="1b293-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1b293-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1b293-111">S_OK</span></span>|<span data-ttu-id="1b293-112">`LeaveRuntime`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="1b293-112">`LeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="1b293-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1b293-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1b293-114">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="1b293-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1b293-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1b293-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1b293-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="1b293-116">The call timed out.</span></span>|  
|<span data-ttu-id="1b293-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1b293-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1b293-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="1b293-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1b293-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1b293-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1b293-120">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="1b293-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1b293-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1b293-121">E_FAIL</span></span>|<span data-ttu-id="1b293-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="1b293-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1b293-123">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="1b293-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1b293-124">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="1b293-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1b293-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="1b293-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="1b293-126">没有足够的内存是可用于完成所请求的分配。</span><span class="sxs-lookup"><span data-stu-id="1b293-126">Not enough memory is available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b293-127">备注</span><span class="sxs-lookup"><span data-stu-id="1b293-127">Remarks</span></span>  
 <span data-ttu-id="1b293-128">可以嵌套到和从非托管代码的调用序列。</span><span class="sxs-lookup"><span data-stu-id="1b293-128">Call sequences to and from unmanaged code can be nested.</span></span> <span data-ttu-id="1b293-129">例如，下面的列表描述的假设的情况下，在其中对的调用序列`LeaveRuntime`， [ihosttaskmanager:: Reverseenterruntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)， [ihosttaskmanager:: Reverseleaveruntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)，和`IHostTaskManager::EnterRuntime`允许宿主确定嵌套的层。</span><span class="sxs-lookup"><span data-stu-id="1b293-129">For example, the list below describes a hypothetical situation in which the sequence of calls to `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), and `IHostTaskManager::EnterRuntime` allows the host to identify the nested layers.</span></span>  
  
|<span data-ttu-id="1b293-130">操作</span><span class="sxs-lookup"><span data-stu-id="1b293-130">Action</span></span>|<span data-ttu-id="1b293-131">相应的方法调用</span><span class="sxs-lookup"><span data-stu-id="1b293-131">Corresponding Method Call</span></span>|  
|------------|-------------------------------|  
|<span data-ttu-id="1b293-132">托管的 Visual Basic 可执行文件调用在 C 中编写通过使用平台非托管的函数调用。</span><span class="sxs-lookup"><span data-stu-id="1b293-132">A managed Visual Basic executable calls an unmanaged function written in C by using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="1b293-133">非托管的 C 函数在 C# 中编写的托管 DLL 中调用的方法。</span><span class="sxs-lookup"><span data-stu-id="1b293-133">The unmanaged C function calls a method in a managed DLL written in C#.</span></span>|`IHostTaskManager::ReverseEnterRuntime`|  
|<span data-ttu-id="1b293-134">托管的 C# 函数调用在 C 中编写的其他非托管的函数，还使用平台调用。</span><span class="sxs-lookup"><span data-stu-id="1b293-134">The managed C# function calls another unmanaged function written in C, also using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="1b293-135">第二个非托管的函数将执行返回给 C# 函数。</span><span class="sxs-lookup"><span data-stu-id="1b293-135">The second unmanaged function returns execution to the C# function.</span></span>|`IHostTaskManager::EnterRuntime`|  
|<span data-ttu-id="1b293-136">C# 函数将执行返回给第一个非托管函数。</span><span class="sxs-lookup"><span data-stu-id="1b293-136">The C# function returns execution to the first unmanaged function.</span></span>|`IHostTaskManager::ReverseLeaveRuntime`|  
|<span data-ttu-id="1b293-137">第一个非托管的函数将执行返回到 Visual Basic 程序。</span><span class="sxs-lookup"><span data-stu-id="1b293-137">The first unmanaged function returns execution to the Visual Basic program.</span></span>|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a><span data-ttu-id="1b293-138">惠?</span><span class="sxs-lookup"><span data-stu-id="1b293-138">Requirements</span></span>  
 <span data-ttu-id="1b293-139">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1b293-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b293-140">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1b293-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1b293-141">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1b293-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b293-142">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b293-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b293-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="1b293-143">See Also</span></span>  
 [<span data-ttu-id="1b293-144">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="1b293-144">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="1b293-145">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="1b293-145">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="1b293-146">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="1b293-146">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="1b293-147">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="1b293-147">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
