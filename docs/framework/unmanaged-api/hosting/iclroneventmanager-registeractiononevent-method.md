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
ms.openlocfilehash: e634b3876d51d461446ed3f5ae537ac1db1545bd
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703501"
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a><span data-ttu-id="8e4a0-102">ICLROnEventManager::RegisterActionOnEvent 方法</span><span class="sxs-lookup"><span data-stu-id="8e4a0-102">ICLROnEventManager::RegisterActionOnEvent Method</span></span>
<span data-ttu-id="8e4a0-103">为指定事件注册回调指针。</span><span class="sxs-lookup"><span data-stu-id="8e4a0-103">Registers a callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e4a0-104">语法</span><span class="sxs-lookup"><span data-stu-id="8e4a0-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e4a0-105">参数</span><span class="sxs-lookup"><span data-stu-id="8e4a0-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="8e4a0-106">中[EClrEvent](eclrevent-enumeration.md)值之一，指示要为其注册所描述的回调指针的事件 `pAction` 。</span><span class="sxs-lookup"><span data-stu-id="8e4a0-106">[in] One of the [EClrEvent](eclrevent-enumeration.md) values, indicating the event for which to register the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="8e4a0-107">中指向[IActionOnCLREvent](iactiononclrevent-interface.md)对象的指针，当注册的事件激发时，将调用该对象。</span><span class="sxs-lookup"><span data-stu-id="8e4a0-107">[in] A pointer to an [IActionOnCLREvent](iactiononclrevent-interface.md) object that is called when the registered event fires.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e4a0-108">返回值</span><span class="sxs-lookup"><span data-stu-id="8e4a0-108">Return Value</span></span>  
  
|<span data-ttu-id="8e4a0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8e4a0-109">HRESULT</span></span>|<span data-ttu-id="8e4a0-110">说明</span><span class="sxs-lookup"><span data-stu-id="8e4a0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8e4a0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8e4a0-111">S_OK</span></span>|<span data-ttu-id="8e4a0-112">`RegisterActionOnEvent`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="8e4a0-112">`RegisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="8e4a0-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8e4a0-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8e4a0-114">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="8e4a0-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8e4a0-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8e4a0-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8e4a0-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="8e4a0-116">The call timed out.</span></span>|  
|<span data-ttu-id="8e4a0-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8e4a0-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8e4a0-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="8e4a0-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8e4a0-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8e4a0-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8e4a0-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="8e4a0-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8e4a0-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8e4a0-121">E_FAIL</span></span>|<span data-ttu-id="8e4a0-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="8e4a0-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8e4a0-123">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="8e4a0-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8e4a0-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="8e4a0-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e4a0-125">备注</span><span class="sxs-lookup"><span data-stu-id="8e4a0-125">Remarks</span></span>  
 <span data-ttu-id="8e4a0-126">宿主可以为描述的两个事件类型中的一个或两个注册回调 `EClrEvent` 。</span><span class="sxs-lookup"><span data-stu-id="8e4a0-126">The host can register callbacks for either or both of the two event types described by `EClrEvent`.</span></span> <span data-ttu-id="8e4a0-127">宿主 `ICLROnEventManager` 通过调用[ICLRControl：： GetCLRManager](iclrcontrol-getclrmanager-method.md)方法获取接口。</span><span class="sxs-lookup"><span data-stu-id="8e4a0-127">The host gets the `ICLROnEventManager` interface by calling the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8e4a0-128">注册的事件 `RegisterActionOnEvent` 可以从不同的线程激发一次，以发出卸载或禁用 CLR 的信号。</span><span class="sxs-lookup"><span data-stu-id="8e4a0-128">The events that `RegisterActionOnEvent` registers can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e4a0-129">要求</span><span class="sxs-lookup"><span data-stu-id="8e4a0-129">Requirements</span></span>  
 <span data-ttu-id="8e4a0-130">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8e4a0-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e4a0-131">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8e4a0-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8e4a0-132">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="8e4a0-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e4a0-133">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e4a0-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e4a0-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e4a0-134">See also</span></span>

- [<span data-ttu-id="8e4a0-135">EClrEvent 枚举</span><span class="sxs-lookup"><span data-stu-id="8e4a0-135">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="8e4a0-136">IActionOnCLREvent 接口</span><span class="sxs-lookup"><span data-stu-id="8e4a0-136">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="8e4a0-137">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="8e4a0-137">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="8e4a0-138">ICLROnEventManager 接口</span><span class="sxs-lookup"><span data-stu-id="8e4a0-138">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
