---
title: "IHostThreadPoolManager::GetMinThreads 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 393400c7a5d9d4d99431cbea4a3c3c82064218f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="2c5b2-102">IHostThreadPoolManager::GetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="2c5b2-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="2c5b2-103">在线程池中为预期的请求中获取的最小主机维护的空闲线程数。</span><span class="sxs-lookup"><span data-stu-id="2c5b2-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c5b2-104">语法</span><span class="sxs-lookup"><span data-stu-id="2c5b2-104">Syntax</span></span>  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2c5b2-105">参数</span><span class="sxs-lookup"><span data-stu-id="2c5b2-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="2c5b2-106">[out]指向当前维护主机的空闲辅助线程的最小数的指针。</span><span class="sxs-lookup"><span data-stu-id="2c5b2-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c5b2-107">返回值</span><span class="sxs-lookup"><span data-stu-id="2c5b2-107">Return Value</span></span>  
  
|<span data-ttu-id="2c5b2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2c5b2-108">HRESULT</span></span>|<span data-ttu-id="2c5b2-109">描述</span><span class="sxs-lookup"><span data-stu-id="2c5b2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2c5b2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2c5b2-110">S_OK</span></span>|<span data-ttu-id="2c5b2-111">`GetMinThreads`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="2c5b2-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="2c5b2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2c5b2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2c5b2-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="2c5b2-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2c5b2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2c5b2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2c5b2-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="2c5b2-115">The call timed out.</span></span>|  
|<span data-ttu-id="2c5b2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2c5b2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2c5b2-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="2c5b2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2c5b2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2c5b2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2c5b2-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="2c5b2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2c5b2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2c5b2-120">E_FAIL</span></span>|<span data-ttu-id="2c5b2-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="2c5b2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2c5b2-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="2c5b2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2c5b2-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="2c5b2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2c5b2-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="2c5b2-124">E_NOTIMPL</span></span>|<span data-ttu-id="2c5b2-125">主机未提供的实现`GetMinThreads`。</span><span class="sxs-lookup"><span data-stu-id="2c5b2-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c5b2-126">备注</span><span class="sxs-lookup"><span data-stu-id="2c5b2-126">Remarks</span></span>  
 <span data-ttu-id="2c5b2-127">主机不需要提供的实现`GetMinThreads`。</span><span class="sxs-lookup"><span data-stu-id="2c5b2-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="2c5b2-128">在这种情况下，它应返回 E_NOTIMPL 的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="2c5b2-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c5b2-129">惠?</span><span class="sxs-lookup"><span data-stu-id="2c5b2-129">Requirements</span></span>  
 <span data-ttu-id="2c5b2-130">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2c5b2-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c5b2-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2c5b2-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2c5b2-132">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2c5b2-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c5b2-133">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c5b2-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c5b2-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c5b2-134">See Also</span></span>  
 <xref:System.Threading.ThreadPool.GetMinThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="2c5b2-135">GetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="2c5b2-135">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)  
 [<span data-ttu-id="2c5b2-136">SetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="2c5b2-136">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)  
 [<span data-ttu-id="2c5b2-137">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="2c5b2-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
