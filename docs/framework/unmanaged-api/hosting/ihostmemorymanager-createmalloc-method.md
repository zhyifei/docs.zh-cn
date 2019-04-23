---
title: IHostMemoryManager::CreateMAlloc 方法
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.CreateMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::CreateMAlloc
helpviewer_keywords:
- CreateAlloc method [.NET Framework hosting]
- IHostMemoryManager::CreateMAlloc method [.NET Framework hosting]
ms.assetid: 9ee6e052-bef7-4350-9e4f-edfffd99ad6f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 194e9b73610ccb7282babf266eea2968a4f035ac
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59179122"
---
# <a name="ihostmemorymanagercreatemalloc-method"></a><span data-ttu-id="832d9-102">IHostMemoryManager::CreateMAlloc 方法</span><span class="sxs-lookup"><span data-stu-id="832d9-102">IHostMemoryManager::CreateMAlloc Method</span></span>
<span data-ttu-id="832d9-103">获取到的接口指针[IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)用于使从由宿主创建堆分配请求的实例。</span><span class="sxs-lookup"><span data-stu-id="832d9-103">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to make allocation requests from a heap created by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="832d9-104">语法</span><span class="sxs-lookup"><span data-stu-id="832d9-104">Syntax</span></span>  
  
```  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="832d9-105">参数</span><span class="sxs-lookup"><span data-stu-id="832d9-105">Parameters</span></span>  
 `dwMallocType`  
 <span data-ttu-id="832d9-106">[in]组合[MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md)指定正为其分配的内存的特征的标志。</span><span class="sxs-lookup"><span data-stu-id="832d9-106">[in] A combination of [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) flags that specifies the characteristics of the memory that is being allocated.</span></span>  
  
 `ppMAlloc`  
 <span data-ttu-id="832d9-107">[out]指向的地址的指针`IHostMAlloc`提供主机实例。</span><span class="sxs-lookup"><span data-stu-id="832d9-107">[out] A pointer to the address of an `IHostMAlloc` instance provided by the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="832d9-108">返回值</span><span class="sxs-lookup"><span data-stu-id="832d9-108">Return Value</span></span>  
  
|<span data-ttu-id="832d9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="832d9-109">HRESULT</span></span>|<span data-ttu-id="832d9-110">描述</span><span class="sxs-lookup"><span data-stu-id="832d9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="832d9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="832d9-111">S_OK</span></span>|<span data-ttu-id="832d9-112">`CreateMAlloc` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="832d9-112">`CreateMAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="832d9-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="832d9-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="832d9-114">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="832d9-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="832d9-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="832d9-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="832d9-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="832d9-116">The call timed out.</span></span>|  
|<span data-ttu-id="832d9-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="832d9-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="832d9-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="832d9-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="832d9-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="832d9-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="832d9-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="832d9-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="832d9-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="832d9-121">E_FAIL</span></span>|<span data-ttu-id="832d9-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="832d9-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="832d9-123">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="832d9-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="832d9-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="832d9-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="832d9-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="832d9-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="832d9-126">没有足够的物理内存已可用于完成分配请求。</span><span class="sxs-lookup"><span data-stu-id="832d9-126">Not enough physical memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="832d9-127">备注</span><span class="sxs-lookup"><span data-stu-id="832d9-127">Remarks</span></span>  
 <span data-ttu-id="832d9-128">`CreateMAlloc` 返回一个对象，使 CLR 发出分配请求通过主机而不是使用标准的 Win32 函数。</span><span class="sxs-lookup"><span data-stu-id="832d9-128">`CreateMAlloc` returns an object that allows the CLR to make allocation requests through the host instead of using the standard Win32 functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="832d9-129">要求</span><span class="sxs-lookup"><span data-stu-id="832d9-129">Requirements</span></span>  
 <span data-ttu-id="832d9-130">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="832d9-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="832d9-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="832d9-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="832d9-132">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="832d9-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="832d9-133">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="832d9-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="832d9-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="832d9-134">See also</span></span>

- [<span data-ttu-id="832d9-135">IHostMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="832d9-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [<span data-ttu-id="832d9-136">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="832d9-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
