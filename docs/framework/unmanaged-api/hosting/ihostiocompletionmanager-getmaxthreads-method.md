---
title: IHostIoCompletionManager::GetMaxThreads 方法
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: e7a6cadc-2433-4472-a701-58891abcde45
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8875fb24512ddfea57d5f9249e58de3c12b8c507
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119154"
---
# <a name="ihostiocompletionmanagergetmaxthreads-method"></a><span data-ttu-id="0a0e8-102">IHostIoCompletionManager::GetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="0a0e8-102">IHostIoCompletionManager::GetMaxThreads Method</span></span>
<span data-ttu-id="0a0e8-103">获取为 I/O 请求提供服务的最大主机可以分配的线程数。</span><span class="sxs-lookup"><span data-stu-id="0a0e8-103">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a0e8-104">语法</span><span class="sxs-lookup"><span data-stu-id="0a0e8-104">Syntax</span></span>  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a0e8-105">参数</span><span class="sxs-lookup"><span data-stu-id="0a0e8-105">Parameters</span></span>  
 `pdwMaxIoCompletionThreads`  
 <span data-ttu-id="0a0e8-106">[out]指向最大主机可以将分配给服务输入/输出请求线程池中的线程数的指针。</span><span class="sxs-lookup"><span data-stu-id="0a0e8-106">[out] A pointer to the maximum number of threads in the thread pool that the host can allot to service I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a0e8-107">返回值</span><span class="sxs-lookup"><span data-stu-id="0a0e8-107">Return Value</span></span>  
  
|<span data-ttu-id="0a0e8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0a0e8-108">HRESULT</span></span>|<span data-ttu-id="0a0e8-109">描述</span><span class="sxs-lookup"><span data-stu-id="0a0e8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0a0e8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0a0e8-110">S_OK</span></span>|`GetMaxThreads` <span data-ttu-id="0a0e8-111">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="0a0e8-111">returned successfully.</span></span>|  
|<span data-ttu-id="0a0e8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0a0e8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0a0e8-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="0a0e8-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0a0e8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0a0e8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0a0e8-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="0a0e8-115">The call timed out.</span></span>|  
|<span data-ttu-id="0a0e8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0a0e8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0a0e8-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="0a0e8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0a0e8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0a0e8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0a0e8-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="0a0e8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0a0e8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0a0e8-120">E_FAIL</span></span>|<span data-ttu-id="0a0e8-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="0a0e8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0a0e8-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="0a0e8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0a0e8-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="0a0e8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0a0e8-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="0a0e8-124">E_NOTIMPL</span></span>|<span data-ttu-id="0a0e8-125">主机未提供的实现`GetMaxThreads`。</span><span class="sxs-lookup"><span data-stu-id="0a0e8-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a0e8-126">备注</span><span class="sxs-lookup"><span data-stu-id="0a0e8-126">Remarks</span></span>  
 <span data-ttu-id="0a0e8-127">主机可能要独占控制可以分配给处理 I/O 请求，原因如实现、 性能或可伸缩性的线程数。</span><span class="sxs-lookup"><span data-stu-id="0a0e8-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="0a0e8-128">出于此原因，该主机不需要实现`GetMaxThreads`。</span><span class="sxs-lookup"><span data-stu-id="0a0e8-128">For this reason, the host is not required to implement `GetMaxThreads`.</span></span> <span data-ttu-id="0a0e8-129">在这种情况下，主机应从此方法返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="0a0e8-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a0e8-130">要求</span><span class="sxs-lookup"><span data-stu-id="0a0e8-130">Requirements</span></span>  
 <span data-ttu-id="0a0e8-131">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0a0e8-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a0e8-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0a0e8-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0a0e8-133">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0a0e8-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="0a0e8-134">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="0a0e8-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0a0e8-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a0e8-135">See also</span></span>

- [<span data-ttu-id="0a0e8-136">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="0a0e8-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="0a0e8-137">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="0a0e8-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
