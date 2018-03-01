---
title: "IHostSyncManager::CreateManualEvent 方法"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 347eaa64b8a5e5b5c9494a779e3d583b10d80052
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="f3e42-102">IHostSyncManager::CreateManualEvent 方法</span><span class="sxs-lookup"><span data-stu-id="f3e42-102">IHostSyncManager::CreateManualEvent Method</span></span>
<span data-ttu-id="f3e42-103">创建手动重置事件对象。</span><span class="sxs-lookup"><span data-stu-id="f3e42-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3e42-104">语法</span><span class="sxs-lookup"><span data-stu-id="f3e42-104">Syntax</span></span>  
  
```  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f3e42-105">参数</span><span class="sxs-lookup"><span data-stu-id="f3e42-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="f3e42-106">[in]`true`、 的对象是否终止; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="f3e42-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="f3e42-107">[out]指向的地址的指针[IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)实例，或如果无法创建事件为 null。</span><span class="sxs-lookup"><span data-stu-id="f3e42-107">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f3e42-108">返回值</span><span class="sxs-lookup"><span data-stu-id="f3e42-108">Return Value</span></span>  
  
|<span data-ttu-id="f3e42-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f3e42-109">HRESULT</span></span>|<span data-ttu-id="f3e42-110">描述</span><span class="sxs-lookup"><span data-stu-id="f3e42-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f3e42-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f3e42-111">S_OK</span></span>|<span data-ttu-id="f3e42-112">`CreateManualEvent`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="f3e42-112">`CreateManualEvent` returned successfully.</span></span>|  
|<span data-ttu-id="f3e42-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f3e42-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f3e42-114">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="f3e42-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f3e42-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f3e42-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f3e42-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="f3e42-116">The call timed out.</span></span>|  
|<span data-ttu-id="f3e42-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f3e42-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f3e42-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="f3e42-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f3e42-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f3e42-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f3e42-120">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="f3e42-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f3e42-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f3e42-121">E_FAIL</span></span>|<span data-ttu-id="f3e42-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="f3e42-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f3e42-123">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="f3e42-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f3e42-124">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="f3e42-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f3e42-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f3e42-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="f3e42-126">没有足够的内存已可用于创建请求的事件对象。</span><span class="sxs-lookup"><span data-stu-id="f3e42-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3e42-127">备注</span><span class="sxs-lookup"><span data-stu-id="f3e42-127">Remarks</span></span>  
 <span data-ttu-id="f3e42-128">`CreateManualEvent`创建`IHostManualEvent`，需要调用手动重置事件对象[ihostmanualevent:: Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)方法以将其设置为非终止状态。</span><span class="sxs-lookup"><span data-stu-id="f3e42-128">`CreateManualEvent` creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> <span data-ttu-id="f3e42-129">`CreateManualEvent`镜像 Win32`CreateEvent`函数中使用的值`true`指定的`bManualReset`参数。</span><span class="sxs-lookup"><span data-stu-id="f3e42-129">`CreateManualEvent` mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3e42-130">惠?</span><span class="sxs-lookup"><span data-stu-id="f3e42-130">Requirements</span></span>  
 <span data-ttu-id="f3e42-131">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f3e42-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3e42-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f3e42-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f3e42-133">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f3e42-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f3e42-134">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3e42-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3e42-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="f3e42-135">See Also</span></span>  
 [<span data-ttu-id="f3e42-136">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="f3e42-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="f3e42-137">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="f3e42-137">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="f3e42-138">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="f3e42-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
