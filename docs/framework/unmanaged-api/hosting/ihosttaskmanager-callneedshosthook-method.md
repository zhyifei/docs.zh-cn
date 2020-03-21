---
title: IHostTaskManager::CallNeedsHostHook 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CallNeedsHostHook
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CallNeedsHostHook
helpviewer_keywords:
- CallNeedsHostHook method [.NET Framework hosting]
- IHostTaskManager::CallNeedsHostHook method [.NET Framework hosting]
ms.assetid: b60f1f59-9825-4b57-961f-d2979518e6a7
topic_type:
- apiref
ms.openlocfilehash: 8b8b8521a09fa54a105e8263a471ab0467fb6ccc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176287"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a><span data-ttu-id="fe22e-102">IHostTaskManager::CallNeedsHostHook 方法</span><span class="sxs-lookup"><span data-stu-id="fe22e-102">IHostTaskManager::CallNeedsHostHook Method</span></span>
<span data-ttu-id="fe22e-103">使主机能够指定通用语言运行时 （CLR） 是否可以将指定的调用内联到非托管函数。</span><span class="sxs-lookup"><span data-stu-id="fe22e-103">Enables the host to specify whether the common language runtime (CLR) can inline the specified call to an unmanaged function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe22e-104">语法</span><span class="sxs-lookup"><span data-stu-id="fe22e-104">Syntax</span></span>  
  
```cpp  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe22e-105">parameters</span><span class="sxs-lookup"><span data-stu-id="fe22e-105">Parameters</span></span>  
 `target`  
 <span data-ttu-id="fe22e-106">[在]要调用的非托管函数的映射的可移植可执行 （PE） 文件中的地址。</span><span class="sxs-lookup"><span data-stu-id="fe22e-106">[in] The address within the mapped portable executable (PE) file of the unmanaged function that is to be called.</span></span>  
  
 `pbCallNeedsHostHook`  
 <span data-ttu-id="fe22e-107">[出]指向布尔值的指针，指示主机是否需要挂接调用。</span><span class="sxs-lookup"><span data-stu-id="fe22e-107">[out] A pointer to a Boolean value that indicates whether the host requires the call to be hooked.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe22e-108">返回值</span><span class="sxs-lookup"><span data-stu-id="fe22e-108">Return Value</span></span>  
  
|<span data-ttu-id="fe22e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fe22e-109">HRESULT</span></span>|<span data-ttu-id="fe22e-110">说明</span><span class="sxs-lookup"><span data-stu-id="fe22e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fe22e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fe22e-111">S_OK</span></span>|<span data-ttu-id="fe22e-112">`CallNeedsHostHook`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="fe22e-112">`CallNeedsHostHook` returned successfully.</span></span>|  
|<span data-ttu-id="fe22e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fe22e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fe22e-114">CLR 尚未加载到进程中，或者 CLR 处于无法成功运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="fe22e-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fe22e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fe22e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fe22e-116">呼叫超时。</span><span class="sxs-lookup"><span data-stu-id="fe22e-116">The call timed out.</span></span>|  
|<span data-ttu-id="fe22e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fe22e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fe22e-118">调用方不拥有锁。</span><span class="sxs-lookup"><span data-stu-id="fe22e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fe22e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fe22e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fe22e-120">当阻塞的线程或光纤等待事件时，事件已被取消。</span><span class="sxs-lookup"><span data-stu-id="fe22e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fe22e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fe22e-121">E_FAIL</span></span>|<span data-ttu-id="fe22e-122">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="fe22e-122">An unknown catastrophic failure has occurred.</span></span> <span data-ttu-id="fe22e-123">当方法返回E_FAIL时，CLR 在进程中不再可用。</span><span class="sxs-lookup"><span data-stu-id="fe22e-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fe22e-124">对托管方法的后续调用返回HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="fe22e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe22e-125">备注</span><span class="sxs-lookup"><span data-stu-id="fe22e-125">Remarks</span></span>  
 <span data-ttu-id="fe22e-126">为了帮助优化代码执行，CLR 在编译期间对每个平台调用调用执行分析，以确定调用是否可以内联。</span><span class="sxs-lookup"><span data-stu-id="fe22e-126">To help optimize code execution, the CLR performs an analysis of each platform invoke call during compilation to determine whether the call can be inlined.</span></span> <span data-ttu-id="fe22e-127">`CallNeedsHostHook`使主机通过要求对非托管函数的调用进行挂接来覆盖该决策。</span><span class="sxs-lookup"><span data-stu-id="fe22e-127">`CallNeedsHostHook` enables the host to override that decision by requiring that a call to an unmanaged function be hooked.</span></span> <span data-ttu-id="fe22e-128">如果主机需要挂钩，则运行时不会内联呼叫。</span><span class="sxs-lookup"><span data-stu-id="fe22e-128">If the host requires a hook, the runtime does not inline the call.</span></span>  
  
 <span data-ttu-id="fe22e-129">主机通常需要一个挂钩，它必须调整浮点状态，或在收到通知时，呼叫正在进入一个状态，其中主机无法跟踪运行时的内存请求或获取的任何锁。</span><span class="sxs-lookup"><span data-stu-id="fe22e-129">The host typically would require a hook where it must adjust a floating-point state, or upon receiving notification that a call is entering a state where the host cannot track the runtime's requests for memory or any locks taken.</span></span> <span data-ttu-id="fe22e-130">当主机要求挂接调用时，运行时通过使用对[EnterRuntime、](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)[离开运行时](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)、[反向EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)和[反向LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)的调用来通知主机与托管代码转换。</span><span class="sxs-lookup"><span data-stu-id="fe22e-130">When the host requires that the call be hooked, the runtime notifies the host of transitions to and from managed code by using calls to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), and [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe22e-131">要求</span><span class="sxs-lookup"><span data-stu-id="fe22e-131">Requirements</span></span>  
 <span data-ttu-id="fe22e-132">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fe22e-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe22e-133">**标题：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fe22e-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fe22e-134">**库：** 作为资源包含在 MSCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="fe22e-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fe22e-135">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe22e-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe22e-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe22e-136">See also</span></span>

- [<span data-ttu-id="fe22e-137">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="fe22e-137">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="fe22e-138">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="fe22e-138">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="fe22e-139">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="fe22e-139">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="fe22e-140">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="fe22e-140">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
