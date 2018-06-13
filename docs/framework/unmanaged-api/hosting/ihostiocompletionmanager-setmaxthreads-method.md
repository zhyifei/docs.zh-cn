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
ms.openlocfilehash: a810f3a25dc90ddb234c70ca3fa5130039350136
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438816"
---
# <a name="ihostiocompletionmanagersetmaxthreads-method"></a><span data-ttu-id="3ebfa-102">IHostIoCompletionManager::SetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="3ebfa-102">IHostIoCompletionManager::SetMaxThreads Method</span></span>
<span data-ttu-id="3ebfa-103">将最大主机分配的线程数设置为服务输入/输出请求。</span><span class="sxs-lookup"><span data-stu-id="3ebfa-103">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ebfa-104">语法</span><span class="sxs-lookup"><span data-stu-id="3ebfa-104">Syntax</span></span>  
  
```  
HRESULT SetMaxThreads (  
    [in] DWORD dwMaxIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3ebfa-105">参数</span><span class="sxs-lookup"><span data-stu-id="3ebfa-105">Parameters</span></span>  
 `dwMaxIoCompletionThreads`  
 <span data-ttu-id="3ebfa-106">[in]最大线程数以分配给输入/输出请求。</span><span class="sxs-lookup"><span data-stu-id="3ebfa-106">[in] The maximum number of threads to allot for I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ebfa-107">返回值</span><span class="sxs-lookup"><span data-stu-id="3ebfa-107">Return Value</span></span>  
  
|<span data-ttu-id="3ebfa-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3ebfa-108">HRESULT</span></span>|<span data-ttu-id="3ebfa-109">描述</span><span class="sxs-lookup"><span data-stu-id="3ebfa-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3ebfa-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3ebfa-110">S_OK</span></span>|<span data-ttu-id="3ebfa-111">`SetMaxThreads` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="3ebfa-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="3ebfa-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3ebfa-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3ebfa-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="3ebfa-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3ebfa-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3ebfa-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3ebfa-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="3ebfa-115">The call timed out.</span></span>|  
|<span data-ttu-id="3ebfa-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3ebfa-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3ebfa-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="3ebfa-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3ebfa-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3ebfa-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3ebfa-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="3ebfa-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3ebfa-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3ebfa-120">E_FAIL</span></span>|<span data-ttu-id="3ebfa-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="3ebfa-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3ebfa-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="3ebfa-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3ebfa-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="3ebfa-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3ebfa-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="3ebfa-124">E_NOTIMPL</span></span>|<span data-ttu-id="3ebfa-125">主机未提供的实现`SetMaxThreads`。</span><span class="sxs-lookup"><span data-stu-id="3ebfa-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ebfa-126">备注</span><span class="sxs-lookup"><span data-stu-id="3ebfa-126">Remarks</span></span>  
 <span data-ttu-id="3ebfa-127">`SetMaxThreads` CLR 提供了机会设置线程可供 I/O 端口上的服务请求的最大数目。</span><span class="sxs-lookup"><span data-stu-id="3ebfa-127">`SetMaxThreads` provides the CLR with an opportunity to set the maximum number of threads that are available to service requests on I/O ports.</span></span> <span data-ttu-id="3ebfa-128">诸如实现、 性能或可伸缩性之类的原因，主机可能需要对的线程池大小的独有控制。</span><span class="sxs-lookup"><span data-stu-id="3ebfa-128">A host might need exclusive control over the size of the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="3ebfa-129">主机不为此，需要实现`SetMaxThreads`。</span><span class="sxs-lookup"><span data-stu-id="3ebfa-129">For this reason, the host is not required to implement `SetMaxThreads`.</span></span> <span data-ttu-id="3ebfa-130">在这种情况下，主机应通过此方法返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="3ebfa-130">In this case, a host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ebfa-131">要求</span><span class="sxs-lookup"><span data-stu-id="3ebfa-131">Requirements</span></span>  
 <span data-ttu-id="3ebfa-132">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3ebfa-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ebfa-133">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3ebfa-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3ebfa-134">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3ebfa-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3ebfa-135">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ebfa-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ebfa-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="3ebfa-136">See Also</span></span>  
 [<span data-ttu-id="3ebfa-137">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="3ebfa-137">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="3ebfa-138">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="3ebfa-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
