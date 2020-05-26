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
ms.openlocfilehash: 8475362ede5ea28009d5abc54c286d6f2a6fed0f
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804636"
---
# <a name="ihostmallocdebugalloc-method"></a><span data-ttu-id="9b78c-102">IHostMAlloc::DebugAlloc 方法</span><span class="sxs-lookup"><span data-stu-id="9b78c-102">IHostMAlloc::DebugAlloc Method</span></span>
<span data-ttu-id="9b78c-103">请求宿主从堆分配指定内存量，并另外跟踪内存的分配位置。</span><span class="sxs-lookup"><span data-stu-id="9b78c-103">Requests that the host allocate the specified amount of memory from the heap, and additionally track where the memory was allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b78c-104">语法</span><span class="sxs-lookup"><span data-stu-id="9b78c-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,
    [in]  EMemoryCriticalLevel dwCriticalLevel,
    [in]  char*   pszFileName,
    [in]  int     iLineNo,
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b78c-105">参数</span><span class="sxs-lookup"><span data-stu-id="9b78c-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="9b78c-106">中当前内存分配请求的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="9b78c-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="9b78c-107">中[EMemoryCriticalLevel](ememorycriticallevel-enumeration.md)值之一，指示分配失败的影响。</span><span class="sxs-lookup"><span data-stu-id="9b78c-107">[in] One of the [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="9b78c-108">中正在调试的可执行文件的代码文件。</span><span class="sxs-lookup"><span data-stu-id="9b78c-108">[in] The code file of the executable being debugged.</span></span>  
  
 `iLineNo`  
 <span data-ttu-id="9b78c-109">中`pszFileName`请求分配的行号。</span><span class="sxs-lookup"><span data-stu-id="9b78c-109">[in] The line number in `pszFileName` where the allocation was requested.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="9b78c-110">弄指向分配的内存的指针; 如果请求无法完成，则为 null。</span><span class="sxs-lookup"><span data-stu-id="9b78c-110">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b78c-111">返回值</span><span class="sxs-lookup"><span data-stu-id="9b78c-111">Return Value</span></span>  
  
|<span data-ttu-id="9b78c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9b78c-112">HRESULT</span></span>|<span data-ttu-id="9b78c-113">说明</span><span class="sxs-lookup"><span data-stu-id="9b78c-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9b78c-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="9b78c-114">S_OK</span></span>|<span data-ttu-id="9b78c-115">`DebugAlloc`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="9b78c-115">`DebugAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="9b78c-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9b78c-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9b78c-117">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="9b78c-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9b78c-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9b78c-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9b78c-119">调用超时。</span><span class="sxs-lookup"><span data-stu-id="9b78c-119">The call timed out.</span></span>|  
|<span data-ttu-id="9b78c-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9b78c-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9b78c-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="9b78c-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9b78c-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9b78c-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9b78c-123">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="9b78c-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9b78c-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9b78c-124">E_FAIL</span></span>|<span data-ttu-id="9b78c-125">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="9b78c-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9b78c-126">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="9b78c-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9b78c-127">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="9b78c-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9b78c-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9b78c-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="9b78c-129">没有足够的内存可用来完成分配请求。</span><span class="sxs-lookup"><span data-stu-id="9b78c-129">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b78c-130">备注</span><span class="sxs-lookup"><span data-stu-id="9b78c-130">Remarks</span></span>  
 <span data-ttu-id="9b78c-131">CLR 通过调用[IHostMemoryManager：： CreateMalloc](ihostmemorymanager-createmalloc-method.md)方法获取指向[IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)实例的接口指针。</span><span class="sxs-lookup"><span data-stu-id="9b78c-131">The CLR gets an interface pointer to an [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance by calling the [IHostMemoryManager::CreateMalloc](ihostmemorymanager-createmalloc-method.md) method.</span></span> <span data-ttu-id="9b78c-132">`DebugAlloc`允许运行时获取代码文件信息，以便在调试期间使用。</span><span class="sxs-lookup"><span data-stu-id="9b78c-132">`DebugAlloc` allows the runtime to get code file information for use during debugging.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b78c-133">要求</span><span class="sxs-lookup"><span data-stu-id="9b78c-133">Requirements</span></span>  
 <span data-ttu-id="9b78c-134">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9b78c-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b78c-135">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9b78c-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9b78c-136">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="9b78c-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b78c-137">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b78c-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b78c-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b78c-138">See also</span></span>

- [<span data-ttu-id="9b78c-139">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="9b78c-139">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="9b78c-140">IHostMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="9b78c-140">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
