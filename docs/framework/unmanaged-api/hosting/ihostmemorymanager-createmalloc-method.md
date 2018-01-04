---
title: "IHostMemoryManager::CreateMAlloc 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.CreateMAlloc
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::CreateMAlloc
helpviewer_keywords:
- CreateAlloc method [.NET Framework hosting]
- IHostMemoryManager::CreateMAlloc method [.NET Framework hosting]
ms.assetid: 9ee6e052-bef7-4350-9e4f-edfffd99ad6f
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 19b43ccf7cb2429c28c052ab8ab3a009ec4a30a4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanagercreatemalloc-method"></a><span data-ttu-id="af674-102">IHostMemoryManager::CreateMAlloc 方法</span><span class="sxs-lookup"><span data-stu-id="af674-102">IHostMemoryManager::CreateMAlloc Method</span></span>
<span data-ttu-id="af674-103">获取到的接口指针[IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)用于使从由宿主创建堆分配请求的实例。</span><span class="sxs-lookup"><span data-stu-id="af674-103">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to make allocation requests from a heap created by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af674-104">语法</span><span class="sxs-lookup"><span data-stu-id="af674-104">Syntax</span></span>  
  
```  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="af674-105">参数</span><span class="sxs-lookup"><span data-stu-id="af674-105">Parameters</span></span>  
 `dwMallocType`  
 <span data-ttu-id="af674-106">[in]组合[MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md)指定所分配的内存的特征的标志。</span><span class="sxs-lookup"><span data-stu-id="af674-106">[in] A combination of [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) flags that specifies the characteristics of the memory that is being allocated.</span></span>  
  
 `ppMAlloc`  
 <span data-ttu-id="af674-107">[out]指向的地址的指针`IHostMAlloc`主机提供的实例。</span><span class="sxs-lookup"><span data-stu-id="af674-107">[out] A pointer to the address of an `IHostMAlloc` instance provided by the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af674-108">返回值</span><span class="sxs-lookup"><span data-stu-id="af674-108">Return Value</span></span>  
  
|<span data-ttu-id="af674-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="af674-109">HRESULT</span></span>|<span data-ttu-id="af674-110">描述</span><span class="sxs-lookup"><span data-stu-id="af674-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="af674-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="af674-111">S_OK</span></span>|<span data-ttu-id="af674-112">`CreateMAlloc`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="af674-112">`CreateMAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="af674-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="af674-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="af674-114">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="af674-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="af674-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="af674-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="af674-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="af674-116">The call timed out.</span></span>|  
|<span data-ttu-id="af674-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="af674-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="af674-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="af674-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="af674-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="af674-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="af674-120">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="af674-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="af674-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="af674-121">E_FAIL</span></span>|<span data-ttu-id="af674-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="af674-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="af674-123">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="af674-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="af674-124">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="af674-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="af674-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="af674-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="af674-126">没有足够的物理内存已可用于完成分配请求。</span><span class="sxs-lookup"><span data-stu-id="af674-126">Not enough physical memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af674-127">备注</span><span class="sxs-lookup"><span data-stu-id="af674-127">Remarks</span></span>  
 <span data-ttu-id="af674-128">`CreateMAlloc`返回一个允许 CLR 发出分配请求通过主机而不是使用标准的 Win32 函数的对象。</span><span class="sxs-lookup"><span data-stu-id="af674-128">`CreateMAlloc` returns an object that allows the CLR to make allocation requests through the host instead of using the standard Win32 functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af674-129">惠?</span><span class="sxs-lookup"><span data-stu-id="af674-129">Requirements</span></span>  
 <span data-ttu-id="af674-130">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="af674-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af674-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="af674-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="af674-132">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="af674-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="af674-133">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af674-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af674-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="af674-134">See Also</span></span>  
 [<span data-ttu-id="af674-135">IHostMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="af674-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 [<span data-ttu-id="af674-136">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="af674-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
