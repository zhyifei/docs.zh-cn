---
title: ICLRReferenceAssemblyEnum::Get 方法
ms.date: 03/30/2017
api_name:
- ICLRReferenceAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRReferenceAssemblyEnum::Get
helpviewer_keywords:
- ICLRReferenceAssemblyEnum::Get method [.NET Framework hosting]
- Get method, ICLRReferenceAssemblyEnum interface [.NET Framework hosting]
ms.assetid: f21c1612-9c5d-4abc-a337-577086d29c17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31d26ed6249bad8a7e2fbaab01264c1b32e1ff55
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59194469"
---
# <a name="iclrreferenceassemblyenumget-method"></a><span data-ttu-id="4b26b-102">ICLRReferenceAssemblyEnum::Get 方法</span><span class="sxs-lookup"><span data-stu-id="4b26b-102">ICLRReferenceAssemblyEnum::Get Method</span></span>
<span data-ttu-id="4b26b-103">提供的索引处获取程序集标识。</span><span class="sxs-lookup"><span data-stu-id="4b26b-103">Gets the assembly identity at the supplied index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b26b-104">语法</span><span class="sxs-lookup"><span data-stu-id="4b26b-104">Syntax</span></span>  
  
```  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b26b-105">参数</span><span class="sxs-lookup"><span data-stu-id="4b26b-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="4b26b-106">[in]要返回的程序集标识的从零开始的索引。</span><span class="sxs-lookup"><span data-stu-id="4b26b-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="4b26b-107">[out]包含程序集标识数据的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="4b26b-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="4b26b-108">[in、 out]大小`pwzBuffer`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="4b26b-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b26b-109">返回值</span><span class="sxs-lookup"><span data-stu-id="4b26b-109">Return Value</span></span>  
  
|<span data-ttu-id="4b26b-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4b26b-110">HRESULT</span></span>|<span data-ttu-id="4b26b-111">描述</span><span class="sxs-lookup"><span data-stu-id="4b26b-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4b26b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4b26b-112">S_OK</span></span>|<span data-ttu-id="4b26b-113">`Get` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="4b26b-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="4b26b-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="4b26b-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="4b26b-115">`pwzBuffer` 是太小。</span><span class="sxs-lookup"><span data-stu-id="4b26b-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="4b26b-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="4b26b-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="4b26b-117">枚举包含没有其他项。</span><span class="sxs-lookup"><span data-stu-id="4b26b-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="4b26b-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4b26b-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4b26b-119">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="4b26b-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4b26b-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4b26b-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4b26b-121">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="4b26b-121">The call timed out.</span></span>|  
|<span data-ttu-id="4b26b-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4b26b-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4b26b-123">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="4b26b-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4b26b-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4b26b-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4b26b-125">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="4b26b-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4b26b-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4b26b-126">E_FAIL</span></span>|<span data-ttu-id="4b26b-127">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="4b26b-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4b26b-128">如果方法返回 E_FAIL，CLR 不再在该过程中可用。</span><span class="sxs-lookup"><span data-stu-id="4b26b-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4b26b-129">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="4b26b-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b26b-130">备注</span><span class="sxs-lookup"><span data-stu-id="4b26b-130">Remarks</span></span>  
 <span data-ttu-id="4b26b-131">`Get` 通常称为两次。</span><span class="sxs-lookup"><span data-stu-id="4b26b-131">`Get` is typically called twice.</span></span> <span data-ttu-id="4b26b-132">第一个调用提供的 null 值`pwzBuffer`，并设置`pcchBufferSize`适用于大小`pwzBuffer`。</span><span class="sxs-lookup"><span data-stu-id="4b26b-132">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="4b26b-133">第二次调用提供大小合适`pwzBuffer`，并包含完成后的规范的程序集标识数据。</span><span class="sxs-lookup"><span data-stu-id="4b26b-133">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b26b-134">要求</span><span class="sxs-lookup"><span data-stu-id="4b26b-134">Requirements</span></span>  
 <span data-ttu-id="4b26b-135">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4b26b-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b26b-136">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4b26b-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4b26b-137">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4b26b-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4b26b-138">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b26b-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b26b-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b26b-139">See also</span></span>

- [<span data-ttu-id="4b26b-140">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="4b26b-140">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="4b26b-141">ICLRReferenceAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="4b26b-141">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
