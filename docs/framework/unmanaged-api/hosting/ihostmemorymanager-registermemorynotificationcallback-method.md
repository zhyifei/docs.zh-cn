---
title: "IHostMemoryManager::RegisterMemoryNotificationCallback 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.RegisterMemoryNotificationCallback
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::RegisterMemoryNotificationCallback
helpviewer_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback method [.NET Framework hosting]
- RegisterMemoryNotificationCallback method [.NET Framework hosting]
ms.assetid: 65d301f6-4dbb-4b5f-8eff-82540e2b6465
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a59de95ea671b6f568ade81005c718cac00350e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a><span data-ttu-id="95954-102">IHostMemoryManager::RegisterMemoryNotificationCallback 方法</span><span class="sxs-lookup"><span data-stu-id="95954-102">IHostMemoryManager::RegisterMemoryNotificationCallback Method</span></span>
<span data-ttu-id="95954-103">在计算机上的当前内存负载注册到主机时，将调用以通知公共语言运行时 (CLR) 的回调函数的指针。</span><span class="sxs-lookup"><span data-stu-id="95954-103">Registers a pointer to a callback function that the host invokes to notify the common language runtime (CLR) of the current memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95954-104">语法</span><span class="sxs-lookup"><span data-stu-id="95954-104">Syntax</span></span>  
  
```  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="95954-105">参数</span><span class="sxs-lookup"><span data-stu-id="95954-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="95954-106">[in]接口指针[ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)由 CLR 实现的实例。</span><span class="sxs-lookup"><span data-stu-id="95954-106">[in] An interface pointer to an [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) instance that is implemented by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95954-107">返回值</span><span class="sxs-lookup"><span data-stu-id="95954-107">Return Value</span></span>  
  
|<span data-ttu-id="95954-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="95954-108">HRESULT</span></span>|<span data-ttu-id="95954-109">描述</span><span class="sxs-lookup"><span data-stu-id="95954-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="95954-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="95954-110">S_OK</span></span>|<span data-ttu-id="95954-111">`RegisterMemoryNotificationCallback`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="95954-111">`RegisterMemoryNotificationCallback` returned successfully.</span></span>|  
|<span data-ttu-id="95954-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="95954-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="95954-113">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="95954-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="95954-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="95954-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="95954-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="95954-115">The call timed out.</span></span>|  
|<span data-ttu-id="95954-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="95954-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="95954-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="95954-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="95954-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="95954-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="95954-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="95954-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="95954-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="95954-120">E_FAIL</span></span>|<span data-ttu-id="95954-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="95954-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="95954-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="95954-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="95954-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="95954-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95954-124">备注</span><span class="sxs-lookup"><span data-stu-id="95954-124">Remarks</span></span>  
 <span data-ttu-id="95954-125">因为`ICLRMemoryNotificationCallback`接口定义只有一个方法 ([iclrmemorynotificationcallback:: Onmemorynotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md))，而是因为`pCallback`是一个指向`ICLRMemoryNotificationCallback`由 CLR，提供的实例注册实际上是本身的回调函数。</span><span class="sxs-lookup"><span data-stu-id="95954-125">Because the `ICLRMemoryNotificationCallback` interface defines only one method ([ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)), and because `pCallback` is a pointer to an `ICLRMemoryNotificationCallback` instance provided by the CLR, the registration is effectively for the callback function itself.</span></span> <span data-ttu-id="95954-126">宿主通过调用`OnMemoryNotification`到报告内存压力情况，而不是使用标准 Win32`CreateMemoryResourceNotification`函数。</span><span class="sxs-lookup"><span data-stu-id="95954-126">The host invokes `OnMemoryNotification` to report memory pressure conditions, rather than using the standard Win32 `CreateMemoryResourceNotification` function.</span></span> <span data-ttu-id="95954-127">有关详细信息，请参阅 Windows 平台文档。</span><span class="sxs-lookup"><span data-stu-id="95954-127">For more information, see the Windows Platform documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95954-128">调用`OnMemoryNotification`永远不会阻止。</span><span class="sxs-lookup"><span data-stu-id="95954-128">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="95954-129">它们始终立即返回。</span><span class="sxs-lookup"><span data-stu-id="95954-129">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95954-130">惠?</span><span class="sxs-lookup"><span data-stu-id="95954-130">Requirements</span></span>  
 <span data-ttu-id="95954-131">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="95954-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95954-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="95954-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="95954-133">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="95954-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95954-134">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95954-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95954-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="95954-135">See Also</span></span>  
 [<span data-ttu-id="95954-136">ICLRMemoryNotificationCallback 接口</span><span class="sxs-lookup"><span data-stu-id="95954-136">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 [<span data-ttu-id="95954-137">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="95954-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
