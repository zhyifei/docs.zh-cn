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
ms.openlocfilehash: de41b5e0aaf835ee2d4e4f32696fe104d5830b57
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804454"
---
# <a name="ihostmemorymanagervirtualalloc-method"></a><span data-ttu-id="05973-102">IHostMemoryManager::VirtualAlloc 方法</span><span class="sxs-lookup"><span data-stu-id="05973-102">IHostMemoryManager::VirtualAlloc Method</span></span>
<span data-ttu-id="05973-103">用作相应 Win32 函数的逻辑包装。</span><span class="sxs-lookup"><span data-stu-id="05973-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="05973-104">的 Win32 实现 `VirtualAlloc` 保留或提交调用进程的虚拟地址空间中的页面区域。</span><span class="sxs-lookup"><span data-stu-id="05973-104">The Win32 implementation of `VirtualAlloc` reserves or commits a region of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05973-105">语法</span><span class="sxs-lookup"><span data-stu-id="05973-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualAlloc (  
    [in]  void*   pAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flAllocationType,  
    [in]  DWORD   flProtect,  
    [in]  EMemoryCriticalLevel dwCriticalLevel,  
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05973-106">参数</span><span class="sxs-lookup"><span data-stu-id="05973-106">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="05973-107">中指向要分配的区域的起始地址的指针。</span><span class="sxs-lookup"><span data-stu-id="05973-107">[in] A pointer to the starting address of the region to allocate.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="05973-108">中区域的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="05973-108">[in] The size, in bytes, of the region.</span></span>  
  
 `flAllocationType`  
 <span data-ttu-id="05973-109">中内存分配的类型。</span><span class="sxs-lookup"><span data-stu-id="05973-109">[in] The type of memory allocation.</span></span>  
  
 `flProtect`  
 <span data-ttu-id="05973-110">中要分配的页面区域的内存保护。</span><span class="sxs-lookup"><span data-stu-id="05973-110">[in] Memory protection for the region of pages to be allocated.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="05973-111">中指示分配失败的影响的[EMemoryCriticalLevel](ememorycriticallevel-enumeration.md)值。</span><span class="sxs-lookup"><span data-stu-id="05973-111">[in] An [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) value that indicates the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="05973-112">弄指向分配的内存的起始地址的指针; 如果无法满足请求，则为 null。</span><span class="sxs-lookup"><span data-stu-id="05973-112">[out] Pointer to the starting address of the allocated memory, or null if the request could not be satisfied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05973-113">返回值</span><span class="sxs-lookup"><span data-stu-id="05973-113">Return Value</span></span>  
  
|<span data-ttu-id="05973-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="05973-114">HRESULT</span></span>|<span data-ttu-id="05973-115">说明</span><span class="sxs-lookup"><span data-stu-id="05973-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="05973-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="05973-116">S_OK</span></span>|<span data-ttu-id="05973-117">`VirtualAlloc`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="05973-117">`VirtualAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="05973-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="05973-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="05973-119">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="05973-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="05973-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="05973-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="05973-121">调用超时。</span><span class="sxs-lookup"><span data-stu-id="05973-121">The call timed out.</span></span>|  
|<span data-ttu-id="05973-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="05973-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="05973-123">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="05973-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="05973-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="05973-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="05973-125">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="05973-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="05973-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="05973-126">E_FAIL</span></span>|<span data-ttu-id="05973-127">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="05973-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="05973-128">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="05973-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="05973-129">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="05973-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="05973-130">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="05973-130">E_OUTOFMEMORY</span></span>|<span data-ttu-id="05973-131">没有足够的可用内存来完成分配请求</span><span class="sxs-lookup"><span data-stu-id="05973-131">Not enough memory was available to complete the allocation request</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05973-132">备注</span><span class="sxs-lookup"><span data-stu-id="05973-132">Remarks</span></span>  
 <span data-ttu-id="05973-133">可以通过调用在进程的地址空间中保留区域 `VirtualAlloc` 。</span><span class="sxs-lookup"><span data-stu-id="05973-133">You reserve a region in the address space of your process by calling `VirtualAlloc`.</span></span> <span data-ttu-id="05973-134">`pAddress`参数包含所需内存块的起始地址。</span><span class="sxs-lookup"><span data-stu-id="05973-134">The `pAddress` parameter contains the beginning address of the memory block you want.</span></span> <span data-ttu-id="05973-135">此参数通常设置为 null。</span><span class="sxs-lookup"><span data-stu-id="05973-135">This parameter is typically set to null.</span></span> <span data-ttu-id="05973-136">操作系统会保留可用于进程的免费地址范围记录。</span><span class="sxs-lookup"><span data-stu-id="05973-136">The operating system keeps a record of free address ranges available to your process.</span></span> <span data-ttu-id="05973-137">如果 `pAddress` 值为 null，则指示系统在其认为合适的位置保留区域。</span><span class="sxs-lookup"><span data-stu-id="05973-137">A `pAddress` value of null instructs the system to reserve the region wherever it sees fit.</span></span> <span data-ttu-id="05973-138">或者，您可以为内存块提供特定的起始地址。</span><span class="sxs-lookup"><span data-stu-id="05973-138">Alternatively, you can provide a specific starting address for the memory block.</span></span> <span data-ttu-id="05973-139">在这两种情况下，output 参数 `ppMem` 将作为指向已分配内存的指针返回。</span><span class="sxs-lookup"><span data-stu-id="05973-139">In both cases, the output parameter `ppMem` is returned as a pointer to the allocated memory.</span></span> <span data-ttu-id="05973-140">函数本身返回 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="05973-140">The function itself returns an HRESULT value.</span></span>  
  
 <span data-ttu-id="05973-141">Win32 `VirtualAlloc` 函数没有 `ppMem` 参数，而是返回指向分配的内存的指针。</span><span class="sxs-lookup"><span data-stu-id="05973-141">The Win32 `VirtualAlloc` function does not have a `ppMem` parameter, and returns the pointer to the allocated memory instead.</span></span> <span data-ttu-id="05973-142">有关详细信息，请参阅 Windows 平台文档。</span><span class="sxs-lookup"><span data-stu-id="05973-142">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05973-143">要求</span><span class="sxs-lookup"><span data-stu-id="05973-143">Requirements</span></span>  
 <span data-ttu-id="05973-144">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="05973-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05973-145">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="05973-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="05973-146">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="05973-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="05973-147">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05973-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05973-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05973-148">See also</span></span>

- [<span data-ttu-id="05973-149">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="05973-149">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
