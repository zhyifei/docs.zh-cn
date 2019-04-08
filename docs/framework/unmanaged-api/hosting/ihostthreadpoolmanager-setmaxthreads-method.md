---
title: IHostThreadPoolManager::SetMaxThreads 方法
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::SetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: 77cfd347-95c2-4425-b807-4ecc2a8d4578
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0df8d11bba870dfec880401064ec3f78f5f04e1f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081471"
---
# <a name="ihostthreadpoolmanagersetmaxthreads-method"></a><span data-ttu-id="077e5-102">IHostThreadPoolManager::SetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="077e5-102">IHostThreadPoolManager::SetMaxThreads Method</span></span>
<span data-ttu-id="077e5-103">设置最大主机可以维护在线程池中的线程数。</span><span class="sxs-lookup"><span data-stu-id="077e5-103">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="077e5-104">语法</span><span class="sxs-lookup"><span data-stu-id="077e5-104">Syntax</span></span>  
  
```  
HRESULT SetMaxThreads (  
    [in] DWORD MaxThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="077e5-105">参数</span><span class="sxs-lookup"><span data-stu-id="077e5-105">Parameters</span></span>  
 `MaxThreads`  
 <span data-ttu-id="077e5-106">线程池中辅助线程的最大数目。</span><span class="sxs-lookup"><span data-stu-id="077e5-106">The maximum number of worker threads in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="077e5-107">返回值</span><span class="sxs-lookup"><span data-stu-id="077e5-107">Return Value</span></span>  
  
|<span data-ttu-id="077e5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="077e5-108">HRESULT</span></span>|<span data-ttu-id="077e5-109">描述</span><span class="sxs-lookup"><span data-stu-id="077e5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="077e5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="077e5-110">S_OK</span></span>|`SetMaxThreads` <span data-ttu-id="077e5-111">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="077e5-111">returned successfully.</span></span>|  
|<span data-ttu-id="077e5-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="077e5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="077e5-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="077e5-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="077e5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="077e5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="077e5-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="077e5-115">The call timed out.</span></span>|  
|<span data-ttu-id="077e5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="077e5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="077e5-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="077e5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="077e5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="077e5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="077e5-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="077e5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="077e5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="077e5-120">E_FAIL</span></span>|<span data-ttu-id="077e5-121">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="077e5-121">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="077e5-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="077e5-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="077e5-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="077e5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="077e5-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="077e5-124">E_NOTIMPL</span></span>|<span data-ttu-id="077e5-125">主机未提供的实现`SetMaxThreads`。</span><span class="sxs-lookup"><span data-stu-id="077e5-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="077e5-126">备注</span><span class="sxs-lookup"><span data-stu-id="077e5-126">Remarks</span></span>  
 <span data-ttu-id="077e5-127">主机不需要以允许 CLR 若要配置的线程池大小。</span><span class="sxs-lookup"><span data-stu-id="077e5-127">A host is not required to allow the CLR to configure the size of the thread pool.</span></span> <span data-ttu-id="077e5-128">由于实现、 性能或可伸缩性的原因，某些主机可能需要线程池的独有控制。</span><span class="sxs-lookup"><span data-stu-id="077e5-128">Some hosts might want exclusive control over the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="077e5-129">在这种情况下，主机应返回 E_NOTIMPL HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="077e5-129">In this case, a host should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="077e5-130">要求</span><span class="sxs-lookup"><span data-stu-id="077e5-130">Requirements</span></span>  
 <span data-ttu-id="077e5-131">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="077e5-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="077e5-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="077e5-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="077e5-133">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="077e5-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="077e5-134">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="077e5-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="077e5-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="077e5-135">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="077e5-136">GetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="077e5-136">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="077e5-137">SetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="077e5-137">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="077e5-138">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="077e5-138">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
