---
title: "IHostThreadPoolManager::SetMinThreads 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.SetMinThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: 10409db9-9fd2-4e4d-b8cd-cf6fec0afaa2
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4fccfeb616b7a1c6d797ad9d91f47e696c4f3599
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a><span data-ttu-id="543a8-102">IHostThreadPoolManager::SetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="543a8-102">IHostThreadPoolManager::SetMinThreads Method</span></span>
<span data-ttu-id="543a8-103">预期的请求中设置的最小主机必须维护的空闲线程数。</span><span class="sxs-lookup"><span data-stu-id="543a8-103">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="543a8-104">语法</span><span class="sxs-lookup"><span data-stu-id="543a8-104">Syntax</span></span>  
  
```  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="543a8-105">参数</span><span class="sxs-lookup"><span data-stu-id="543a8-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="543a8-106">[in]新最小线程数，主机必须维护。</span><span class="sxs-lookup"><span data-stu-id="543a8-106">[in] The new minimum number of threads that the host must maintain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="543a8-107">返回值</span><span class="sxs-lookup"><span data-stu-id="543a8-107">Return Value</span></span>  
  
|<span data-ttu-id="543a8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="543a8-108">HRESULT</span></span>|<span data-ttu-id="543a8-109">描述</span><span class="sxs-lookup"><span data-stu-id="543a8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="543a8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="543a8-110">S_OK</span></span>|<span data-ttu-id="543a8-111">`SetMinThreads`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="543a8-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="543a8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="543a8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="543a8-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="543a8-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="543a8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="543a8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="543a8-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="543a8-115">The call timed out.</span></span>|  
|<span data-ttu-id="543a8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="543a8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="543a8-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="543a8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="543a8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="543a8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="543a8-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="543a8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="543a8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="543a8-120">E_FAIL</span></span>|<span data-ttu-id="543a8-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="543a8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="543a8-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="543a8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="543a8-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="543a8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="543a8-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="543a8-124">E_NOTIMPL</span></span>|<span data-ttu-id="543a8-125">主机未提供的实现`SetMinThreads`。</span><span class="sxs-lookup"><span data-stu-id="543a8-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="543a8-126">备注</span><span class="sxs-lookup"><span data-stu-id="543a8-126">Remarks</span></span>  
 <span data-ttu-id="543a8-127">主机不需要提供的实现`SetMinThreads`。</span><span class="sxs-lookup"><span data-stu-id="543a8-127">A host is not required to provide an implementation of `SetMinThreads`.</span></span> <span data-ttu-id="543a8-128">在这种情况下，它应返回 E_NOTIMPL 的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="543a8-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="543a8-129">惠?</span><span class="sxs-lookup"><span data-stu-id="543a8-129">Requirements</span></span>  
 <span data-ttu-id="543a8-130">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="543a8-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="543a8-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="543a8-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="543a8-132">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="543a8-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="543a8-133">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="543a8-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="543a8-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="543a8-134">See Also</span></span>  
 <xref:System.Threading.ThreadPool.SetMinThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="543a8-135">GetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="543a8-135">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)  
 [<span data-ttu-id="543a8-136">SetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="543a8-136">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)  
 [<span data-ttu-id="543a8-137">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="543a8-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
