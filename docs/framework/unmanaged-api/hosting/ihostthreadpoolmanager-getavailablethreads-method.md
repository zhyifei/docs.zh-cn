---
title: IHostThreadPoolManager::GetAvailableThreads 方法
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: 61d26dfd-7f24-4e7d-a63e-b30a463f08e1
topic_type:
- apiref
ms.openlocfilehash: 21449d9365e6260267d3c79f384f6136ce894821
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122094"
---
# <a name="ihostthreadpoolmanagergetavailablethreads-method"></a><span data-ttu-id="726e5-102">IHostThreadPoolManager::GetAvailableThreads 方法</span><span class="sxs-lookup"><span data-stu-id="726e5-102">IHostThreadPoolManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="726e5-103">获取线程池中当前未处理工作项的线程的数目。</span><span class="sxs-lookup"><span data-stu-id="726e5-103">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="726e5-104">语法</span><span class="sxs-lookup"><span data-stu-id="726e5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="726e5-105">参数</span><span class="sxs-lookup"><span data-stu-id="726e5-105">Parameters</span></span>  
 `pdwAvailableWorkerThreads`  
 <span data-ttu-id="726e5-106">弄一个指针，指向线程池中当前未处理工作项的线程数。</span><span class="sxs-lookup"><span data-stu-id="726e5-106">[out] Pointer to the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="726e5-107">返回值</span><span class="sxs-lookup"><span data-stu-id="726e5-107">Return Value</span></span>  
  
|<span data-ttu-id="726e5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="726e5-108">HRESULT</span></span>|<span data-ttu-id="726e5-109">描述</span><span class="sxs-lookup"><span data-stu-id="726e5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="726e5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="726e5-110">S_OK</span></span>|<span data-ttu-id="726e5-111">`GetAvailableThreads` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="726e5-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="726e5-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="726e5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="726e5-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="726e5-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="726e5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="726e5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="726e5-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="726e5-115">The call timed out.</span></span>|  
|<span data-ttu-id="726e5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="726e5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="726e5-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="726e5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="726e5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="726e5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="726e5-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="726e5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="726e5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="726e5-120">E_FAIL</span></span>|<span data-ttu-id="726e5-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="726e5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="726e5-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="726e5-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="726e5-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="726e5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="726e5-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="726e5-124">E_NOTIMPL</span></span>|<span data-ttu-id="726e5-125">宿主不提供 `GetAvailableThreads`的实现。</span><span class="sxs-lookup"><span data-stu-id="726e5-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="726e5-126">备注</span><span class="sxs-lookup"><span data-stu-id="726e5-126">Remarks</span></span>  
 <span data-ttu-id="726e5-127">如果主机未提供 `GetAvailableThreads`的实现，它应返回 E_NOTIMPL 的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="726e5-127">If the host does not provide an implementation of `GetAvailableThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="726e5-128">要求</span><span class="sxs-lookup"><span data-stu-id="726e5-128">Requirements</span></span>  
 <span data-ttu-id="726e5-129">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="726e5-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="726e5-130">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="726e5-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="726e5-131">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="726e5-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="726e5-132">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="726e5-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="726e5-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="726e5-133">See also</span></span>

- <xref:System.Threading.ThreadPool.GetAvailableThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="726e5-134">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="726e5-134">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
