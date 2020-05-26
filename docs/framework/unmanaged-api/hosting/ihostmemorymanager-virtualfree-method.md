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
ms.openlocfilehash: 4d37b7d803509ebfa861b7502d419f868bd12e11
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804388"
---
# <a name="ihostmemorymanagervirtualfree-method"></a><span data-ttu-id="b9a92-102">IHostMemoryManager::VirtualFree 方法</span><span class="sxs-lookup"><span data-stu-id="b9a92-102">IHostMemoryManager::VirtualFree Method</span></span>
<span data-ttu-id="b9a92-103">用作相应 Win32 函数的逻辑包装。</span><span class="sxs-lookup"><span data-stu-id="b9a92-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="b9a92-104">在 `VirtualFree` 调用进程的虚拟地址空间内释放、解除或释放和解除页区域的 Win32 实现。</span><span class="sxs-lookup"><span data-stu-id="b9a92-104">The Win32 implementation of `VirtualFree` releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9a92-105">语法</span><span class="sxs-lookup"><span data-stu-id="b9a92-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9a92-106">参数</span><span class="sxs-lookup"><span data-stu-id="b9a92-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="b9a92-107">中一个指针，指向要释放的虚拟内存页的基址。</span><span class="sxs-lookup"><span data-stu-id="b9a92-107">[in] A pointer to the base address of the virtual memory pages to be freed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="b9a92-108">中要释放的区域的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="b9a92-108">[in] The size, in bytes, of the region to be freed.</span></span>  
  
 `dwFreeType`  
 <span data-ttu-id="b9a92-109">中释放操作的类型。</span><span class="sxs-lookup"><span data-stu-id="b9a92-109">[in] The type of freeing operation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9a92-110">返回值</span><span class="sxs-lookup"><span data-stu-id="b9a92-110">Return Value</span></span>  
  
|<span data-ttu-id="b9a92-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b9a92-111">HRESULT</span></span>|<span data-ttu-id="b9a92-112">说明</span><span class="sxs-lookup"><span data-stu-id="b9a92-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b9a92-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b9a92-113">S_OK</span></span>|<span data-ttu-id="b9a92-114">`VirtualFree`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="b9a92-114">`VirtualFree` returned successfully.</span></span>|  
|<span data-ttu-id="b9a92-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b9a92-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b9a92-116">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="b9a92-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b9a92-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b9a92-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b9a92-118">调用超时。</span><span class="sxs-lookup"><span data-stu-id="b9a92-118">The call timed out.</span></span>|  
|<span data-ttu-id="b9a92-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b9a92-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b9a92-120">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="b9a92-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b9a92-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b9a92-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b9a92-122">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="b9a92-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b9a92-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b9a92-123">E_FAIL</span></span>|<span data-ttu-id="b9a92-124">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="b9a92-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b9a92-125">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="b9a92-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b9a92-126">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="b9a92-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b9a92-127">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="b9a92-127">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="b9a92-128">尝试释放未通过主机分配的内存。</span><span class="sxs-lookup"><span data-stu-id="b9a92-128">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9a92-129">备注</span><span class="sxs-lookup"><span data-stu-id="b9a92-129">Remarks</span></span>  
 <span data-ttu-id="b9a92-130">`VirtualFree``lpAddress`通过对[IHostMemoryManager：： VirtualAlloc](ihostmemorymanager-virtualalloc-method.md)函数的更早调用来释放与参数关联的虚拟内存页。</span><span class="sxs-lookup"><span data-stu-id="b9a92-130">`VirtualFree` frees virtual memory pages associated with the `lpAddress` parameter through an earlier call to the [IHostMemoryManager::VirtualAlloc](ihostmemorymanager-virtualalloc-method.md) function.</span></span> <span data-ttu-id="b9a92-131">尝试释放未通过主机分配的内存应返回 HOST_E_INVALIDOPERATION。</span><span class="sxs-lookup"><span data-stu-id="b9a92-131">Attempts to free memory that was not allocated through the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
 <span data-ttu-id="b9a92-132">语义与的 Win32 实现的语义相同 `VirtualFree` 。</span><span class="sxs-lookup"><span data-stu-id="b9a92-132">The semantics are identical to those of the Win32 implementation of `VirtualFree`.</span></span> <span data-ttu-id="b9a92-133">有关详细信息，请参阅 Windows 平台文档。</span><span class="sxs-lookup"><span data-stu-id="b9a92-133">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9a92-134">要求</span><span class="sxs-lookup"><span data-stu-id="b9a92-134">Requirements</span></span>  
 <span data-ttu-id="b9a92-135">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b9a92-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9a92-136">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b9a92-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b9a92-137">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="b9a92-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9a92-138">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9a92-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9a92-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9a92-139">See also</span></span>

- [<span data-ttu-id="b9a92-140">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="b9a92-140">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="b9a92-141">IHostMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="b9a92-141">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
