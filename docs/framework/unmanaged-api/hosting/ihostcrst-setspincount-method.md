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
ms.openlocfilehash: 2436809f35d5c46416f48987cc92feb51d291a6a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804882"
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="a3b0b-102">IHostCrst::SetSpinCount 方法</span><span class="sxs-lookup"><span data-stu-id="a3b0b-102">IHostCrst::SetSpinCount Method</span></span>
<span data-ttu-id="a3b0b-103">为当前的[IHostCrst](ihostcrst-interface.md)实例设置自旋计数。</span><span class="sxs-lookup"><span data-stu-id="a3b0b-103">Sets the spin count for the current [IHostCrst](ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3b0b-104">语法</span><span class="sxs-lookup"><span data-stu-id="a3b0b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3b0b-105">参数</span><span class="sxs-lookup"><span data-stu-id="a3b0b-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="a3b0b-106">中当前实例的新自旋计数 `IHostCrst` 。</span><span class="sxs-lookup"><span data-stu-id="a3b0b-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3b0b-107">返回值</span><span class="sxs-lookup"><span data-stu-id="a3b0b-107">Return Value</span></span>  
  
|<span data-ttu-id="a3b0b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a3b0b-108">HRESULT</span></span>|<span data-ttu-id="a3b0b-109">说明</span><span class="sxs-lookup"><span data-stu-id="a3b0b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a3b0b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a3b0b-110">S_OK</span></span>|<span data-ttu-id="a3b0b-111">`SetSpinCount`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="a3b0b-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="a3b0b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a3b0b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a3b0b-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="a3b0b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a3b0b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a3b0b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a3b0b-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="a3b0b-115">The call timed out.</span></span>|  
|<span data-ttu-id="a3b0b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a3b0b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a3b0b-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="a3b0b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a3b0b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a3b0b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a3b0b-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="a3b0b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a3b0b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a3b0b-120">E_FAIL</span></span>|<span data-ttu-id="a3b0b-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="a3b0b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a3b0b-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="a3b0b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a3b0b-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="a3b0b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3b0b-124">备注</span><span class="sxs-lookup"><span data-stu-id="a3b0b-124">Remarks</span></span>  
 <span data-ttu-id="a3b0b-125">在多处理器系统上，如果当前实例所表示的临界区 `IHostCrst` 不可用，则调用线程将在 `dwSpinCount` 调用[IHostSemaphore：： Wait](ihostsemaphore-wait-method.md)与临界区关联的信号量之前，旋转时间。</span><span class="sxs-lookup"><span data-stu-id="a3b0b-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="a3b0b-126">如果在自旋操作期间关键部分变为免费，则调用线程将避免等待操作。</span><span class="sxs-lookup"><span data-stu-id="a3b0b-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="a3b0b-127">的用法与 `dwSpinCount` Win32 函数中具有相同名称的参数的用法相同 `InitializeCriticalSectionAndSpinCount` 。</span><span class="sxs-lookup"><span data-stu-id="a3b0b-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3b0b-128">要求</span><span class="sxs-lookup"><span data-stu-id="a3b0b-128">Requirements</span></span>  
 <span data-ttu-id="a3b0b-129">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a3b0b-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3b0b-130">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a3b0b-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a3b0b-131">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="a3b0b-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3b0b-132">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3b0b-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3b0b-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3b0b-133">See also</span></span>

- [<span data-ttu-id="a3b0b-134">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="a3b0b-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="a3b0b-135">IHostCrst 接口</span><span class="sxs-lookup"><span data-stu-id="a3b0b-135">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="a3b0b-136">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="a3b0b-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
