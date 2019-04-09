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
ms.openlocfilehash: 54abd54662d4e99881dddf15876b596a4a705f70
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108896"
---
# <a name="iclroneventmanagerunregisteractiononevent-method"></a><span data-ttu-id="92ffe-102">ICLROnEventManager::UnregisterActionOnEvent 方法</span><span class="sxs-lookup"><span data-stu-id="92ffe-102">ICLROnEventManager::UnregisterActionOnEvent Method</span></span>
<span data-ttu-id="92ffe-103">注销以前注册的回调指针为指定的事件。</span><span class="sxs-lookup"><span data-stu-id="92ffe-103">Unregisters a previously registered callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92ffe-104">语法</span><span class="sxs-lookup"><span data-stu-id="92ffe-104">Syntax</span></span>  
  
```  
HRESULT UnregisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92ffe-105">参数</span><span class="sxs-lookup"><span data-stu-id="92ffe-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="92ffe-106">[in]之一[EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)值，它指示要为其取消注册回调指针由描述事件`pAction`。</span><span class="sxs-lookup"><span data-stu-id="92ffe-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to unregister the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="92ffe-107">[in]一个指向[IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)对象作为参数传递[RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="92ffe-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that was passed as a parameter to the [RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="92ffe-108">返回值</span><span class="sxs-lookup"><span data-stu-id="92ffe-108">Return Value</span></span>  
  
|<span data-ttu-id="92ffe-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="92ffe-109">HRESULT</span></span>|<span data-ttu-id="92ffe-110">描述</span><span class="sxs-lookup"><span data-stu-id="92ffe-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="92ffe-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="92ffe-111">S_OK</span></span>|`UnregisterActionOnEvent` <span data-ttu-id="92ffe-112">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="92ffe-112">returned successfully.</span></span>|  
|<span data-ttu-id="92ffe-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="92ffe-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="92ffe-114">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="92ffe-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="92ffe-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="92ffe-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="92ffe-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="92ffe-116">The call timed out.</span></span>|  
|<span data-ttu-id="92ffe-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="92ffe-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="92ffe-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="92ffe-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="92ffe-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="92ffe-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="92ffe-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="92ffe-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="92ffe-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="92ffe-121">E_FAIL</span></span>|<span data-ttu-id="92ffe-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="92ffe-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="92ffe-123">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="92ffe-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="92ffe-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="92ffe-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="92ffe-125">要求</span><span class="sxs-lookup"><span data-stu-id="92ffe-125">Requirements</span></span>  
 <span data-ttu-id="92ffe-126">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="92ffe-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92ffe-127">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="92ffe-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="92ffe-128">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="92ffe-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="92ffe-129">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="92ffe-129">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="92ffe-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="92ffe-130">See also</span></span>

- [<span data-ttu-id="92ffe-131">EClrEvent 枚举</span><span class="sxs-lookup"><span data-stu-id="92ffe-131">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="92ffe-132">IActionOnCLREvent 接口</span><span class="sxs-lookup"><span data-stu-id="92ffe-132">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="92ffe-133">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="92ffe-133">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="92ffe-134">ICLROnEventManager 接口</span><span class="sxs-lookup"><span data-stu-id="92ffe-134">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
