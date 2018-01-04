---
title: "ICLROnEventManager::RegisterActionOnEvent 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLROnEventManager.RegisterActionOnEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLROnEventManager::RegisterActionOnEvent
helpviewer_keywords:
- ICLROnEventManager::RegisterActionOnEvent method [.NET Framework hosting]
- RegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: b944cf49-918d-4c4e-993b-77d097a52550
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 008bdc856c9fbede7398f467674ac191c1860128
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a><span data-ttu-id="4cd02-102">ICLROnEventManager::RegisterActionOnEvent 方法</span><span class="sxs-lookup"><span data-stu-id="4cd02-102">ICLROnEventManager::RegisterActionOnEvent Method</span></span>
<span data-ttu-id="4cd02-103">注册指定的事件的回调指针。</span><span class="sxs-lookup"><span data-stu-id="4cd02-103">Registers a callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cd02-104">语法</span><span class="sxs-lookup"><span data-stu-id="4cd02-104">Syntax</span></span>  
  
```  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4cd02-105">参数</span><span class="sxs-lookup"><span data-stu-id="4cd02-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="4cd02-106">[in]之一[EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)值，指示要为其注册回调指针所描述事件`pAction`。</span><span class="sxs-lookup"><span data-stu-id="4cd02-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to register the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="4cd02-107">[in]指向的指针[IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)时，已注册的事件将激发调用的对象。</span><span class="sxs-lookup"><span data-stu-id="4cd02-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that is called when the registered event fires.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4cd02-108">返回值</span><span class="sxs-lookup"><span data-stu-id="4cd02-108">Return Value</span></span>  
  
|<span data-ttu-id="4cd02-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4cd02-109">HRESULT</span></span>|<span data-ttu-id="4cd02-110">描述</span><span class="sxs-lookup"><span data-stu-id="4cd02-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4cd02-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4cd02-111">S_OK</span></span>|<span data-ttu-id="4cd02-112">`RegisterActionOnEvent`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="4cd02-112">`RegisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="4cd02-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4cd02-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4cd02-114">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="4cd02-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4cd02-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4cd02-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4cd02-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="4cd02-116">The call timed out.</span></span>|  
|<span data-ttu-id="4cd02-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4cd02-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4cd02-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="4cd02-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4cd02-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4cd02-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4cd02-120">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="4cd02-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4cd02-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4cd02-121">E_FAIL</span></span>|<span data-ttu-id="4cd02-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="4cd02-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4cd02-123">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="4cd02-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4cd02-124">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="4cd02-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4cd02-125">备注</span><span class="sxs-lookup"><span data-stu-id="4cd02-125">Remarks</span></span>  
 <span data-ttu-id="4cd02-126">主机可以注册一个或两个所描述的两个事件类型的回调`EClrEvent`。</span><span class="sxs-lookup"><span data-stu-id="4cd02-126">The host can register callbacks for either or both of the two event types described by `EClrEvent`.</span></span> <span data-ttu-id="4cd02-127">主机获取`ICLROnEventManager`接口通过调用[iclrcontrol:: Getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="4cd02-127">The host gets the `ICLROnEventManager` interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4cd02-128">事件的`RegisterActionOnEvent`不止一次和从不同的线程，以卸载或禁用 CLR 发出信号，则可以激发寄存器。</span><span class="sxs-lookup"><span data-stu-id="4cd02-128">The events that `RegisterActionOnEvent` registers can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cd02-129">惠?</span><span class="sxs-lookup"><span data-stu-id="4cd02-129">Requirements</span></span>  
 <span data-ttu-id="4cd02-130">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4cd02-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cd02-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4cd02-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4cd02-132">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4cd02-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4cd02-133">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cd02-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cd02-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="4cd02-134">See Also</span></span>  
 [<span data-ttu-id="4cd02-135">EClrEvent 枚举</span><span class="sxs-lookup"><span data-stu-id="4cd02-135">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="4cd02-136">IActionOnCLREvent 接口</span><span class="sxs-lookup"><span data-stu-id="4cd02-136">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [<span data-ttu-id="4cd02-137">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="4cd02-137">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="4cd02-138">ICLROnEventManager 接口</span><span class="sxs-lookup"><span data-stu-id="4cd02-138">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
