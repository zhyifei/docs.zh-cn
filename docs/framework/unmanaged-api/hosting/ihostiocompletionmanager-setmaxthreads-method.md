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
ms.openlocfilehash: 7a16c141d9d07af82bd984955e06199e66ce3bbf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133762"
---
# <a name="ihostiocompletionmanagersetmaxthreads-method"></a><span data-ttu-id="07160-102">IHostIoCompletionManager::SetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="07160-102">IHostIoCompletionManager::SetMaxThreads Method</span></span>
<span data-ttu-id="07160-103">设置主机 allots i/o 请求的最大线程数。</span><span class="sxs-lookup"><span data-stu-id="07160-103">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07160-104">语法</span><span class="sxs-lookup"><span data-stu-id="07160-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMaxThreads (  
    [in] DWORD dwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07160-105">参数</span><span class="sxs-lookup"><span data-stu-id="07160-105">Parameters</span></span>  
 `dwMaxIoCompletionThreads`  
 <span data-ttu-id="07160-106">中为 i/o 请求分配的最大线程数。</span><span class="sxs-lookup"><span data-stu-id="07160-106">[in] The maximum number of threads to allot for I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="07160-107">返回值</span><span class="sxs-lookup"><span data-stu-id="07160-107">Return Value</span></span>  
  
|<span data-ttu-id="07160-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="07160-108">HRESULT</span></span>|<span data-ttu-id="07160-109">描述</span><span class="sxs-lookup"><span data-stu-id="07160-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="07160-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="07160-110">S_OK</span></span>|<span data-ttu-id="07160-111">`SetMaxThreads` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="07160-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="07160-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="07160-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="07160-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="07160-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="07160-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="07160-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="07160-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="07160-115">The call timed out.</span></span>|  
|<span data-ttu-id="07160-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="07160-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="07160-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="07160-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="07160-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="07160-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="07160-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="07160-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="07160-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="07160-120">E_FAIL</span></span>|<span data-ttu-id="07160-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="07160-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="07160-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="07160-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="07160-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="07160-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="07160-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="07160-124">E_NOTIMPL</span></span>|<span data-ttu-id="07160-125">宿主不提供 `SetMaxThreads`的实现。</span><span class="sxs-lookup"><span data-stu-id="07160-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07160-126">备注</span><span class="sxs-lookup"><span data-stu-id="07160-126">Remarks</span></span>  
 <span data-ttu-id="07160-127">`SetMaxThreads` 为 CLR 提供了一个机会，用于设置对 i/o 端口上的服务请求可用的最大线程数。</span><span class="sxs-lookup"><span data-stu-id="07160-127">`SetMaxThreads` provides the CLR with an opportunity to set the maximum number of threads that are available to service requests on I/O ports.</span></span> <span data-ttu-id="07160-128">出于实现、性能或可伸缩性等原因，主机可能需要独占控制线程池的大小。</span><span class="sxs-lookup"><span data-stu-id="07160-128">A host might need exclusive control over the size of the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="07160-129">出于此原因，主机不需要实现 `SetMaxThreads`。</span><span class="sxs-lookup"><span data-stu-id="07160-129">For this reason, the host is not required to implement `SetMaxThreads`.</span></span> <span data-ttu-id="07160-130">在这种情况下，主机应从此方法返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="07160-130">In this case, a host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07160-131">要求</span><span class="sxs-lookup"><span data-stu-id="07160-131">Requirements</span></span>  
 <span data-ttu-id="07160-132">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="07160-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07160-133">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="07160-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="07160-134">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="07160-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="07160-135">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07160-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07160-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="07160-136">See also</span></span>

- [<span data-ttu-id="07160-137">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="07160-137">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="07160-138">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="07160-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
