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
ms.openlocfilehash: 13eb23c530a4fe1b491f41cc65cc94dacc9d34f4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192012"
---
# <a name="ihostsyncmanagercreaterwlockwriterevent-method"></a><span data-ttu-id="373c0-102">IHostSyncManager::CreateRWLockWriterEvent 方法</span><span class="sxs-lookup"><span data-stu-id="373c0-102">IHostSyncManager::CreateRWLockWriterEvent Method</span></span>
<span data-ttu-id="373c0-103">创建自动重置事件对象，以便实现编写器锁。</span><span class="sxs-lookup"><span data-stu-id="373c0-103">Creates an auto-reset event object for the implementation of a writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="373c0-104">语法</span><span class="sxs-lookup"><span data-stu-id="373c0-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockWriterEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="373c0-105">参数</span><span class="sxs-lookup"><span data-stu-id="373c0-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="373c0-106">中与自动重置事件关联的 cookie。</span><span class="sxs-lookup"><span data-stu-id="373c0-106">[in] A cookie to associate with the auto-reset event.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="373c0-107">弄指向[IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)实例的地址的指针; 如果无法创建事件对象，则为 null。</span><span class="sxs-lookup"><span data-stu-id="373c0-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="373c0-108">返回值</span><span class="sxs-lookup"><span data-stu-id="373c0-108">Return Value</span></span>  
  
|<span data-ttu-id="373c0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="373c0-109">HRESULT</span></span>|<span data-ttu-id="373c0-110">描述</span><span class="sxs-lookup"><span data-stu-id="373c0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="373c0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="373c0-111">S_OK</span></span>|<span data-ttu-id="373c0-112">`CreateRWLockWriterEvent` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="373c0-112">`CreateRWLockWriterEvent` returned successfully.</span></span>|  
|<span data-ttu-id="373c0-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="373c0-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="373c0-114">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="373c0-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="373c0-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="373c0-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="373c0-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="373c0-116">The call timed out.</span></span>|  
|<span data-ttu-id="373c0-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="373c0-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="373c0-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="373c0-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="373c0-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="373c0-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="373c0-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="373c0-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="373c0-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="373c0-121">E_FAIL</span></span>|<span data-ttu-id="373c0-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="373c0-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="373c0-123">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="373c0-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="373c0-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="373c0-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="373c0-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="373c0-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="373c0-126">没有足够的内存可用于创建请求的事件对象。</span><span class="sxs-lookup"><span data-stu-id="373c0-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="373c0-127">备注</span><span class="sxs-lookup"><span data-stu-id="373c0-127">Remarks</span></span>  
 <span data-ttu-id="373c0-128">CLR 调用 `CreateRWLockWriterEvent` 方法来获取对要在其编写器锁实现中使用的 `IHostAutoEvent` 实例的引用。</span><span class="sxs-lookup"><span data-stu-id="373c0-128">The CLR calls the `CreateRWLockWriterEvent` method to get a reference to an `IHostAutoEvent` instance to use in its implementation of a writer lock.</span></span> <span data-ttu-id="373c0-129">主机可以通过调用[ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)接口的迭代方法，使用指定的 cookie 来确定哪些任务正在等待锁定。</span><span class="sxs-lookup"><span data-stu-id="373c0-129">The host can use the specified cookie to determine which tasks are waiting on the lock by calling the iteration methods of the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="373c0-130">要求</span><span class="sxs-lookup"><span data-stu-id="373c0-130">Requirements</span></span>  
 <span data-ttu-id="373c0-131">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="373c0-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="373c0-132">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="373c0-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="373c0-133">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="373c0-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="373c0-134">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="373c0-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="373c0-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="373c0-135">See also</span></span>

- [<span data-ttu-id="373c0-136">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="373c0-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="373c0-137">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="373c0-137">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="373c0-138">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="373c0-138">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="373c0-139">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="373c0-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
