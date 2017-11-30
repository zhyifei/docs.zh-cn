---
title: "ICLRReferenceAssemblyEnum::Get 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRReferenceAssemblyEnum.Get
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRReferenceAssemblyEnum::Get
helpviewer_keywords:
- ICLRReferenceAssemblyEnum::Get method [.NET Framework hosting]
- Get method, ICLRReferenceAssemblyEnum interface [.NET Framework hosting]
ms.assetid: f21c1612-9c5d-4abc-a337-577086d29c17
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ab64f7983b5825505421e7bfbcf6866004778a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrreferenceassemblyenumget-method"></a><span data-ttu-id="4ccb2-102">ICLRReferenceAssemblyEnum::Get 方法</span><span class="sxs-lookup"><span data-stu-id="4ccb2-102">ICLRReferenceAssemblyEnum::Get Method</span></span>
<span data-ttu-id="4ccb2-103">获取所提供的索引处的程序集标识。</span><span class="sxs-lookup"><span data-stu-id="4ccb2-103">Gets the assembly identity at the supplied index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ccb2-104">语法</span><span class="sxs-lookup"><span data-stu-id="4ccb2-104">Syntax</span></span>  
  
```  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4ccb2-105">参数</span><span class="sxs-lookup"><span data-stu-id="4ccb2-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="4ccb2-106">[in]要返回的程序集标识的从零开始的索引。</span><span class="sxs-lookup"><span data-stu-id="4ccb2-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="4ccb2-107">[out]包含程序集标识数据的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="4ccb2-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="4ccb2-108">[在中，out]大小`pwzBuffer`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="4ccb2-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ccb2-109">返回值</span><span class="sxs-lookup"><span data-stu-id="4ccb2-109">Return Value</span></span>  
  
|<span data-ttu-id="4ccb2-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4ccb2-110">HRESULT</span></span>|<span data-ttu-id="4ccb2-111">描述</span><span class="sxs-lookup"><span data-stu-id="4ccb2-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4ccb2-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4ccb2-112">S_OK</span></span>|<span data-ttu-id="4ccb2-113">`Get`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="4ccb2-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="4ccb2-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="4ccb2-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="4ccb2-115">`pwzBuffer`对于太小。</span><span class="sxs-lookup"><span data-stu-id="4ccb2-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="4ccb2-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="4ccb2-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="4ccb2-117">该枚举包含更多的项。</span><span class="sxs-lookup"><span data-stu-id="4ccb2-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="4ccb2-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4ccb2-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4ccb2-119">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="4ccb2-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4ccb2-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4ccb2-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4ccb2-121">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="4ccb2-121">The call timed out.</span></span>|  
|<span data-ttu-id="4ccb2-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4ccb2-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4ccb2-123">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="4ccb2-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4ccb2-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4ccb2-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4ccb2-125">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="4ccb2-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4ccb2-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4ccb2-126">E_FAIL</span></span>|<span data-ttu-id="4ccb2-127">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="4ccb2-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4ccb2-128">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="4ccb2-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4ccb2-129">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="4ccb2-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ccb2-130">备注</span><span class="sxs-lookup"><span data-stu-id="4ccb2-130">Remarks</span></span>  
 <span data-ttu-id="4ccb2-131">`Get`通常称为两次。</span><span class="sxs-lookup"><span data-stu-id="4ccb2-131">`Get` is typically called twice.</span></span> <span data-ttu-id="4ccb2-132">第一个调用提供的 null 值`pwzBuffer`，并将设置`pcchBufferSize`到适合的大小`pwzBuffer`。</span><span class="sxs-lookup"><span data-stu-id="4ccb2-132">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="4ccb2-133">第二个调用提供大小合适`pwzBuffer`，并包含完成后的规范的程序集标识数据。</span><span class="sxs-lookup"><span data-stu-id="4ccb2-133">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ccb2-134">要求</span><span class="sxs-lookup"><span data-stu-id="4ccb2-134">Requirements</span></span>  
 <span data-ttu-id="4ccb2-135">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4ccb2-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ccb2-136">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4ccb2-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4ccb2-137">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4ccb2-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4ccb2-138">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ccb2-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ccb2-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ccb2-139">See Also</span></span>  
 [<span data-ttu-id="4ccb2-140">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="4ccb2-140">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="4ccb2-141">ICLRReferenceAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="4ccb2-141">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
