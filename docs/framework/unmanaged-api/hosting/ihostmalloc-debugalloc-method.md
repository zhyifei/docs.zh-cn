---
title: IHostMAlloc::DebugAlloc 方法
ms.date: 03/30/2017
api_name:
- IHostMAlloc.DebugAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::DebugAlloc
helpviewer_keywords:
- DebugAlloc method [.NET Framework hosting]
- IHostMAlloc::DebugAlloc method [.NET Framework hosting]
ms.assetid: 0bfbc527-bea2-43ce-b041-69186f4440dd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f87c9c04c4d5b1d65e8c844630a6034f3c72d484
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780966"
---
# <a name="ihostmallocdebugalloc-method"></a><span data-ttu-id="ce042-102">IHostMAlloc::DebugAlloc 方法</span><span class="sxs-lookup"><span data-stu-id="ce042-102">IHostMAlloc::DebugAlloc Method</span></span>
<span data-ttu-id="ce042-103">请求主机从堆中分配指定的数量的内存和此外来跟踪分配内存时。</span><span class="sxs-lookup"><span data-stu-id="ce042-103">Requests that the host allocate the specified amount of memory from the heap, and additionally track where the memory was allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce042-104">语法</span><span class="sxs-lookup"><span data-stu-id="ce042-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,   
    [in]  EMemoryCriticalLevel dwCriticalLevel,   
    [in]  char*   pszFileName,   
    [in]  int     iLineNo,   
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce042-105">参数</span><span class="sxs-lookup"><span data-stu-id="ce042-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="ce042-106">[in]以字节为单位的当前内存分配请求的大小。</span><span class="sxs-lookup"><span data-stu-id="ce042-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="ce042-107">[in]之一[EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md)值，它指示发生分配失败的影响。</span><span class="sxs-lookup"><span data-stu-id="ce042-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="ce042-108">[in]正在调试的可执行文件的代码文件。</span><span class="sxs-lookup"><span data-stu-id="ce042-108">[in] The code file of the executable being debugged.</span></span>  
  
 `iLineNo`  
 <span data-ttu-id="ce042-109">[in]中的行号`pszFileName`分配请求所在。</span><span class="sxs-lookup"><span data-stu-id="ce042-109">[in] The line number in `pszFileName` where the allocation was requested.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="ce042-110">[out]一个指向已分配的内存或如果无法完成请求，则为 null。</span><span class="sxs-lookup"><span data-stu-id="ce042-110">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce042-111">返回值</span><span class="sxs-lookup"><span data-stu-id="ce042-111">Return Value</span></span>  
  
|<span data-ttu-id="ce042-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ce042-112">HRESULT</span></span>|<span data-ttu-id="ce042-113">描述</span><span class="sxs-lookup"><span data-stu-id="ce042-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ce042-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ce042-114">S_OK</span></span>|<span data-ttu-id="ce042-115">`DebugAlloc` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="ce042-115">`DebugAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="ce042-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ce042-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ce042-117">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="ce042-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ce042-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ce042-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ce042-119">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="ce042-119">The call timed out.</span></span>|  
|<span data-ttu-id="ce042-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ce042-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ce042-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="ce042-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ce042-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ce042-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ce042-123">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="ce042-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ce042-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ce042-124">E_FAIL</span></span>|<span data-ttu-id="ce042-125">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="ce042-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ce042-126">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="ce042-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ce042-127">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="ce042-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ce042-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ce042-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ce042-129">没有足够的内存是可用于完成分配请求。</span><span class="sxs-lookup"><span data-stu-id="ce042-129">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce042-130">备注</span><span class="sxs-lookup"><span data-stu-id="ce042-130">Remarks</span></span>  
 <span data-ttu-id="ce042-131">CLR 获取到的接口指针[IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)实例通过调用[ihostmemorymanager:: Createmalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ce042-131">The CLR gets an interface pointer to an [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span> <span data-ttu-id="ce042-132">`DebugAlloc` 允许运行时获取在调试期间使用的代码文件信息。</span><span class="sxs-lookup"><span data-stu-id="ce042-132">`DebugAlloc` allows the runtime to get code file information for use during debugging.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce042-133">要求</span><span class="sxs-lookup"><span data-stu-id="ce042-133">Requirements</span></span>  
 <span data-ttu-id="ce042-134">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ce042-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce042-135">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ce042-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ce042-136">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ce042-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce042-137">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce042-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce042-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="ce042-138">See also</span></span>

- [<span data-ttu-id="ce042-139">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="ce042-139">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="ce042-140">IHostMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="ce042-140">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
