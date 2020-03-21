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
ms.openlocfilehash: 88acd50c83eb1ff4d59aa50d677db2383912659a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176274"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a><span data-ttu-id="896c4-102">IHostMemoryManager::GetMemoryLoad 方法</span><span class="sxs-lookup"><span data-stu-id="896c4-102">IHostMemoryManager::GetMemoryLoad Method</span></span>
<span data-ttu-id="896c4-103">获取主机报告当前正在使用且因此不可用的物理内存量。</span><span class="sxs-lookup"><span data-stu-id="896c4-103">Gets the amount of physical memory that is currently in use, and therefore unavailable, as reported by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="896c4-104">语法</span><span class="sxs-lookup"><span data-stu-id="896c4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="896c4-105">parameters</span><span class="sxs-lookup"><span data-stu-id="896c4-105">Parameters</span></span>  
 `pMemoryLoad`  
 <span data-ttu-id="896c4-106">[出]指向当前正在使用的总物理内存的近似百分比的指针。</span><span class="sxs-lookup"><span data-stu-id="896c4-106">[out] A pointer to the approximate percentage of total physical memory that is currently in use.</span></span>  
  
 `pAvailableBytes`  
 <span data-ttu-id="896c4-107">[出]指向公共语言运行时 （CLR） 可用的字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="896c4-107">[out] A pointer to the number of bytes available to the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="896c4-108">返回值</span><span class="sxs-lookup"><span data-stu-id="896c4-108">Return Value</span></span>  
  
|<span data-ttu-id="896c4-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="896c4-109">HRESULT</span></span>|<span data-ttu-id="896c4-110">说明</span><span class="sxs-lookup"><span data-stu-id="896c4-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="896c4-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="896c4-111">S_OK</span></span>|<span data-ttu-id="896c4-112">`GetMemoryLoad`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="896c4-112">`GetMemoryLoad` returned successfully.</span></span>|  
|<span data-ttu-id="896c4-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="896c4-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="896c4-114">CLR 尚未加载到进程中，或者 CLR 处于无法成功运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="896c4-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="896c4-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="896c4-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="896c4-116">呼叫超时。</span><span class="sxs-lookup"><span data-stu-id="896c4-116">The call timed out.</span></span>|  
|<span data-ttu-id="896c4-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="896c4-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="896c4-118">调用方不拥有锁。</span><span class="sxs-lookup"><span data-stu-id="896c4-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="896c4-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="896c4-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="896c4-120">当阻塞的线程或光纤等待事件时，事件已被取消。</span><span class="sxs-lookup"><span data-stu-id="896c4-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="896c4-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="896c4-121">E_FAIL</span></span>|<span data-ttu-id="896c4-122">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="896c4-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="896c4-123">当方法返回E_FAIL时，CLR 在进程中不再可用。</span><span class="sxs-lookup"><span data-stu-id="896c4-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="896c4-124">对托管方法的后续调用返回HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="896c4-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="896c4-125">备注</span><span class="sxs-lookup"><span data-stu-id="896c4-125">Remarks</span></span>  
 <span data-ttu-id="896c4-126">`GetMemoryLoad`包装 Win32`GlobalMemoryStatus`函数。</span><span class="sxs-lookup"><span data-stu-id="896c4-126">`GetMemoryLoad` wraps the Win32 `GlobalMemoryStatus` function.</span></span> <span data-ttu-id="896c4-127">的值`pMemoryLoad`相当于从`dwMemoryLoad``MEMORYSTATUS``GlobalMemoryStatus`返回的结构中的字段。</span><span class="sxs-lookup"><span data-stu-id="896c4-127">The value of `pMemoryLoad` is the equivalent of the `dwMemoryLoad` field in the `MEMORYSTATUS` structure returned from `GlobalMemoryStatus`.</span></span>  
  
 <span data-ttu-id="896c4-128">运行时使用返回值作为垃圾回收器的启发式。</span><span class="sxs-lookup"><span data-stu-id="896c4-128">The runtime uses the return value as a heuristic for the garbage collector.</span></span> <span data-ttu-id="896c4-129">例如，如果主机报告大多数内存正在使用中，垃圾回收器可能会选择从多代收集，以增加可能可用的内存量。</span><span class="sxs-lookup"><span data-stu-id="896c4-129">For example, if the host reports that the majority of memory is in use, the garbage collector may elect to collect from multiple generations to increase the amount of memory that can potentially become available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="896c4-130">要求</span><span class="sxs-lookup"><span data-stu-id="896c4-130">Requirements</span></span>  
 <span data-ttu-id="896c4-131">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="896c4-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="896c4-132">**标题：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="896c4-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="896c4-133">**库：** 作为资源包含在 MSCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="896c4-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="896c4-134">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="896c4-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="896c4-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="896c4-135">See also</span></span>

- <xref:System.GC?displayProperty=nameWithType>
- [<span data-ttu-id="896c4-136">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="896c4-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
