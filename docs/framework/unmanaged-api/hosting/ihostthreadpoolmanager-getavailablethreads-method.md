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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b4f16db1d35f8a0de1c755566e27b07bf9067dfe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129189"
---
# <a name="ihostthreadpoolmanagergetavailablethreads-method"></a><span data-ttu-id="0b15a-102">IHostThreadPoolManager::GetAvailableThreads 方法</span><span class="sxs-lookup"><span data-stu-id="0b15a-102">IHostThreadPoolManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="0b15a-103">获取当前不在处理工作项在线程池中的线程数。</span><span class="sxs-lookup"><span data-stu-id="0b15a-103">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b15a-104">语法</span><span class="sxs-lookup"><span data-stu-id="0b15a-104">Syntax</span></span>  
  
```  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b15a-105">参数</span><span class="sxs-lookup"><span data-stu-id="0b15a-105">Parameters</span></span>  
 `pdwAvailableWorkerThreads`  
 <span data-ttu-id="0b15a-106">[out]指向当前不在处理工作项在线程池中的线程数。</span><span class="sxs-lookup"><span data-stu-id="0b15a-106">[out] Pointer to the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b15a-107">返回值</span><span class="sxs-lookup"><span data-stu-id="0b15a-107">Return Value</span></span>  
  
|<span data-ttu-id="0b15a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0b15a-108">HRESULT</span></span>|<span data-ttu-id="0b15a-109">描述</span><span class="sxs-lookup"><span data-stu-id="0b15a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0b15a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0b15a-110">S_OK</span></span>|`GetAvailableThreads` <span data-ttu-id="0b15a-111">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="0b15a-111">returned successfully.</span></span>|  
|<span data-ttu-id="0b15a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0b15a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0b15a-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="0b15a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0b15a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0b15a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0b15a-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="0b15a-115">The call timed out.</span></span>|  
|<span data-ttu-id="0b15a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0b15a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0b15a-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="0b15a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0b15a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0b15a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0b15a-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="0b15a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0b15a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0b15a-120">E_FAIL</span></span>|<span data-ttu-id="0b15a-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="0b15a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0b15a-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="0b15a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0b15a-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="0b15a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0b15a-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="0b15a-124">E_NOTIMPL</span></span>|<span data-ttu-id="0b15a-125">主机未提供的实现`GetAvailableThreads`。</span><span class="sxs-lookup"><span data-stu-id="0b15a-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b15a-126">备注</span><span class="sxs-lookup"><span data-stu-id="0b15a-126">Remarks</span></span>  
 <span data-ttu-id="0b15a-127">如果主机未提供的实现`GetAvailableThreads`，它应返回 E_NOTIMPL HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="0b15a-127">If the host does not provide an implementation of `GetAvailableThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b15a-128">要求</span><span class="sxs-lookup"><span data-stu-id="0b15a-128">Requirements</span></span>  
 <span data-ttu-id="0b15a-129">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0b15a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b15a-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0b15a-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0b15a-131">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0b15a-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="0b15a-132">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="0b15a-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0b15a-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b15a-133">See also</span></span>

- <xref:System.Threading.ThreadPool.GetAvailableThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="0b15a-134">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="0b15a-134">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
