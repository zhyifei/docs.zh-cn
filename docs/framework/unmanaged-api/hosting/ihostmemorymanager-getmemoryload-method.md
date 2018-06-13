---
title: IHostMemoryManager::GetMemoryLoad 方法
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.GetMemoryLoad
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::GetMemoryLoad
helpviewer_keywords:
- IHostMemoryManager::GetMemoryLoad method [.NET Framework hosting]
- GetMemoryLoad method [.NET Framework hosting]
ms.assetid: e8138f6e-a0a4-48d4-8dae-9466b4dc6180
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b92ef3a6d7eb45a3b978c916c406bfa6199f17d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440143"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a><span data-ttu-id="c6c2e-102">IHostMemoryManager::GetMemoryLoad 方法</span><span class="sxs-lookup"><span data-stu-id="c6c2e-102">IHostMemoryManager::GetMemoryLoad Method</span></span>
<span data-ttu-id="c6c2e-103">获取当前已在使用中，并因此不可用，报告的主机的物理内存量。</span><span class="sxs-lookup"><span data-stu-id="c6c2e-103">Gets the amount of physical memory that is currently in use, and therefore unavailable, as reported by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6c2e-104">语法</span><span class="sxs-lookup"><span data-stu-id="c6c2e-104">Syntax</span></span>  
  
```  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,   
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c6c2e-105">参数</span><span class="sxs-lookup"><span data-stu-id="c6c2e-105">Parameters</span></span>  
 `pMemoryLoad`  
 <span data-ttu-id="c6c2e-106">[out]指向当前正在使用的总物理内存的近似百分比的指针。</span><span class="sxs-lookup"><span data-stu-id="c6c2e-106">[out] A pointer to the approximate percentage of total physical memory that is currently in use.</span></span>  
  
 `pAvailableBytes`  
 <span data-ttu-id="c6c2e-107">[out]指向公共语言运行时 (CLR) 可用的字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="c6c2e-107">[out] A pointer to the number of bytes available to the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6c2e-108">返回值</span><span class="sxs-lookup"><span data-stu-id="c6c2e-108">Return Value</span></span>  
  
|<span data-ttu-id="c6c2e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c6c2e-109">HRESULT</span></span>|<span data-ttu-id="c6c2e-110">描述</span><span class="sxs-lookup"><span data-stu-id="c6c2e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c6c2e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c6c2e-111">S_OK</span></span>|<span data-ttu-id="c6c2e-112">`GetMemoryLoad` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="c6c2e-112">`GetMemoryLoad` returned successfully.</span></span>|  
|<span data-ttu-id="c6c2e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c6c2e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c6c2e-114">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="c6c2e-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c6c2e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c6c2e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c6c2e-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="c6c2e-116">The call timed out.</span></span>|  
|<span data-ttu-id="c6c2e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c6c2e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c6c2e-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="c6c2e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c6c2e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c6c2e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c6c2e-120">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="c6c2e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c6c2e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c6c2e-121">E_FAIL</span></span>|<span data-ttu-id="c6c2e-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="c6c2e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c6c2e-123">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="c6c2e-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c6c2e-124">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c6c2e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6c2e-125">备注</span><span class="sxs-lookup"><span data-stu-id="c6c2e-125">Remarks</span></span>  
 <span data-ttu-id="c6c2e-126">`GetMemoryLoad` 包装 Win32`GlobalMemoryStatus`函数。</span><span class="sxs-lookup"><span data-stu-id="c6c2e-126">`GetMemoryLoad` wraps the Win32 `GlobalMemoryStatus` function.</span></span> <span data-ttu-id="c6c2e-127">值`pMemoryLoad`等同于`dwMemoryLoad`字段`MEMORYSTATUS`从返回的结构`GlobalMemoryStatus`。</span><span class="sxs-lookup"><span data-stu-id="c6c2e-127">The value of `pMemoryLoad` is the equivalent of the `dwMemoryLoad` field in the `MEMORYSTATUS` structure returned from `GlobalMemoryStatus`.</span></span>  
  
 <span data-ttu-id="c6c2e-128">运行时为垃圾回收器使用作为启发式方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="c6c2e-128">The runtime uses the return value as a heuristic for the garbage collector.</span></span> <span data-ttu-id="c6c2e-129">例如，如果主机报告的大部分内存正在使用，则可以选择垃圾回收器来收集多个代增加可能将可以使用的内存量。</span><span class="sxs-lookup"><span data-stu-id="c6c2e-129">For example, if the host reports that the majority of memory is in use, the garbage collector may elect to collect from multiple generations to increase the amount of memory that can potentially become available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6c2e-130">要求</span><span class="sxs-lookup"><span data-stu-id="c6c2e-130">Requirements</span></span>  
 <span data-ttu-id="c6c2e-131">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c6c2e-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6c2e-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c6c2e-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6c2e-133">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c6c2e-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6c2e-134">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6c2e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6c2e-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6c2e-135">See Also</span></span>  
 <xref:System.GC?displayProperty=nameWithType>  
 [<span data-ttu-id="c6c2e-136">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="c6c2e-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
