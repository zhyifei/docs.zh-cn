---
title: IHostIoCompletionManager::GetAvailableThreads 方法
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: bab363d1-b859-47a4-9884-5661c611cce7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1e96a12bbf9c4fdc8a0bc79661070eb7fec1a593
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973077"
---
# <a name="ihostiocompletionmanagergetavailablethreads-method"></a><span data-ttu-id="9d53e-102">IHostIoCompletionManager::GetAvailableThreads 方法</span><span class="sxs-lookup"><span data-stu-id="9d53e-102">IHostIoCompletionManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="9d53e-103">获取由主机管理，当前不处理请求的线程总数的 I/O 完成线程数。</span><span class="sxs-lookup"><span data-stu-id="9d53e-103">Gets the number of I/O completion threads, of the total number of threads managed by the host, that are not currently servicing requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d53e-104">语法</span><span class="sxs-lookup"><span data-stu-id="9d53e-104">Syntax</span></span>  
  
```  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d53e-105">参数</span><span class="sxs-lookup"><span data-stu-id="9d53e-105">Parameters</span></span>  
 `pdwAvailableIoCompletionThreads`  
 <span data-ttu-id="9d53e-106">[out]为请求提供服务当前可用的 I/O 完成线程管理的主机数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="9d53e-106">[out] A pointer to the number of I/O completion threads managed by the host that are currently available to service requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9d53e-107">返回值</span><span class="sxs-lookup"><span data-stu-id="9d53e-107">Return Value</span></span>  
  
|<span data-ttu-id="9d53e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9d53e-108">HRESULT</span></span>|<span data-ttu-id="9d53e-109">描述</span><span class="sxs-lookup"><span data-stu-id="9d53e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9d53e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9d53e-110">S_OK</span></span>|<span data-ttu-id="9d53e-111">`GetAvailableThreads` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="9d53e-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="9d53e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9d53e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9d53e-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="9d53e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9d53e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9d53e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9d53e-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="9d53e-115">The call timed out.</span></span>|  
|<span data-ttu-id="9d53e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9d53e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9d53e-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="9d53e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9d53e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9d53e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9d53e-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="9d53e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9d53e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9d53e-120">E_FAIL</span></span>|<span data-ttu-id="9d53e-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="9d53e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9d53e-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="9d53e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9d53e-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="9d53e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9d53e-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="9d53e-124">E_NOTIMPL</span></span>|<span data-ttu-id="9d53e-125">主机未提供的实现`GetAvailableThreads`。</span><span class="sxs-lookup"><span data-stu-id="9d53e-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d53e-126">备注</span><span class="sxs-lookup"><span data-stu-id="9d53e-126">Remarks</span></span>  
 <span data-ttu-id="9d53e-127">由于实现、 性能或可伸缩性的原因，主机可能需要的 I/O 完成线程池大小的独有控制。</span><span class="sxs-lookup"><span data-stu-id="9d53e-127">A host might want exclusive control over the size of the I/O completion thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="9d53e-128">因此，该主机不需要实现`GetAvailableThreads`。</span><span class="sxs-lookup"><span data-stu-id="9d53e-128">Therefore, the host is not required to implement `GetAvailableThreads`.</span></span> <span data-ttu-id="9d53e-129">在这种情况下，主机应从此方法返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="9d53e-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d53e-130">要求</span><span class="sxs-lookup"><span data-stu-id="9d53e-130">Requirements</span></span>  
 <span data-ttu-id="9d53e-131">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9d53e-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d53e-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9d53e-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9d53e-133">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9d53e-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9d53e-134">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d53e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d53e-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d53e-135">See also</span></span>

- [<span data-ttu-id="9d53e-136">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="9d53e-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="9d53e-137">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="9d53e-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
