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
ms.openlocfilehash: a05cfb43b5b4a328d22c4df04049a7fa156ca080
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841927"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="fa96a-102">IHostThreadPoolManager::GetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="fa96a-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="fa96a-103">获取主机在线程池中维持的请求的最小空闲线程数。</span><span class="sxs-lookup"><span data-stu-id="fa96a-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa96a-104">语法</span><span class="sxs-lookup"><span data-stu-id="fa96a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa96a-105">参数</span><span class="sxs-lookup"><span data-stu-id="fa96a-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="fa96a-106">弄一个指针，它指向主机当前维护的空闲工作线程的最小数目。</span><span class="sxs-lookup"><span data-stu-id="fa96a-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa96a-107">返回值</span><span class="sxs-lookup"><span data-stu-id="fa96a-107">Return Value</span></span>  
  
|<span data-ttu-id="fa96a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fa96a-108">HRESULT</span></span>|<span data-ttu-id="fa96a-109">说明</span><span class="sxs-lookup"><span data-stu-id="fa96a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fa96a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fa96a-110">S_OK</span></span>|<span data-ttu-id="fa96a-111">`GetMinThreads`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="fa96a-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="fa96a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fa96a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fa96a-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="fa96a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fa96a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fa96a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fa96a-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="fa96a-115">The call timed out.</span></span>|  
|<span data-ttu-id="fa96a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fa96a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fa96a-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="fa96a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fa96a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fa96a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fa96a-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="fa96a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fa96a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fa96a-120">E_FAIL</span></span>|<span data-ttu-id="fa96a-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="fa96a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fa96a-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="fa96a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fa96a-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="fa96a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fa96a-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="fa96a-124">E_NOTIMPL</span></span>|<span data-ttu-id="fa96a-125">宿主不提供的实现 `GetMinThreads` 。</span><span class="sxs-lookup"><span data-stu-id="fa96a-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa96a-126">备注</span><span class="sxs-lookup"><span data-stu-id="fa96a-126">Remarks</span></span>  
 <span data-ttu-id="fa96a-127">宿主无需提供的实现 `GetMinThreads` 。</span><span class="sxs-lookup"><span data-stu-id="fa96a-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="fa96a-128">在这种情况下，它应返回 E_NOTIMPL 的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="fa96a-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa96a-129">要求</span><span class="sxs-lookup"><span data-stu-id="fa96a-129">Requirements</span></span>  
 <span data-ttu-id="fa96a-130">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fa96a-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa96a-131">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fa96a-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fa96a-132">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="fa96a-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa96a-133">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa96a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa96a-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa96a-134">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="fa96a-135">GetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="fa96a-135">GetMaxThreads Method</span></span>](ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="fa96a-136">SetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="fa96a-136">SetMinThreads Method</span></span>](ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="fa96a-137">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="fa96a-137">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
