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
ms.openlocfilehash: c43fd1c63b14fc3254044247213bf09453da870e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599372"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a><span data-ttu-id="58dc5-102">IHostMemoryManager::GetMemoryLoad 方法</span><span class="sxs-lookup"><span data-stu-id="58dc5-102">IHostMemoryManager::GetMemoryLoad Method</span></span>
<span data-ttu-id="58dc5-103">获取当前已在使用中，并因此不可用，报告的主机的物理内存量。</span><span class="sxs-lookup"><span data-stu-id="58dc5-103">Gets the amount of physical memory that is currently in use, and therefore unavailable, as reported by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58dc5-104">语法</span><span class="sxs-lookup"><span data-stu-id="58dc5-104">Syntax</span></span>  
  
```  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,   
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58dc5-105">参数</span><span class="sxs-lookup"><span data-stu-id="58dc5-105">Parameters</span></span>  
 `pMemoryLoad`  
 <span data-ttu-id="58dc5-106">[out]一个指向当前正在使用的总物理内存的近似的百分比。</span><span class="sxs-lookup"><span data-stu-id="58dc5-106">[out] A pointer to the approximate percentage of total physical memory that is currently in use.</span></span>  
  
 `pAvailableBytes`  
 <span data-ttu-id="58dc5-107">[out]指向公共语言运行时 (CLR) 可用的字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="58dc5-107">[out] A pointer to the number of bytes available to the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58dc5-108">返回值</span><span class="sxs-lookup"><span data-stu-id="58dc5-108">Return Value</span></span>  
  
|<span data-ttu-id="58dc5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="58dc5-109">HRESULT</span></span>|<span data-ttu-id="58dc5-110">描述</span><span class="sxs-lookup"><span data-stu-id="58dc5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="58dc5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="58dc5-111">S_OK</span></span>|<span data-ttu-id="58dc5-112">`GetMemoryLoad` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="58dc5-112">`GetMemoryLoad` returned successfully.</span></span>|  
|<span data-ttu-id="58dc5-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="58dc5-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="58dc5-114">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="58dc5-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="58dc5-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="58dc5-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="58dc5-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="58dc5-116">The call timed out.</span></span>|  
|<span data-ttu-id="58dc5-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="58dc5-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="58dc5-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="58dc5-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="58dc5-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="58dc5-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="58dc5-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="58dc5-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="58dc5-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="58dc5-121">E_FAIL</span></span>|<span data-ttu-id="58dc5-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="58dc5-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="58dc5-123">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="58dc5-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="58dc5-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="58dc5-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58dc5-125">备注</span><span class="sxs-lookup"><span data-stu-id="58dc5-125">Remarks</span></span>  
 <span data-ttu-id="58dc5-126">`GetMemoryLoad` 包装 Win32`GlobalMemoryStatus`函数。</span><span class="sxs-lookup"><span data-stu-id="58dc5-126">`GetMemoryLoad` wraps the Win32 `GlobalMemoryStatus` function.</span></span> <span data-ttu-id="58dc5-127">值`pMemoryLoad`等效于`dwMemoryLoad`字段中`MEMORYSTATUS`从返回的结构`GlobalMemoryStatus`。</span><span class="sxs-lookup"><span data-stu-id="58dc5-127">The value of `pMemoryLoad` is the equivalent of the `dwMemoryLoad` field in the `MEMORYSTATUS` structure returned from `GlobalMemoryStatus`.</span></span>  
  
 <span data-ttu-id="58dc5-128">运行时使用的垃圾回收器作为启发式方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="58dc5-128">The runtime uses the return value as a heuristic for the garbage collector.</span></span> <span data-ttu-id="58dc5-129">例如，如果主机报告的大部分内存正在使用中，垃圾回收器可以选择从多个以增加可能会变为可用的内存量的代中收集。</span><span class="sxs-lookup"><span data-stu-id="58dc5-129">For example, if the host reports that the majority of memory is in use, the garbage collector may elect to collect from multiple generations to increase the amount of memory that can potentially become available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58dc5-130">要求</span><span class="sxs-lookup"><span data-stu-id="58dc5-130">Requirements</span></span>  
 <span data-ttu-id="58dc5-131">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="58dc5-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58dc5-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="58dc5-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="58dc5-133">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="58dc5-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58dc5-134">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58dc5-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58dc5-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="58dc5-135">See also</span></span>

- <xref:System.GC?displayProperty=nameWithType>
- [<span data-ttu-id="58dc5-136">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="58dc5-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
