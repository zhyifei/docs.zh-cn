---
title: IHostSyncManager 接口
ms.date: 03/30/2017
api_name:
- IHostSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager
helpviewer_keywords:
- IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type:
- apiref
ms.openlocfilehash: 02a59b8ef63f7e866e419db4e3232da7eec19558
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132633"
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="78416-102">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="78416-102">IHostSyncManager Interface</span></span>
<span data-ttu-id="78416-103">提供一些方法，使公共语言运行时（CLR）可以通过调用主机而不是使用 Win32 同步函数来创建同步基元。</span><span class="sxs-lookup"><span data-stu-id="78416-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="78416-104">方法</span><span class="sxs-lookup"><span data-stu-id="78416-104">Methods</span></span>  
  
|<span data-ttu-id="78416-105">方法</span><span class="sxs-lookup"><span data-stu-id="78416-105">Method</span></span>|<span data-ttu-id="78416-106">描述</span><span class="sxs-lookup"><span data-stu-id="78416-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="78416-107">CreateAutoEvent 方法</span><span class="sxs-lookup"><span data-stu-id="78416-107">CreateAutoEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="78416-108">创建自动重置事件对象。</span><span class="sxs-lookup"><span data-stu-id="78416-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="78416-109">CreateCrst 方法</span><span class="sxs-lookup"><span data-stu-id="78416-109">CreateCrst Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="78416-110">创建用于同步的临界区对象。</span><span class="sxs-lookup"><span data-stu-id="78416-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="78416-111">CreateCrstWithSpinCount 方法</span><span class="sxs-lookup"><span data-stu-id="78416-111">CreateCrstWithSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="78416-112">使用自旋计数为同步创建一个临界区对象。</span><span class="sxs-lookup"><span data-stu-id="78416-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="78416-113">CreateManualEvent 方法</span><span class="sxs-lookup"><span data-stu-id="78416-113">CreateManualEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="78416-114">创建手动重置的事件对象。</span><span class="sxs-lookup"><span data-stu-id="78416-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="78416-115">CreateMonitorEvent 方法</span><span class="sxs-lookup"><span data-stu-id="78416-115">CreateMonitorEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="78416-116">创建监视的自动重置事件对象。</span><span class="sxs-lookup"><span data-stu-id="78416-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="78416-117">CreateRWLockReaderEvent 方法</span><span class="sxs-lookup"><span data-stu-id="78416-117">CreateRWLockReaderEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="78416-118">创建手动重置的事件对象，以便实现读取器锁。</span><span class="sxs-lookup"><span data-stu-id="78416-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="78416-119">CreateRWLockWriterEvent 方法</span><span class="sxs-lookup"><span data-stu-id="78416-119">CreateRWLockWriterEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="78416-120">创建自动重置事件对象，以便实现编写器锁。</span><span class="sxs-lookup"><span data-stu-id="78416-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="78416-121">CreateSemaphore 方法</span><span class="sxs-lookup"><span data-stu-id="78416-121">CreateSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="78416-122">为 CLR 创建一个[IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)对象，以用作等待事件的信号量。</span><span class="sxs-lookup"><span data-stu-id="78416-122">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="78416-123">SetCLRSyncManager 方法</span><span class="sxs-lookup"><span data-stu-id="78416-123">SetCLRSyncManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="78416-124">设置要与当前 `IHostSyncManager` 实例关联的[ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="78416-124">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78416-125">备注</span><span class="sxs-lookup"><span data-stu-id="78416-125">Remarks</span></span>  
 <span data-ttu-id="78416-126">CLR 通过使用 `IID` IID_IHostSyncManager 调用[IHostControl：： GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)方法来发现主机的 `IHostSyncManager` 实现。</span><span class="sxs-lookup"><span data-stu-id="78416-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78416-127">要求</span><span class="sxs-lookup"><span data-stu-id="78416-127">Requirements</span></span>  
 <span data-ttu-id="78416-128">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="78416-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78416-129">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="78416-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="78416-130">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="78416-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="78416-131">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78416-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78416-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="78416-132">See also</span></span>

- [<span data-ttu-id="78416-133">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="78416-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="78416-134">承载接口</span><span class="sxs-lookup"><span data-stu-id="78416-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
