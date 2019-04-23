---
title: IHostSyncManager::CreateRWLockWriterEvent 方法
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateRWLockWriterEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateRWLockWriterEvent
helpviewer_keywords:
- CreateRWLockWriterEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockWriterEvent method [.NET Framework hosting]
ms.assetid: 70e488c2-cf53-4dc0-ba52-74372d215c41
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e994cf5c68871d6e81d53ac522259bc973c173ea
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223610"
---
# <a name="ihostsyncmanagercreaterwlockwriterevent-method"></a><span data-ttu-id="89722-102">IHostSyncManager::CreateRWLockWriterEvent 方法</span><span class="sxs-lookup"><span data-stu-id="89722-102">IHostSyncManager::CreateRWLockWriterEvent Method</span></span>
<span data-ttu-id="89722-103">创建的编写器锁实现自动重置事件对象。</span><span class="sxs-lookup"><span data-stu-id="89722-103">Creates an auto-reset event object for the implementation of a writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89722-104">语法</span><span class="sxs-lookup"><span data-stu-id="89722-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockWriterEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89722-105">参数</span><span class="sxs-lookup"><span data-stu-id="89722-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="89722-106">[in]一个要与自动重置事件关联的 cookie。</span><span class="sxs-lookup"><span data-stu-id="89722-106">[in] A cookie to associate with the auto-reset event.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="89722-107">[out]指向的地址的指针[IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)实例，或如果无法创建事件对象，则为 null。</span><span class="sxs-lookup"><span data-stu-id="89722-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="89722-108">返回值</span><span class="sxs-lookup"><span data-stu-id="89722-108">Return Value</span></span>  
  
|<span data-ttu-id="89722-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="89722-109">HRESULT</span></span>|<span data-ttu-id="89722-110">描述</span><span class="sxs-lookup"><span data-stu-id="89722-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="89722-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="89722-111">S_OK</span></span>|<span data-ttu-id="89722-112">`CreateRWLockWriterEvent` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="89722-112">`CreateRWLockWriterEvent` returned successfully.</span></span>|  
|<span data-ttu-id="89722-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="89722-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="89722-114">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="89722-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="89722-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="89722-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="89722-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="89722-116">The call timed out.</span></span>|  
|<span data-ttu-id="89722-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="89722-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="89722-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="89722-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="89722-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="89722-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="89722-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="89722-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="89722-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="89722-121">E_FAIL</span></span>|<span data-ttu-id="89722-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="89722-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="89722-123">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="89722-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="89722-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="89722-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="89722-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="89722-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="89722-126">没有足够的内存是可用于创建请求的事件对象。</span><span class="sxs-lookup"><span data-stu-id="89722-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89722-127">备注</span><span class="sxs-lookup"><span data-stu-id="89722-127">Remarks</span></span>  
 <span data-ttu-id="89722-128">CLR 调用`CreateRWLockWriterEvent`方法以获取对引用`IHostAutoEvent`实例，以使用在其实现中的编写器锁。</span><span class="sxs-lookup"><span data-stu-id="89722-128">The CLR calls the `CreateRWLockWriterEvent` method to get a reference to an `IHostAutoEvent` instance to use in its implementation of a writer lock.</span></span> <span data-ttu-id="89722-129">主机可以使用指定的 cookie 来确定哪些任务正在等待锁通过调用的迭代方法[ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="89722-129">The host can use the specified cookie to determine which tasks are waiting on the lock by calling the iteration methods of the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89722-130">要求</span><span class="sxs-lookup"><span data-stu-id="89722-130">Requirements</span></span>  
 <span data-ttu-id="89722-131">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="89722-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89722-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="89722-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="89722-133">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="89722-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="89722-134">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89722-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89722-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="89722-135">See also</span></span>

- [<span data-ttu-id="89722-136">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="89722-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="89722-137">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="89722-137">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="89722-138">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="89722-138">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="89722-139">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="89722-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
