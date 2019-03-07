---
title: IHostMAlloc::Alloc 方法
ms.date: 03/30/2017
api_name:
- IHostMAlloc.Alloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Alloc
helpviewer_keywords:
- Alloc method, IHostMAlloc interface [.NET Framework hosting]
- IHostMAlloc::Alloc method [.NET Framework hosting]
ms.assetid: a3007f5e-d75d-4b37-842b-704e9edced5e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3104fd032f1a5de04f85a895c77cdf777df0a367
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489938"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="f6e57-102">IHostMAlloc::Alloc 方法</span><span class="sxs-lookup"><span data-stu-id="f6e57-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="f6e57-103">请求主机从堆中分配指定的内存量。</span><span class="sxs-lookup"><span data-stu-id="f6e57-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6e57-104">语法</span><span class="sxs-lookup"><span data-stu-id="f6e57-104">Syntax</span></span>  
  
```  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,   
    [in] EMemoryCriticalLevel dwCriticalLevel,   
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6e57-105">参数</span><span class="sxs-lookup"><span data-stu-id="f6e57-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="f6e57-106">[in]以字节为单位的当前内存分配请求的大小。</span><span class="sxs-lookup"><span data-stu-id="f6e57-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="f6e57-107">[in]之一[EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md)值，它指示发生分配失败的影响。</span><span class="sxs-lookup"><span data-stu-id="f6e57-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="f6e57-108">[out]一个指向已分配的内存或如果无法完成请求，则为 null。</span><span class="sxs-lookup"><span data-stu-id="f6e57-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6e57-109">返回值</span><span class="sxs-lookup"><span data-stu-id="f6e57-109">Return Value</span></span>  
  
|<span data-ttu-id="f6e57-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f6e57-110">HRESULT</span></span>|<span data-ttu-id="f6e57-111">描述</span><span class="sxs-lookup"><span data-stu-id="f6e57-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f6e57-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f6e57-112">S_OK</span></span>|<span data-ttu-id="f6e57-113">`Alloc` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="f6e57-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="f6e57-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f6e57-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f6e57-115">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="f6e57-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f6e57-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f6e57-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f6e57-117">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="f6e57-117">The call timed out.</span></span>|  
|<span data-ttu-id="f6e57-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f6e57-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f6e57-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="f6e57-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f6e57-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f6e57-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f6e57-121">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="f6e57-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f6e57-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f6e57-122">E_FAIL</span></span>|<span data-ttu-id="f6e57-123">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="f6e57-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f6e57-124">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="f6e57-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f6e57-125">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="f6e57-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f6e57-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f6e57-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="f6e57-127">没有足够的内存是可用于完成分配请求。</span><span class="sxs-lookup"><span data-stu-id="f6e57-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6e57-128">备注</span><span class="sxs-lookup"><span data-stu-id="f6e57-128">Remarks</span></span>  
 <span data-ttu-id="f6e57-129">CLR 获取到的接口指针`IHostMalloc`实例通过调用[ihostmemorymanager:: Createmalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="f6e57-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6e57-130">要求</span><span class="sxs-lookup"><span data-stu-id="f6e57-130">Requirements</span></span>  
 <span data-ttu-id="f6e57-131">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f6e57-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6e57-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f6e57-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f6e57-133">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f6e57-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f6e57-134">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6e57-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6e57-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6e57-135">See also</span></span>
- [<span data-ttu-id="f6e57-136">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="f6e57-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="f6e57-137">IHostMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="f6e57-137">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
