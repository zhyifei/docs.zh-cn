---
title: "IHostIoCompletionManager::SetMinThreads 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.SetMinThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: dea34b81-8d2b-4cc3-8696-0ad4291d8a92
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a8903aa2f2119ad3c4dceebfaba9ede26200e899
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihostiocompletionmanagersetminthreads-method"></a><span data-ttu-id="40665-102">IHostIoCompletionManager::SetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="40665-102">IHostIoCompletionManager::SetMinThreads Method</span></span>
<span data-ttu-id="40665-103">将最小应分配主机的线程数设置为 I/O 完成。</span><span class="sxs-lookup"><span data-stu-id="40665-103">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40665-104">语法</span><span class="sxs-lookup"><span data-stu-id="40665-104">Syntax</span></span>  
  
```  
HRESULT SetMinThreads (  
    [in] DWORD dwMinIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40665-105">参数</span><span class="sxs-lookup"><span data-stu-id="40665-105">Parameters</span></span>  
 `dwMinIoCompletionThreads`  
 <span data-ttu-id="40665-106">[in]最小主机应创建的 I/O 完成线程数。</span><span class="sxs-lookup"><span data-stu-id="40665-106">[in] The minimum number of I/O completion threads that the host should create.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40665-107">返回值</span><span class="sxs-lookup"><span data-stu-id="40665-107">Return Value</span></span>  
  
|<span data-ttu-id="40665-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="40665-108">HRESULT</span></span>|<span data-ttu-id="40665-109">描述</span><span class="sxs-lookup"><span data-stu-id="40665-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="40665-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="40665-110">S_OK</span></span>|<span data-ttu-id="40665-111">`SetMinThreads`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="40665-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="40665-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="40665-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="40665-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="40665-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="40665-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="40665-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="40665-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="40665-115">The call timed out.</span></span>|  
|<span data-ttu-id="40665-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="40665-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="40665-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="40665-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="40665-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="40665-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="40665-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="40665-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="40665-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="40665-120">E_FAIL</span></span>|<span data-ttu-id="40665-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="40665-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="40665-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="40665-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="40665-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="40665-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="40665-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="40665-124">E_NOTIMPL</span></span>|<span data-ttu-id="40665-125">主机未提供的实现`SetMinThreads`。</span><span class="sxs-lookup"><span data-stu-id="40665-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40665-126">备注</span><span class="sxs-lookup"><span data-stu-id="40665-126">Remarks</span></span>  
 <span data-ttu-id="40665-127">主机可能想对可以分配给来处理 I/O 请求，原因例如实现、 性能或可伸缩性的线程数的独有控制。</span><span class="sxs-lookup"><span data-stu-id="40665-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="40665-128">主机不为此，需要实现`SetMinThreads`。</span><span class="sxs-lookup"><span data-stu-id="40665-128">For this reason, the host is not required to implement `SetMinThreads`.</span></span> <span data-ttu-id="40665-129">在这种情况下，主机应通过此方法返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="40665-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40665-130">要求</span><span class="sxs-lookup"><span data-stu-id="40665-130">Requirements</span></span>  
 <span data-ttu-id="40665-131">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="40665-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40665-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="40665-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="40665-133">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="40665-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40665-134">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40665-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40665-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40665-135">See Also</span></span>  
 [<span data-ttu-id="40665-136">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="40665-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="40665-137">SetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="40665-137">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)  
 [<span data-ttu-id="40665-138">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="40665-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
