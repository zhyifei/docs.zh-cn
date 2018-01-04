---
title: "IHostIoCompletionManager::GetAvailableThreads 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.GetAvailableThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: bab363d1-b859-47a4-9884-5661c611cce7
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 66f2471e07ae5827d2edb553b4226784b42278c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostiocompletionmanagergetavailablethreads-method"></a><span data-ttu-id="5a992-102">IHostIoCompletionManager::GetAvailableThreads 方法</span><span class="sxs-lookup"><span data-stu-id="5a992-102">IHostIoCompletionManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="5a992-103">获取由主机，管理，当前不支持请求的线程总数的 I/O 完成线程数。</span><span class="sxs-lookup"><span data-stu-id="5a992-103">Gets the number of I/O completion threads, of the total number of threads managed by the host, that are not currently servicing requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a992-104">语法</span><span class="sxs-lookup"><span data-stu-id="5a992-104">Syntax</span></span>  
  
```  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a992-105">参数</span><span class="sxs-lookup"><span data-stu-id="5a992-105">Parameters</span></span>  
 `pdwAvailableIoCompletionThreads`  
 <span data-ttu-id="5a992-106">[out]为请求提供服务当前可用的 I/O 完成线程管理的主机数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="5a992-106">[out] A pointer to the number of I/O completion threads managed by the host that are currently available to service requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a992-107">返回值</span><span class="sxs-lookup"><span data-stu-id="5a992-107">Return Value</span></span>  
  
|<span data-ttu-id="5a992-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5a992-108">HRESULT</span></span>|<span data-ttu-id="5a992-109">描述</span><span class="sxs-lookup"><span data-stu-id="5a992-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5a992-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5a992-110">S_OK</span></span>|<span data-ttu-id="5a992-111">`GetAvailableThreads`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="5a992-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="5a992-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5a992-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5a992-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="5a992-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5a992-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5a992-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5a992-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="5a992-115">The call timed out.</span></span>|  
|<span data-ttu-id="5a992-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5a992-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5a992-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="5a992-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5a992-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5a992-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5a992-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="5a992-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5a992-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5a992-120">E_FAIL</span></span>|<span data-ttu-id="5a992-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="5a992-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5a992-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="5a992-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5a992-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="5a992-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5a992-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="5a992-124">E_NOTIMPL</span></span>|<span data-ttu-id="5a992-125">主机未提供的实现`GetAvailableThreads`。</span><span class="sxs-lookup"><span data-stu-id="5a992-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a992-126">备注</span><span class="sxs-lookup"><span data-stu-id="5a992-126">Remarks</span></span>  
 <span data-ttu-id="5a992-127">原因例如，实现、 性能或可伸缩性的情况下，宿主可能需要对 I/O 完成线程池的大小的独有控制。</span><span class="sxs-lookup"><span data-stu-id="5a992-127">A host might want exclusive control over the size of the I/O completion thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="5a992-128">因此，主机不需要实现`GetAvailableThreads`。</span><span class="sxs-lookup"><span data-stu-id="5a992-128">Therefore, the host is not required to implement `GetAvailableThreads`.</span></span> <span data-ttu-id="5a992-129">在这种情况下，主机应通过此方法返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="5a992-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a992-130">惠?</span><span class="sxs-lookup"><span data-stu-id="5a992-130">Requirements</span></span>  
 <span data-ttu-id="5a992-131">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5a992-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a992-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5a992-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5a992-133">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5a992-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5a992-134">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a992-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a992-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a992-135">See Also</span></span>  
 [<span data-ttu-id="5a992-136">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="5a992-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="5a992-137">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="5a992-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
