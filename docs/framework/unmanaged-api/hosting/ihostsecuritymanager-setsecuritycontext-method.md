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
ms.openlocfilehash: 79ef08ef70ad1132ceacc3e2b997651e57032b9a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803814"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="282c6-102">IHostSecurityManager::SetSecurityContext 方法</span><span class="sxs-lookup"><span data-stu-id="282c6-102">IHostSecurityManager::SetSecurityContext Method</span></span>
<span data-ttu-id="282c6-103">设置当前正在执行的线程的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="282c6-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="282c6-104">语法</span><span class="sxs-lookup"><span data-stu-id="282c6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="282c6-105">参数</span><span class="sxs-lookup"><span data-stu-id="282c6-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="282c6-106">中[EContextType](econtexttype-enumeration.md)值之一，指示公共语言运行时（CLR）在主机上放置的上下文的类型。</span><span class="sxs-lookup"><span data-stu-id="282c6-106">[in] One of the [EContextType](econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="282c6-107">弄指向新[IHostSecurityContext](ihostsecuritycontext-interface.md)对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="282c6-107">[out] A pointer to the address of a new [IHostSecurityContext](ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="282c6-108">返回值</span><span class="sxs-lookup"><span data-stu-id="282c6-108">Return Value</span></span>  
  
|<span data-ttu-id="282c6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="282c6-109">HRESULT</span></span>|<span data-ttu-id="282c6-110">说明</span><span class="sxs-lookup"><span data-stu-id="282c6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="282c6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="282c6-111">S_OK</span></span>|<span data-ttu-id="282c6-112">`SetSecurityContext`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="282c6-112">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="282c6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="282c6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="282c6-114">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="282c6-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="282c6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="282c6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="282c6-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="282c6-116">The call timed out.</span></span>|  
|<span data-ttu-id="282c6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="282c6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="282c6-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="282c6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="282c6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="282c6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="282c6-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="282c6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="282c6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="282c6-121">E_FAIL</span></span>|<span data-ttu-id="282c6-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="282c6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="282c6-123">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="282c6-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="282c6-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="282c6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="282c6-125">备注</span><span class="sxs-lookup"><span data-stu-id="282c6-125">Remarks</span></span>  
 <span data-ttu-id="282c6-126">CLR `SetSecurityContext` 在多个方案中调用。</span><span class="sxs-lookup"><span data-stu-id="282c6-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="282c6-127">在执行类和模块构造函数和终结器之前，CLR 将调用 `SetSecurityContext` 以防止执行失败。</span><span class="sxs-lookup"><span data-stu-id="282c6-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="282c6-128">然后，在执行构造函数或终结器后，通过使用对的另一调用，将安全上下文重置为其原始状态 `SetSecurityContext` 。</span><span class="sxs-lookup"><span data-stu-id="282c6-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="282c6-129">I/o 完成时，会出现类似的模式。</span><span class="sxs-lookup"><span data-stu-id="282c6-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="282c6-130">如果主机实现[IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)，则 CLR 会在 `SetSecurityContext` 主机调用[ICLRIoCompletionManager：： OnComplete](iclriocompletionmanager-oncomplete-method.md)后调用。</span><span class="sxs-lookup"><span data-stu-id="282c6-130">If the host implements [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="282c6-131">在工作线程中的异步点，CLR 在 `SetSecurityContext` <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> [IHostThreadPoolManager：： QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md)内或内调用，具体取决于宿主或 CLR 是否实现线程池。</span><span class="sxs-lookup"><span data-stu-id="282c6-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="282c6-132">要求</span><span class="sxs-lookup"><span data-stu-id="282c6-132">Requirements</span></span>  
 <span data-ttu-id="282c6-133">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="282c6-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="282c6-134">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="282c6-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="282c6-135">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="282c6-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="282c6-136">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="282c6-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="282c6-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="282c6-137">See also</span></span>

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [<span data-ttu-id="282c6-138">EContextType 枚举</span><span class="sxs-lookup"><span data-stu-id="282c6-138">EContextType Enumeration</span></span>](econtexttype-enumeration.md)
- [<span data-ttu-id="282c6-139">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="282c6-139">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="282c6-140">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="282c6-140">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="282c6-141">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="282c6-141">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="282c6-142">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="282c6-142">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="282c6-143">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="282c6-143">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
