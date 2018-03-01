---
title: "IHostSecurityManager::SetSecurityContext 方法"
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
- IHostSecurityManager.SetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetSecurityContext
helpviewer_keywords:
- SetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::SetSecurityContext method [.NET Framework hosting]
ms.assetid: e4372384-ee69-48d7-97e0-8fab7866597a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 29a7652e20c08b9de584a9e11ac343ad92f40653
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="4208f-102">IHostSecurityManager::SetSecurityContext 方法</span><span class="sxs-lookup"><span data-stu-id="4208f-102">IHostSecurityManager::SetSecurityContext Method</span></span>
<span data-ttu-id="4208f-103">设置当前执行线程的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="4208f-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4208f-104">语法</span><span class="sxs-lookup"><span data-stu-id="4208f-104">Syntax</span></span>  
  
```  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4208f-105">参数</span><span class="sxs-lookup"><span data-stu-id="4208f-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="4208f-106">[in]之一[EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)值，该值指示公共语言运行时 (CLR) 的上下文的类型放置在主机上。</span><span class="sxs-lookup"><span data-stu-id="4208f-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="4208f-107">[out]新的地址指针[IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="4208f-107">[out] A pointer to the address of a new [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4208f-108">返回值</span><span class="sxs-lookup"><span data-stu-id="4208f-108">Return Value</span></span>  
  
|<span data-ttu-id="4208f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4208f-109">HRESULT</span></span>|<span data-ttu-id="4208f-110">描述</span><span class="sxs-lookup"><span data-stu-id="4208f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4208f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4208f-111">S_OK</span></span>|<span data-ttu-id="4208f-112">`SetSecurityContext`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="4208f-112">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="4208f-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4208f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4208f-114">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="4208f-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4208f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4208f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4208f-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="4208f-116">The call timed out.</span></span>|  
|<span data-ttu-id="4208f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4208f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4208f-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="4208f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4208f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4208f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4208f-120">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="4208f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4208f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4208f-121">E_FAIL</span></span>|<span data-ttu-id="4208f-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="4208f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4208f-123">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="4208f-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4208f-124">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="4208f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4208f-125">备注</span><span class="sxs-lookup"><span data-stu-id="4208f-125">Remarks</span></span>  
 <span data-ttu-id="4208f-126">CLR 调用`SetSecurityContext`在几种场景。</span><span class="sxs-lookup"><span data-stu-id="4208f-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="4208f-127">它会执行类和模块构造函数和终结器之前，CLR 调用`SetSecurityContext`以防止执行故障的主机。</span><span class="sxs-lookup"><span data-stu-id="4208f-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="4208f-128">它然后通过重置的安全上下文为其原始状态后的构造函数或终结器中，执行另一个调用`SetSecurityContext`。</span><span class="sxs-lookup"><span data-stu-id="4208f-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="4208f-129">使用 I/O 完成时出现类似的模式。</span><span class="sxs-lookup"><span data-stu-id="4208f-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="4208f-130">如果主机实现[IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)，CLR 调用`SetSecurityContext`后宿主调用[iclriocompletionmanager:: Oncomplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)。</span><span class="sxs-lookup"><span data-stu-id="4208f-130">If the host implements [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="4208f-131">在辅助线程中的异步点，CLR 调用`SetSecurityContext`内<xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType>或[ihostthreadpoolmanager:: Queueuserworkitem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)，取决于主机或者 CLR 正在实现的线程池。</span><span class="sxs-lookup"><span data-stu-id="4208f-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4208f-132">惠?</span><span class="sxs-lookup"><span data-stu-id="4208f-132">Requirements</span></span>  
 <span data-ttu-id="4208f-133">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4208f-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4208f-134">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4208f-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4208f-135">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4208f-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4208f-136">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4208f-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4208f-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="4208f-137">See Also</span></span>  
 <xref:System.Threading.ThreadPool?displayProperty=nameWithType>  
 [<span data-ttu-id="4208f-138">EContextType 枚举</span><span class="sxs-lookup"><span data-stu-id="4208f-138">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)  
 [<span data-ttu-id="4208f-139">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="4208f-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="4208f-140">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="4208f-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [<span data-ttu-id="4208f-141">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="4208f-141">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="4208f-142">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="4208f-142">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="4208f-143">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="4208f-143">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
