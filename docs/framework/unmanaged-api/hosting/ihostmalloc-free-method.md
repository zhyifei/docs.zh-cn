---
title: "IHostMAlloc::Free 方法"
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
- IHostMAlloc.Free
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Free
helpviewer_keywords:
- IHostMAlloc::Free method [.NET Framework hosting]
- Free method, IHostMAlloc interface [.NET Framework hosting]
ms.assetid: c89abf5b-1120-4437-8b57-4a99fb3ae7f9
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4775b6ae00f34d7d046515f8700a35470b2f6650
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmallocfree-method"></a><span data-ttu-id="80fdd-102">IHostMAlloc::Free 方法</span><span class="sxs-lookup"><span data-stu-id="80fdd-102">IHostMAlloc::Free Method</span></span>
<span data-ttu-id="80fdd-103">释放使用分配的内存[Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)函数。</span><span class="sxs-lookup"><span data-stu-id="80fdd-103">Frees memory that was allocated by using the [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80fdd-104">语法</span><span class="sxs-lookup"><span data-stu-id="80fdd-104">Syntax</span></span>  
  
```  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="80fdd-105">参数</span><span class="sxs-lookup"><span data-stu-id="80fdd-105">Parameters</span></span>  
 `pMem`  
 <span data-ttu-id="80fdd-106">[in]指向要释放的内存的指针。</span><span class="sxs-lookup"><span data-stu-id="80fdd-106">[in] A pointer to the memory to be freed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80fdd-107">返回值</span><span class="sxs-lookup"><span data-stu-id="80fdd-107">Return Value</span></span>  
  
|<span data-ttu-id="80fdd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="80fdd-108">HRESULT</span></span>|<span data-ttu-id="80fdd-109">描述</span><span class="sxs-lookup"><span data-stu-id="80fdd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="80fdd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="80fdd-110">S_OK</span></span>|<span data-ttu-id="80fdd-111">`Free`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="80fdd-111">`Free` returned successfully.</span></span>|  
|<span data-ttu-id="80fdd-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="80fdd-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="80fdd-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="80fdd-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="80fdd-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="80fdd-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="80fdd-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="80fdd-115">The call timed out.</span></span>|  
|<span data-ttu-id="80fdd-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="80fdd-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="80fdd-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="80fdd-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="80fdd-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="80fdd-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="80fdd-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="80fdd-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="80fdd-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="80fdd-120">E_FAIL</span></span>|<span data-ttu-id="80fdd-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="80fdd-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="80fdd-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="80fdd-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="80fdd-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="80fdd-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="80fdd-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="80fdd-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="80fdd-125">尝试释放通过主机未分配的内存。</span><span class="sxs-lookup"><span data-stu-id="80fdd-125">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80fdd-126">备注</span><span class="sxs-lookup"><span data-stu-id="80fdd-126">Remarks</span></span>  
 <span data-ttu-id="80fdd-127">如果`pMem`参数是指通过调用未分配的内存区域`Alloc`，主机应返回 HOST_E_INVALIDOPERATION。</span><span class="sxs-lookup"><span data-stu-id="80fdd-127">If the `pMem` parameter refers to a region of memory that was not allocated by using a call to `Alloc`, the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80fdd-128">惠?</span><span class="sxs-lookup"><span data-stu-id="80fdd-128">Requirements</span></span>  
 <span data-ttu-id="80fdd-129">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="80fdd-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80fdd-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="80fdd-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="80fdd-131">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="80fdd-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="80fdd-132">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80fdd-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80fdd-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="80fdd-133">See Also</span></span>  
 [<span data-ttu-id="80fdd-134">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="80fdd-134">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="80fdd-135">IHostMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="80fdd-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
