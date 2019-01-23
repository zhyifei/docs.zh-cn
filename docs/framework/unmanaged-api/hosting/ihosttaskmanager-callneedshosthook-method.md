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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb91c5dfbe5c83e08d786043d7e4732fa19e53db
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566771"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a><span data-ttu-id="c6962-102">IHostTaskManager::CallNeedsHostHook 方法</span><span class="sxs-lookup"><span data-stu-id="c6962-102">IHostTaskManager::CallNeedsHostHook Method</span></span>
<span data-ttu-id="c6962-103">使宿主能够指定公共语言运行时 (CLR) 是否可以内联指定调用非托管函数。</span><span class="sxs-lookup"><span data-stu-id="c6962-103">Enables the host to specify whether the common language runtime (CLR) can inline the specified call to an unmanaged function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6962-104">语法</span><span class="sxs-lookup"><span data-stu-id="c6962-104">Syntax</span></span>  
  
```  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,   
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c6962-105">参数</span><span class="sxs-lookup"><span data-stu-id="c6962-105">Parameters</span></span>  
 `target`  
 <span data-ttu-id="c6962-106">[in]若要调用的非托管函数的映射的可移植可执行 (PE) 文件内的地址。</span><span class="sxs-lookup"><span data-stu-id="c6962-106">[in] The address within the mapped portable executable (PE) file of the unmanaged function that is to be called.</span></span>  
  
 `pbCallNeedsHostHook`  
 <span data-ttu-id="c6962-107">[out]一个布尔值，该值指示主机是否需要调用要挂钩到指针。</span><span class="sxs-lookup"><span data-stu-id="c6962-107">[out] A pointer to a Boolean value that indicates whether the host requires the call to be hooked.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6962-108">返回值</span><span class="sxs-lookup"><span data-stu-id="c6962-108">Return Value</span></span>  
  
|<span data-ttu-id="c6962-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c6962-109">HRESULT</span></span>|<span data-ttu-id="c6962-110">描述</span><span class="sxs-lookup"><span data-stu-id="c6962-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c6962-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c6962-111">S_OK</span></span>|<span data-ttu-id="c6962-112">`CallNeedsHostHook` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="c6962-112">`CallNeedsHostHook` returned successfully.</span></span>|  
|<span data-ttu-id="c6962-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c6962-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c6962-114">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="c6962-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c6962-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c6962-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c6962-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="c6962-116">The call timed out.</span></span>|  
|<span data-ttu-id="c6962-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c6962-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c6962-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="c6962-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c6962-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c6962-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c6962-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="c6962-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c6962-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c6962-121">E_FAIL</span></span>|<span data-ttu-id="c6962-122">发生了未知的灾难性错误。</span><span class="sxs-lookup"><span data-stu-id="c6962-122">An unknown catastrophic failure has occurred.</span></span> <span data-ttu-id="c6962-123">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="c6962-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c6962-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c6962-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6962-125">备注</span><span class="sxs-lookup"><span data-stu-id="c6962-125">Remarks</span></span>  
 <span data-ttu-id="c6962-126">为了帮助优化执行代码，CLR 将执行分析的每个平台 invoke 调用期间编译，以确定是否可以内联调用。</span><span class="sxs-lookup"><span data-stu-id="c6962-126">To help optimize code execution, the CLR performs an analysis of each platform invoke call during compilation to determine whether the call can be inlined.</span></span> <span data-ttu-id="c6962-127">`CallNeedsHostHook` 使宿主能够重写该决定，通过要求挂接到非托管函数的调用。</span><span class="sxs-lookup"><span data-stu-id="c6962-127">`CallNeedsHostHook` enables the host to override that decision by requiring that a call to an unmanaged function be hooked.</span></span> <span data-ttu-id="c6962-128">如果主机需要挂钩，运行时执行不内联调用。</span><span class="sxs-lookup"><span data-stu-id="c6962-128">If the host requires a hook, the runtime does not inline the call.</span></span>  
  
 <span data-ttu-id="c6962-129">主机通常会要求挂钩，必须调整浮点状态，或接收通知调用即将进入其中主机不能跟踪内存或任何锁的运行时的请求的状态。</span><span class="sxs-lookup"><span data-stu-id="c6962-129">The host typically would require a hook where it must adjust a floating-point state, or upon receiving notification that a call is entering a state where the host cannot track the runtime's requests for memory or any locks taken.</span></span> <span data-ttu-id="c6962-130">当主机需要进行挂钩调用时，运行时通知宿主转换到和从托管代码通过调用[EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)， [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)， [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)，并[ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)。</span><span class="sxs-lookup"><span data-stu-id="c6962-130">When the host requires that the call be hooked, the runtime notifies the host of transitions to and from managed code by using calls to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), and [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6962-131">要求</span><span class="sxs-lookup"><span data-stu-id="c6962-131">Requirements</span></span>  
 <span data-ttu-id="c6962-132">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c6962-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6962-133">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c6962-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6962-134">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c6962-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6962-135">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6962-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6962-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6962-136">See also</span></span>
- [<span data-ttu-id="c6962-137">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="c6962-137">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="c6962-138">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="c6962-138">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="c6962-139">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="c6962-139">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="c6962-140">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="c6962-140">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
