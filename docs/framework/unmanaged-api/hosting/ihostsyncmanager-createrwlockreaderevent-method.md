---
title: "IHostSyncManager::CreateRWLockReaderEvent 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateRWLockReaderEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateRWLockReaderEvent
helpviewer_keywords:
- CreateRWLockReaderEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockReaderEvent method [.NET Framework hosting]
ms.assetid: 68c4ea19-c47c-45c6-b420-d3a2ba1c2d50
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a783f4511e27b5d230a90444e5a91b34327543cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanagercreaterwlockreaderevent-method"></a><span data-ttu-id="1bf9b-102">IHostSyncManager::CreateRWLockReaderEvent 方法</span><span class="sxs-lookup"><span data-stu-id="1bf9b-102">IHostSyncManager::CreateRWLockReaderEvent Method</span></span>
<span data-ttu-id="1bf9b-103">为创建一个手动重置事件对象将读线程锁的实现。</span><span class="sxs-lookup"><span data-stu-id="1bf9b-103">Creates a manual-reset event object for the implementation of a reader lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bf9b-104">语法</span><span class="sxs-lookup"><span data-stu-id="1bf9b-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockReaderEvent (  
    [in]  BOOL bInitialState,  
    [in]  SIZE_T cookie,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1bf9b-105">参数</span><span class="sxs-lookup"><span data-stu-id="1bf9b-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="1bf9b-106">[in]`true`，如果`ppEvent`终止; 否则为应为`false`。</span><span class="sxs-lookup"><span data-stu-id="1bf9b-106">[in] `true`, if `ppEvent` should be signaled; otherwise, `false`.</span></span>  
  
 `cookie`  
 <span data-ttu-id="1bf9b-107">[in]一个将读线程锁与关联的 cookie。</span><span class="sxs-lookup"><span data-stu-id="1bf9b-107">[in] A cookie to associate with the reader lock.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="1bf9b-108">[out]指向的地址的指针[IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)实例，或如果无法创建事件对象为 null。</span><span class="sxs-lookup"><span data-stu-id="1bf9b-108">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1bf9b-109">返回值</span><span class="sxs-lookup"><span data-stu-id="1bf9b-109">Return Value</span></span>  
  
|<span data-ttu-id="1bf9b-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1bf9b-110">HRESULT</span></span>|<span data-ttu-id="1bf9b-111">描述</span><span class="sxs-lookup"><span data-stu-id="1bf9b-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1bf9b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="1bf9b-112">S_OK</span></span>|<span data-ttu-id="1bf9b-113">`CreateRWLockReaderEvent`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="1bf9b-113">`CreateRWLockReaderEvent` returned successfully.</span></span>|  
|<span data-ttu-id="1bf9b-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1bf9b-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1bf9b-115">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="1bf9b-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1bf9b-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1bf9b-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1bf9b-117">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="1bf9b-117">The call timed out.</span></span>|  
|<span data-ttu-id="1bf9b-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1bf9b-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1bf9b-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="1bf9b-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1bf9b-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1bf9b-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1bf9b-121">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="1bf9b-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1bf9b-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1bf9b-122">E_FAIL</span></span>|<span data-ttu-id="1bf9b-123">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="1bf9b-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1bf9b-124">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="1bf9b-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1bf9b-125">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="1bf9b-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1bf9b-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="1bf9b-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="1bf9b-127">没有足够的内存已可用于创建请求的事件对象。</span><span class="sxs-lookup"><span data-stu-id="1bf9b-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bf9b-128">备注</span><span class="sxs-lookup"><span data-stu-id="1bf9b-128">Remarks</span></span>  
 <span data-ttu-id="1bf9b-129">CLR 调用`CreateRWLockReaderEvent`获取对引用`IHostManualEvent`实例，以使用在其实现中将读线程锁。</span><span class="sxs-lookup"><span data-stu-id="1bf9b-129">The CLR calls `CreateRWLockReaderEvent` to get a reference to an `IHostManualEvent` instance to use in its implementation of a reader lock.</span></span> <span data-ttu-id="1bf9b-130">主机可以使用 cookie 来确定哪些任务在通过查询读取器锁等待[ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="1bf9b-130">The host can use the cookie to determine which tasks are waiting on the reader lock by querying the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bf9b-131">要求</span><span class="sxs-lookup"><span data-stu-id="1bf9b-131">Requirements</span></span>  
 <span data-ttu-id="1bf9b-132">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1bf9b-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bf9b-133">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1bf9b-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1bf9b-134">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1bf9b-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1bf9b-135">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bf9b-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bf9b-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1bf9b-136">See Also</span></span>  
 [<span data-ttu-id="1bf9b-137">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="1bf9b-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="1bf9b-138">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="1bf9b-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="1bf9b-139">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="1bf9b-139">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="1bf9b-140">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="1bf9b-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
