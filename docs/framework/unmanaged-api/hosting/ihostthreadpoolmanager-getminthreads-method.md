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
ms.openlocfilehash: 8010ac602c82c7da2af9d0678227a6ce1c91391a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521460"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="ae0fe-102">IHostThreadPoolManager::GetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="ae0fe-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="ae0fe-103">获取预期的请求在线程池中的最小主机维护的空闲线程数。</span><span class="sxs-lookup"><span data-stu-id="ae0fe-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae0fe-104">语法</span><span class="sxs-lookup"><span data-stu-id="ae0fe-104">Syntax</span></span>  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae0fe-105">参数</span><span class="sxs-lookup"><span data-stu-id="ae0fe-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="ae0fe-106">[out]指向的最小的主机目前维护空闲工作线程数的指针。</span><span class="sxs-lookup"><span data-stu-id="ae0fe-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae0fe-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ae0fe-107">Return Value</span></span>  
  
|<span data-ttu-id="ae0fe-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ae0fe-108">HRESULT</span></span>|<span data-ttu-id="ae0fe-109">描述</span><span class="sxs-lookup"><span data-stu-id="ae0fe-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ae0fe-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ae0fe-110">S_OK</span></span>|<span data-ttu-id="ae0fe-111">`GetMinThreads` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="ae0fe-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="ae0fe-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ae0fe-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ae0fe-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="ae0fe-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ae0fe-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ae0fe-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ae0fe-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="ae0fe-115">The call timed out.</span></span>|  
|<span data-ttu-id="ae0fe-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ae0fe-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ae0fe-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="ae0fe-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ae0fe-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ae0fe-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ae0fe-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="ae0fe-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ae0fe-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ae0fe-120">E_FAIL</span></span>|<span data-ttu-id="ae0fe-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="ae0fe-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ae0fe-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="ae0fe-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ae0fe-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="ae0fe-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ae0fe-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="ae0fe-124">E_NOTIMPL</span></span>|<span data-ttu-id="ae0fe-125">主机未提供的实现`GetMinThreads`。</span><span class="sxs-lookup"><span data-stu-id="ae0fe-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae0fe-126">备注</span><span class="sxs-lookup"><span data-stu-id="ae0fe-126">Remarks</span></span>  
 <span data-ttu-id="ae0fe-127">主机不需要提供的实现`GetMinThreads`。</span><span class="sxs-lookup"><span data-stu-id="ae0fe-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="ae0fe-128">在这种情况下，它应返回 E_NOTIMPL HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="ae0fe-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae0fe-129">要求</span><span class="sxs-lookup"><span data-stu-id="ae0fe-129">Requirements</span></span>  
 <span data-ttu-id="ae0fe-130">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ae0fe-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae0fe-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ae0fe-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ae0fe-132">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ae0fe-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ae0fe-133">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae0fe-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae0fe-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae0fe-134">See also</span></span>
- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="ae0fe-135">GetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="ae0fe-135">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="ae0fe-136">SetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="ae0fe-136">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="ae0fe-137">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="ae0fe-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
