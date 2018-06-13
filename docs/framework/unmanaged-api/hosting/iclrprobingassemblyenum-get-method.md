---
title: ICLRProbingAssemblyEnum::Get 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f5ddd352d027365e02366e9aa779053da3bdc2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434799"
---
# <a name="iclrprobingassemblyenumget-method"></a><span data-ttu-id="be6b3-102">ICLRProbingAssemblyEnum::Get 方法</span><span class="sxs-lookup"><span data-stu-id="be6b3-102">ICLRProbingAssemblyEnum::Get Method</span></span>
<span data-ttu-id="be6b3-103">获取指定索引处的程序集标识。</span><span class="sxs-lookup"><span data-stu-id="be6b3-103">Gets the assembly identity at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be6b3-104">语法</span><span class="sxs-lookup"><span data-stu-id="be6b3-104">Syntax</span></span>  
  
```  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="be6b3-105">参数</span><span class="sxs-lookup"><span data-stu-id="be6b3-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="be6b3-106">[in]要返回的程序集标识的从零开始的索引。</span><span class="sxs-lookup"><span data-stu-id="be6b3-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="be6b3-107">[out]包含程序集标识数据的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="be6b3-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="be6b3-108">[在中，out]大小`pwzBuffer`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="be6b3-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="be6b3-109">返回值</span><span class="sxs-lookup"><span data-stu-id="be6b3-109">Return Value</span></span>  
  
|<span data-ttu-id="be6b3-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="be6b3-110">HRESULT</span></span>|<span data-ttu-id="be6b3-111">描述</span><span class="sxs-lookup"><span data-stu-id="be6b3-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="be6b3-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="be6b3-112">S_OK</span></span>|<span data-ttu-id="be6b3-113">`Get` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="be6b3-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="be6b3-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="be6b3-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="be6b3-115">`pwzBuffer` 对于太小。</span><span class="sxs-lookup"><span data-stu-id="be6b3-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="be6b3-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="be6b3-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="be6b3-117">该枚举包含更多的项。</span><span class="sxs-lookup"><span data-stu-id="be6b3-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="be6b3-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="be6b3-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="be6b3-119">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="be6b3-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="be6b3-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="be6b3-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="be6b3-121">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="be6b3-121">The call timed out.</span></span>|  
|<span data-ttu-id="be6b3-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="be6b3-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="be6b3-123">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="be6b3-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="be6b3-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="be6b3-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="be6b3-125">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="be6b3-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="be6b3-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="be6b3-126">E_FAIL</span></span>|<span data-ttu-id="be6b3-127">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="be6b3-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="be6b3-128">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="be6b3-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="be6b3-129">对任何托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="be6b3-129">Subsequent calls to any hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be6b3-130">备注</span><span class="sxs-lookup"><span data-stu-id="be6b3-130">Remarks</span></span>  
 <span data-ttu-id="be6b3-131">在索引 0 处的标识是特定于处理器体系结构的标识。</span><span class="sxs-lookup"><span data-stu-id="be6b3-131">The identity at index 0 is the identity specific to the processor architecture.</span></span> <span data-ttu-id="be6b3-132">索引 1 处的标识是 Microsoft 中间语言 (MSIL) 的非特定于体系结构的程序集。</span><span class="sxs-lookup"><span data-stu-id="be6b3-132">The identity at index 1 is the architecture-neutral assembly for Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="be6b3-133">索引 2 处的标识不包含体系结构信息。</span><span class="sxs-lookup"><span data-stu-id="be6b3-133">The identity at index 2 contains no architecture information.</span></span>  
  
 <span data-ttu-id="be6b3-134">`Get` 通常称为两次。</span><span class="sxs-lookup"><span data-stu-id="be6b3-134">`Get` is typically called twice.</span></span> <span data-ttu-id="be6b3-135">第一个调用提供的 null 值`pwzBuffer`，并将设置`pcchBufferSize`到适合的大小`pwzBuffer`。</span><span class="sxs-lookup"><span data-stu-id="be6b3-135">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="be6b3-136">第二个调用提供大小合适`pwzBuffer`，并包含完成后的规范的程序集标识数据。</span><span class="sxs-lookup"><span data-stu-id="be6b3-136">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be6b3-137">要求</span><span class="sxs-lookup"><span data-stu-id="be6b3-137">Requirements</span></span>  
 <span data-ttu-id="be6b3-138">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="be6b3-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be6b3-139">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="be6b3-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="be6b3-140">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="be6b3-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="be6b3-141">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be6b3-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be6b3-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="be6b3-142">See Also</span></span>  
 [<span data-ttu-id="be6b3-143">ICLRProbingAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="be6b3-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 [<span data-ttu-id="be6b3-144">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="be6b3-144">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
