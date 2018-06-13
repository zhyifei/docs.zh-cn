---
title: IHostMemoryManager::VirtualAlloc 方法
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualAlloc
helpviewer_keywords:
- VirtualAlloc method [.NET Framework hosting]
- IHostMemoryManager::VirtualAlloc method [.NET Framework hosting]
ms.assetid: 4dff3646-a050-4bd9-ac31-fe307e8637ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe54aed47d240be37ab9dbc5381235c4e962f1f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440309"
---
# <a name="ihostmemorymanagervirtualalloc-method"></a><span data-ttu-id="97852-102">IHostMemoryManager::VirtualAlloc 方法</span><span class="sxs-lookup"><span data-stu-id="97852-102">IHostMemoryManager::VirtualAlloc Method</span></span>
<span data-ttu-id="97852-103">用作相应的 Win32 函数的逻辑包装。</span><span class="sxs-lookup"><span data-stu-id="97852-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="97852-104">Win32 实现`VirtualAlloc`保留或提交调用进程虚拟地址空间中的页面的区域。</span><span class="sxs-lookup"><span data-stu-id="97852-104">The Win32 implementation of `VirtualAlloc` reserves or commits a region of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97852-105">语法</span><span class="sxs-lookup"><span data-stu-id="97852-105">Syntax</span></span>  
  
```  
HRESULT VirtualAlloc (  
    [in]  void*   pAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flAllocationType,  
    [in]  DWORD   flProtect,  
    [in]  EMemoryCriticalLevel dwCriticalLevel,  
    [out] void**  ppMem  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97852-106">参数</span><span class="sxs-lookup"><span data-stu-id="97852-106">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="97852-107">[in]指向要分配的区域的起始地址的指针。</span><span class="sxs-lookup"><span data-stu-id="97852-107">[in] A pointer to the starting address of the region to allocate.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="97852-108">[in]以字节为单位的区域的大小。</span><span class="sxs-lookup"><span data-stu-id="97852-108">[in] The size, in bytes, of the region.</span></span>  
  
 `flAllocationType`  
 <span data-ttu-id="97852-109">[in]内存分配的类型。</span><span class="sxs-lookup"><span data-stu-id="97852-109">[in] The type of memory allocation.</span></span>  
  
 `flProtect`  
 <span data-ttu-id="97852-110">[in]区域页，并将其分配的内存保护。</span><span class="sxs-lookup"><span data-stu-id="97852-110">[in] Memory protection for the region of pages to be allocated.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="97852-111">[in][EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md)值，该值指示分配失败的影响。</span><span class="sxs-lookup"><span data-stu-id="97852-111">[in] An [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) value that indicates the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="97852-112">[out]指向分配的内存，则为 null，如果不能满足请求的起始地址的指针。</span><span class="sxs-lookup"><span data-stu-id="97852-112">[out] Pointer to the starting address of the allocated memory, or null if the request could not be satisfied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="97852-113">返回值</span><span class="sxs-lookup"><span data-stu-id="97852-113">Return Value</span></span>  
  
|<span data-ttu-id="97852-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="97852-114">HRESULT</span></span>|<span data-ttu-id="97852-115">描述</span><span class="sxs-lookup"><span data-stu-id="97852-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="97852-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="97852-116">S_OK</span></span>|<span data-ttu-id="97852-117">`VirtualAlloc` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="97852-117">`VirtualAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="97852-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="97852-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="97852-119">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="97852-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="97852-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="97852-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="97852-121">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="97852-121">The call timed out.</span></span>|  
|<span data-ttu-id="97852-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="97852-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="97852-123">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="97852-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="97852-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="97852-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="97852-125">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="97852-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="97852-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="97852-126">E_FAIL</span></span>|<span data-ttu-id="97852-127">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="97852-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="97852-128">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="97852-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="97852-129">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="97852-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="97852-130">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="97852-130">E_OUTOFMEMORY</span></span>|<span data-ttu-id="97852-131">没有足够的内存已可用于完成分配请求</span><span class="sxs-lookup"><span data-stu-id="97852-131">Not enough memory was available to complete the allocation request</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97852-132">备注</span><span class="sxs-lookup"><span data-stu-id="97852-132">Remarks</span></span>  
 <span data-ttu-id="97852-133">在你的过程的地址空间中调用保留区域`VirtualAlloc`。</span><span class="sxs-lookup"><span data-stu-id="97852-133">You reserve a region in the address space of your process by calling `VirtualAlloc`.</span></span> <span data-ttu-id="97852-134">`pAddress`参数包含所需的内存块的起始地址。</span><span class="sxs-lookup"><span data-stu-id="97852-134">The `pAddress` parameter contains the beginning address of the memory block you want.</span></span> <span data-ttu-id="97852-135">通常情况下设置此参数为 null。</span><span class="sxs-lookup"><span data-stu-id="97852-135">This parameter is typically set to null.</span></span> <span data-ttu-id="97852-136">操作系统将保留的可用地址范围可供你的过程的记录。</span><span class="sxs-lookup"><span data-stu-id="97852-136">The operating system keeps a record of free address ranges available to your process.</span></span> <span data-ttu-id="97852-137">A `pAddress` null 值指示系统将保留区域，只要它认为合适。</span><span class="sxs-lookup"><span data-stu-id="97852-137">A `pAddress` value of null instructs the system to reserve the region wherever it sees fit.</span></span> <span data-ttu-id="97852-138">或者，你可以为内存块提供特定的起始地址。</span><span class="sxs-lookup"><span data-stu-id="97852-138">Alternatively, you can provide a specific starting address for the memory block.</span></span> <span data-ttu-id="97852-139">在这两种情况下，输出参数`ppMem`作为指针返回到分配的内存。</span><span class="sxs-lookup"><span data-stu-id="97852-139">In both cases, the output parameter `ppMem` is returned as a pointer to the allocated memory.</span></span> <span data-ttu-id="97852-140">该函数本身返回的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="97852-140">The function itself returns an HRESULT value.</span></span>  
  
 <span data-ttu-id="97852-141">Win32`VirtualAlloc`函数没有`ppMem`参数，并改为返回指向分配的内存的指针。</span><span class="sxs-lookup"><span data-stu-id="97852-141">The Win32 `VirtualAlloc` function does not have a `ppMem` parameter, and returns the pointer to the allocated memory instead.</span></span> <span data-ttu-id="97852-142">有关详细信息，请参阅 Windows 平台文档。</span><span class="sxs-lookup"><span data-stu-id="97852-142">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97852-143">要求</span><span class="sxs-lookup"><span data-stu-id="97852-143">Requirements</span></span>  
 <span data-ttu-id="97852-144">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="97852-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97852-145">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="97852-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="97852-146">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="97852-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="97852-147">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97852-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97852-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="97852-148">See Also</span></span>  
 [<span data-ttu-id="97852-149">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="97852-149">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
