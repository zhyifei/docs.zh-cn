---
title: "IHostThreadPoolManager::GetMaxThreads 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.GetMaxThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::GetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: db268876-6178-4a81-aca3-318ee7f96001
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 84867f1b5dfdcfd7a50d01c9e51cb0c42da62f0e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a><span data-ttu-id="95737-102">IHostThreadPoolManager::GetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="95737-102">IHostThreadPoolManager::GetMaxThreads Method</span></span>
<span data-ttu-id="95737-103">在线程池中同时获取最大主机维护的线程数。</span><span class="sxs-lookup"><span data-stu-id="95737-103">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95737-104">语法</span><span class="sxs-lookup"><span data-stu-id="95737-104">Syntax</span></span>  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="95737-105">参数</span><span class="sxs-lookup"><span data-stu-id="95737-105">Parameters</span></span>  
 `pdwMaxWorkerThreads`  
 <span data-ttu-id="95737-106">[out]指向主机维护在线程池中的线程的最大数的指针。</span><span class="sxs-lookup"><span data-stu-id="95737-106">[out] A pointer to the maximum number of threads that the host maintains in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95737-107">返回值</span><span class="sxs-lookup"><span data-stu-id="95737-107">Return Value</span></span>  
  
|<span data-ttu-id="95737-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="95737-108">HRESULT</span></span>|<span data-ttu-id="95737-109">描述</span><span class="sxs-lookup"><span data-stu-id="95737-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="95737-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="95737-110">S_OK</span></span>|<span data-ttu-id="95737-111">`GetMaxThreads`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="95737-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="95737-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="95737-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="95737-113">公共语言运行时 (CLR (尚未加载到进程，或 CLR 正处于状态它不能运行托管的代码或过程调用已成功。</span><span class="sxs-lookup"><span data-stu-id="95737-113">The common language runtime (CLR( has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="95737-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="95737-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="95737-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="95737-115">The call timed out.</span></span>|  
|<span data-ttu-id="95737-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="95737-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="95737-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="95737-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="95737-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="95737-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="95737-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="95737-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="95737-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="95737-120">E_FAIL</span></span>|<span data-ttu-id="95737-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="95737-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="95737-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="95737-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="95737-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="95737-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="95737-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="95737-124">E_NOTIMPL</span></span>|<span data-ttu-id="95737-125">主机未提供的实现`GetMaxThreads`。</span><span class="sxs-lookup"><span data-stu-id="95737-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95737-126">备注</span><span class="sxs-lookup"><span data-stu-id="95737-126">Remarks</span></span>  
 <span data-ttu-id="95737-127">CLR 调用`GetMaxThreads`以确定线程池中的线程总数。</span><span class="sxs-lookup"><span data-stu-id="95737-127">The CLR calls `GetMaxThreads` to determine the total number of threads in the thread pool.</span></span> <span data-ttu-id="95737-128">[GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)方法获取的当前不在处理工作项的线程数。</span><span class="sxs-lookup"><span data-stu-id="95737-128">The [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) method gets the number of threads that are not currently processing work items.</span></span> <span data-ttu-id="95737-129">上面的返回值的所有请求`pdwMaxWorkerThreads`参数保持排队状态，直到线程变为可用。</span><span class="sxs-lookup"><span data-stu-id="95737-129">All requests above the returned value of the `pdwMaxWorkerThreads` parameter remain queued until threads become available.</span></span>  
  
 <span data-ttu-id="95737-130">如果主机未提供的实现`GetMaxThreads`，它应返回 E_NOTIMPL 的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="95737-130">If the host does not provide an implementation of `GetMaxThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95737-131">惠?</span><span class="sxs-lookup"><span data-stu-id="95737-131">Requirements</span></span>  
 <span data-ttu-id="95737-132">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="95737-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95737-133">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="95737-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="95737-134">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="95737-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95737-135">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95737-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95737-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="95737-136">See Also</span></span>  
 <xref:System.Threading.ThreadPool.GetMaxThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="95737-137">GetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="95737-137">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)  
 [<span data-ttu-id="95737-138">SetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="95737-138">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)  
 [<span data-ttu-id="95737-139">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="95737-139">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
