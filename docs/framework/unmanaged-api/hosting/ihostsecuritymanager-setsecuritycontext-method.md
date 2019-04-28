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
ms.openlocfilehash: d31aa0dfad70bed31bd72be5029c7bdff0925ba2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696660"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="1e873-102">IHostSecurityManager::SetSecurityContext 方法</span><span class="sxs-lookup"><span data-stu-id="1e873-102">IHostSecurityManager::SetSecurityContext Method</span></span>
<span data-ttu-id="1e873-103">设置当前执行线程的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="1e873-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e873-104">语法</span><span class="sxs-lookup"><span data-stu-id="1e873-104">Syntax</span></span>  
  
```  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e873-105">参数</span><span class="sxs-lookup"><span data-stu-id="1e873-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="1e873-106">[in]之一[EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)值，该值指示公共语言运行时 (CLR) 的上下文类型放置在主机上。</span><span class="sxs-lookup"><span data-stu-id="1e873-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="1e873-107">[out]指向一个新的地址的指针[IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="1e873-107">[out] A pointer to the address of a new [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1e873-108">返回值</span><span class="sxs-lookup"><span data-stu-id="1e873-108">Return Value</span></span>  
  
|<span data-ttu-id="1e873-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1e873-109">HRESULT</span></span>|<span data-ttu-id="1e873-110">描述</span><span class="sxs-lookup"><span data-stu-id="1e873-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1e873-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1e873-111">S_OK</span></span>|<span data-ttu-id="1e873-112">`SetSecurityContext` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="1e873-112">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="1e873-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1e873-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1e873-114">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="1e873-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1e873-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1e873-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1e873-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="1e873-116">The call timed out.</span></span>|  
|<span data-ttu-id="1e873-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1e873-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1e873-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="1e873-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1e873-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1e873-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1e873-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="1e873-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1e873-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1e873-121">E_FAIL</span></span>|<span data-ttu-id="1e873-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="1e873-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1e873-123">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="1e873-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1e873-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="1e873-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e873-125">备注</span><span class="sxs-lookup"><span data-stu-id="1e873-125">Remarks</span></span>  
 <span data-ttu-id="1e873-126">CLR 调用`SetSecurityContext`几个方案中。</span><span class="sxs-lookup"><span data-stu-id="1e873-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="1e873-127">它将执行类和模块构造函数和终结器之前，CLR 将调用`SetSecurityContext`主机防止执行失败数。</span><span class="sxs-lookup"><span data-stu-id="1e873-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="1e873-128">它将重置的安全上下文为其原始状态后执行构造函数或终结器，通过使用到另一个调用`SetSecurityContext`。</span><span class="sxs-lookup"><span data-stu-id="1e873-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="1e873-129">使用 I/O 完成时出现类似的模式。</span><span class="sxs-lookup"><span data-stu-id="1e873-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="1e873-130">如果主机实现[IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)，CLR 将调用`SetSecurityContext`主机调用后[iclriocompletionmanager:: Oncomplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)。</span><span class="sxs-lookup"><span data-stu-id="1e873-130">If the host implements [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="1e873-131">在工作线程异步点，CLR 将调用`SetSecurityContext`内<xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType>中或在[ihostthreadpoolmanager:: Queueuserworkitem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)，取决于主机或 CLR 实现线程池。</span><span class="sxs-lookup"><span data-stu-id="1e873-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e873-132">要求</span><span class="sxs-lookup"><span data-stu-id="1e873-132">Requirements</span></span>  
 <span data-ttu-id="1e873-133">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1e873-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e873-134">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1e873-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1e873-135">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1e873-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1e873-136">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e873-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e873-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e873-137">See also</span></span>

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [<span data-ttu-id="1e873-138">EContextType 枚举</span><span class="sxs-lookup"><span data-stu-id="1e873-138">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="1e873-139">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="1e873-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="1e873-140">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="1e873-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="1e873-141">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="1e873-141">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="1e873-142">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="1e873-142">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="1e873-143">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="1e873-143">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
