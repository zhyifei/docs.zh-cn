---
title: IHostIoCompletionManager::GetMinThreads 方法
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetMinThreads
helpviewer_keywords:
- GetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetMinThreads method [.NET Framework hosting]
ms.assetid: d7a7f733-677d-481c-b3d5-444fcc502b8e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: faac5adccecdd0aeecede3b4f50a4db554e3d162
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077155"
---
# <a name="ihostiocompletionmanagergetminthreads-method"></a><span data-ttu-id="3da77-102">IHostIoCompletionManager::GetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="3da77-102">IHostIoCompletionManager::GetMinThreads Method</span></span>
<span data-ttu-id="3da77-103">获取主机提供用于处理 I/O 请求的线程的最小数目。</span><span class="sxs-lookup"><span data-stu-id="3da77-103">Gets the minimum number of threads that the host provides for processing I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3da77-104">语法</span><span class="sxs-lookup"><span data-stu-id="3da77-104">Syntax</span></span>  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *pdwMinIOCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3da77-105">参数</span><span class="sxs-lookup"><span data-stu-id="3da77-105">Parameters</span></span>  
 `pdwMinIOCompletionThreads`  
 <span data-ttu-id="3da77-106">[out]指向的最小主机提供处理 I/O 请求的线程数的指针。</span><span class="sxs-lookup"><span data-stu-id="3da77-106">[out] A pointer to the minimum number of threads that the host provides to process I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3da77-107">返回值</span><span class="sxs-lookup"><span data-stu-id="3da77-107">Return Value</span></span>  
  
|<span data-ttu-id="3da77-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3da77-108">HRESULT</span></span>|<span data-ttu-id="3da77-109">描述</span><span class="sxs-lookup"><span data-stu-id="3da77-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3da77-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3da77-110">S_OK</span></span>|`GetMinThreads` <span data-ttu-id="3da77-111">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="3da77-111">returned successfully.</span></span>|  
|<span data-ttu-id="3da77-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3da77-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3da77-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="3da77-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3da77-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3da77-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3da77-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="3da77-115">The call timed out.</span></span>|  
|<span data-ttu-id="3da77-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3da77-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3da77-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="3da77-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3da77-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3da77-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3da77-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="3da77-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3da77-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3da77-120">E_FAIL</span></span>|<span data-ttu-id="3da77-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="3da77-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3da77-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="3da77-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3da77-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="3da77-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3da77-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="3da77-124">E_NOTIMPL</span></span>|<span data-ttu-id="3da77-125">主机未提供的实现`GetMinThreads`。</span><span class="sxs-lookup"><span data-stu-id="3da77-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3da77-126">备注</span><span class="sxs-lookup"><span data-stu-id="3da77-126">Remarks</span></span>  
 <span data-ttu-id="3da77-127">主机可能要独占控制分配给服务 I/O 请求，原因如实现、 性能或可伸缩性的线程数。</span><span class="sxs-lookup"><span data-stu-id="3da77-127">A host might want exclusive control over the number of threads allotted to service I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="3da77-128">出于此原因，该主机不需要实现`GetMinThreads`。</span><span class="sxs-lookup"><span data-stu-id="3da77-128">For this reason, the host is not required to implement `GetMinThreads`.</span></span> <span data-ttu-id="3da77-129">在这种情况下，主机应从此方法返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="3da77-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3da77-130">要求</span><span class="sxs-lookup"><span data-stu-id="3da77-130">Requirements</span></span>  
 <span data-ttu-id="3da77-131">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3da77-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3da77-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3da77-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3da77-133">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3da77-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="3da77-134">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="3da77-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3da77-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="3da77-135">See also</span></span>

- [<span data-ttu-id="3da77-136">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="3da77-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="3da77-137">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="3da77-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
