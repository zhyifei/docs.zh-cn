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
ms.openlocfilehash: 20ad5485b8603cc7de1c27c00d53c8939871d525
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178040"
---
# <a name="ihostmallocdebugalloc-method"></a><span data-ttu-id="9b388-102">IHostMAlloc::DebugAlloc 方法</span><span class="sxs-lookup"><span data-stu-id="9b388-102">IHostMAlloc::DebugAlloc Method</span></span>
<span data-ttu-id="9b388-103">请求主机从堆中分配指定数量的内存，并另外跟踪内存的分配位置。</span><span class="sxs-lookup"><span data-stu-id="9b388-103">Requests that the host allocate the specified amount of memory from the heap, and additionally track where the memory was allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b388-104">语法</span><span class="sxs-lookup"><span data-stu-id="9b388-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,
    [in]  EMemoryCriticalLevel dwCriticalLevel,
    [in]  char*   pszFileName,
    [in]  int     iLineNo,
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b388-105">parameters</span><span class="sxs-lookup"><span data-stu-id="9b388-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="9b388-106">[在]当前内存分配请求的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="9b388-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="9b388-107">[在][EMemory临界级别值](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md)之一，指示分配失败的影响。</span><span class="sxs-lookup"><span data-stu-id="9b388-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="9b388-108">[在]正在调试的可执行文件的代码文件。</span><span class="sxs-lookup"><span data-stu-id="9b388-108">[in] The code file of the executable being debugged.</span></span>  
  
 `iLineNo`  
 <span data-ttu-id="9b388-109">[在]请求分配`pszFileName`中的行号。</span><span class="sxs-lookup"><span data-stu-id="9b388-109">[in] The line number in `pszFileName` where the allocation was requested.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="9b388-110">[出]指向已分配的内存的指针，如果无法完成请求，则为 null。</span><span class="sxs-lookup"><span data-stu-id="9b388-110">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b388-111">返回值</span><span class="sxs-lookup"><span data-stu-id="9b388-111">Return Value</span></span>  
  
|<span data-ttu-id="9b388-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9b388-112">HRESULT</span></span>|<span data-ttu-id="9b388-113">说明</span><span class="sxs-lookup"><span data-stu-id="9b388-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9b388-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="9b388-114">S_OK</span></span>|<span data-ttu-id="9b388-115">`DebugAlloc`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="9b388-115">`DebugAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="9b388-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9b388-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9b388-117">CLR 尚未加载到进程中，或者 CLR 处于无法成功运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="9b388-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9b388-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9b388-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9b388-119">呼叫超时。</span><span class="sxs-lookup"><span data-stu-id="9b388-119">The call timed out.</span></span>|  
|<span data-ttu-id="9b388-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9b388-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9b388-121">调用方不拥有锁。</span><span class="sxs-lookup"><span data-stu-id="9b388-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9b388-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9b388-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9b388-123">当阻塞的线程或光纤等待事件时，事件已被取消。</span><span class="sxs-lookup"><span data-stu-id="9b388-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9b388-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9b388-124">E_FAIL</span></span>|<span data-ttu-id="9b388-125">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="9b388-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9b388-126">当方法返回E_FAIL时，CLR 在进程中不再可用。</span><span class="sxs-lookup"><span data-stu-id="9b388-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9b388-127">对托管方法的后续调用返回HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="9b388-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9b388-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9b388-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="9b388-129">没有足够的内存来完成分配请求。</span><span class="sxs-lookup"><span data-stu-id="9b388-129">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b388-130">备注</span><span class="sxs-lookup"><span data-stu-id="9b388-130">Remarks</span></span>  
 <span data-ttu-id="9b388-131">CLR 通过调用[IHostMemoryManagerManager：：createMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)方法获取指向[IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)实例的接口指针。</span><span class="sxs-lookup"><span data-stu-id="9b388-131">The CLR gets an interface pointer to an [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span> <span data-ttu-id="9b388-132">`DebugAlloc`允许运行时获取代码文件信息，供调试期间使用。</span><span class="sxs-lookup"><span data-stu-id="9b388-132">`DebugAlloc` allows the runtime to get code file information for use during debugging.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b388-133">要求</span><span class="sxs-lookup"><span data-stu-id="9b388-133">Requirements</span></span>  
 <span data-ttu-id="9b388-134">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9b388-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b388-135">**标题：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9b388-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9b388-136">**库：** 作为资源包含在 MSCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="9b388-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b388-137">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b388-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b388-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b388-138">See also</span></span>

- [<span data-ttu-id="9b388-139">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="9b388-139">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="9b388-140">IHostMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="9b388-140">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
