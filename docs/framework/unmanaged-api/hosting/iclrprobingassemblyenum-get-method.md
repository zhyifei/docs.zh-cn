---
title: "ICLRProbingAssemblyEnum::Get 方法"
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
- ICLRProbingAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum::Get
helpviewer_keywords:
- Get method, ICLRProbingAssemblyEnum interface [.NET Framework hosting]
- ICLRProbingAssemblyEnum::Get method [.NET Framework hosting]
ms.assetid: fdb67a77-782f-44cf-a8a1-b75999b0f3c8
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dd54558eeb49ebf7a2a2e9304830b09a08d1038e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrprobingassemblyenumget-method"></a><span data-ttu-id="2f51f-102">ICLRProbingAssemblyEnum::Get 方法</span><span class="sxs-lookup"><span data-stu-id="2f51f-102">ICLRProbingAssemblyEnum::Get Method</span></span>
<span data-ttu-id="2f51f-103">获取指定索引处的程序集标识。</span><span class="sxs-lookup"><span data-stu-id="2f51f-103">Gets the assembly identity at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f51f-104">语法</span><span class="sxs-lookup"><span data-stu-id="2f51f-104">Syntax</span></span>  
  
```  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f51f-105">参数</span><span class="sxs-lookup"><span data-stu-id="2f51f-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="2f51f-106">[in]要返回的程序集标识的从零开始的索引。</span><span class="sxs-lookup"><span data-stu-id="2f51f-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="2f51f-107">[out]包含程序集标识数据的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="2f51f-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="2f51f-108">[在中，out]大小`pwzBuffer`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="2f51f-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f51f-109">返回值</span><span class="sxs-lookup"><span data-stu-id="2f51f-109">Return Value</span></span>  
  
|<span data-ttu-id="2f51f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2f51f-110">HRESULT</span></span>|<span data-ttu-id="2f51f-111">描述</span><span class="sxs-lookup"><span data-stu-id="2f51f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2f51f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2f51f-112">S_OK</span></span>|<span data-ttu-id="2f51f-113">`Get`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="2f51f-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="2f51f-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="2f51f-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="2f51f-115">`pwzBuffer`对于太小。</span><span class="sxs-lookup"><span data-stu-id="2f51f-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="2f51f-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="2f51f-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="2f51f-117">该枚举包含更多的项。</span><span class="sxs-lookup"><span data-stu-id="2f51f-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="2f51f-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2f51f-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2f51f-119">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="2f51f-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2f51f-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2f51f-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2f51f-121">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="2f51f-121">The call timed out.</span></span>|  
|<span data-ttu-id="2f51f-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2f51f-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2f51f-123">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="2f51f-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2f51f-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2f51f-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2f51f-125">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="2f51f-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2f51f-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2f51f-126">E_FAIL</span></span>|<span data-ttu-id="2f51f-127">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="2f51f-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2f51f-128">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="2f51f-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2f51f-129">对任何托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="2f51f-129">Subsequent calls to any hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f51f-130">备注</span><span class="sxs-lookup"><span data-stu-id="2f51f-130">Remarks</span></span>  
 <span data-ttu-id="2f51f-131">在索引 0 处的标识是特定于处理器体系结构的标识。</span><span class="sxs-lookup"><span data-stu-id="2f51f-131">The identity at index 0 is the identity specific to the processor architecture.</span></span> <span data-ttu-id="2f51f-132">索引 1 处的标识是 Microsoft 中间语言 (MSIL) 的非特定于体系结构的程序集。</span><span class="sxs-lookup"><span data-stu-id="2f51f-132">The identity at index 1 is the architecture-neutral assembly for Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="2f51f-133">索引 2 处的标识不包含体系结构信息。</span><span class="sxs-lookup"><span data-stu-id="2f51f-133">The identity at index 2 contains no architecture information.</span></span>  
  
 <span data-ttu-id="2f51f-134">`Get`通常称为两次。</span><span class="sxs-lookup"><span data-stu-id="2f51f-134">`Get` is typically called twice.</span></span> <span data-ttu-id="2f51f-135">第一个调用提供的 null 值`pwzBuffer`，并将设置`pcchBufferSize`到适合的大小`pwzBuffer`。</span><span class="sxs-lookup"><span data-stu-id="2f51f-135">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="2f51f-136">第二个调用提供大小合适`pwzBuffer`，并包含完成后的规范的程序集标识数据。</span><span class="sxs-lookup"><span data-stu-id="2f51f-136">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f51f-137">惠?</span><span class="sxs-lookup"><span data-stu-id="2f51f-137">Requirements</span></span>  
 <span data-ttu-id="2f51f-138">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2f51f-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f51f-139">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2f51f-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2f51f-140">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2f51f-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2f51f-141">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f51f-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f51f-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="2f51f-142">See Also</span></span>  
 [<span data-ttu-id="2f51f-143">ICLRProbingAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="2f51f-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 [<span data-ttu-id="2f51f-144">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="2f51f-144">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
