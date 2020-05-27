---
title: IHostIoCompletionManager::GetMaxThreads 方法
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: e7a6cadc-2433-4472-a701-58891abcde45
topic_type:
- apiref
ms.openlocfilehash: a97a7abf4f561a5aba41d8019f2ba5bd8e879acd
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804742"
---
# <a name="ihostiocompletionmanagergetmaxthreads-method"></a><span data-ttu-id="d9010-102">IHostIoCompletionManager::GetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="d9010-102">IHostIoCompletionManager::GetMaxThreads Method</span></span>
<span data-ttu-id="d9010-103">获取主机可为服务 i/o 请求分配的最大线程数。</span><span class="sxs-lookup"><span data-stu-id="d9010-103">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9010-104">语法</span><span class="sxs-lookup"><span data-stu-id="d9010-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9010-105">参数</span><span class="sxs-lookup"><span data-stu-id="d9010-105">Parameters</span></span>  
 `pdwMaxIoCompletionThreads`  
 <span data-ttu-id="d9010-106">弄一个指针，它指向线程池中的最大线程数，主机可以为这些线程分配服务 i/o 请求。</span><span class="sxs-lookup"><span data-stu-id="d9010-106">[out] A pointer to the maximum number of threads in the thread pool that the host can allot to service I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9010-107">返回值</span><span class="sxs-lookup"><span data-stu-id="d9010-107">Return Value</span></span>  
  
|<span data-ttu-id="d9010-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d9010-108">HRESULT</span></span>|<span data-ttu-id="d9010-109">说明</span><span class="sxs-lookup"><span data-stu-id="d9010-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d9010-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d9010-110">S_OK</span></span>|<span data-ttu-id="d9010-111">`GetMaxThreads`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="d9010-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="d9010-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d9010-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d9010-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="d9010-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d9010-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d9010-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d9010-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="d9010-115">The call timed out.</span></span>|  
|<span data-ttu-id="d9010-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d9010-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d9010-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="d9010-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d9010-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d9010-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d9010-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="d9010-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d9010-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d9010-120">E_FAIL</span></span>|<span data-ttu-id="d9010-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="d9010-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d9010-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="d9010-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d9010-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="d9010-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d9010-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="d9010-124">E_NOTIMPL</span></span>|<span data-ttu-id="d9010-125">宿主不提供的实现 `GetMaxThreads` 。</span><span class="sxs-lookup"><span data-stu-id="d9010-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9010-126">备注</span><span class="sxs-lookup"><span data-stu-id="d9010-126">Remarks</span></span>  
 <span data-ttu-id="d9010-127">出于实现、性能或可伸缩性等原因，主机可能需要对可分配给处理 i/o 请求的线程数进行独占控制。</span><span class="sxs-lookup"><span data-stu-id="d9010-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="d9010-128">出于此原因，主机不需要实现 `GetMaxThreads` 。</span><span class="sxs-lookup"><span data-stu-id="d9010-128">For this reason, the host is not required to implement `GetMaxThreads`.</span></span> <span data-ttu-id="d9010-129">在这种情况下，宿主应从此方法返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="d9010-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9010-130">要求</span><span class="sxs-lookup"><span data-stu-id="d9010-130">Requirements</span></span>  
 <span data-ttu-id="d9010-131">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d9010-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9010-132">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d9010-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d9010-133">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="d9010-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d9010-134">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9010-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9010-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9010-135">See also</span></span>

- [<span data-ttu-id="d9010-136">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="d9010-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="d9010-137">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="d9010-137">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
