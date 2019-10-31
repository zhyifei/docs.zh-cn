---
title: IHostSyncManager::CreateManualEvent 方法
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateManualEvent
helpviewer_keywords:
- CreateManualEvent method [.NET Framework hosting]
- IHostSyncManager::CreateManualEvent method [.NET Framework hosting]
ms.assetid: 68661fbd-09cf-46dc-890b-e694f8a3880a
topic_type:
- apiref
ms.openlocfilehash: 13679b4d40e660dfdd18e6fbafe19226b2ffda37
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195871"
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="87c95-102">IHostSyncManager::CreateManualEvent 方法</span><span class="sxs-lookup"><span data-stu-id="87c95-102">IHostSyncManager::CreateManualEvent Method</span></span>
<span data-ttu-id="87c95-103">创建手动重置的事件对象。</span><span class="sxs-lookup"><span data-stu-id="87c95-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87c95-104">语法</span><span class="sxs-lookup"><span data-stu-id="87c95-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87c95-105">参数</span><span class="sxs-lookup"><span data-stu-id="87c95-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="87c95-106">[in] 如果对象已发出信号，则 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="87c95-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="87c95-107">弄指向[IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)实例的地址的指针; 如果未能创建该事件，则为 null。</span><span class="sxs-lookup"><span data-stu-id="87c95-107">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87c95-108">返回值</span><span class="sxs-lookup"><span data-stu-id="87c95-108">Return Value</span></span>  
  
|<span data-ttu-id="87c95-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="87c95-109">HRESULT</span></span>|<span data-ttu-id="87c95-110">描述</span><span class="sxs-lookup"><span data-stu-id="87c95-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="87c95-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="87c95-111">S_OK</span></span>|<span data-ttu-id="87c95-112">`CreateManualEvent` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="87c95-112">`CreateManualEvent` returned successfully.</span></span>|  
|<span data-ttu-id="87c95-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="87c95-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="87c95-114">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="87c95-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="87c95-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="87c95-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="87c95-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="87c95-116">The call timed out.</span></span>|  
|<span data-ttu-id="87c95-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="87c95-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="87c95-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="87c95-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="87c95-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="87c95-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="87c95-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="87c95-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="87c95-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="87c95-121">E_FAIL</span></span>|<span data-ttu-id="87c95-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="87c95-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="87c95-123">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="87c95-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="87c95-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="87c95-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="87c95-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="87c95-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="87c95-126">没有足够的内存可用于创建请求的事件对象。</span><span class="sxs-lookup"><span data-stu-id="87c95-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87c95-127">备注</span><span class="sxs-lookup"><span data-stu-id="87c95-127">Remarks</span></span>  
 <span data-ttu-id="87c95-128">`CreateManualEvent` 创建一个 `IHostManualEvent`的手动重置事件对象，该对象需要调用[IHostManualEvent：： reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)方法将其设置为非终止状态。</span><span class="sxs-lookup"><span data-stu-id="87c95-128">`CreateManualEvent` creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> <span data-ttu-id="87c95-129">`CreateManualEvent` 使用为 `bManualReset` 参数指定的值 `true` 镜像 Win32 `CreateEvent` 函数。</span><span class="sxs-lookup"><span data-stu-id="87c95-129">`CreateManualEvent` mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87c95-130">要求</span><span class="sxs-lookup"><span data-stu-id="87c95-130">Requirements</span></span>  
 <span data-ttu-id="87c95-131">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="87c95-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87c95-132">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="87c95-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="87c95-133">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="87c95-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87c95-134">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87c95-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87c95-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="87c95-135">See also</span></span>

- [<span data-ttu-id="87c95-136">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="87c95-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="87c95-137">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="87c95-137">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="87c95-138">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="87c95-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
