---
title: IHostSyncManager::CreateRWLockReaderEvent 方法
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateRWLockReaderEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateRWLockReaderEvent
helpviewer_keywords:
- CreateRWLockReaderEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockReaderEvent method [.NET Framework hosting]
ms.assetid: 68c4ea19-c47c-45c6-b420-d3a2ba1c2d50
topic_type:
- apiref
ms.openlocfilehash: 64cf6c80ab1cf4b3ca52c60d6e72b54c438f9f4a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195841"
---
# <a name="ihostsyncmanagercreaterwlockreaderevent-method"></a><span data-ttu-id="575f8-102">IHostSyncManager::CreateRWLockReaderEvent 方法</span><span class="sxs-lookup"><span data-stu-id="575f8-102">IHostSyncManager::CreateRWLockReaderEvent Method</span></span>
<span data-ttu-id="575f8-103">创建手动重置的事件对象，以便实现读取器锁。</span><span class="sxs-lookup"><span data-stu-id="575f8-103">Creates a manual-reset event object for the implementation of a reader lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="575f8-104">语法</span><span class="sxs-lookup"><span data-stu-id="575f8-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockReaderEvent (  
    [in]  BOOL bInitialState,  
    [in]  SIZE_T cookie,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="575f8-105">参数</span><span class="sxs-lookup"><span data-stu-id="575f8-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="575f8-106">[in] `true`，如果 `ppEvent` 应收到信号，则为;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="575f8-106">[in] `true`, if `ppEvent` should be signaled; otherwise, `false`.</span></span>  
  
 `cookie`  
 <span data-ttu-id="575f8-107">中与读取器锁关联的 cookie。</span><span class="sxs-lookup"><span data-stu-id="575f8-107">[in] A cookie to associate with the reader lock.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="575f8-108">弄指向[IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)实例的地址的指针; 如果无法创建事件对象，则为 null。</span><span class="sxs-lookup"><span data-stu-id="575f8-108">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="575f8-109">返回值</span><span class="sxs-lookup"><span data-stu-id="575f8-109">Return Value</span></span>  
  
|<span data-ttu-id="575f8-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="575f8-110">HRESULT</span></span>|<span data-ttu-id="575f8-111">描述</span><span class="sxs-lookup"><span data-stu-id="575f8-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="575f8-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="575f8-112">S_OK</span></span>|<span data-ttu-id="575f8-113">`CreateRWLockReaderEvent` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="575f8-113">`CreateRWLockReaderEvent` returned successfully.</span></span>|  
|<span data-ttu-id="575f8-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="575f8-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="575f8-115">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="575f8-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="575f8-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="575f8-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="575f8-117">调用超时。</span><span class="sxs-lookup"><span data-stu-id="575f8-117">The call timed out.</span></span>|  
|<span data-ttu-id="575f8-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="575f8-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="575f8-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="575f8-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="575f8-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="575f8-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="575f8-121">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="575f8-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="575f8-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="575f8-122">E_FAIL</span></span>|<span data-ttu-id="575f8-123">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="575f8-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="575f8-124">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="575f8-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="575f8-125">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="575f8-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="575f8-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="575f8-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="575f8-127">没有足够的内存可用于创建请求的事件对象。</span><span class="sxs-lookup"><span data-stu-id="575f8-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="575f8-128">备注</span><span class="sxs-lookup"><span data-stu-id="575f8-128">Remarks</span></span>  
 <span data-ttu-id="575f8-129">CLR 调用 `CreateRWLockReaderEvent` 获取对 `IHostManualEvent` 实例的引用，以便在它的读取器锁实现中使用。</span><span class="sxs-lookup"><span data-stu-id="575f8-129">The CLR calls `CreateRWLockReaderEvent` to get a reference to an `IHostManualEvent` instance to use in its implementation of a reader lock.</span></span> <span data-ttu-id="575f8-130">主机可以使用 cookie 来确定哪些任务正在等待读取器锁（通过查询[ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)接口）。</span><span class="sxs-lookup"><span data-stu-id="575f8-130">The host can use the cookie to determine which tasks are waiting on the reader lock by querying the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="575f8-131">要求</span><span class="sxs-lookup"><span data-stu-id="575f8-131">Requirements</span></span>  
 <span data-ttu-id="575f8-132">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="575f8-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="575f8-133">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="575f8-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="575f8-134">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="575f8-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="575f8-135">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="575f8-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="575f8-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="575f8-136">See also</span></span>

- [<span data-ttu-id="575f8-137">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="575f8-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="575f8-138">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="575f8-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="575f8-139">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="575f8-139">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="575f8-140">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="575f8-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
