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
ms.openlocfilehash: 9837e4e3428a0293c8e689b3f3e081aa07f055b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192066"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="8f83f-102">IHostMAlloc::Alloc 方法</span><span class="sxs-lookup"><span data-stu-id="8f83f-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="8f83f-103">请求宿主从堆分配指定内存量。</span><span class="sxs-lookup"><span data-stu-id="8f83f-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f83f-104">语法</span><span class="sxs-lookup"><span data-stu-id="8f83f-104">Syntax</span></span>  
  
```cpp  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,   
    [in] EMemoryCriticalLevel dwCriticalLevel,   
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f83f-105">参数</span><span class="sxs-lookup"><span data-stu-id="8f83f-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="8f83f-106">中当前内存分配请求的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="8f83f-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="8f83f-107">中[EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md)值之一，指示分配失败的影响。</span><span class="sxs-lookup"><span data-stu-id="8f83f-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="8f83f-108">弄指向分配的内存的指针; 如果请求无法完成，则为 null。</span><span class="sxs-lookup"><span data-stu-id="8f83f-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f83f-109">返回值</span><span class="sxs-lookup"><span data-stu-id="8f83f-109">Return Value</span></span>  
  
|<span data-ttu-id="8f83f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8f83f-110">HRESULT</span></span>|<span data-ttu-id="8f83f-111">描述</span><span class="sxs-lookup"><span data-stu-id="8f83f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8f83f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="8f83f-112">S_OK</span></span>|<span data-ttu-id="8f83f-113">`Alloc` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="8f83f-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="8f83f-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8f83f-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8f83f-115">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="8f83f-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8f83f-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8f83f-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8f83f-117">调用超时。</span><span class="sxs-lookup"><span data-stu-id="8f83f-117">The call timed out.</span></span>|  
|<span data-ttu-id="8f83f-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8f83f-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8f83f-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="8f83f-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8f83f-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8f83f-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8f83f-121">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="8f83f-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8f83f-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8f83f-122">E_FAIL</span></span>|<span data-ttu-id="8f83f-123">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="8f83f-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8f83f-124">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="8f83f-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8f83f-125">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="8f83f-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8f83f-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="8f83f-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="8f83f-127">没有足够的内存可用来完成分配请求。</span><span class="sxs-lookup"><span data-stu-id="8f83f-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f83f-128">备注</span><span class="sxs-lookup"><span data-stu-id="8f83f-128">Remarks</span></span>  
 <span data-ttu-id="8f83f-129">CLR 通过调用[IHostMemoryManager：： CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)方法获取指向 `IHostMalloc` 实例的接口指针。</span><span class="sxs-lookup"><span data-stu-id="8f83f-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f83f-130">要求</span><span class="sxs-lookup"><span data-stu-id="8f83f-130">Requirements</span></span>  
 <span data-ttu-id="8f83f-131">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8f83f-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f83f-132">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8f83f-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8f83f-133">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="8f83f-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f83f-134">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f83f-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f83f-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f83f-135">See also</span></span>

- [<span data-ttu-id="8f83f-136">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="8f83f-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="8f83f-137">IHostMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="8f83f-137">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
