---
title: IHostIoCompletionManager::SetMinThreads 方法
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: dea34b81-8d2b-4cc3-8696-0ad4291d8a92
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d127aa1cfa8784f51fcff4eaa774361a2cbbdbc9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503016"
---
# <a name="ihostiocompletionmanagersetminthreads-method"></a><span data-ttu-id="1749c-102">IHostIoCompletionManager::SetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="1749c-102">IHostIoCompletionManager::SetMinThreads Method</span></span>
<span data-ttu-id="1749c-103">将最小主机应分配的线程数设置为 I/O 完成。</span><span class="sxs-lookup"><span data-stu-id="1749c-103">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1749c-104">语法</span><span class="sxs-lookup"><span data-stu-id="1749c-104">Syntax</span></span>  
  
```  
HRESULT SetMinThreads (  
    [in] DWORD dwMinIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1749c-105">参数</span><span class="sxs-lookup"><span data-stu-id="1749c-105">Parameters</span></span>  
 `dwMinIoCompletionThreads`  
 <span data-ttu-id="1749c-106">[in]最小主机应创建的 I/O 完成线程数。</span><span class="sxs-lookup"><span data-stu-id="1749c-106">[in] The minimum number of I/O completion threads that the host should create.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1749c-107">返回值</span><span class="sxs-lookup"><span data-stu-id="1749c-107">Return Value</span></span>  
  
|<span data-ttu-id="1749c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1749c-108">HRESULT</span></span>|<span data-ttu-id="1749c-109">描述</span><span class="sxs-lookup"><span data-stu-id="1749c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1749c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1749c-110">S_OK</span></span>|<span data-ttu-id="1749c-111">`SetMinThreads` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="1749c-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="1749c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1749c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1749c-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="1749c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1749c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1749c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1749c-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="1749c-115">The call timed out.</span></span>|  
|<span data-ttu-id="1749c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1749c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1749c-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="1749c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1749c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1749c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1749c-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="1749c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1749c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1749c-120">E_FAIL</span></span>|<span data-ttu-id="1749c-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="1749c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1749c-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="1749c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1749c-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="1749c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1749c-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="1749c-124">E_NOTIMPL</span></span>|<span data-ttu-id="1749c-125">主机未提供的实现`SetMinThreads`。</span><span class="sxs-lookup"><span data-stu-id="1749c-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1749c-126">备注</span><span class="sxs-lookup"><span data-stu-id="1749c-126">Remarks</span></span>  
 <span data-ttu-id="1749c-127">主机可能要独占控制可以分配给处理 I/O 请求，原因如实现、 性能或可伸缩性的线程数。</span><span class="sxs-lookup"><span data-stu-id="1749c-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="1749c-128">出于此原因，该主机不需要实现`SetMinThreads`。</span><span class="sxs-lookup"><span data-stu-id="1749c-128">For this reason, the host is not required to implement `SetMinThreads`.</span></span> <span data-ttu-id="1749c-129">在这种情况下，主机应从此方法返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="1749c-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1749c-130">要求</span><span class="sxs-lookup"><span data-stu-id="1749c-130">Requirements</span></span>  
 <span data-ttu-id="1749c-131">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1749c-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1749c-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1749c-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1749c-133">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1749c-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1749c-134">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1749c-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1749c-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="1749c-135">See also</span></span>
- [<span data-ttu-id="1749c-136">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="1749c-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="1749c-137">SetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="1749c-137">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)
- [<span data-ttu-id="1749c-138">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="1749c-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
