---
title: IHostMemoryManager::VirtualProtect 方法
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualProtect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualProtect
helpviewer_keywords:
- IHostMemoryManager::VirtualProtect method [.NET Framework hosting]
- VirtualProtect method [.NET Framework hosting]
ms.assetid: 13be0299-df0d-4951-aabf-0676a30b385f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6ebba2f6d7f40c835b6ffdc479bdc9f2fdc354e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568057"
---
# <a name="ihostmemorymanagervirtualprotect-method"></a><span data-ttu-id="0000c-102">IHostMemoryManager::VirtualProtect 方法</span><span class="sxs-lookup"><span data-stu-id="0000c-102">IHostMemoryManager::VirtualProtect Method</span></span>
<span data-ttu-id="0000c-103">充当相应的 Win32 函数的逻辑包装。</span><span class="sxs-lookup"><span data-stu-id="0000c-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="0000c-104">Win32 实现`VirtualProtect`更改调用进程的虚拟地址空间中已提交页面区域上的保护。</span><span class="sxs-lookup"><span data-stu-id="0000c-104">The Win32 implementation of `VirtualProtect` changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0000c-105">语法</span><span class="sxs-lookup"><span data-stu-id="0000c-105">Syntax</span></span>  
  
```  
HRESULT VirtualProtect (  
    [in]  void*   lpAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flNewProtect,  
    [out] DWORD*  pflOldProtect  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0000c-106">参数</span><span class="sxs-lookup"><span data-stu-id="0000c-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="0000c-107">[in]指向其保护属性是要更改虚拟内存的基址的指针。</span><span class="sxs-lookup"><span data-stu-id="0000c-107">[in] A pointer to the base address of the virtual memory whose protection attributes are to be changed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="0000c-108">[in]以字节为单位的内存页，若要更改的区域的大小。</span><span class="sxs-lookup"><span data-stu-id="0000c-108">[in] The size, in bytes, of the region of memory pages to be changed.</span></span>  
  
 `flNewProtect`  
 <span data-ttu-id="0000c-109">[in]要应用的内存保护的类型。</span><span class="sxs-lookup"><span data-stu-id="0000c-109">[in] The type of memory protection to apply.</span></span>  
  
 `pflOldProtect`  
 <span data-ttu-id="0000c-110">[out]指向上一个内存保护值的指针。</span><span class="sxs-lookup"><span data-stu-id="0000c-110">[out] A pointer to the previous memory protection value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0000c-111">返回值</span><span class="sxs-lookup"><span data-stu-id="0000c-111">Return Value</span></span>  
  
|<span data-ttu-id="0000c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0000c-112">HRESULT</span></span>|<span data-ttu-id="0000c-113">描述</span><span class="sxs-lookup"><span data-stu-id="0000c-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0000c-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="0000c-114">S_OK</span></span>|<span data-ttu-id="0000c-115">`VirtualProtect` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="0000c-115">`VirtualProtect` returned successfully.</span></span>|  
|<span data-ttu-id="0000c-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0000c-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0000c-117">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="0000c-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0000c-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0000c-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0000c-119">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="0000c-119">The call timed out.</span></span>|  
|<span data-ttu-id="0000c-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0000c-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0000c-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="0000c-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0000c-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0000c-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0000c-123">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="0000c-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0000c-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0000c-124">E_FAIL</span></span>|<span data-ttu-id="0000c-125">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="0000c-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0000c-126">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="0000c-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0000c-127">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="0000c-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0000c-128">备注</span><span class="sxs-lookup"><span data-stu-id="0000c-128">Remarks</span></span>  
 <span data-ttu-id="0000c-129">此实现`VirtualProtect`返回 HRESULT 值，而 Win32 实现返回一个非零值来指示进程成功，而零值以指示失败。</span><span class="sxs-lookup"><span data-stu-id="0000c-129">This implementation of `VirtualProtect` returns an HRESULT value, while the Win32 implementation returns a non-zero value to indicate success, and a zero value to indicate failure.</span></span> <span data-ttu-id="0000c-130">有关详细信息，请参阅 Windows 平台文档。</span><span class="sxs-lookup"><span data-stu-id="0000c-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0000c-131">要求</span><span class="sxs-lookup"><span data-stu-id="0000c-131">Requirements</span></span>  
 <span data-ttu-id="0000c-132">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0000c-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0000c-133">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0000c-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0000c-134">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0000c-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0000c-135">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0000c-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0000c-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="0000c-136">See also</span></span>
- [<span data-ttu-id="0000c-137">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="0000c-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
