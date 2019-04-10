---
title: IHostThreadPoolManager::GetMinThreads 方法
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMinThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMinThreads method [.NET Framework hosting]
- GetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: dc07232b-b2e4-4dab-87e2-3c955974ab48
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1230a72d06677b4d36d10a8a31d63638c1fcd41
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170685"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="2c2ed-102">IHostThreadPoolManager::GetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="2c2ed-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="2c2ed-103">获取预期的请求在线程池中的最小主机维护的空闲线程数。</span><span class="sxs-lookup"><span data-stu-id="2c2ed-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c2ed-104">语法</span><span class="sxs-lookup"><span data-stu-id="2c2ed-104">Syntax</span></span>  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c2ed-105">参数</span><span class="sxs-lookup"><span data-stu-id="2c2ed-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="2c2ed-106">[out]指向的最小的主机目前维护空闲工作线程数的指针。</span><span class="sxs-lookup"><span data-stu-id="2c2ed-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c2ed-107">返回值</span><span class="sxs-lookup"><span data-stu-id="2c2ed-107">Return Value</span></span>  
  
|<span data-ttu-id="2c2ed-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2c2ed-108">HRESULT</span></span>|<span data-ttu-id="2c2ed-109">描述</span><span class="sxs-lookup"><span data-stu-id="2c2ed-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2c2ed-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2c2ed-110">S_OK</span></span>|`GetMinThreads` <span data-ttu-id="2c2ed-111">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="2c2ed-111">returned successfully.</span></span>|  
|<span data-ttu-id="2c2ed-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2c2ed-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2c2ed-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="2c2ed-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2c2ed-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2c2ed-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2c2ed-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="2c2ed-115">The call timed out.</span></span>|  
|<span data-ttu-id="2c2ed-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2c2ed-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2c2ed-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="2c2ed-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2c2ed-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2c2ed-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2c2ed-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="2c2ed-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2c2ed-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2c2ed-120">E_FAIL</span></span>|<span data-ttu-id="2c2ed-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="2c2ed-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2c2ed-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="2c2ed-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2c2ed-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="2c2ed-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2c2ed-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="2c2ed-124">E_NOTIMPL</span></span>|<span data-ttu-id="2c2ed-125">主机未提供的实现`GetMinThreads`。</span><span class="sxs-lookup"><span data-stu-id="2c2ed-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c2ed-126">备注</span><span class="sxs-lookup"><span data-stu-id="2c2ed-126">Remarks</span></span>  
 <span data-ttu-id="2c2ed-127">主机不需要提供的实现`GetMinThreads`。</span><span class="sxs-lookup"><span data-stu-id="2c2ed-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="2c2ed-128">在这种情况下，它应返回 E_NOTIMPL HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="2c2ed-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c2ed-129">要求</span><span class="sxs-lookup"><span data-stu-id="2c2ed-129">Requirements</span></span>  
 <span data-ttu-id="2c2ed-130">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2c2ed-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c2ed-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2c2ed-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2c2ed-132">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2c2ed-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="2c2ed-133">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="2c2ed-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2c2ed-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c2ed-134">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="2c2ed-135">GetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="2c2ed-135">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="2c2ed-136">SetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="2c2ed-136">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="2c2ed-137">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="2c2ed-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
