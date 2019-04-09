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
ms.openlocfilehash: 6e089d133374f112dea13e91f9bd571bd2b5af07
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132920"
---
# <a name="ihostmallocdebugalloc-method"></a><span data-ttu-id="d7551-102">IHostMAlloc::DebugAlloc 方法</span><span class="sxs-lookup"><span data-stu-id="d7551-102">IHostMAlloc::DebugAlloc Method</span></span>
<span data-ttu-id="d7551-103">请求主机从堆中分配指定的数量的内存和此外来跟踪分配内存时。</span><span class="sxs-lookup"><span data-stu-id="d7551-103">Requests that the host allocate the specified amount of memory from the heap, and additionally track where the memory was allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7551-104">语法</span><span class="sxs-lookup"><span data-stu-id="d7551-104">Syntax</span></span>  
  
```  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,   
    [in]  EMemoryCriticalLevel dwCriticalLevel,   
    [in]  char*   pszFileName,   
    [in]  int     iLineNo,   
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7551-105">参数</span><span class="sxs-lookup"><span data-stu-id="d7551-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="d7551-106">[in]以字节为单位的当前内存分配请求的大小。</span><span class="sxs-lookup"><span data-stu-id="d7551-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="d7551-107">[in]之一[EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md)值，它指示发生分配失败的影响。</span><span class="sxs-lookup"><span data-stu-id="d7551-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="d7551-108">[in]正在调试的可执行文件的代码文件。</span><span class="sxs-lookup"><span data-stu-id="d7551-108">[in] The code file of the executable being debugged.</span></span>  
  
 `iLineNo`  
 <span data-ttu-id="d7551-109">[in]中的行号`pszFileName`分配请求所在。</span><span class="sxs-lookup"><span data-stu-id="d7551-109">[in] The line number in `pszFileName` where the allocation was requested.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="d7551-110">[out]一个指向已分配的内存或如果无法完成请求，则为 null。</span><span class="sxs-lookup"><span data-stu-id="d7551-110">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7551-111">返回值</span><span class="sxs-lookup"><span data-stu-id="d7551-111">Return Value</span></span>  
  
|<span data-ttu-id="d7551-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d7551-112">HRESULT</span></span>|<span data-ttu-id="d7551-113">描述</span><span class="sxs-lookup"><span data-stu-id="d7551-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d7551-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="d7551-114">S_OK</span></span>|`DebugAlloc` <span data-ttu-id="d7551-115">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="d7551-115">returned successfully.</span></span>|  
|<span data-ttu-id="d7551-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d7551-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d7551-117">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="d7551-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d7551-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d7551-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d7551-119">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="d7551-119">The call timed out.</span></span>|  
|<span data-ttu-id="d7551-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d7551-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d7551-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="d7551-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d7551-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d7551-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d7551-123">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="d7551-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d7551-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d7551-124">E_FAIL</span></span>|<span data-ttu-id="d7551-125">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="d7551-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d7551-126">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="d7551-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d7551-127">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="d7551-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d7551-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d7551-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d7551-129">没有足够的内存是可用于完成分配请求。</span><span class="sxs-lookup"><span data-stu-id="d7551-129">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7551-130">备注</span><span class="sxs-lookup"><span data-stu-id="d7551-130">Remarks</span></span>  
 <span data-ttu-id="d7551-131">CLR 获取到的接口指针[IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)实例通过调用[ihostmemorymanager:: Createmalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d7551-131">The CLR gets an interface pointer to an [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span> `DebugAlloc` <span data-ttu-id="d7551-132">允许运行时获取在调试期间使用的代码文件信息。</span><span class="sxs-lookup"><span data-stu-id="d7551-132">allows the runtime to get code file information for use during debugging.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7551-133">要求</span><span class="sxs-lookup"><span data-stu-id="d7551-133">Requirements</span></span>  
 <span data-ttu-id="d7551-134">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d7551-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7551-135">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d7551-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d7551-136">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d7551-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d7551-137">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="d7551-137">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d7551-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7551-138">See also</span></span>

- [<span data-ttu-id="d7551-139">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="d7551-139">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="d7551-140">IHostMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="d7551-140">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
