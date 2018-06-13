---
title: IHostIoCompletionManager::GetMinThreads 方法
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetMinThreads
helpviewer_keywords:
- GetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetMinThreads method [.NET Framework hosting]
ms.assetid: d7a7f733-677d-481c-b3d5-444fcc502b8e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 353d98feed2ab54cf13af92883348598e822c1d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439086"
---
# <a name="ihostiocompletionmanagergetminthreads-method"></a><span data-ttu-id="8e860-102">IHostIoCompletionManager::GetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="8e860-102">IHostIoCompletionManager::GetMinThreads Method</span></span>
<span data-ttu-id="8e860-103">获取的最小宿主提供用于处理输入/输出请求的线程数。</span><span class="sxs-lookup"><span data-stu-id="8e860-103">Gets the minimum number of threads that the host provides for processing I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e860-104">语法</span><span class="sxs-lookup"><span data-stu-id="8e860-104">Syntax</span></span>  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *pdwMinIOCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8e860-105">参数</span><span class="sxs-lookup"><span data-stu-id="8e860-105">Parameters</span></span>  
 `pdwMinIOCompletionThreads`  
 <span data-ttu-id="8e860-106">[out]指向主机提供处理 I/O 请求的线程的最小数的指针。</span><span class="sxs-lookup"><span data-stu-id="8e860-106">[out] A pointer to the minimum number of threads that the host provides to process I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e860-107">返回值</span><span class="sxs-lookup"><span data-stu-id="8e860-107">Return Value</span></span>  
  
|<span data-ttu-id="8e860-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8e860-108">HRESULT</span></span>|<span data-ttu-id="8e860-109">描述</span><span class="sxs-lookup"><span data-stu-id="8e860-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8e860-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8e860-110">S_OK</span></span>|<span data-ttu-id="8e860-111">`GetMinThreads` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="8e860-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="8e860-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8e860-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8e860-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="8e860-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8e860-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8e860-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8e860-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="8e860-115">The call timed out.</span></span>|  
|<span data-ttu-id="8e860-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8e860-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8e860-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="8e860-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8e860-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8e860-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8e860-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="8e860-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8e860-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8e860-120">E_FAIL</span></span>|<span data-ttu-id="8e860-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="8e860-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8e860-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="8e860-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8e860-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="8e860-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8e860-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="8e860-124">E_NOTIMPL</span></span>|<span data-ttu-id="8e860-125">主机未提供的实现`GetMinThreads`。</span><span class="sxs-lookup"><span data-stu-id="8e860-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e860-126">备注</span><span class="sxs-lookup"><span data-stu-id="8e860-126">Remarks</span></span>  
 <span data-ttu-id="8e860-127">主机可能想对分配给服务 I/O 请求，原因例如，实现、 性能或可伸缩性的线程数的独有控制。</span><span class="sxs-lookup"><span data-stu-id="8e860-127">A host might want exclusive control over the number of threads allotted to service I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="8e860-128">主机不为此，需要实现`GetMinThreads`。</span><span class="sxs-lookup"><span data-stu-id="8e860-128">For this reason, the host is not required to implement `GetMinThreads`.</span></span> <span data-ttu-id="8e860-129">在这种情况下，主机应通过此方法返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="8e860-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e860-130">要求</span><span class="sxs-lookup"><span data-stu-id="8e860-130">Requirements</span></span>  
 <span data-ttu-id="8e860-131">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8e860-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e860-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8e860-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8e860-133">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8e860-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e860-134">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e860-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e860-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e860-135">See Also</span></span>  
 [<span data-ttu-id="8e860-136">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="8e860-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="8e860-137">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="8e860-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
