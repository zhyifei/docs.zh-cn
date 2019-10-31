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
ms.openlocfilehash: 676a1d50202333203c13fcf916dbb14a6d91fb8f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121449"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="b7a3e-102">IHostSecurityManager::SetSecurityContext 方法</span><span class="sxs-lookup"><span data-stu-id="b7a3e-102">IHostSecurityManager::SetSecurityContext Method</span></span>
<span data-ttu-id="b7a3e-103">设置当前正在执行的线程的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="b7a3e-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7a3e-104">语法</span><span class="sxs-lookup"><span data-stu-id="b7a3e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7a3e-105">参数</span><span class="sxs-lookup"><span data-stu-id="b7a3e-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="b7a3e-106">中[EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)值之一，指示公共语言运行时（CLR）在主机上放置的上下文的类型。</span><span class="sxs-lookup"><span data-stu-id="b7a3e-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="b7a3e-107">弄指向新[IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="b7a3e-107">[out] A pointer to the address of a new [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7a3e-108">返回值</span><span class="sxs-lookup"><span data-stu-id="b7a3e-108">Return Value</span></span>  
  
|<span data-ttu-id="b7a3e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b7a3e-109">HRESULT</span></span>|<span data-ttu-id="b7a3e-110">描述</span><span class="sxs-lookup"><span data-stu-id="b7a3e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b7a3e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b7a3e-111">S_OK</span></span>|<span data-ttu-id="b7a3e-112">`SetSecurityContext` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="b7a3e-112">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="b7a3e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b7a3e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b7a3e-114">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="b7a3e-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b7a3e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b7a3e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b7a3e-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="b7a3e-116">The call timed out.</span></span>|  
|<span data-ttu-id="b7a3e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b7a3e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b7a3e-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="b7a3e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b7a3e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b7a3e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b7a3e-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="b7a3e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b7a3e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b7a3e-121">E_FAIL</span></span>|<span data-ttu-id="b7a3e-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="b7a3e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b7a3e-123">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="b7a3e-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b7a3e-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="b7a3e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7a3e-125">备注</span><span class="sxs-lookup"><span data-stu-id="b7a3e-125">Remarks</span></span>  
 <span data-ttu-id="b7a3e-126">CLR 在多个方案中调用 `SetSecurityContext`。</span><span class="sxs-lookup"><span data-stu-id="b7a3e-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="b7a3e-127">在执行类和模块构造函数和终结器之前，CLR 调用 `SetSecurityContext` 来保护宿主不会执行失败。</span><span class="sxs-lookup"><span data-stu-id="b7a3e-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="b7a3e-128">然后，它会在执行构造函数或终结器后将安全上下文重置为其原始状态，方法是使用另一次调用 `SetSecurityContext`。</span><span class="sxs-lookup"><span data-stu-id="b7a3e-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="b7a3e-129">I/o 完成时，会出现类似的模式。</span><span class="sxs-lookup"><span data-stu-id="b7a3e-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="b7a3e-130">如果主机实现[IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)，则 CLR 会在主机调用[ICLRIoCompletionManager：： OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)后调用 `SetSecurityContext`。</span><span class="sxs-lookup"><span data-stu-id="b7a3e-130">If the host implements [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="b7a3e-131">在工作线程的异步点，CLR 在 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> 或[IHostThreadPoolManager：： QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)内调用 `SetSecurityContext`，具体取决于宿主或 CLR 是否实现线程池。</span><span class="sxs-lookup"><span data-stu-id="b7a3e-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7a3e-132">要求</span><span class="sxs-lookup"><span data-stu-id="b7a3e-132">Requirements</span></span>  
 <span data-ttu-id="b7a3e-133">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b7a3e-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7a3e-134">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b7a3e-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b7a3e-135">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="b7a3e-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b7a3e-136">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7a3e-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7a3e-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="b7a3e-137">See also</span></span>

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [<span data-ttu-id="b7a3e-138">EContextType 枚举</span><span class="sxs-lookup"><span data-stu-id="b7a3e-138">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="b7a3e-139">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="b7a3e-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="b7a3e-140">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="b7a3e-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="b7a3e-141">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="b7a3e-141">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="b7a3e-142">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="b7a3e-142">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="b7a3e-143">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="b7a3e-143">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
