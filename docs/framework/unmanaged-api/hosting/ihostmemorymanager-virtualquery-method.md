---
title: "IHostMemoryManager::VirtualQuery 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4fd893cd92f7e7621aefe59595cfd9905bc77afd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanagervirtualquery-method"></a><span data-ttu-id="9c47e-102">IHostMemoryManager::VirtualQuery 方法</span><span class="sxs-lookup"><span data-stu-id="9c47e-102">IHostMemoryManager::VirtualQuery Method</span></span>
<span data-ttu-id="9c47e-103">用作相应的 Win32 函数的逻辑包装。</span><span class="sxs-lookup"><span data-stu-id="9c47e-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="9c47e-104">Win32 实现`VirtualQuery`检索有关调用进程虚拟地址空间中的页面范围的信息。</span><span class="sxs-lookup"><span data-stu-id="9c47e-104">The Win32 implementation of `VirtualQuery` retrieves information about a range of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c47e-105">语法</span><span class="sxs-lookup"><span data-stu-id="9c47e-105">Syntax</span></span>  
  
```  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9c47e-106">参数</span><span class="sxs-lookup"><span data-stu-id="9c47e-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="9c47e-107">[in]指向要查询的虚拟内存中的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="9c47e-107">[in] A pointer to the address in virtual memory to be queried.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="9c47e-108">[out]指向包含有关指定的内存区域的信息的结构的指针。</span><span class="sxs-lookup"><span data-stu-id="9c47e-108">[out] A pointer to a structure that contains information about the specified memory region.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="9c47e-109">[in]以字节为单位的缓冲区的大小，`lpBuffer`指向。</span><span class="sxs-lookup"><span data-stu-id="9c47e-109">[in] The size, in bytes, of the buffer that `lpBuffer` points to.</span></span>  
  
 `pResult`  
 <span data-ttu-id="9c47e-110">[out]指向返回的信息缓冲区的字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="9c47e-110">[out] A pointer to the number of bytes returned by the information buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9c47e-111">返回值</span><span class="sxs-lookup"><span data-stu-id="9c47e-111">Return Value</span></span>  
  
|<span data-ttu-id="9c47e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9c47e-112">HRESULT</span></span>|<span data-ttu-id="9c47e-113">描述</span><span class="sxs-lookup"><span data-stu-id="9c47e-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9c47e-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="9c47e-114">S_OK</span></span>|<span data-ttu-id="9c47e-115">`VirtualQuery`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="9c47e-115">`VirtualQuery` returned successfully.</span></span>|  
|<span data-ttu-id="9c47e-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9c47e-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9c47e-117">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="9c47e-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9c47e-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9c47e-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9c47e-119">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="9c47e-119">The call timed out.</span></span>|  
|<span data-ttu-id="9c47e-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9c47e-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9c47e-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="9c47e-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9c47e-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9c47e-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9c47e-123">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="9c47e-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9c47e-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9c47e-124">E_FAIL</span></span>|<span data-ttu-id="9c47e-125">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="9c47e-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9c47e-126">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="9c47e-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9c47e-127">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="9c47e-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c47e-128">备注</span><span class="sxs-lookup"><span data-stu-id="9c47e-128">Remarks</span></span>  
 <span data-ttu-id="9c47e-129">`VirtualQuery`提供有关调用进程虚拟地址空间中的页面范围的信息。</span><span class="sxs-lookup"><span data-stu-id="9c47e-129">`VirtualQuery` provides information about a range of pages in the virtual address space of the calling process.</span></span> <span data-ttu-id="9c47e-130">此实现设置的值`pResult`到的字节数的参数返回信息缓冲区中并返回 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="9c47e-130">This implementation sets the value of the `pResult` parameter to the number of bytes returned in the information buffer, and returns an HRESULT value.</span></span> <span data-ttu-id="9c47e-131">在 Win32`VirtualQuery`函数，返回值是缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="9c47e-131">In the Win32 `VirtualQuery` function, the return value is the buffer size.</span></span> <span data-ttu-id="9c47e-132">有关详细信息，请参阅 Windows 平台文档。</span><span class="sxs-lookup"><span data-stu-id="9c47e-132">For more information, see the Windows Platform documentation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9c47e-133">操作系统的实现`VirtualQuery`不会产生死锁，并可以与在用户代码中挂起的随机线程运行到完成。</span><span class="sxs-lookup"><span data-stu-id="9c47e-133">The operating system's implementation of `VirtualQuery` does not incur deadlock and can run to completion with random threads suspended in user code.</span></span> <span data-ttu-id="9c47e-134">实现此方法的托管的版本时，请使用非常小心地。</span><span class="sxs-lookup"><span data-stu-id="9c47e-134">Use great caution when implementing a hosted version of this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c47e-135">惠?</span><span class="sxs-lookup"><span data-stu-id="9c47e-135">Requirements</span></span>  
 <span data-ttu-id="9c47e-136">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9c47e-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c47e-137">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9c47e-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9c47e-138">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9c47e-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9c47e-139">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c47e-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c47e-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="9c47e-140">See Also</span></span>  
 [<span data-ttu-id="9c47e-141">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="9c47e-141">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
