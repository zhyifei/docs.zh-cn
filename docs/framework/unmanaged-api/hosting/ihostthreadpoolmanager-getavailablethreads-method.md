---
title: "IHostThreadPoolManager::GetAvailableThreads 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.GetAvailableThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: 61d26dfd-7f24-4e7d-a63e-b30a463f08e1
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 11cd8de264a332cd553ad44a35355bf45039ab84
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanagergetavailablethreads-method"></a><span data-ttu-id="22f94-102">IHostThreadPoolManager::GetAvailableThreads 方法</span><span class="sxs-lookup"><span data-stu-id="22f94-102">IHostThreadPoolManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="22f94-103">获取在当前不在处理工作项的线程池中的线程数。</span><span class="sxs-lookup"><span data-stu-id="22f94-103">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22f94-104">语法</span><span class="sxs-lookup"><span data-stu-id="22f94-104">Syntax</span></span>  
  
```  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableWorkerThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="22f94-105">参数</span><span class="sxs-lookup"><span data-stu-id="22f94-105">Parameters</span></span>  
 `pdwAvailableWorkerThreads`  
 <span data-ttu-id="22f94-106">[out]指向当前不在处理工作项在线程池中的线程数的指针。</span><span class="sxs-lookup"><span data-stu-id="22f94-106">[out] Pointer to the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22f94-107">返回值</span><span class="sxs-lookup"><span data-stu-id="22f94-107">Return Value</span></span>  
  
|<span data-ttu-id="22f94-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="22f94-108">HRESULT</span></span>|<span data-ttu-id="22f94-109">描述</span><span class="sxs-lookup"><span data-stu-id="22f94-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="22f94-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="22f94-110">S_OK</span></span>|<span data-ttu-id="22f94-111">`GetAvailableThreads`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="22f94-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="22f94-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="22f94-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="22f94-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="22f94-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="22f94-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="22f94-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="22f94-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="22f94-115">The call timed out.</span></span>|  
|<span data-ttu-id="22f94-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="22f94-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="22f94-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="22f94-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="22f94-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="22f94-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="22f94-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="22f94-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="22f94-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="22f94-120">E_FAIL</span></span>|<span data-ttu-id="22f94-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="22f94-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="22f94-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="22f94-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="22f94-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="22f94-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="22f94-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="22f94-124">E_NOTIMPL</span></span>|<span data-ttu-id="22f94-125">主机未提供的实现`GetAvailableThreads`。</span><span class="sxs-lookup"><span data-stu-id="22f94-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22f94-126">备注</span><span class="sxs-lookup"><span data-stu-id="22f94-126">Remarks</span></span>  
 <span data-ttu-id="22f94-127">如果主机未提供的实现`GetAvailableThreads`，它应返回 E_NOTIMPL 的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="22f94-127">If the host does not provide an implementation of `GetAvailableThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22f94-128">要求</span><span class="sxs-lookup"><span data-stu-id="22f94-128">Requirements</span></span>  
 <span data-ttu-id="22f94-129">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="22f94-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22f94-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="22f94-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="22f94-131">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="22f94-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22f94-132">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22f94-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22f94-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22f94-133">See Also</span></span>  
 <xref:System.Threading.ThreadPool.GetAvailableThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="22f94-134">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="22f94-134">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
