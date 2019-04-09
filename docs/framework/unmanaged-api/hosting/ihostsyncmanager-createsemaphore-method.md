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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ef9a5896c2ecc54b7fd48670f751d193ac74554
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138614"
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a><span data-ttu-id="1cf20-102">IHostSyncManager::CreateSemaphore 方法</span><span class="sxs-lookup"><span data-stu-id="1cf20-102">IHostSyncManager::CreateSemaphore Method</span></span>
<span data-ttu-id="1cf20-103">创建[IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)公共语言运行时 (CLR) 将用作一个信号量的等待事件的对象。</span><span class="sxs-lookup"><span data-stu-id="1cf20-103">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the common language runtime (CLR) to use as a semaphore for wait events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cf20-104">语法</span><span class="sxs-lookup"><span data-stu-id="1cf20-104">Syntax</span></span>  
  
```  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1cf20-105">参数</span><span class="sxs-lookup"><span data-stu-id="1cf20-105">Parameters</span></span>  
 `dwInitial`  
 <span data-ttu-id="1cf20-106">[in]初始计数`ppSemaphore`。</span><span class="sxs-lookup"><span data-stu-id="1cf20-106">[in] The initial count for `ppSemaphore`.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="1cf20-107">[in]最大计数`ppSemaphore`。</span><span class="sxs-lookup"><span data-stu-id="1cf20-107">[in] The maximum count for `ppSemaphore`.</span></span>  
  
 `ppSemaphore`  
 <span data-ttu-id="1cf20-108">[out]指向的地址的指针`IHostSemaphore`实例，或如果无法创建信号量，则为 null。</span><span class="sxs-lookup"><span data-stu-id="1cf20-108">[out] A pointer to the address of an `IHostSemaphore` instance, or null if the semaphore could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1cf20-109">返回值</span><span class="sxs-lookup"><span data-stu-id="1cf20-109">Return Value</span></span>  
  
|<span data-ttu-id="1cf20-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1cf20-110">HRESULT</span></span>|<span data-ttu-id="1cf20-111">描述</span><span class="sxs-lookup"><span data-stu-id="1cf20-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1cf20-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="1cf20-112">S_OK</span></span>|`CreateSemaphore` <span data-ttu-id="1cf20-113">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="1cf20-113">returned successfully.</span></span>|  
|<span data-ttu-id="1cf20-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1cf20-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1cf20-115">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="1cf20-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1cf20-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1cf20-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1cf20-117">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="1cf20-117">The call timed out.</span></span>|  
|<span data-ttu-id="1cf20-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1cf20-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1cf20-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="1cf20-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1cf20-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1cf20-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1cf20-121">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="1cf20-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1cf20-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1cf20-122">E_FAIL</span></span>|<span data-ttu-id="1cf20-123">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="1cf20-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1cf20-124">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="1cf20-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1cf20-125">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="1cf20-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1cf20-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="1cf20-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="1cf20-127">没有足够的内存是可用于创建请求的事件对象。</span><span class="sxs-lookup"><span data-stu-id="1cf20-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1cf20-128">备注</span><span class="sxs-lookup"><span data-stu-id="1cf20-128">Remarks</span></span>  
 `CreateSemaphore` <span data-ttu-id="1cf20-129">镜像的 Win32 函数具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="1cf20-129">mirrors the Win32 function that has the same name.</span></span> <span data-ttu-id="1cf20-130">`dwInitial`并`dwMax`参数使用相同的语义的信号量计数为 Win32`lInitialCount`和`lMaximumCount`参数，分别。</span><span class="sxs-lookup"><span data-stu-id="1cf20-130">The `dwInitial` and `dwMax` parameters use the same semantics for the semaphore count as the Win32 `lInitialCount` and `lMaximumCount` parameters, respectively.</span></span> `dwInitial` <span data-ttu-id="1cf20-131">必须介于零和`dwMax`(含） 之间。</span><span class="sxs-lookup"><span data-stu-id="1cf20-131">must be between zero and `dwMax`, inclusive.</span></span> `dwMax` <span data-ttu-id="1cf20-132">必须是大于零。</span><span class="sxs-lookup"><span data-stu-id="1cf20-132">must be greater than zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cf20-133">要求</span><span class="sxs-lookup"><span data-stu-id="1cf20-133">Requirements</span></span>  
 <span data-ttu-id="1cf20-134">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1cf20-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cf20-135">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1cf20-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1cf20-136">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1cf20-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="1cf20-137">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="1cf20-137">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1cf20-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="1cf20-138">See also</span></span>

- [<span data-ttu-id="1cf20-139">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="1cf20-139">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="1cf20-140">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="1cf20-140">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="1cf20-141">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="1cf20-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
