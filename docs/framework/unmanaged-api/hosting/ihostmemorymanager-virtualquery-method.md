---
title: IHostMemoryManager::VirtualQuery 方法
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualQuery
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualQuery
helpviewer_keywords:
- IHostMemoryManager::VirtualQuery method [.NET Framework hosting]
- VirtualQuery method [.NET Framework hosting]
ms.assetid: 757af1e6-b9e8-49e7-b5db-342be3aa205f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 028ca0b9cb917d3e6cc0242cbc8c3f4a5a19ab39
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199617"
---
# <a name="ihostmemorymanagervirtualquery-method"></a><span data-ttu-id="6e5af-102">IHostMemoryManager::VirtualQuery 方法</span><span class="sxs-lookup"><span data-stu-id="6e5af-102">IHostMemoryManager::VirtualQuery Method</span></span>
<span data-ttu-id="6e5af-103">充当相应的 Win32 函数的逻辑包装。</span><span class="sxs-lookup"><span data-stu-id="6e5af-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="6e5af-104">Win32 实现`VirtualQuery`检索有关调用进程的虚拟地址空间中的页范围的信息。</span><span class="sxs-lookup"><span data-stu-id="6e5af-104">The Win32 implementation of `VirtualQuery` retrieves information about a range of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e5af-105">语法</span><span class="sxs-lookup"><span data-stu-id="6e5af-105">Syntax</span></span>  
  
```  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e5af-106">参数</span><span class="sxs-lookup"><span data-stu-id="6e5af-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="6e5af-107">[in]指向要查询的虚拟内存中地址的指针。</span><span class="sxs-lookup"><span data-stu-id="6e5af-107">[in] A pointer to the address in virtual memory to be queried.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="6e5af-108">[out]指向包含有关指定的内存区域的信息的结构的指针。</span><span class="sxs-lookup"><span data-stu-id="6e5af-108">[out] A pointer to a structure that contains information about the specified memory region.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="6e5af-109">[in]以字节为单位的缓冲区的大小，`lpBuffer`指向。</span><span class="sxs-lookup"><span data-stu-id="6e5af-109">[in] The size, in bytes, of the buffer that `lpBuffer` points to.</span></span>  
  
 `pResult`  
 <span data-ttu-id="6e5af-110">[out]指向返回的信息缓冲区的字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="6e5af-110">[out] A pointer to the number of bytes returned by the information buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e5af-111">返回值</span><span class="sxs-lookup"><span data-stu-id="6e5af-111">Return Value</span></span>  
  
|<span data-ttu-id="6e5af-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6e5af-112">HRESULT</span></span>|<span data-ttu-id="6e5af-113">描述</span><span class="sxs-lookup"><span data-stu-id="6e5af-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6e5af-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="6e5af-114">S_OK</span></span>|`VirtualQuery` <span data-ttu-id="6e5af-115">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="6e5af-115">returned successfully.</span></span>|  
|<span data-ttu-id="6e5af-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6e5af-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6e5af-117">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="6e5af-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6e5af-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6e5af-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6e5af-119">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="6e5af-119">The call timed out.</span></span>|  
|<span data-ttu-id="6e5af-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6e5af-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6e5af-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="6e5af-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6e5af-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6e5af-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6e5af-123">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="6e5af-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6e5af-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6e5af-124">E_FAIL</span></span>|<span data-ttu-id="6e5af-125">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="6e5af-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6e5af-126">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="6e5af-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6e5af-127">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="6e5af-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e5af-128">备注</span><span class="sxs-lookup"><span data-stu-id="6e5af-128">Remarks</span></span>  
 `VirtualQuery` <span data-ttu-id="6e5af-129">提供有关调用进程的虚拟地址空间中的页范围信息。</span><span class="sxs-lookup"><span data-stu-id="6e5af-129">provides information about a range of pages in the virtual address space of the calling process.</span></span> <span data-ttu-id="6e5af-130">此实现中设置的值`pResult`到的字节数的参数信息缓冲区中返回，并返回 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="6e5af-130">This implementation sets the value of the `pResult` parameter to the number of bytes returned in the information buffer, and returns an HRESULT value.</span></span> <span data-ttu-id="6e5af-131">在 Win32 中`VirtualQuery`函数，返回值是缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="6e5af-131">In the Win32 `VirtualQuery` function, the return value is the buffer size.</span></span> <span data-ttu-id="6e5af-132">有关详细信息，请参阅 Windows 平台文档。</span><span class="sxs-lookup"><span data-stu-id="6e5af-132">For more information, see the Windows Platform documentation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6e5af-133">操作系统的实现`VirtualQuery`不会引起死锁，可以使用随机线程在用户代码中挂起完成运行。</span><span class="sxs-lookup"><span data-stu-id="6e5af-133">The operating system's implementation of `VirtualQuery` does not incur deadlock and can run to completion with random threads suspended in user code.</span></span> <span data-ttu-id="6e5af-134">实现此方法的托管的版本时，请使用格外注意。</span><span class="sxs-lookup"><span data-stu-id="6e5af-134">Use great caution when implementing a hosted version of this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e5af-135">要求</span><span class="sxs-lookup"><span data-stu-id="6e5af-135">Requirements</span></span>  
 <span data-ttu-id="6e5af-136">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6e5af-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e5af-137">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6e5af-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6e5af-138">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6e5af-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="6e5af-139">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="6e5af-139">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6e5af-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e5af-140">See also</span></span>

- [<span data-ttu-id="6e5af-141">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="6e5af-141">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
