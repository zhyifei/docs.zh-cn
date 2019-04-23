---
title: IHostIoCompletionManager::SetMaxThreads 方法
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: ebad4f40-d9f1-4dc6-9b27-a89c9eb3926f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 345c7b88b6967773a185538943591383a686748c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59224043"
---
# <a name="ihostiocompletionmanagersetmaxthreads-method"></a><span data-ttu-id="bbd93-102">IHostIoCompletionManager::SetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="bbd93-102">IHostIoCompletionManager::SetMaxThreads Method</span></span>
<span data-ttu-id="bbd93-103">设置为 I/O 请求提供服务的最大主机分配的线程数。</span><span class="sxs-lookup"><span data-stu-id="bbd93-103">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbd93-104">语法</span><span class="sxs-lookup"><span data-stu-id="bbd93-104">Syntax</span></span>  
  
```  
HRESULT SetMaxThreads (  
    [in] DWORD dwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bbd93-105">参数</span><span class="sxs-lookup"><span data-stu-id="bbd93-105">Parameters</span></span>  
 `dwMaxIoCompletionThreads`  
 <span data-ttu-id="bbd93-106">[in]最大线程分配给 I/O 请求数。</span><span class="sxs-lookup"><span data-stu-id="bbd93-106">[in] The maximum number of threads to allot for I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bbd93-107">返回值</span><span class="sxs-lookup"><span data-stu-id="bbd93-107">Return Value</span></span>  
  
|<span data-ttu-id="bbd93-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bbd93-108">HRESULT</span></span>|<span data-ttu-id="bbd93-109">描述</span><span class="sxs-lookup"><span data-stu-id="bbd93-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bbd93-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="bbd93-110">S_OK</span></span>|<span data-ttu-id="bbd93-111">`SetMaxThreads` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="bbd93-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="bbd93-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bbd93-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bbd93-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="bbd93-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bbd93-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bbd93-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bbd93-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="bbd93-115">The call timed out.</span></span>|  
|<span data-ttu-id="bbd93-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bbd93-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bbd93-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="bbd93-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bbd93-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bbd93-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bbd93-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="bbd93-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bbd93-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bbd93-120">E_FAIL</span></span>|<span data-ttu-id="bbd93-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="bbd93-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bbd93-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="bbd93-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bbd93-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="bbd93-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="bbd93-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="bbd93-124">E_NOTIMPL</span></span>|<span data-ttu-id="bbd93-125">主机未提供的实现`SetMaxThreads`。</span><span class="sxs-lookup"><span data-stu-id="bbd93-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bbd93-126">备注</span><span class="sxs-lookup"><span data-stu-id="bbd93-126">Remarks</span></span>  
 <span data-ttu-id="bbd93-127">`SetMaxThreads` 提供 CLR 的机会，若要设置的最大可为 I/O 端口上请求提供服务的线程数。</span><span class="sxs-lookup"><span data-stu-id="bbd93-127">`SetMaxThreads` provides the CLR with an opportunity to set the maximum number of threads that are available to service requests on I/O ports.</span></span> <span data-ttu-id="bbd93-128">由于实现、 性能或可伸缩性的原因，主机可能需要的线程池大小的独有控制。</span><span class="sxs-lookup"><span data-stu-id="bbd93-128">A host might need exclusive control over the size of the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="bbd93-129">出于此原因，该主机不需要实现`SetMaxThreads`。</span><span class="sxs-lookup"><span data-stu-id="bbd93-129">For this reason, the host is not required to implement `SetMaxThreads`.</span></span> <span data-ttu-id="bbd93-130">在这种情况下，主机应从此方法返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="bbd93-130">In this case, a host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbd93-131">要求</span><span class="sxs-lookup"><span data-stu-id="bbd93-131">Requirements</span></span>  
 <span data-ttu-id="bbd93-132">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bbd93-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbd93-133">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bbd93-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bbd93-134">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="bbd93-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bbd93-135">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbd93-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbd93-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="bbd93-136">See also</span></span>

- [<span data-ttu-id="bbd93-137">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="bbd93-137">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="bbd93-138">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="bbd93-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
