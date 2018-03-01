---
title: "IHostSyncManager::CreateMonitorEvent 方法"
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
- IHostSyncManager.CreateMonitorEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateMonitorEvent
helpviewer_keywords:
- CreateMonitorEvent method [.NET Framework hosting]
- IHostSyncManager::CreateMonitorEvent method [.NET Framework hosting]
ms.assetid: 524c7fd3-9b5c-46e7-99ba-555fd2fe33f0
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ae12db71f4eae0f7d887fda26e05401f4f23ee5c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a><span data-ttu-id="963af-102">IHostSyncManager::CreateMonitorEvent 方法</span><span class="sxs-lookup"><span data-stu-id="963af-102">IHostSyncManager::CreateMonitorEvent Method</span></span>
<span data-ttu-id="963af-103">创建监视的自动重置事件对象。</span><span class="sxs-lookup"><span data-stu-id="963af-103">Creates a monitored auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="963af-104">语法</span><span class="sxs-lookup"><span data-stu-id="963af-104">Syntax</span></span>  
  
```  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="963af-105">参数</span><span class="sxs-lookup"><span data-stu-id="963af-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="963af-106">[in]一个要与事件对象关联的 cookie。</span><span class="sxs-lookup"><span data-stu-id="963af-106">[in] A cookie to associate with the event object.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="963af-107">[out]指向的地址的指针[IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)实例，或如果无法创建事件对象为 null。</span><span class="sxs-lookup"><span data-stu-id="963af-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="963af-108">返回值</span><span class="sxs-lookup"><span data-stu-id="963af-108">Return Value</span></span>  
  
|<span data-ttu-id="963af-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="963af-109">HRESULT</span></span>|<span data-ttu-id="963af-110">描述</span><span class="sxs-lookup"><span data-stu-id="963af-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="963af-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="963af-111">S_OK</span></span>|<span data-ttu-id="963af-112">`CreateMonitorEvent`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="963af-112">`CreateMonitorEvent` returned successfully.</span></span>|  
|<span data-ttu-id="963af-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="963af-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="963af-114">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="963af-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="963af-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="963af-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="963af-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="963af-116">The call timed out.</span></span>|  
|<span data-ttu-id="963af-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="963af-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="963af-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="963af-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="963af-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="963af-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="963af-120">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="963af-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="963af-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="963af-121">E_FAIL</span></span>|<span data-ttu-id="963af-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="963af-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="963af-123">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="963af-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="963af-124">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="963af-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="963af-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="963af-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="963af-126">没有足够的内存已可用于创建请求的事件对象。</span><span class="sxs-lookup"><span data-stu-id="963af-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="963af-127">备注</span><span class="sxs-lookup"><span data-stu-id="963af-127">Remarks</span></span>  
 <span data-ttu-id="963af-128">`CreateMonitorEvent`返回`IHostAutoEvent`，则 CLR 会使用在其实现的托管<xref:System.Threading.Monitor?displayProperty=nameWithType>类型。</span><span class="sxs-lookup"><span data-stu-id="963af-128">`CreateMonitorEvent` returns an `IHostAutoEvent` that the CLR uses in its implementation of the managed <xref:System.Threading.Monitor?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="963af-129">此方法将镜像 Win32`CreateEvent`函数中，使用的值`false`指定的`bManualReset`参数。</span><span class="sxs-lookup"><span data-stu-id="963af-129">This method mirrors the Win32 `CreateEvent` function, with a value of `false` specified for the `bManualReset` parameter.</span></span>  
  
 <span data-ttu-id="963af-130">主机可以使用 cookie 来确定哪些任务在等待监视器通过调用[iclrsyncmanager:: Getmonitorowner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="963af-130">The host can use the cookie to determine which task is waiting on the monitor by calling the [ICLRSyncManager::GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="963af-131">惠?</span><span class="sxs-lookup"><span data-stu-id="963af-131">Requirements</span></span>  
 <span data-ttu-id="963af-132">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="963af-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="963af-133">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="963af-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="963af-134">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="963af-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="963af-135">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="963af-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="963af-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="963af-136">See Also</span></span>  
 [<span data-ttu-id="963af-137">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="963af-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="963af-138">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="963af-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="963af-139">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="963af-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="963af-140">监视器</span><span class="sxs-lookup"><span data-stu-id="963af-140">Monitors</span></span>](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)
