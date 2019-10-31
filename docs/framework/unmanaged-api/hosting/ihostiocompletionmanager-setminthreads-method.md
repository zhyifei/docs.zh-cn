---
title: IHostIoCompletionManager::SetMinThreads 方法
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: dea34b81-8d2b-4cc3-8696-0ad4291d8a92
topic_type:
- apiref
ms.openlocfilehash: 8b1fc936b601d327ce6306f22dbec2c1078718da
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133738"
---
# <a name="ihostiocompletionmanagersetminthreads-method"></a><span data-ttu-id="b4f65-102">IHostIoCompletionManager::SetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="b4f65-102">IHostIoCompletionManager::SetMinThreads Method</span></span>
<span data-ttu-id="b4f65-103">设置主机应为 i/o 完成分配的最小线程数。</span><span class="sxs-lookup"><span data-stu-id="b4f65-103">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4f65-104">语法</span><span class="sxs-lookup"><span data-stu-id="b4f65-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD dwMinIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4f65-105">参数</span><span class="sxs-lookup"><span data-stu-id="b4f65-105">Parameters</span></span>  
 `dwMinIoCompletionThreads`  
 <span data-ttu-id="b4f65-106">中宿主应创建的 i/o 完成线程的最小数目。</span><span class="sxs-lookup"><span data-stu-id="b4f65-106">[in] The minimum number of I/O completion threads that the host should create.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4f65-107">返回值</span><span class="sxs-lookup"><span data-stu-id="b4f65-107">Return Value</span></span>  
  
|<span data-ttu-id="b4f65-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b4f65-108">HRESULT</span></span>|<span data-ttu-id="b4f65-109">描述</span><span class="sxs-lookup"><span data-stu-id="b4f65-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b4f65-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b4f65-110">S_OK</span></span>|<span data-ttu-id="b4f65-111">`SetMinThreads` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="b4f65-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="b4f65-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b4f65-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b4f65-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="b4f65-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b4f65-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b4f65-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b4f65-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="b4f65-115">The call timed out.</span></span>|  
|<span data-ttu-id="b4f65-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b4f65-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b4f65-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="b4f65-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b4f65-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b4f65-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b4f65-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="b4f65-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b4f65-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b4f65-120">E_FAIL</span></span>|<span data-ttu-id="b4f65-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="b4f65-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b4f65-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="b4f65-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b4f65-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="b4f65-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b4f65-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="b4f65-124">E_NOTIMPL</span></span>|<span data-ttu-id="b4f65-125">宿主不提供 `SetMinThreads`的实现。</span><span class="sxs-lookup"><span data-stu-id="b4f65-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4f65-126">备注</span><span class="sxs-lookup"><span data-stu-id="b4f65-126">Remarks</span></span>  
 <span data-ttu-id="b4f65-127">出于实现、性能或可伸缩性等原因，主机可能需要对可分配给处理 i/o 请求的线程数进行独占控制。</span><span class="sxs-lookup"><span data-stu-id="b4f65-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="b4f65-128">出于此原因，主机不需要实现 `SetMinThreads`。</span><span class="sxs-lookup"><span data-stu-id="b4f65-128">For this reason, the host is not required to implement `SetMinThreads`.</span></span> <span data-ttu-id="b4f65-129">在这种情况下，宿主应从此方法返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="b4f65-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4f65-130">要求</span><span class="sxs-lookup"><span data-stu-id="b4f65-130">Requirements</span></span>  
 <span data-ttu-id="b4f65-131">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b4f65-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4f65-132">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b4f65-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b4f65-133">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="b4f65-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4f65-134">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4f65-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4f65-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4f65-135">See also</span></span>

- [<span data-ttu-id="b4f65-136">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="b4f65-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="b4f65-137">SetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="b4f65-137">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)
- [<span data-ttu-id="b4f65-138">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="b4f65-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
