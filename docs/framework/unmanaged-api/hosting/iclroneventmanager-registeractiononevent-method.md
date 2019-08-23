---
title: ICLROnEventManager::RegisterActionOnEvent 方法
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.RegisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::RegisterActionOnEvent
helpviewer_keywords:
- ICLROnEventManager::RegisterActionOnEvent method [.NET Framework hosting]
- RegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: b944cf49-918d-4c4e-993b-77d097a52550
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36d4b0692b112a66fea3dd878c7054a083fb68ff
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951151"
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a><span data-ttu-id="f49b9-102">ICLROnEventManager::RegisterActionOnEvent 方法</span><span class="sxs-lookup"><span data-stu-id="f49b9-102">ICLROnEventManager::RegisterActionOnEvent Method</span></span>
<span data-ttu-id="f49b9-103">为指定事件注册回调指针。</span><span class="sxs-lookup"><span data-stu-id="f49b9-103">Registers a callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f49b9-104">语法</span><span class="sxs-lookup"><span data-stu-id="f49b9-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f49b9-105">参数</span><span class="sxs-lookup"><span data-stu-id="f49b9-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="f49b9-106">中[EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)值之一, 指示要为其注册所描述`pAction`的回调指针的事件。</span><span class="sxs-lookup"><span data-stu-id="f49b9-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to register the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="f49b9-107">中指向[IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)对象的指针, 当注册的事件激发时, 将调用该对象。</span><span class="sxs-lookup"><span data-stu-id="f49b9-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that is called when the registered event fires.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f49b9-108">返回值</span><span class="sxs-lookup"><span data-stu-id="f49b9-108">Return Value</span></span>  
  
|<span data-ttu-id="f49b9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f49b9-109">HRESULT</span></span>|<span data-ttu-id="f49b9-110">描述</span><span class="sxs-lookup"><span data-stu-id="f49b9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f49b9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f49b9-111">S_OK</span></span>|<span data-ttu-id="f49b9-112">`RegisterActionOnEvent`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="f49b9-112">`RegisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="f49b9-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f49b9-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f49b9-114">公共语言运行时 (CLR) 未加载到进程中, 或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="f49b9-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f49b9-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f49b9-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f49b9-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="f49b9-116">The call timed out.</span></span>|  
|<span data-ttu-id="f49b9-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f49b9-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f49b9-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="f49b9-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f49b9-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f49b9-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f49b9-120">已阻止的线程或纤程正在等待某个事件时, 该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="f49b9-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f49b9-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f49b9-121">E_FAIL</span></span>|<span data-ttu-id="f49b9-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="f49b9-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f49b9-123">方法返回 E_FAIL 后, CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="f49b9-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f49b9-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="f49b9-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f49b9-125">备注</span><span class="sxs-lookup"><span data-stu-id="f49b9-125">Remarks</span></span>  
 <span data-ttu-id="f49b9-126">宿主可以为描述`EClrEvent`的两个事件类型中的一个或两个注册回调。</span><span class="sxs-lookup"><span data-stu-id="f49b9-126">The host can register callbacks for either or both of the two event types described by `EClrEvent`.</span></span> <span data-ttu-id="f49b9-127">宿主通过调用`ICLROnEventManager` [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)方法获取接口。</span><span class="sxs-lookup"><span data-stu-id="f49b9-127">The host gets the `ICLROnEventManager` interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f49b9-128">`RegisterActionOnEvent`注册的事件可以从不同的线程激发一次, 以发出卸载或禁用 CLR 的信号。</span><span class="sxs-lookup"><span data-stu-id="f49b9-128">The events that `RegisterActionOnEvent` registers can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f49b9-129">要求</span><span class="sxs-lookup"><span data-stu-id="f49b9-129">Requirements</span></span>  
 <span data-ttu-id="f49b9-130">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f49b9-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f49b9-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f49b9-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f49b9-132">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="f49b9-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f49b9-133">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f49b9-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f49b9-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="f49b9-134">See also</span></span>

- [<span data-ttu-id="f49b9-135">EClrEvent 枚举</span><span class="sxs-lookup"><span data-stu-id="f49b9-135">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="f49b9-136">IActionOnCLREvent 接口</span><span class="sxs-lookup"><span data-stu-id="f49b9-136">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="f49b9-137">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="f49b9-137">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="f49b9-138">ICLROnEventManager 接口</span><span class="sxs-lookup"><span data-stu-id="f49b9-138">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
