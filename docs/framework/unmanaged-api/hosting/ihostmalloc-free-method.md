---
title: IHostMAlloc::Free 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 719c963d1627250da5f3705af9801dc287e1bb19
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54507236"
---
# <a name="ihostmallocfree-method"></a><span data-ttu-id="77342-102">IHostMAlloc::Free 方法</span><span class="sxs-lookup"><span data-stu-id="77342-102">IHostMAlloc::Free Method</span></span>
<span data-ttu-id="77342-103">释放由使用分配的内存[Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)函数。</span><span class="sxs-lookup"><span data-stu-id="77342-103">Frees memory that was allocated by using the [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77342-104">语法</span><span class="sxs-lookup"><span data-stu-id="77342-104">Syntax</span></span>  
  
```  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="77342-105">参数</span><span class="sxs-lookup"><span data-stu-id="77342-105">Parameters</span></span>  
 `pMem`  
 <span data-ttu-id="77342-106">[in]指向要释放的内存的指针。</span><span class="sxs-lookup"><span data-stu-id="77342-106">[in] A pointer to the memory to be freed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="77342-107">返回值</span><span class="sxs-lookup"><span data-stu-id="77342-107">Return Value</span></span>  
  
|<span data-ttu-id="77342-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="77342-108">HRESULT</span></span>|<span data-ttu-id="77342-109">描述</span><span class="sxs-lookup"><span data-stu-id="77342-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="77342-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="77342-110">S_OK</span></span>|<span data-ttu-id="77342-111">`Free` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="77342-111">`Free` returned successfully.</span></span>|  
|<span data-ttu-id="77342-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="77342-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="77342-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="77342-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="77342-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="77342-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="77342-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="77342-115">The call timed out.</span></span>|  
|<span data-ttu-id="77342-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="77342-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="77342-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="77342-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="77342-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="77342-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="77342-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="77342-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="77342-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="77342-120">E_FAIL</span></span>|<span data-ttu-id="77342-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="77342-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="77342-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="77342-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="77342-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="77342-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="77342-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="77342-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="77342-125">尝试释放通过主机未分配的内存。</span><span class="sxs-lookup"><span data-stu-id="77342-125">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77342-126">备注</span><span class="sxs-lookup"><span data-stu-id="77342-126">Remarks</span></span>  
 <span data-ttu-id="77342-127">如果`pMem`参数是指通过使用调用未分配的内存区域`Alloc`，主机应返回 HOST_E_INVALIDOPERATION。</span><span class="sxs-lookup"><span data-stu-id="77342-127">If the `pMem` parameter refers to a region of memory that was not allocated by using a call to `Alloc`, the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77342-128">要求</span><span class="sxs-lookup"><span data-stu-id="77342-128">Requirements</span></span>  
 <span data-ttu-id="77342-129">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="77342-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77342-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="77342-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="77342-131">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="77342-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77342-132">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77342-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77342-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="77342-133">See also</span></span>
- [<span data-ttu-id="77342-134">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="77342-134">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="77342-135">IHostMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="77342-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
