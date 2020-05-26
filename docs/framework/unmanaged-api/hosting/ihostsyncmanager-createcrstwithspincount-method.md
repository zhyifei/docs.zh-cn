---
title: IHostSyncManager::CreateCrstWithSpinCount 方法
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateCrstWithSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateCrstWithSpinCount
helpviewer_keywords:
- CreateCrstWithSpinCount method [.NET Framework hosting]
- IHostSyncManager::CreateCrstWithSpinCount method [.NET Framework hosting]
ms.assetid: 7280fa8c-3639-4abf-91cb-bc343da742d1
topic_type:
- apiref
ms.openlocfilehash: 86bc320c28a5fbf122d234a4a1f15b674628c0b5
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803402"
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a><span data-ttu-id="49a94-102">IHostSyncManager::CreateCrstWithSpinCount 方法</span><span class="sxs-lookup"><span data-stu-id="49a94-102">IHostSyncManager::CreateCrstWithSpinCount Method</span></span>
<span data-ttu-id="49a94-103">使用自旋计数为同步创建一个临界区对象。</span><span class="sxs-lookup"><span data-stu-id="49a94-103">Creates a critical section object with spin count for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49a94-104">语法</span><span class="sxs-lookup"><span data-stu-id="49a94-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49a94-105">参数</span><span class="sxs-lookup"><span data-stu-id="49a94-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="49a94-106">中为临界区对象指定自旋计数。</span><span class="sxs-lookup"><span data-stu-id="49a94-106">[in] Specifies the spin count for the critical section object.</span></span>  
  
 `ppCrst`  
 <span data-ttu-id="49a94-107">弄指向[IHostCrst](ihostcrst-interface.md)实例的地址的指针; 如果无法创建关键节，则为 null。</span><span class="sxs-lookup"><span data-stu-id="49a94-107">[out] A pointer to the address of an [IHostCrst](ihostcrst-interface.md) instance, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49a94-108">返回值</span><span class="sxs-lookup"><span data-stu-id="49a94-108">Return Value</span></span>  
  
|<span data-ttu-id="49a94-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="49a94-109">HRESULT</span></span>|<span data-ttu-id="49a94-110">说明</span><span class="sxs-lookup"><span data-stu-id="49a94-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="49a94-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="49a94-111">S_OK</span></span>|<span data-ttu-id="49a94-112">`CreateCrstWithSpinCount`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="49a94-112">`CreateCrstWithSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="49a94-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="49a94-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="49a94-114">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="49a94-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="49a94-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="49a94-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="49a94-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="49a94-116">The call timed out.</span></span>|  
|<span data-ttu-id="49a94-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="49a94-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="49a94-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="49a94-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="49a94-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="49a94-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="49a94-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="49a94-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="49a94-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="49a94-121">E_FAIL</span></span>|<span data-ttu-id="49a94-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="49a94-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="49a94-123">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="49a94-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="49a94-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="49a94-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="49a94-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="49a94-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="49a94-126">没有足够的内存可用于创建请求的关键部分。</span><span class="sxs-lookup"><span data-stu-id="49a94-126">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49a94-127">备注</span><span class="sxs-lookup"><span data-stu-id="49a94-127">Remarks</span></span>  
 <span data-ttu-id="49a94-128">自旋计数仅在多处理器系统上使用。</span><span class="sxs-lookup"><span data-stu-id="49a94-128">A spin count is used only on a multi-processor system.</span></span> <span data-ttu-id="49a94-129">自旋计数指定调用线程在与不可用关键部分关联的信号量上执行等待操作之前必须旋转的次数。</span><span class="sxs-lookup"><span data-stu-id="49a94-129">The spin count specifies the number of times a calling thread must spin before it performs a wait operation on a semaphore that is associated with an unavailable critical section.</span></span> <span data-ttu-id="49a94-130">如果在自旋操作期间关键部分变为免费，则调用线程将避免等待操作。</span><span class="sxs-lookup"><span data-stu-id="49a94-130">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span> <span data-ttu-id="49a94-131">`CreateCrstWithSpinCount`对 Win32 函数进行镜像 `InitializeCriticalSectionAndSpinCount` 。</span><span class="sxs-lookup"><span data-stu-id="49a94-131">`CreateCrstWithSpinCount` mirrors the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49a94-132">要求</span><span class="sxs-lookup"><span data-stu-id="49a94-132">Requirements</span></span>  
 <span data-ttu-id="49a94-133">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="49a94-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49a94-134">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="49a94-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="49a94-135">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="49a94-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="49a94-136">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49a94-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49a94-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49a94-137">See also</span></span>

- [<span data-ttu-id="49a94-138">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="49a94-138">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="49a94-139">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="49a94-139">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="49a94-140">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="49a94-140">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
