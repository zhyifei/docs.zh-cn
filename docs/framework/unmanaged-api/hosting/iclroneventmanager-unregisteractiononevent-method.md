---
title: ICLROnEventManager::UnregisterActionOnEvent 方法
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.UnregisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::UnregisterActionOnEvent
helpviewer_keywords:
- UnRegisterActionOnEvent method [.NET Framework hosting]
- ICLROnEventManager::UnRegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: 4c02ec37-cdf0-46b2-890e-235092741236
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7add5e85aac273b4d513a24196af8305082c417f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434645"
---
# <a name="iclroneventmanagerunregisteractiononevent-method"></a><span data-ttu-id="735ed-102">ICLROnEventManager::UnregisterActionOnEvent 方法</span><span class="sxs-lookup"><span data-stu-id="735ed-102">ICLROnEventManager::UnregisterActionOnEvent Method</span></span>
<span data-ttu-id="735ed-103">注销之前注册的回调指针为指定的事件。</span><span class="sxs-lookup"><span data-stu-id="735ed-103">Unregisters a previously registered callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="735ed-104">语法</span><span class="sxs-lookup"><span data-stu-id="735ed-104">Syntax</span></span>  
  
```  
HRESULT UnregisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="735ed-105">参数</span><span class="sxs-lookup"><span data-stu-id="735ed-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="735ed-106">[in]之一[EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)值，指示要为其取消注册回调指针所描述事件`pAction`。</span><span class="sxs-lookup"><span data-stu-id="735ed-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to unregister the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="735ed-107">[in]指向的指针[IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)对象作为参数传递给传递[RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="735ed-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that was passed as a parameter to the [RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="735ed-108">返回值</span><span class="sxs-lookup"><span data-stu-id="735ed-108">Return Value</span></span>  
  
|<span data-ttu-id="735ed-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="735ed-109">HRESULT</span></span>|<span data-ttu-id="735ed-110">描述</span><span class="sxs-lookup"><span data-stu-id="735ed-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="735ed-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="735ed-111">S_OK</span></span>|<span data-ttu-id="735ed-112">`UnregisterActionOnEvent` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="735ed-112">`UnregisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="735ed-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="735ed-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="735ed-114">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="735ed-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="735ed-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="735ed-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="735ed-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="735ed-116">The call timed out.</span></span>|  
|<span data-ttu-id="735ed-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="735ed-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="735ed-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="735ed-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="735ed-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="735ed-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="735ed-120">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="735ed-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="735ed-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="735ed-121">E_FAIL</span></span>|<span data-ttu-id="735ed-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="735ed-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="735ed-123">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="735ed-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="735ed-124">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="735ed-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="735ed-125">要求</span><span class="sxs-lookup"><span data-stu-id="735ed-125">Requirements</span></span>  
 <span data-ttu-id="735ed-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="735ed-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="735ed-127">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="735ed-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="735ed-128">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="735ed-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="735ed-129">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="735ed-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="735ed-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="735ed-130">See Also</span></span>  
 [<span data-ttu-id="735ed-131">EClrEvent 枚举</span><span class="sxs-lookup"><span data-stu-id="735ed-131">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="735ed-132">IActionOnCLREvent 接口</span><span class="sxs-lookup"><span data-stu-id="735ed-132">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [<span data-ttu-id="735ed-133">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="735ed-133">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="735ed-134">ICLROnEventManager 接口</span><span class="sxs-lookup"><span data-stu-id="735ed-134">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
