---
title: IHostThreadPoolManager::SetMinThreads 方法
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.SetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: 10409db9-9fd2-4e4d-b8cd-cf6fec0afaa2
topic_type:
- apiref
ms.openlocfilehash: f2d2665382559596563d9b155d2afa4d99c91ee7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141256"
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a><span data-ttu-id="d4505-102">IHostThreadPoolManager::SetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="d4505-102">IHostThreadPoolManager::SetMinThreads Method</span></span>
<span data-ttu-id="d4505-103">设置主机在预期请求中必须保持的空闲线程的最小数目。</span><span class="sxs-lookup"><span data-stu-id="d4505-103">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4505-104">语法</span><span class="sxs-lookup"><span data-stu-id="d4505-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4505-105">参数</span><span class="sxs-lookup"><span data-stu-id="d4505-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="d4505-106">中宿主必须维持的新最小线程数。</span><span class="sxs-lookup"><span data-stu-id="d4505-106">[in] The new minimum number of threads that the host must maintain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4505-107">返回值</span><span class="sxs-lookup"><span data-stu-id="d4505-107">Return Value</span></span>  
  
|<span data-ttu-id="d4505-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d4505-108">HRESULT</span></span>|<span data-ttu-id="d4505-109">描述</span><span class="sxs-lookup"><span data-stu-id="d4505-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d4505-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d4505-110">S_OK</span></span>|<span data-ttu-id="d4505-111">`SetMinThreads` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="d4505-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="d4505-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d4505-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d4505-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="d4505-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d4505-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d4505-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d4505-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="d4505-115">The call timed out.</span></span>|  
|<span data-ttu-id="d4505-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d4505-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d4505-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="d4505-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d4505-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d4505-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d4505-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="d4505-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d4505-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d4505-120">E_FAIL</span></span>|<span data-ttu-id="d4505-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="d4505-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d4505-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="d4505-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d4505-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="d4505-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d4505-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="d4505-124">E_NOTIMPL</span></span>|<span data-ttu-id="d4505-125">宿主不提供 `SetMinThreads`的实现。</span><span class="sxs-lookup"><span data-stu-id="d4505-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4505-126">备注</span><span class="sxs-lookup"><span data-stu-id="d4505-126">Remarks</span></span>  
 <span data-ttu-id="d4505-127">主机不需要提供 `SetMinThreads`的实现。</span><span class="sxs-lookup"><span data-stu-id="d4505-127">A host is not required to provide an implementation of `SetMinThreads`.</span></span> <span data-ttu-id="d4505-128">在这种情况下，它应返回 E_NOTIMPL 的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="d4505-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4505-129">要求</span><span class="sxs-lookup"><span data-stu-id="d4505-129">Requirements</span></span>  
 <span data-ttu-id="d4505-130">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d4505-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4505-131">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d4505-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d4505-132">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="d4505-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d4505-133">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4505-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4505-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4505-134">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="d4505-135">GetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="d4505-135">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="d4505-136">SetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="d4505-136">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="d4505-137">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="d4505-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
