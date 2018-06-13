---
title: IHostThreadPoolManager::GetMinThreads 方法
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMinThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMinThreads method [.NET Framework hosting]
- GetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: dc07232b-b2e4-4dab-87e2-3c955974ab48
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2064f134d83e6d410e851d8ea9498b45e36aea37
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442262"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="67c59-102">IHostThreadPoolManager::GetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="67c59-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="67c59-103">在线程池中为预期的请求中获取的最小主机维护的空闲线程数。</span><span class="sxs-lookup"><span data-stu-id="67c59-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67c59-104">语法</span><span class="sxs-lookup"><span data-stu-id="67c59-104">Syntax</span></span>  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67c59-105">参数</span><span class="sxs-lookup"><span data-stu-id="67c59-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="67c59-106">[out]指向当前维护主机的空闲辅助线程的最小数的指针。</span><span class="sxs-lookup"><span data-stu-id="67c59-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67c59-107">返回值</span><span class="sxs-lookup"><span data-stu-id="67c59-107">Return Value</span></span>  
  
|<span data-ttu-id="67c59-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="67c59-108">HRESULT</span></span>|<span data-ttu-id="67c59-109">描述</span><span class="sxs-lookup"><span data-stu-id="67c59-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="67c59-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="67c59-110">S_OK</span></span>|<span data-ttu-id="67c59-111">`GetMinThreads` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="67c59-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="67c59-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="67c59-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="67c59-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="67c59-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="67c59-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="67c59-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="67c59-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="67c59-115">The call timed out.</span></span>|  
|<span data-ttu-id="67c59-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="67c59-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="67c59-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="67c59-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="67c59-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="67c59-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="67c59-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="67c59-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="67c59-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="67c59-120">E_FAIL</span></span>|<span data-ttu-id="67c59-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="67c59-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="67c59-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="67c59-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="67c59-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="67c59-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="67c59-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="67c59-124">E_NOTIMPL</span></span>|<span data-ttu-id="67c59-125">主机未提供的实现`GetMinThreads`。</span><span class="sxs-lookup"><span data-stu-id="67c59-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67c59-126">备注</span><span class="sxs-lookup"><span data-stu-id="67c59-126">Remarks</span></span>  
 <span data-ttu-id="67c59-127">主机不需要提供的实现`GetMinThreads`。</span><span class="sxs-lookup"><span data-stu-id="67c59-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="67c59-128">在这种情况下，它应返回 E_NOTIMPL 的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="67c59-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67c59-129">要求</span><span class="sxs-lookup"><span data-stu-id="67c59-129">Requirements</span></span>  
 <span data-ttu-id="67c59-130">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="67c59-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67c59-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="67c59-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="67c59-132">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="67c59-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67c59-133">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67c59-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67c59-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="67c59-134">See Also</span></span>  
 <xref:System.Threading.ThreadPool.GetMinThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="67c59-135">GetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="67c59-135">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)  
 [<span data-ttu-id="67c59-136">SetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="67c59-136">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)  
 [<span data-ttu-id="67c59-137">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="67c59-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
