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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c79f18c1deec4183a5a736c5acf88e9a1fd8021
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749091"
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a><span data-ttu-id="f0dec-102">IHostThreadPoolManager::SetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="f0dec-102">IHostThreadPoolManager::SetMinThreads Method</span></span>
<span data-ttu-id="f0dec-103">设置预期的请求的最小的主机必须维护的空闲线程数。</span><span class="sxs-lookup"><span data-stu-id="f0dec-103">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0dec-104">语法</span><span class="sxs-lookup"><span data-stu-id="f0dec-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0dec-105">参数</span><span class="sxs-lookup"><span data-stu-id="f0dec-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="f0dec-106">[in]主机必须维护的线程的新的最小数目。</span><span class="sxs-lookup"><span data-stu-id="f0dec-106">[in] The new minimum number of threads that the host must maintain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0dec-107">返回值</span><span class="sxs-lookup"><span data-stu-id="f0dec-107">Return Value</span></span>  
  
|<span data-ttu-id="f0dec-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f0dec-108">HRESULT</span></span>|<span data-ttu-id="f0dec-109">描述</span><span class="sxs-lookup"><span data-stu-id="f0dec-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f0dec-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f0dec-110">S_OK</span></span>|<span data-ttu-id="f0dec-111">`SetMinThreads` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="f0dec-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="f0dec-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f0dec-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f0dec-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="f0dec-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f0dec-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f0dec-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f0dec-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="f0dec-115">The call timed out.</span></span>|  
|<span data-ttu-id="f0dec-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f0dec-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f0dec-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="f0dec-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f0dec-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f0dec-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f0dec-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="f0dec-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f0dec-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f0dec-120">E_FAIL</span></span>|<span data-ttu-id="f0dec-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="f0dec-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f0dec-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="f0dec-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f0dec-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="f0dec-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f0dec-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="f0dec-124">E_NOTIMPL</span></span>|<span data-ttu-id="f0dec-125">主机未提供的实现`SetMinThreads`。</span><span class="sxs-lookup"><span data-stu-id="f0dec-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0dec-126">备注</span><span class="sxs-lookup"><span data-stu-id="f0dec-126">Remarks</span></span>  
 <span data-ttu-id="f0dec-127">主机不需要提供的实现`SetMinThreads`。</span><span class="sxs-lookup"><span data-stu-id="f0dec-127">A host is not required to provide an implementation of `SetMinThreads`.</span></span> <span data-ttu-id="f0dec-128">在这种情况下，它应返回 E_NOTIMPL HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="f0dec-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0dec-129">要求</span><span class="sxs-lookup"><span data-stu-id="f0dec-129">Requirements</span></span>  
 <span data-ttu-id="f0dec-130">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f0dec-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0dec-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f0dec-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f0dec-132">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f0dec-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0dec-133">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0dec-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0dec-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0dec-134">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="f0dec-135">GetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="f0dec-135">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="f0dec-136">SetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="f0dec-136">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="f0dec-137">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="f0dec-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
