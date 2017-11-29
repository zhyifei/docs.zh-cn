---
title: "IHostMemoryManager::VirtualProtect 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.VirtualProtect
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::VirtualProtect
helpviewer_keywords:
- IHostMemoryManager::VirtualProtect method [.NET Framework hosting]
- VirtualProtect method [.NET Framework hosting]
ms.assetid: 13be0299-df0d-4951-aabf-0676a30b385f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8f8d363054ab4728ae031ccea44eb8eb853354ef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ihostmemorymanagervirtualprotect-method"></a><span data-ttu-id="ac2ed-102">IHostMemoryManager::VirtualProtect 方法</span><span class="sxs-lookup"><span data-stu-id="ac2ed-102">IHostMemoryManager::VirtualProtect Method</span></span>
<span data-ttu-id="ac2ed-103">用作相应的 Win32 函数的逻辑包装。</span><span class="sxs-lookup"><span data-stu-id="ac2ed-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="ac2ed-104">Win32 实现`VirtualProtect`更改调用进程的虚拟地址空间中的提交页面区域上的保护。</span><span class="sxs-lookup"><span data-stu-id="ac2ed-104">The Win32 implementation of `VirtualProtect` changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac2ed-105">语法</span><span class="sxs-lookup"><span data-stu-id="ac2ed-105">Syntax</span></span>  
  
```  
HRESULT VirtualProtect (  
    [in]  void*   lpAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flNewProtect,  
    [out] DWORD*  pflOldProtect  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac2ed-106">参数</span><span class="sxs-lookup"><span data-stu-id="ac2ed-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="ac2ed-107">[in]指向要更改其保护特性的虚拟内存的基址的指针。</span><span class="sxs-lookup"><span data-stu-id="ac2ed-107">[in] A pointer to the base address of the virtual memory whose protection attributes are to be changed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="ac2ed-108">[in]以字节为单位的内存页要更改区域的大小。</span><span class="sxs-lookup"><span data-stu-id="ac2ed-108">[in] The size, in bytes, of the region of memory pages to be changed.</span></span>  
  
 `flNewProtect`  
 <span data-ttu-id="ac2ed-109">[in]内存要应用的保护类型。</span><span class="sxs-lookup"><span data-stu-id="ac2ed-109">[in] The type of memory protection to apply.</span></span>  
  
 `pflOldProtect`  
 <span data-ttu-id="ac2ed-110">[out]指向以前的内存保护值的指针。</span><span class="sxs-lookup"><span data-stu-id="ac2ed-110">[out] A pointer to the previous memory protection value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac2ed-111">返回值</span><span class="sxs-lookup"><span data-stu-id="ac2ed-111">Return Value</span></span>  
  
|<span data-ttu-id="ac2ed-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ac2ed-112">HRESULT</span></span>|<span data-ttu-id="ac2ed-113">描述</span><span class="sxs-lookup"><span data-stu-id="ac2ed-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ac2ed-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac2ed-114">S_OK</span></span>|<span data-ttu-id="ac2ed-115">`VirtualProtect`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="ac2ed-115">`VirtualProtect` returned successfully.</span></span>|  
|<span data-ttu-id="ac2ed-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ac2ed-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ac2ed-117">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="ac2ed-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ac2ed-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ac2ed-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ac2ed-119">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="ac2ed-119">The call timed out.</span></span>|  
|<span data-ttu-id="ac2ed-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ac2ed-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ac2ed-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="ac2ed-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ac2ed-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ac2ed-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ac2ed-123">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="ac2ed-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ac2ed-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ac2ed-124">E_FAIL</span></span>|<span data-ttu-id="ac2ed-125">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="ac2ed-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ac2ed-126">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="ac2ed-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ac2ed-127">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="ac2ed-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac2ed-128">备注</span><span class="sxs-lookup"><span data-stu-id="ac2ed-128">Remarks</span></span>  
 <span data-ttu-id="ac2ed-129">此实现的`VirtualProtect`返回 HRESULT 值，而 Win32 实现返回一个非零值以指示成功和零值以指示失败。</span><span class="sxs-lookup"><span data-stu-id="ac2ed-129">This implementation of `VirtualProtect` returns an HRESULT value, while the Win32 implementation returns a non-zero value to indicate success, and a zero value to indicate failure.</span></span> <span data-ttu-id="ac2ed-130">有关详细信息，请参阅 Windows 平台文档。</span><span class="sxs-lookup"><span data-stu-id="ac2ed-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac2ed-131">要求</span><span class="sxs-lookup"><span data-stu-id="ac2ed-131">Requirements</span></span>  
 <span data-ttu-id="ac2ed-132">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ac2ed-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac2ed-133">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ac2ed-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ac2ed-134">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ac2ed-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ac2ed-135">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac2ed-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac2ed-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac2ed-136">See Also</span></span>  
 [<span data-ttu-id="ac2ed-137">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="ac2ed-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
