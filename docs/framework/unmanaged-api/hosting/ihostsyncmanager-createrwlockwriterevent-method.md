---
title: "IHostSyncManager::CreateRWLockWriterEvent 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateRWLockWriterEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateRWLockWriterEvent
helpviewer_keywords:
- CreateRWLockWriterEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockWriterEvent method [.NET Framework hosting]
ms.assetid: 70e488c2-cf53-4dc0-ba52-74372d215c41
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eb38cd76a051b1a4459dff4f8164a6405f5fb32d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanagercreaterwlockwriterevent-method"></a><span data-ttu-id="74676-102">IHostSyncManager::CreateRWLockWriterEvent 方法</span><span class="sxs-lookup"><span data-stu-id="74676-102">IHostSyncManager::CreateRWLockWriterEvent Method</span></span>
<span data-ttu-id="74676-103">创建用于实现的编写器锁的自动重置事件对象。</span><span class="sxs-lookup"><span data-stu-id="74676-103">Creates an auto-reset event object for the implementation of a writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74676-104">语法</span><span class="sxs-lookup"><span data-stu-id="74676-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockWriterEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74676-105">参数</span><span class="sxs-lookup"><span data-stu-id="74676-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="74676-106">[in]一个要与自动重置事件关联的 cookie。</span><span class="sxs-lookup"><span data-stu-id="74676-106">[in] A cookie to associate with the auto-reset event.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="74676-107">[out]指向的地址的指针[IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)实例，或如果无法创建事件对象为 null。</span><span class="sxs-lookup"><span data-stu-id="74676-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74676-108">返回值</span><span class="sxs-lookup"><span data-stu-id="74676-108">Return Value</span></span>  
  
|<span data-ttu-id="74676-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="74676-109">HRESULT</span></span>|<span data-ttu-id="74676-110">描述</span><span class="sxs-lookup"><span data-stu-id="74676-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="74676-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="74676-111">S_OK</span></span>|<span data-ttu-id="74676-112">`CreateRWLockWriterEvent`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="74676-112">`CreateRWLockWriterEvent` returned successfully.</span></span>|  
|<span data-ttu-id="74676-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="74676-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="74676-114">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="74676-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="74676-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="74676-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="74676-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="74676-116">The call timed out.</span></span>|  
|<span data-ttu-id="74676-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="74676-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="74676-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="74676-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="74676-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="74676-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="74676-120">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="74676-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="74676-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="74676-121">E_FAIL</span></span>|<span data-ttu-id="74676-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="74676-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="74676-123">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="74676-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="74676-124">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="74676-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="74676-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="74676-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="74676-126">没有足够的内存已可用于创建请求的事件对象。</span><span class="sxs-lookup"><span data-stu-id="74676-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74676-127">备注</span><span class="sxs-lookup"><span data-stu-id="74676-127">Remarks</span></span>  
 <span data-ttu-id="74676-128">CLR 调用`CreateRWLockWriterEvent`方法要获取对引用`IHostAutoEvent`实例，以使用在其实现中的编写器锁。</span><span class="sxs-lookup"><span data-stu-id="74676-128">The CLR calls the `CreateRWLockWriterEvent` method to get a reference to an `IHostAutoEvent` instance to use in its implementation of a writer lock.</span></span> <span data-ttu-id="74676-129">主机可以使用指定的 cookie 来确定哪些任务在等待锁的调用的迭代方法[ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="74676-129">The host can use the specified cookie to determine which tasks are waiting on the lock by calling the iteration methods of the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74676-130">惠?</span><span class="sxs-lookup"><span data-stu-id="74676-130">Requirements</span></span>  
 <span data-ttu-id="74676-131">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="74676-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74676-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="74676-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="74676-133">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="74676-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74676-134">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74676-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74676-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="74676-135">See Also</span></span>  
 [<span data-ttu-id="74676-136">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="74676-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="74676-137">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="74676-137">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="74676-138">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="74676-138">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="74676-139">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="74676-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
