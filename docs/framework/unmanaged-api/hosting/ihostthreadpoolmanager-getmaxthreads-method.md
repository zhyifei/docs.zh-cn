---
title: IHostThreadPoolManager::GetMaxThreads 方法
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: db268876-6178-4a81-aca3-318ee7f96001
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4dce4efeb82f44e2c0d19e95551696b16e9f07ba
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157540"
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a><span data-ttu-id="0c5b0-102">IHostThreadPoolManager::GetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="0c5b0-102">IHostThreadPoolManager::GetMaxThreads Method</span></span>
<span data-ttu-id="0c5b0-103">在线程池中同时获取的最大主机维护的线程数。</span><span class="sxs-lookup"><span data-stu-id="0c5b0-103">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c5b0-104">语法</span><span class="sxs-lookup"><span data-stu-id="0c5b0-104">Syntax</span></span>  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c5b0-105">参数</span><span class="sxs-lookup"><span data-stu-id="0c5b0-105">Parameters</span></span>  
 `pdwMaxWorkerThreads`  
 <span data-ttu-id="0c5b0-106">[out]指向的最大主机将在线程池中的线程数的指针。</span><span class="sxs-lookup"><span data-stu-id="0c5b0-106">[out] A pointer to the maximum number of threads that the host maintains in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c5b0-107">返回值</span><span class="sxs-lookup"><span data-stu-id="0c5b0-107">Return Value</span></span>  
  
|<span data-ttu-id="0c5b0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0c5b0-108">HRESULT</span></span>|<span data-ttu-id="0c5b0-109">描述</span><span class="sxs-lookup"><span data-stu-id="0c5b0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0c5b0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0c5b0-110">S_OK</span></span>|`GetMaxThreads` <span data-ttu-id="0c5b0-111">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="0c5b0-111">returned successfully.</span></span>|  
|<span data-ttu-id="0c5b0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0c5b0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0c5b0-113">公共语言运行时 (CLR (尚未加载到进程，或在 CLR 处于状态它不能运行托管的代码或过程调用已成功。</span><span class="sxs-lookup"><span data-stu-id="0c5b0-113">The common language runtime (CLR( has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0c5b0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0c5b0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0c5b0-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="0c5b0-115">The call timed out.</span></span>|  
|<span data-ttu-id="0c5b0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0c5b0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0c5b0-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="0c5b0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0c5b0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0c5b0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0c5b0-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="0c5b0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0c5b0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0c5b0-120">E_FAIL</span></span>|<span data-ttu-id="0c5b0-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="0c5b0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0c5b0-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="0c5b0-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0c5b0-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="0c5b0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0c5b0-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="0c5b0-124">E_NOTIMPL</span></span>|<span data-ttu-id="0c5b0-125">主机未提供的实现`GetMaxThreads`。</span><span class="sxs-lookup"><span data-stu-id="0c5b0-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c5b0-126">备注</span><span class="sxs-lookup"><span data-stu-id="0c5b0-126">Remarks</span></span>  
 <span data-ttu-id="0c5b0-127">CLR 调用`GetMaxThreads`来确定线程池中线程的总数。</span><span class="sxs-lookup"><span data-stu-id="0c5b0-127">The CLR calls `GetMaxThreads` to determine the total number of threads in the thread pool.</span></span> <span data-ttu-id="0c5b0-128">[GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)方法获取当前不在处理工作项的线程数。</span><span class="sxs-lookup"><span data-stu-id="0c5b0-128">The [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) method gets the number of threads that are not currently processing work items.</span></span> <span data-ttu-id="0c5b0-129">返回值的所有请求`pdwMaxWorkerThreads`参数保持排队状态，直到线程变为可用。</span><span class="sxs-lookup"><span data-stu-id="0c5b0-129">All requests above the returned value of the `pdwMaxWorkerThreads` parameter remain queued until threads become available.</span></span>  
  
 <span data-ttu-id="0c5b0-130">如果主机未提供的实现`GetMaxThreads`，它应返回 E_NOTIMPL HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="0c5b0-130">If the host does not provide an implementation of `GetMaxThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c5b0-131">要求</span><span class="sxs-lookup"><span data-stu-id="0c5b0-131">Requirements</span></span>  
 <span data-ttu-id="0c5b0-132">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0c5b0-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c5b0-133">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0c5b0-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0c5b0-134">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0c5b0-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="0c5b0-135">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="0c5b0-135">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0c5b0-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c5b0-136">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="0c5b0-137">GetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="0c5b0-137">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="0c5b0-138">SetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="0c5b0-138">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="0c5b0-139">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="0c5b0-139">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
