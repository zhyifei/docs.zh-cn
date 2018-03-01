---
title: "ICLRMemoryNotificationCallback::OnMemoryNotification 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRMemoryNotificationCallback.OnMemoryNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification
helpviewer_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification method [.NET Framework hosting]
- OnMemoryNotification method [.NET Framework hosting]
ms.assetid: 5612a44d-56cc-4f34-af31-8c9809ba9431
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 651dcd6380702a392d2dd06cf899ea567b004ce1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="261de-102">ICLRMemoryNotificationCallback::OnMemoryNotification 方法</span><span class="sxs-lookup"><span data-stu-id="261de-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="261de-103">通知在计算机上的内存负载公共语言运行时 (CLR)。</span><span class="sxs-lookup"><span data-stu-id="261de-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="261de-104">语法</span><span class="sxs-lookup"><span data-stu-id="261de-104">Syntax</span></span>  
  
```  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="261de-105">参数</span><span class="sxs-lookup"><span data-stu-id="261de-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="261de-106">[in]之一[EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md)值，指示内存压力计算机当前遇到。</span><span class="sxs-lookup"><span data-stu-id="261de-106">[in] One of the [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="261de-107">返回值</span><span class="sxs-lookup"><span data-stu-id="261de-107">Return Value</span></span>  
  
|<span data-ttu-id="261de-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="261de-108">HRESULT</span></span>|<span data-ttu-id="261de-109">描述</span><span class="sxs-lookup"><span data-stu-id="261de-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="261de-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="261de-110">S_OK</span></span>|<span data-ttu-id="261de-111">`OnMemoryNotification`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="261de-111">`OnMemoryNotification` returned successfully.</span></span>|  
|<span data-ttu-id="261de-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="261de-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="261de-113">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="261de-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="261de-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="261de-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="261de-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="261de-115">The call timed out.</span></span>|  
|<span data-ttu-id="261de-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="261de-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="261de-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="261de-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="261de-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="261de-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="261de-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="261de-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="261de-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="261de-120">E_FAIL</span></span>|<span data-ttu-id="261de-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="261de-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="261de-122">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="261de-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="261de-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="261de-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="261de-124">备注</span><span class="sxs-lookup"><span data-stu-id="261de-124">Remarks</span></span>  
 <span data-ttu-id="261de-125">CLR 注册到回调`OnMemoryNotification`通过调用[ihostmemorymanager:: Registermemorynotificationcallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="261de-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="261de-126">运行时使用该回调中返回的信息可在宿主报告的内存资源不足时释放其他内存。</span><span class="sxs-lookup"><span data-stu-id="261de-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="261de-127">调用`OnMemoryNotification`永远不会阻止。</span><span class="sxs-lookup"><span data-stu-id="261de-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="261de-128">它们始终立即返回。</span><span class="sxs-lookup"><span data-stu-id="261de-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="261de-129">惠?</span><span class="sxs-lookup"><span data-stu-id="261de-129">Requirements</span></span>  
 <span data-ttu-id="261de-130">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="261de-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="261de-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="261de-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="261de-132">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="261de-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="261de-133">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="261de-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="261de-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="261de-134">See Also</span></span>  
 [<span data-ttu-id="261de-135">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="261de-135">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="261de-136">RegisterMemoryNotificationCallback 方法</span><span class="sxs-lookup"><span data-stu-id="261de-136">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)  
 [<span data-ttu-id="261de-137">ICLRMemoryNotificationCallback 接口</span><span class="sxs-lookup"><span data-stu-id="261de-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
