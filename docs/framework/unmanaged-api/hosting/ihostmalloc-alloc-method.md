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
ms.openlocfilehash: dded37fdef02963f60883b289462aa6a96693b3d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176300"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="4633a-102">IHostMAlloc::Alloc 方法</span><span class="sxs-lookup"><span data-stu-id="4633a-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="4633a-103">请求主机从堆分配指定的内存量。</span><span class="sxs-lookup"><span data-stu-id="4633a-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4633a-104">语法</span><span class="sxs-lookup"><span data-stu-id="4633a-104">Syntax</span></span>  
  
```cpp  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,
    [in] EMemoryCriticalLevel dwCriticalLevel,
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4633a-105">parameters</span><span class="sxs-lookup"><span data-stu-id="4633a-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="4633a-106">[在]当前内存分配请求的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="4633a-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="4633a-107">[在][EMemory临界级别值](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md)之一，指示分配失败的影响。</span><span class="sxs-lookup"><span data-stu-id="4633a-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="4633a-108">[出]指向已分配的内存的指针，如果无法完成请求，则为 null。</span><span class="sxs-lookup"><span data-stu-id="4633a-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4633a-109">返回值</span><span class="sxs-lookup"><span data-stu-id="4633a-109">Return Value</span></span>  
  
|<span data-ttu-id="4633a-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4633a-110">HRESULT</span></span>|<span data-ttu-id="4633a-111">说明</span><span class="sxs-lookup"><span data-stu-id="4633a-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4633a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4633a-112">S_OK</span></span>|<span data-ttu-id="4633a-113">`Alloc`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="4633a-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="4633a-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4633a-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4633a-115">公共语言运行时 （CLR） 尚未加载到进程中，或者 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="4633a-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4633a-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4633a-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4633a-117">呼叫超时。</span><span class="sxs-lookup"><span data-stu-id="4633a-117">The call timed out.</span></span>|  
|<span data-ttu-id="4633a-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4633a-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4633a-119">调用方不拥有锁。</span><span class="sxs-lookup"><span data-stu-id="4633a-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4633a-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4633a-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4633a-121">当阻塞的线程或光纤等待事件时，事件已被取消。</span><span class="sxs-lookup"><span data-stu-id="4633a-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4633a-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4633a-122">E_FAIL</span></span>|<span data-ttu-id="4633a-123">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="4633a-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4633a-124">当方法返回E_FAIL时，CLR 在进程中不再可用。</span><span class="sxs-lookup"><span data-stu-id="4633a-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4633a-125">对托管方法的后续调用返回HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="4633a-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4633a-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4633a-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="4633a-127">没有足够的内存来完成分配请求。</span><span class="sxs-lookup"><span data-stu-id="4633a-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4633a-128">备注</span><span class="sxs-lookup"><span data-stu-id="4633a-128">Remarks</span></span>  
 <span data-ttu-id="4633a-129">CLR 通过调用`IHostMalloc`[IHostMemoryManager：：createMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)方法获取指向实例的接口指针。</span><span class="sxs-lookup"><span data-stu-id="4633a-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4633a-130">要求</span><span class="sxs-lookup"><span data-stu-id="4633a-130">Requirements</span></span>  
 <span data-ttu-id="4633a-131">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4633a-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4633a-132">**标题：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4633a-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4633a-133">**库：** 作为资源包含在 MSCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="4633a-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4633a-134">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4633a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4633a-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4633a-135">See also</span></span>

- [<span data-ttu-id="4633a-136">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="4633a-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="4633a-137">IHostMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="4633a-137">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
