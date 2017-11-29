---
title: "IHostMAlloc::DebugAlloc 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMAlloc.DebugAlloc
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMAlloc::DebugAlloc
helpviewer_keywords:
- DebugAlloc method [.NET Framework hosting]
- IHostMAlloc::DebugAlloc method [.NET Framework hosting]
ms.assetid: 0bfbc527-bea2-43ce-b041-69186f4440dd
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 18759aa319bf39c49418e3b9388d96829ed52f7f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmallocdebugalloc-method"></a><span data-ttu-id="ddeae-102">IHostMAlloc::DebugAlloc 方法</span><span class="sxs-lookup"><span data-stu-id="ddeae-102">IHostMAlloc::DebugAlloc Method</span></span>
<span data-ttu-id="ddeae-103">请求主机从堆中，分配指定的数量的内存和此外跟踪分配内存时。</span><span class="sxs-lookup"><span data-stu-id="ddeae-103">Requests that the host allocate the specified amount of memory from the heap, and additionally track where the memory was allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddeae-104">语法</span><span class="sxs-lookup"><span data-stu-id="ddeae-104">Syntax</span></span>  
  
```  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,   
    [in]  EMemoryCriticalLevel dwCriticalLevel,   
    [in]  char*   pszFileName,   
    [in]  int     iLineNo,   
    [out] void**  ppMem  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ddeae-105">参数</span><span class="sxs-lookup"><span data-stu-id="ddeae-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="ddeae-106">[in]以字节为单位的当前内存分配请求的大小。</span><span class="sxs-lookup"><span data-stu-id="ddeae-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="ddeae-107">[in]之一[EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md)值，指示分配失败的影响。</span><span class="sxs-lookup"><span data-stu-id="ddeae-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="ddeae-108">[in]正在调试的可执行文件代码文件。</span><span class="sxs-lookup"><span data-stu-id="ddeae-108">[in] The code file of the executable being debugged.</span></span>  
  
 `iLineNo`  
 <span data-ttu-id="ddeae-109">[in]中的行号`pszFileName`分配请求所在。</span><span class="sxs-lookup"><span data-stu-id="ddeae-109">[in] The line number in `pszFileName` where the allocation was requested.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="ddeae-110">[out]指向分配的内存或如果无法完成请求的 null 指针。</span><span class="sxs-lookup"><span data-stu-id="ddeae-110">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ddeae-111">返回值</span><span class="sxs-lookup"><span data-stu-id="ddeae-111">Return Value</span></span>  
  
|<span data-ttu-id="ddeae-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ddeae-112">HRESULT</span></span>|<span data-ttu-id="ddeae-113">描述</span><span class="sxs-lookup"><span data-stu-id="ddeae-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ddeae-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ddeae-114">S_OK</span></span>|<span data-ttu-id="ddeae-115">`DebugAlloc`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="ddeae-115">`DebugAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="ddeae-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ddeae-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ddeae-117">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="ddeae-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ddeae-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ddeae-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ddeae-119">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="ddeae-119">The call timed out.</span></span>|  
|<span data-ttu-id="ddeae-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ddeae-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ddeae-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="ddeae-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ddeae-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ddeae-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ddeae-123">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="ddeae-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ddeae-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ddeae-124">E_FAIL</span></span>|<span data-ttu-id="ddeae-125">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="ddeae-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ddeae-126">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="ddeae-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ddeae-127">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="ddeae-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ddeae-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ddeae-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ddeae-129">可用于完成分配请求没有足够的内存。</span><span class="sxs-lookup"><span data-stu-id="ddeae-129">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ddeae-130">备注</span><span class="sxs-lookup"><span data-stu-id="ddeae-130">Remarks</span></span>  
 <span data-ttu-id="ddeae-131">CLR 获取到的接口指针[IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)实例通过调用[ihostmemorymanager:: Createmalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ddeae-131">The CLR gets an interface pointer to an [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span> <span data-ttu-id="ddeae-132">`DebugAlloc`允许运行时获取代码文件信息以供在调试期间使用。</span><span class="sxs-lookup"><span data-stu-id="ddeae-132">`DebugAlloc` allows the runtime to get code file information for use during debugging.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddeae-133">要求</span><span class="sxs-lookup"><span data-stu-id="ddeae-133">Requirements</span></span>  
 <span data-ttu-id="ddeae-134">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ddeae-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddeae-135">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ddeae-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ddeae-136">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ddeae-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ddeae-137">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddeae-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddeae-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ddeae-138">See Also</span></span>  
 [<span data-ttu-id="ddeae-139">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="ddeae-139">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="ddeae-140">IHostMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="ddeae-140">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
