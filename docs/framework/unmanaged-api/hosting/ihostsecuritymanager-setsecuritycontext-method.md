---
title: IHostSecurityManager::SetSecurityContext 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3fa2df44d631b7e6c606ebb831f2915e9e649aab
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480164"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="acd31-102">IHostSecurityManager::SetSecurityContext 方法</span><span class="sxs-lookup"><span data-stu-id="acd31-102">IHostSecurityManager::SetSecurityContext Method</span></span>
<span data-ttu-id="acd31-103">设置当前执行线程的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="acd31-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acd31-104">语法</span><span class="sxs-lookup"><span data-stu-id="acd31-104">Syntax</span></span>  
  
```  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acd31-105">参数</span><span class="sxs-lookup"><span data-stu-id="acd31-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="acd31-106">[in]之一[EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)值，该值指示公共语言运行时 (CLR) 的上下文类型放置在主机上。</span><span class="sxs-lookup"><span data-stu-id="acd31-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="acd31-107">[out]指向一个新的地址的指针[IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="acd31-107">[out] A pointer to the address of a new [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="acd31-108">返回值</span><span class="sxs-lookup"><span data-stu-id="acd31-108">Return Value</span></span>  
  
|<span data-ttu-id="acd31-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="acd31-109">HRESULT</span></span>|<span data-ttu-id="acd31-110">描述</span><span class="sxs-lookup"><span data-stu-id="acd31-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="acd31-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="acd31-111">S_OK</span></span>|<span data-ttu-id="acd31-112">`SetSecurityContext` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="acd31-112">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="acd31-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="acd31-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="acd31-114">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="acd31-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="acd31-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="acd31-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="acd31-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="acd31-116">The call timed out.</span></span>|  
|<span data-ttu-id="acd31-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="acd31-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="acd31-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="acd31-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="acd31-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="acd31-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="acd31-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="acd31-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="acd31-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="acd31-121">E_FAIL</span></span>|<span data-ttu-id="acd31-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="acd31-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="acd31-123">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="acd31-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="acd31-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="acd31-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acd31-125">备注</span><span class="sxs-lookup"><span data-stu-id="acd31-125">Remarks</span></span>  
 <span data-ttu-id="acd31-126">CLR 调用`SetSecurityContext`几个方案中。</span><span class="sxs-lookup"><span data-stu-id="acd31-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="acd31-127">它将执行类和模块构造函数和终结器之前，CLR 将调用`SetSecurityContext`主机防止执行失败数。</span><span class="sxs-lookup"><span data-stu-id="acd31-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="acd31-128">它将重置的安全上下文为其原始状态后执行构造函数或终结器，通过使用到另一个调用`SetSecurityContext`。</span><span class="sxs-lookup"><span data-stu-id="acd31-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="acd31-129">使用 I/O 完成时出现类似的模式。</span><span class="sxs-lookup"><span data-stu-id="acd31-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="acd31-130">如果主机实现[IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)，CLR 将调用`SetSecurityContext`主机调用后[iclriocompletionmanager:: Oncomplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)。</span><span class="sxs-lookup"><span data-stu-id="acd31-130">If the host implements [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="acd31-131">在工作线程异步点，CLR 将调用`SetSecurityContext`内<xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType>中或在[ihostthreadpoolmanager:: Queueuserworkitem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)，取决于主机或 CLR 实现线程池。</span><span class="sxs-lookup"><span data-stu-id="acd31-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acd31-132">要求</span><span class="sxs-lookup"><span data-stu-id="acd31-132">Requirements</span></span>  
 <span data-ttu-id="acd31-133">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="acd31-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acd31-134">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="acd31-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="acd31-135">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="acd31-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="acd31-136">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acd31-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acd31-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="acd31-137">See also</span></span>
- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [<span data-ttu-id="acd31-138">EContextType 枚举</span><span class="sxs-lookup"><span data-stu-id="acd31-138">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="acd31-139">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="acd31-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="acd31-140">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="acd31-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="acd31-141">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="acd31-141">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="acd31-142">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="acd31-142">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="acd31-143">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="acd31-143">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
