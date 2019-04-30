---
title: IHostCrst::SetSpinCount 方法
ms.date: 03/30/2017
api_name:
- IHostCrst.SetSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::SetSpinCount
helpviewer_keywords:
- IHostCrst::SetSpinCount method [.NET Framework hosting]
- SetSpinCount method [.NET Framework hosting]
ms.assetid: 863fc8ce-9b8a-477e-8dd8-75c8544bb43a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ca17a6814b56c0fe781cfb28a35a576f02f1943
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967669"
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="296ce-102">IHostCrst::SetSpinCount 方法</span><span class="sxs-lookup"><span data-stu-id="296ce-102">IHostCrst::SetSpinCount Method</span></span>
<span data-ttu-id="296ce-103">设置当前的旋转计数[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="296ce-103">Sets the spin count for the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="296ce-104">语法</span><span class="sxs-lookup"><span data-stu-id="296ce-104">Syntax</span></span>  
  
```  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="296ce-105">参数</span><span class="sxs-lookup"><span data-stu-id="296ce-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="296ce-106">[in]当前新的旋转计数`IHostCrst`实例。</span><span class="sxs-lookup"><span data-stu-id="296ce-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="296ce-107">返回值</span><span class="sxs-lookup"><span data-stu-id="296ce-107">Return Value</span></span>  
  
|<span data-ttu-id="296ce-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="296ce-108">HRESULT</span></span>|<span data-ttu-id="296ce-109">描述</span><span class="sxs-lookup"><span data-stu-id="296ce-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="296ce-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="296ce-110">S_OK</span></span>|<span data-ttu-id="296ce-111">`SetSpinCount` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="296ce-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="296ce-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="296ce-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="296ce-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="296ce-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="296ce-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="296ce-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="296ce-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="296ce-115">The call timed out.</span></span>|  
|<span data-ttu-id="296ce-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="296ce-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="296ce-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="296ce-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="296ce-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="296ce-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="296ce-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="296ce-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="296ce-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="296ce-120">E_FAIL</span></span>|<span data-ttu-id="296ce-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="296ce-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="296ce-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="296ce-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="296ce-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="296ce-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="296ce-124">备注</span><span class="sxs-lookup"><span data-stu-id="296ce-124">Remarks</span></span>  
 <span data-ttu-id="296ce-125">在多处理器系统中，如果关键节表示由当前`IHostCrst`实例不可用，调用线程旋转`dwSpinCount`调用之前的时间[ihostsemaphore:: Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)上关联的信号量使用关键节。</span><span class="sxs-lookup"><span data-stu-id="296ce-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="296ce-126">如果数值调节钮操作期间，临界区变得可用，调用线程可以避免等待操作。</span><span class="sxs-lookup"><span data-stu-id="296ce-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="296ce-127">使用情况`dwSpinCount`等同于 Win32 中的相同名称的参数的使用情况`InitializeCriticalSectionAndSpinCount`函数。</span><span class="sxs-lookup"><span data-stu-id="296ce-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="296ce-128">要求</span><span class="sxs-lookup"><span data-stu-id="296ce-128">Requirements</span></span>  
 <span data-ttu-id="296ce-129">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="296ce-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="296ce-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="296ce-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="296ce-131">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="296ce-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="296ce-132">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="296ce-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="296ce-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="296ce-133">See also</span></span>

- [<span data-ttu-id="296ce-134">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="296ce-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="296ce-135">IHostCrst 接口</span><span class="sxs-lookup"><span data-stu-id="296ce-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="296ce-136">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="296ce-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
