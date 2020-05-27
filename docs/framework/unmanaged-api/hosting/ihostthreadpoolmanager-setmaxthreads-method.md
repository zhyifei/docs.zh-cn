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
ms.openlocfilehash: 53d42afda6668acc6462c419fcefd6bc1435a34c
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842447"
---
# <a name="ihostthreadpoolmanagersetmaxthreads-method"></a><span data-ttu-id="0bf16-102">IHostThreadPoolManager::SetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="0bf16-102">IHostThreadPoolManager::SetMaxThreads Method</span></span>
<span data-ttu-id="0bf16-103">设置宿主可在线程池中维护的最大线程数。</span><span class="sxs-lookup"><span data-stu-id="0bf16-103">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bf16-104">语法</span><span class="sxs-lookup"><span data-stu-id="0bf16-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMaxThreads (  
    [in] DWORD MaxThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0bf16-105">参数</span><span class="sxs-lookup"><span data-stu-id="0bf16-105">Parameters</span></span>  
 `MaxThreads`  
 <span data-ttu-id="0bf16-106">线程池中辅助线程的最大数目。</span><span class="sxs-lookup"><span data-stu-id="0bf16-106">The maximum number of worker threads in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0bf16-107">返回值</span><span class="sxs-lookup"><span data-stu-id="0bf16-107">Return Value</span></span>  
  
|<span data-ttu-id="0bf16-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0bf16-108">HRESULT</span></span>|<span data-ttu-id="0bf16-109">说明</span><span class="sxs-lookup"><span data-stu-id="0bf16-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0bf16-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0bf16-110">S_OK</span></span>|<span data-ttu-id="0bf16-111">`SetMaxThreads`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="0bf16-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="0bf16-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0bf16-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0bf16-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="0bf16-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0bf16-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0bf16-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0bf16-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="0bf16-115">The call timed out.</span></span>|  
|<span data-ttu-id="0bf16-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0bf16-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0bf16-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="0bf16-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0bf16-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0bf16-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0bf16-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="0bf16-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0bf16-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0bf16-120">E_FAIL</span></span>|<span data-ttu-id="0bf16-121">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="0bf16-121">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="0bf16-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="0bf16-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0bf16-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="0bf16-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0bf16-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="0bf16-124">E_NOTIMPL</span></span>|<span data-ttu-id="0bf16-125">宿主不提供的实现 `SetMaxThreads` 。</span><span class="sxs-lookup"><span data-stu-id="0bf16-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0bf16-126">备注</span><span class="sxs-lookup"><span data-stu-id="0bf16-126">Remarks</span></span>  
 <span data-ttu-id="0bf16-127">宿主无需允许 CLR 配置线程池的大小。</span><span class="sxs-lookup"><span data-stu-id="0bf16-127">A host is not required to allow the CLR to configure the size of the thread pool.</span></span> <span data-ttu-id="0bf16-128">出于实现、性能或可伸缩性等原因，某些主机可能需要对线程池进行独占控制。</span><span class="sxs-lookup"><span data-stu-id="0bf16-128">Some hosts might want exclusive control over the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="0bf16-129">在这种情况下，主机应返回 E_NOTIMPL 的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="0bf16-129">In this case, a host should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bf16-130">要求</span><span class="sxs-lookup"><span data-stu-id="0bf16-130">Requirements</span></span>  
 <span data-ttu-id="0bf16-131">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0bf16-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bf16-132">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0bf16-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0bf16-133">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="0bf16-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0bf16-134">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bf16-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bf16-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0bf16-135">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="0bf16-136">GetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="0bf16-136">GetMaxThreads Method</span></span>](ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="0bf16-137">SetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="0bf16-137">SetMinThreads Method</span></span>](ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="0bf16-138">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="0bf16-138">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
