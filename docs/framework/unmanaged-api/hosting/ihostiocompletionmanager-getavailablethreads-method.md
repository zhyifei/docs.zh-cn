---
title: IHostIoCompletionManager::GetAvailableThreads 方法
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: bab363d1-b859-47a4-9884-5661c611cce7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb5de5b46a46d5caa74b83f16d943edc39d08b01
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="ihostiocompletionmanagergetavailablethreads-method"></a><span data-ttu-id="fccb4-102">IHostIoCompletionManager::GetAvailableThreads 方法</span><span class="sxs-lookup"><span data-stu-id="fccb4-102">IHostIoCompletionManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="fccb4-103">获取由主机，管理，当前不支持请求的线程总数的 I/O 完成线程数。</span><span class="sxs-lookup"><span data-stu-id="fccb4-103">Gets the number of I/O completion threads, of the total number of threads managed by the host, that are not currently servicing requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fccb4-104">语法</span><span class="sxs-lookup"><span data-stu-id="fccb4-104">Syntax</span></span>  
  
```  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fccb4-105">参数</span><span class="sxs-lookup"><span data-stu-id="fccb4-105">Parameters</span></span>  
 `pdwAvailableIoCompletionThreads`  
 <span data-ttu-id="fccb4-106">[out]为请求提供服务当前可用的 I/O 完成线程管理的主机数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="fccb4-106">[out] A pointer to the number of I/O completion threads managed by the host that are currently available to service requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fccb4-107">返回值</span><span class="sxs-lookup"><span data-stu-id="fccb4-107">Return Value</span></span>  
  
|<span data-ttu-id="fccb4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fccb4-108">HRESULT</span></span>|<span data-ttu-id="fccb4-109">描述</span><span class="sxs-lookup"><span data-stu-id="fccb4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fccb4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fccb4-110">S_OK</span></span>|<span data-ttu-id="fccb4-111">`GetAvailableThreads` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="fccb4-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="fccb4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fccb4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fccb4-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="fccb4-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fccb4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fccb4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fccb4-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="fccb4-115">The call timed out.</span></span>|  
|<span data-ttu-id="fccb4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fccb4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fccb4-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="fccb4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fccb4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fccb4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fccb4-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="fccb4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fccb4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fccb4-120">E_FAIL</span></span>|<span data-ttu-id="fccb4-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="fccb4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fccb4-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="fccb4-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fccb4-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="fccb4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fccb4-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="fccb4-124">E_NOTIMPL</span></span>|<span data-ttu-id="fccb4-125">主机未提供的实现`GetAvailableThreads`。</span><span class="sxs-lookup"><span data-stu-id="fccb4-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fccb4-126">备注</span><span class="sxs-lookup"><span data-stu-id="fccb4-126">Remarks</span></span>  
 <span data-ttu-id="fccb4-127">原因例如，实现、 性能或可伸缩性的情况下，宿主可能需要对 I/O 完成线程池的大小的独有控制。</span><span class="sxs-lookup"><span data-stu-id="fccb4-127">A host might want exclusive control over the size of the I/O completion thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="fccb4-128">因此，主机不需要实现`GetAvailableThreads`。</span><span class="sxs-lookup"><span data-stu-id="fccb4-128">Therefore, the host is not required to implement `GetAvailableThreads`.</span></span> <span data-ttu-id="fccb4-129">在这种情况下，主机应通过此方法返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="fccb4-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fccb4-130">要求</span><span class="sxs-lookup"><span data-stu-id="fccb4-130">Requirements</span></span>  
 <span data-ttu-id="fccb4-131">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fccb4-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fccb4-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fccb4-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fccb4-133">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="fccb4-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fccb4-134">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fccb4-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fccb4-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="fccb4-135">See Also</span></span>  
 [<span data-ttu-id="fccb4-136">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="fccb4-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="fccb4-137">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="fccb4-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
