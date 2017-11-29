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
ms.openlocfilehash: ab0b107c050b1c4b686f761ede75ea2349825270
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a><span data-ttu-id="7c202-102">IHostThreadPoolManager::SetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="7c202-102">IHostThreadPoolManager::SetMinThreads Method</span></span>
<span data-ttu-id="7c202-103">预期的请求中设置的最小主机必须维护的空闲线程数。</span><span class="sxs-lookup"><span data-stu-id="7c202-103">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c202-104">语法</span><span class="sxs-lookup"><span data-stu-id="7c202-104">Syntax</span></span>  
  
```  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7c202-105">参数</span><span class="sxs-lookup"><span data-stu-id="7c202-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="7c202-106">[in]新最小线程数，主机必须维护。</span><span class="sxs-lookup"><span data-stu-id="7c202-106">[in] The new minimum number of threads that the host must maintain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c202-107">返回值</span><span class="sxs-lookup"><span data-stu-id="7c202-107">Return Value</span></span>  
  
|<span data-ttu-id="7c202-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c202-108">HRESULT</span></span>|<span data-ttu-id="7c202-109">描述</span><span class="sxs-lookup"><span data-stu-id="7c202-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c202-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c202-110">S_OK</span></span>|<span data-ttu-id="7c202-111">`SetMinThreads`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="7c202-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="7c202-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7c202-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7c202-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="7c202-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7c202-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7c202-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7c202-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="7c202-115">The call timed out.</span></span>|  
|<span data-ttu-id="7c202-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7c202-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7c202-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="7c202-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7c202-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7c202-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7c202-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="7c202-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7c202-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7c202-120">E_FAIL</span></span>|<span data-ttu-id="7c202-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="7c202-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7c202-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="7c202-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7c202-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="7c202-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7c202-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="7c202-124">E_NOTIMPL</span></span>|<span data-ttu-id="7c202-125">主机未提供的实现`SetMinThreads`。</span><span class="sxs-lookup"><span data-stu-id="7c202-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c202-126">备注</span><span class="sxs-lookup"><span data-stu-id="7c202-126">Remarks</span></span>  
 <span data-ttu-id="7c202-127">主机不需要提供的实现`SetMinThreads`。</span><span class="sxs-lookup"><span data-stu-id="7c202-127">A host is not required to provide an implementation of `SetMinThreads`.</span></span> <span data-ttu-id="7c202-128">在这种情况下，它应返回 E_NOTIMPL 的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="7c202-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c202-129">要求</span><span class="sxs-lookup"><span data-stu-id="7c202-129">Requirements</span></span>  
 <span data-ttu-id="7c202-130">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7c202-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c202-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7c202-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c202-132">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7c202-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c202-133">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c202-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c202-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c202-134">See Also</span></span>  
 <xref:System.Threading.ThreadPool.SetMinThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="7c202-135">GetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="7c202-135">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)  
 [<span data-ttu-id="7c202-136">SetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="7c202-136">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)  
 [<span data-ttu-id="7c202-137">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="7c202-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
