---
title: IHostSyncManager::CreateSemaphore 方法
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateSemaphore
helpviewer_keywords:
- CreateSemaphore method [.NET Framework hosting]
- IHostSyncManager::CreateSemaphore method [.NET Framework hosting]
ms.assetid: 37679e94-5ff9-4173-8fa5-457febeb89bf
topic_type:
- apiref
ms.openlocfilehash: 680280e959d523356b95a5a4d9390c80720c0330
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803143"
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a><span data-ttu-id="8ac1f-102">IHostSyncManager::CreateSemaphore 方法</span><span class="sxs-lookup"><span data-stu-id="8ac1f-102">IHostSyncManager::CreateSemaphore Method</span></span>
<span data-ttu-id="8ac1f-103">创建公共语言运行时（CLR）的[IHostSemaphore](ihostsemaphore-interface.md)对象，以用作等待事件的信号量。</span><span class="sxs-lookup"><span data-stu-id="8ac1f-103">Creates an [IHostSemaphore](ihostsemaphore-interface.md) object for the common language runtime (CLR) to use as a semaphore for wait events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ac1f-104">语法</span><span class="sxs-lookup"><span data-stu-id="8ac1f-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ac1f-105">参数</span><span class="sxs-lookup"><span data-stu-id="8ac1f-105">Parameters</span></span>  
 `dwInitial`  
 <span data-ttu-id="8ac1f-106">中的初始计数 `ppSemaphore` 。</span><span class="sxs-lookup"><span data-stu-id="8ac1f-106">[in] The initial count for `ppSemaphore`.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="8ac1f-107">中的最大计数 `ppSemaphore` 。</span><span class="sxs-lookup"><span data-stu-id="8ac1f-107">[in] The maximum count for `ppSemaphore`.</span></span>  
  
 `ppSemaphore`  
 <span data-ttu-id="8ac1f-108">弄指向实例的地址的指针 `IHostSemaphore` ; 如果无法创建信号量，则为 null。</span><span class="sxs-lookup"><span data-stu-id="8ac1f-108">[out] A pointer to the address of an `IHostSemaphore` instance, or null if the semaphore could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ac1f-109">返回值</span><span class="sxs-lookup"><span data-stu-id="8ac1f-109">Return Value</span></span>  
  
|<span data-ttu-id="8ac1f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8ac1f-110">HRESULT</span></span>|<span data-ttu-id="8ac1f-111">说明</span><span class="sxs-lookup"><span data-stu-id="8ac1f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8ac1f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="8ac1f-112">S_OK</span></span>|<span data-ttu-id="8ac1f-113">`CreateSemaphore`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="8ac1f-113">`CreateSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="8ac1f-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8ac1f-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8ac1f-115">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="8ac1f-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8ac1f-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8ac1f-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8ac1f-117">调用超时。</span><span class="sxs-lookup"><span data-stu-id="8ac1f-117">The call timed out.</span></span>|  
|<span data-ttu-id="8ac1f-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8ac1f-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8ac1f-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="8ac1f-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8ac1f-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8ac1f-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8ac1f-121">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="8ac1f-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8ac1f-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8ac1f-122">E_FAIL</span></span>|<span data-ttu-id="8ac1f-123">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="8ac1f-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8ac1f-124">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="8ac1f-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8ac1f-125">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="8ac1f-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8ac1f-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="8ac1f-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="8ac1f-127">没有足够的内存可用于创建请求的事件对象。</span><span class="sxs-lookup"><span data-stu-id="8ac1f-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ac1f-128">备注</span><span class="sxs-lookup"><span data-stu-id="8ac1f-128">Remarks</span></span>  
 <span data-ttu-id="8ac1f-129">`CreateSemaphore`镜像同名的 Win32 函数。</span><span class="sxs-lookup"><span data-stu-id="8ac1f-129">`CreateSemaphore` mirrors the Win32 function that has the same name.</span></span> <span data-ttu-id="8ac1f-130">`dwInitial`和 `dwMax` 参数分别对信号量和参数使用相同的语义 `lInitialCount` `lMaximumCount` 。</span><span class="sxs-lookup"><span data-stu-id="8ac1f-130">The `dwInitial` and `dwMax` parameters use the same semantics for the semaphore count as the Win32 `lInitialCount` and `lMaximumCount` parameters, respectively.</span></span> <span data-ttu-id="8ac1f-131">`dwInitial`必须介于零和 `dwMax` （含）之间。</span><span class="sxs-lookup"><span data-stu-id="8ac1f-131">`dwInitial` must be between zero and `dwMax`, inclusive.</span></span> <span data-ttu-id="8ac1f-132">`dwMax`必须大于零。</span><span class="sxs-lookup"><span data-stu-id="8ac1f-132">`dwMax` must be greater than zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ac1f-133">要求</span><span class="sxs-lookup"><span data-stu-id="8ac1f-133">Requirements</span></span>  
 <span data-ttu-id="8ac1f-134">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8ac1f-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ac1f-135">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8ac1f-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8ac1f-136">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="8ac1f-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ac1f-137">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ac1f-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ac1f-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ac1f-138">See also</span></span>

- [<span data-ttu-id="8ac1f-139">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="8ac1f-139">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="8ac1f-140">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="8ac1f-140">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="8ac1f-141">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="8ac1f-141">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
