---
title: "IHostSyncManager 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager
helpviewer_keywords: IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 951f7808e238f514ffcf19a8dda0033b7b07172c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="0ba37-102">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="0ba37-102">IHostSyncManager Interface</span></span>
<span data-ttu-id="0ba37-103">提供允许公共语言运行时 (CLR) 以通过调用而不是使用 Win32 同步函数主机创建同步基元的方法。</span><span class="sxs-lookup"><span data-stu-id="0ba37-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0ba37-104">方法</span><span class="sxs-lookup"><span data-stu-id="0ba37-104">Methods</span></span>  
  
|<span data-ttu-id="0ba37-105">方法</span><span class="sxs-lookup"><span data-stu-id="0ba37-105">Method</span></span>|<span data-ttu-id="0ba37-106">描述</span><span class="sxs-lookup"><span data-stu-id="0ba37-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0ba37-107">CreateAutoEvent 方法</span><span class="sxs-lookup"><span data-stu-id="0ba37-107">CreateAutoEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="0ba37-108">创建一个自动重置事件对象。</span><span class="sxs-lookup"><span data-stu-id="0ba37-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="0ba37-109">CreateCrst 方法</span><span class="sxs-lookup"><span data-stu-id="0ba37-109">CreateCrst Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="0ba37-110">创建同步的关键部分对象。</span><span class="sxs-lookup"><span data-stu-id="0ba37-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="0ba37-111">CreateCrstWithSpinCount 方法</span><span class="sxs-lookup"><span data-stu-id="0ba37-111">CreateCrstWithSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="0ba37-112">创建具有同步的重试次数的关键部分对象。</span><span class="sxs-lookup"><span data-stu-id="0ba37-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="0ba37-113">CreateManualEvent 方法</span><span class="sxs-lookup"><span data-stu-id="0ba37-113">CreateManualEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="0ba37-114">创建手动重置事件对象。</span><span class="sxs-lookup"><span data-stu-id="0ba37-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="0ba37-115">CreateMonitorEvent 方法</span><span class="sxs-lookup"><span data-stu-id="0ba37-115">CreateMonitorEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="0ba37-116">创建监视的自动重置事件对象。</span><span class="sxs-lookup"><span data-stu-id="0ba37-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="0ba37-117">CreateRWLockReaderEvent 方法</span><span class="sxs-lookup"><span data-stu-id="0ba37-117">CreateRWLockReaderEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="0ba37-118">为创建一个手动重置事件对象将读线程锁的实现。</span><span class="sxs-lookup"><span data-stu-id="0ba37-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="0ba37-119">CreateRWLockWriterEvent 方法</span><span class="sxs-lookup"><span data-stu-id="0ba37-119">CreateRWLockWriterEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="0ba37-120">创建用于实现的编写器锁的自动重置事件对象。</span><span class="sxs-lookup"><span data-stu-id="0ba37-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="0ba37-121">CreateSemaphore 方法</span><span class="sxs-lookup"><span data-stu-id="0ba37-121">CreateSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="0ba37-122">创建[IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) CLR 用作等待事件信号量的对象。</span><span class="sxs-lookup"><span data-stu-id="0ba37-122">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="0ba37-123">SetCLRSyncManager 方法</span><span class="sxs-lookup"><span data-stu-id="0ba37-123">SetCLRSyncManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="0ba37-124">集[ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)实例要与当前关联`IHostSyncManager`实例。</span><span class="sxs-lookup"><span data-stu-id="0ba37-124">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ba37-125">备注</span><span class="sxs-lookup"><span data-stu-id="0ba37-125">Remarks</span></span>  
 <span data-ttu-id="0ba37-126">CLR 发现主机的实现`IHostSyncManager`通过调用[ihostcontrol:: Gethostmanager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)方法替换`IID`IID_IHostSyncManager。</span><span class="sxs-lookup"><span data-stu-id="0ba37-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ba37-127">要求</span><span class="sxs-lookup"><span data-stu-id="0ba37-127">Requirements</span></span>  
 <span data-ttu-id="0ba37-128">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0ba37-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ba37-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0ba37-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0ba37-130">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0ba37-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ba37-131">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ba37-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ba37-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ba37-132">See Also</span></span>  
 [<span data-ttu-id="0ba37-133">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="0ba37-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="0ba37-134">承载接口</span><span class="sxs-lookup"><span data-stu-id="0ba37-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
