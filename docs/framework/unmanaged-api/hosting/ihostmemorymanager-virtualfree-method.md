---
title: IHostMemoryManager::VirtualFree 方法
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualFree
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualFree
helpviewer_keywords:
- IHostMemoryManager::VirtualFree method [.NET Framework hosting]
- VirtualFree method [.NET Framework hosting]
ms.assetid: 1a436e89-eb28-4d15-bcf1-a072f86dbd99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03cac2b8433d6491d1fa474a0d4064ef4e260d6e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099906"
---
# <a name="ihostmemorymanagervirtualfree-method"></a><span data-ttu-id="b1f78-102">IHostMemoryManager::VirtualFree 方法</span><span class="sxs-lookup"><span data-stu-id="b1f78-102">IHostMemoryManager::VirtualFree Method</span></span>
<span data-ttu-id="b1f78-103">充当相应的 Win32 函数的逻辑包装。</span><span class="sxs-lookup"><span data-stu-id="b1f78-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="b1f78-104">Win32 实现`VirtualFree`释放、 解除，或释放和解除调用进程虚拟地址空间中的页面区域。</span><span class="sxs-lookup"><span data-stu-id="b1f78-104">The Win32 implementation of `VirtualFree` releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1f78-105">语法</span><span class="sxs-lookup"><span data-stu-id="b1f78-105">Syntax</span></span>  
  
```  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1f78-106">参数</span><span class="sxs-lookup"><span data-stu-id="b1f78-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="b1f78-107">[in]指向要释放的虚拟内存页的基址的指针。</span><span class="sxs-lookup"><span data-stu-id="b1f78-107">[in] A pointer to the base address of the virtual memory pages to be freed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="b1f78-108">[in]以字节为单位，要释放的区域的大小。</span><span class="sxs-lookup"><span data-stu-id="b1f78-108">[in] The size, in bytes, of the region to be freed.</span></span>  
  
 `dwFreeType`  
 <span data-ttu-id="b1f78-109">[in]释放操作的类型。</span><span class="sxs-lookup"><span data-stu-id="b1f78-109">[in] The type of freeing operation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b1f78-110">返回值</span><span class="sxs-lookup"><span data-stu-id="b1f78-110">Return Value</span></span>  
  
|<span data-ttu-id="b1f78-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b1f78-111">HRESULT</span></span>|<span data-ttu-id="b1f78-112">描述</span><span class="sxs-lookup"><span data-stu-id="b1f78-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b1f78-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b1f78-113">S_OK</span></span>|`VirtualFree` <span data-ttu-id="b1f78-114">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="b1f78-114">returned successfully.</span></span>|  
|<span data-ttu-id="b1f78-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b1f78-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b1f78-116">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="b1f78-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b1f78-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b1f78-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b1f78-118">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="b1f78-118">The call timed out.</span></span>|  
|<span data-ttu-id="b1f78-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b1f78-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b1f78-120">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="b1f78-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b1f78-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b1f78-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b1f78-122">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="b1f78-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b1f78-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b1f78-123">E_FAIL</span></span>|<span data-ttu-id="b1f78-124">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="b1f78-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b1f78-125">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="b1f78-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b1f78-126">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="b1f78-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b1f78-127">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="b1f78-127">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="b1f78-128">尝试释放通过主机未分配的内存。</span><span class="sxs-lookup"><span data-stu-id="b1f78-128">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1f78-129">备注</span><span class="sxs-lookup"><span data-stu-id="b1f78-129">Remarks</span></span>  
 `VirtualFree` <span data-ttu-id="b1f78-130">释放与关联的虚拟内存页`lpAddress`通过以前调用的参数[ihostmemorymanager:: Virtualalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)函数。</span><span class="sxs-lookup"><span data-stu-id="b1f78-130">frees virtual memory pages associated with the `lpAddress` parameter through an earlier call to the [IHostMemoryManager::VirtualAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) function.</span></span> <span data-ttu-id="b1f78-131">尝试释放通过主机未分配的内存应返回 HOST_E_INVALIDOPERATION。</span><span class="sxs-lookup"><span data-stu-id="b1f78-131">Attempts to free memory that was not allocated through the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
 <span data-ttu-id="b1f78-132">与 Win32 实现相同的语义是`VirtualFree`。</span><span class="sxs-lookup"><span data-stu-id="b1f78-132">The semantics are identical to those of the Win32 implementation of `VirtualFree`.</span></span> <span data-ttu-id="b1f78-133">有关详细信息，请参阅 Windows 平台文档。</span><span class="sxs-lookup"><span data-stu-id="b1f78-133">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1f78-134">要求</span><span class="sxs-lookup"><span data-stu-id="b1f78-134">Requirements</span></span>  
 <span data-ttu-id="b1f78-135">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b1f78-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1f78-136">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b1f78-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b1f78-137">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b1f78-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="b1f78-138">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="b1f78-138">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b1f78-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="b1f78-139">See also</span></span>

- [<span data-ttu-id="b1f78-140">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="b1f78-140">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="b1f78-141">IHostMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="b1f78-141">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
